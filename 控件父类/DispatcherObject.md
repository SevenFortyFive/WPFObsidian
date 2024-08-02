***
# 两个线程

在.NET中，WPF存在两个线程，分别呈现界面（UI线程）和管理界面（后台线程），其中，后台线程隐藏

***绝大多数对象或者控件都必须在UI线程上创建***，并且其他后台子线程不能直接访问UI线程上的控件

为了解决后台线程对UI线程控件或者对象的访问问题，微软在UI线程中提供中间调度员（Dispatcher），将***所有空间按从DispatcherObject类继承***，当后台线程要访问控件时，就可以从空间中找到Dispatcher，由其完成空间的操作访问

***

# Dispatcher

提供两个方法
- Invoke同步
- BeginInvoke异步


> [!NOTE] 微软
> 在 WPF 中， DispatcherObject 只能由 Dispatcher 它与之关联的访问。 例如，后台线程无法更新与 Dispatcher UI 线程上关联的内容Button。 为了使后台线程访问该 Content 属性 Button，后台线程必须将工作委托给 Dispatcher 与 UI 线程关联的工作。 这是通过使用 Invoke 或BeginInvoke。 Invoke 是同步的， BeginInvoke 是异步的。 操作将添加到指定DispatcherPriority位置的队列Dispatcher中。

## 使用Dispatcher

```xml
<Window x:Class="MyWPF.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:MyWPF"
        mc:Ignorable="d"
        Title="HelloWorld" Height="450" Width="800">
    <Grid>
        <Button x:Name="button"/>
    </Grid>
</Window>

```

```cs
using System.Text;
using System.Windows;
using System.Windows.Controls;
using System.Windows.Data;
using System.Windows.Documents;
using System.Windows.Input;
using System.Windows.Media;
using System.Windows.Media.Imaging;
using System.Windows.Navigation;
using System.Windows.Shapes;

namespace MyWPF
{
    /// <summary>
    /// Interaction logic for MainWindow.xaml
    /// </summary>
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();

            Task.Factory.StartNew(() =>
            {
                Task.Delay(3000).Wait();

                button.Dispatcher.Invoke(() =>
                {
                    button.Content = "www.wpfsoft.com";
                });
            });
        }
    }
}
```

 使用Task工厂创建子线程（后台线程），然后调用button的Dispatcher调度员，向Invoke方法中传入匿名函数改变button的Content属性

## DispatcherObject的职责

- 提供对对象所关联的当前Dispatcher的访问权限
- 提供方法检查（CheckAccess）和验证（VerifyAccess）某个线程是否有权访问对象（派生自DispatcherObject）。其中，CheckAccess返回一个布尔值，表示当前线程是否有可以使用的对象，而VerifyAccess则在线程无权访问对象的情况下引发异常


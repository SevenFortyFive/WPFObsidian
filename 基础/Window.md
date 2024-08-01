***

# Window继承路线

MainWindow->Window->ContentControl->Control->FrameworkElement->UIElement->Visual->DependenctObject->DispatcherObject

```cs
namespace MyWPF
{
	/// <summary>
	/// MyWPF.xaml交互逻辑
	/// </summary>
	public partial class MainWindow : Window
	{
		public MainWindow()
		{
			InitalizeComponent();
		}
	}
}
```

***

# Window执行顺序

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

            this.SourceInitialized += (s, e) => Console.WriteLine("1.MainWindow的SourceInitialized被执行");

            this.Activated += (s, e) => Console.WriteLine("2.MainWindow的Activated被执行");

            this.Loaded += (s, e) => Console.WriteLine("3,MainWindow的Loaded被执行");

            this.ContentRendered += (s, e) => Console.WriteLine("4.MainWindow的ContentRendered被执行");

            this.Deactivated += (s, e) => Console.WriteLine("5.MainWindow的Deactivated被执行");

            this.Closing += (s, e) => Console.WriteLine("6.MainWindow的Closing被执行");

            this.Closed += (s, e) => Console.WriteLine("7.MainWindow的Closed被执行");

            this.Unloaded += (s, e) => Console.WriteLine("8.MainWindow的Unloaded被执行 ");

        }
    }
}
```

![[Pasted image 20240801104514.png]]

## 执行事件

- SourceInitalized
  创建窗体源时引发此事件
- Activated
  当前窗体成为前台窗体时引发此事件
- Loaded
  当前窗体内部所有元素完成布局和呈现时引发此事件
- ContentRendered
  当前窗体的内容呈现之后引发此事件
- Closing
  当前窗体关闭之前引发此事件
- Deactivated
  当前窗体成为后台窗体时引发此事件
- Closed
  当前窗体关闭之后引发此事件
- unloaded
  当前窗体从元素树删除时引发此事件

![[Pasted image 20240801110108.png]]

***

# Window窗体组成

- ***本质是一个控件***
- 具有Closing和Closed事件，***一般控件是不可关闭的***

## 非工作区

- 图标
- 标题
- 窗体菜单
- 最小化按钮
- 最大化按钮
- 关闭按钮
- 窗体边框
- 鼠标拖动调整窗体尺寸

## 工作区

***本质上指Window类的Content属性，Content属性表示窗体的内容，类型为Object，可以是任意的引用类型***
***Content属性并不在Window类中，在其父类ContentControl类中***


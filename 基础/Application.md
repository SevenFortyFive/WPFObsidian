***

```cs
using System;
using System.Collections.Generic;
using System.Configuration;
using System.Data;
using System.Linq;
using System.Threading.Tasks;
using System.Windows;
 
namespace HelloWorld
{
    /// <summary>
    /// App.xaml 的交互逻辑
    /// </summary>
    public partial class App : Application
    {
        protected override void OnStartup(StartupEventArgs e)
        {
            base.OnStartup(e);
            Console.WriteLine("1.OnStartup被触发");
        }
 
        protected override void OnActivated(EventArgs e)
        {
            base.OnActivated(e);
            Console.WriteLine("2.OnActivated被触发");
        }
 
        protected override void OnDeactivated(EventArgs e)
        {
            base.OnDeactivated(e);
            Console.WriteLine("3.OnDeactivated被触发");
        }
 
        protected override void OnExit(ExitEventArgs e)
        {
            base.OnExit(e);
            Console.WriteLine("4.OnExit被触发");
        }
    }
}
```

![[Pasted image 20240801100448.png]]

当启动WPF应用时，首先执行`OnStartup`方法，其次`OnActivated`，当应用最小化或者切换其他程序时，`OnDeactivated`会执行，并且返回时再次执行`OnActivated`方法。关闭应用时，`OnDeactivated`会再次执行，然后执行`OnExit`

- OnStartuo
  表示启动应用程序时
- OnActivated
  表示激活应用程序时
- OnDeactivated
  表示由激活状态变为非激活状态时
- OnExit
  表示退出应用程序时


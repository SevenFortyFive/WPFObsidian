***

# 两部分组成

一个xaml类型文件***包含两个部分***：
- 以`.xaml`扩展名为结尾的前端代码
- 以`.xaml.cs`扩展名为结尾的后端代码（隐藏代码）

## 前端代码

```js
//前端代码
<Application x:Class="HelloWorld.App"
             xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
             xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
             xmlns:local="clr-namespace:HelloWorld"
             StartupUri="MainWindow.xaml">
    <Application.Resources>
         
    </Application.Resources>
</Application>
```


## 后端代码

```cs
//后端代码
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
    }
}
```
***

# 后端

- WPF的后端代码采用C#或者V两种语言

- 定义了一个名为App的类型，并且修饰符为partial关键字，表明App是一个局部类型

- **App继承自Application**



> [!NOTE] Partial
> 在C#中，使用partial关键字将一个类、结构体、接口或者方法分为多个部分进行声明，这些部分可以分布在同一个源文件中，也可以分布在不同的文件中。这里***App类型被分别定义在前端xaml文件和后端cs文件中***


***

# 前端

在xaml文件中存在一个`<application>`标签，和`:x:Class="MyWPF.App"`定义了一个名为App的类型，位于命名空间MyWPF之中，***与后端代码namespace MyWPF***保持一致


***

# Application

```cs
namespace System.Windows
{
    //
    // 摘要:
    //     封装 Windows Presentation Foundation (WPF) 应用程序。
    public class Application : DispatcherObject, IHaveResources, IQueryAmbient
    {
        [SecurityCritical]
        public Application();
        //获取或设置 System.Reflection.Assembly 提供包 统一资源标识符 (URI) 中的资源 WPF 应用程序。        
        public static Assembly ResourceAssembly { get; set; }
 
        //获取 System.Windows.Application 当前对象 System.AppDomain。
        public static Application Current { get; }
 
        //获取应用程序中实例化的窗口。
        public WindowCollection Windows { get; }
 
        //获取或设置该应用程序的主窗口。
        public Window MainWindow { get; set; }
 
        //获取或设置导致的情况， System.Windows.Application.Shutdown 来调用方法。
        public ShutdownMode ShutdownMode { get; set; }
 
        //获取或设置应用程序范围的资源，如样式和画笔的集合。
        [Ambient]
        public ResourceDictionary Resources { get; set; }
 
        //获取或设置 UI 一个应用程序启动时自动显示。
        public Uri StartupUri { get; set; }
 
        //获取应用程序作用域属性的集合。
        public IDictionary Properties { get; }
 
        
        public event EventHandler Deactivated;
        public event SessionEndingCancelEventHandler SessionEnding;
        public event DispatcherUnhandledExceptionEventHandler DispatcherUnhandledException;
        public event NavigatingCancelEventHandler Navigating;
        public event NavigatedEventHandler Navigated;
        public event NavigationProgressEventHandler NavigationProgress;
        public event NavigationFailedEventHandler NavigationFailed;
        public event LoadCompletedEventHandler LoadCompleted;
        public event EventHandler Activated;
        public event NavigationStoppedEventHandler NavigationStopped;
        public event FragmentNavigationEventHandler FragmentNavigation;
 
        public static StreamResourceInfo GetContentStream(Uri uriContent);
        public static string GetCookie(Uri uri);
        public static StreamResourceInfo GetRemoteStream(Uri uriRemote);
        public static StreamResourceInfo GetResourceStream(Uri uriResource);
        public static object LoadComponent(Uri resourceLocator);
        public static void LoadComponent(object component, Uri resourceLocator);
        public static void SetCookie(Uri uri, string value);
        public object FindResource(object resourceKey);
        public int Run(Window window);
        public int Run();
        public void Shutdown();
        public void Shutdown(int exitCode);
        public object TryFindResource(object resourceKey);
        protected virtual void OnActivated(EventArgs e);
        protected virtual void OnDeactivated(EventArgs e);
        protected virtual void OnExit(ExitEventArgs e);
        protected virtual void OnFragmentNavigation(FragmentNavigationEventArgs e);
        protected virtual void OnLoadCompleted(NavigationEventArgs e);
        protected virtual void OnNavigated(NavigationEventArgs e);
        protected virtual void OnNavigating(NavigatingCancelEventArgs e);
        protected virtual void OnNavigationFailed(NavigationFailedEventArgs e);
        protected virtual void OnNavigationProgress(NavigationProgressEventArgs e);
        protected virtual void OnNavigationStopped(NavigationEventArgs e);
        protected virtual void OnSessionEnding(SessionEndingCancelEventArgs e);
        protected virtual void OnStartup(StartupEventArgs e);
 
    }
}
```

Applicaiton继承自DispatcherObject父类
***DispatchaerObject是WPF的最终抽象基类***


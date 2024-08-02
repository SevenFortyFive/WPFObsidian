***

- 布局系统定义
  为UIElement定义为虚拟成员的某些方法提供特定的WPF框架实现，FrameworkElement会密封某些WPF核心级布局替代，并改为提供派生类映替代的WPF框架级别的等效项。例如，密封蛋FrameworkElementArrangeCore提供ArrangeOverride，这些更改放映了这样一个事实，即在WPF框架级别，有一个可以呈现任何FrameworkElement派生类的完整布局系统。在WPF核心级别，将构建基于WPF的常规布局解决方案的某些成员已经九尾，但未定义布局系统的实际引擎
- 逻辑树
  常规WPF编程模型通常以元素树的方式表示。支持将元素树表示为逻辑树，以及支持在标记中定义该树的支持是在级别实现的FrameworkElement。FrameworkElement故意不定义内容模型，并将该责任留给派生类
- 对象生存期事件
  了解何时初始化元素（调用构造函数）或首次将元素加载到逻辑树中。FrameworkElement定义多个与对象生存期相关的事件，这些事件为设计元素的代码隐藏操作（例如添加更多子元素）提供有用的挂钩
- 支持数据绑定和动态资源引用
  对数据绑定和资源的属性级支持由DependencyProperty类实现，并体现在属性系统中，但解析存储为Expression（数据绑定和动态资源的编程构造）中存储的成员值的能力由FrameworkElemet实现
- 风格
  FrameworkElement定义Style属性。但是，FrameworkElement尚未定义对模板的支持或支持修饰器。这些功能由控件类（如和ContentContorl）Control引入
- 更多动画支持
  某些动画支持已在WPF核心级别定义，但FrameworkElement通过实现BeginStoryboard和相关成员扩展了此支持

```cs
public class FrameworkElement : UIElement, IFrameworkInputElement, IInputElement, ISupportInitialize, IHaveResources, IQueryAmbient
{
    public static readonly DependencyProperty StyleProperty;
    public static readonly DependencyProperty MaxHeightProperty;
    public static readonly DependencyProperty FlowDirectionProperty;
    public static readonly DependencyProperty MarginProperty;
    public static readonly DependencyProperty HorizontalAlignmentProperty;
    public static readonly DependencyProperty VerticalAlignmentProperty;
    public static readonly DependencyProperty FocusVisualStyleProperty;
    public static readonly DependencyProperty CursorProperty;
    public static readonly DependencyProperty ForceCursorProperty;
    public static readonly RoutedEvent UnloadedEvent;
    public static readonly DependencyProperty ToolTipProperty;
    public static readonly DependencyProperty ContextMenuProperty;
    public static readonly RoutedEvent ToolTipOpeningEvent;
    public static readonly RoutedEvent ToolTipClosingEvent;
    public static readonly RoutedEvent ContextMenuOpeningEvent;
    public static readonly RoutedEvent ContextMenuClosingEvent;
    public static readonly DependencyProperty MinHeightProperty;
    public static readonly DependencyProperty HeightProperty;
    public static readonly RoutedEvent LoadedEvent;
    public static readonly DependencyProperty MinWidthProperty;
    public static readonly DependencyProperty MaxWidthProperty;
    public static readonly DependencyProperty OverridesDefaultStyleProperty;
    public static readonly DependencyProperty UseLayoutRoundingProperty;
    public static readonly DependencyProperty BindingGroupProperty;
    public static readonly DependencyProperty LanguageProperty;
    public static readonly DependencyProperty NameProperty;
    public static readonly DependencyProperty TagProperty;
    public static readonly DependencyProperty DataContextProperty;
    public static readonly RoutedEvent RequestBringIntoViewEvent;
    public static readonly RoutedEvent SizeChangedEvent;
    public static readonly DependencyProperty ActualWidthProperty;
    public static readonly DependencyProperty ActualHeightProperty;
    public static readonly DependencyProperty LayoutTransformProperty;
    public static readonly DependencyProperty InputScopeProperty;
    public static readonly DependencyProperty WidthProperty;
    protected internal static readonly DependencyProperty DefaultStyleKeyProperty;
 
    public FrameworkElement();
 
    public Transform LayoutTransform { get; set; }
    public double Width { get; set; }
    public double MinWidth { get; set; }
    public double MaxHeight { get; set; }
    public double Height { get; set; }
    public double MinHeight { get; set; }
    public double ActualHeight { get; }
    public double MaxWidth { get; set; }
    public double ActualWidth { get; }
    public TriggerCollection Triggers { get; }
    public object Tag { get; set; }
    public string Name { get; set; }
    public XmlLanguage Language { get; set; }
    public BindingGroup BindingGroup { get; set; }
    public object DataContext { get; set; }
    public ResourceDictionary Resources { get; set; }
    public DependencyObject TemplatedParent { get; }
    public bool UseLayoutRounding { get; set; }
    public FlowDirection FlowDirection { get; set; }
    public InputScope InputScope { get; set; }
    public Thickness Margin { get; set; }
    public Style Style { get; set; }
    public VerticalAlignment VerticalAlignment { get; set; }
    public bool OverridesDefaultStyle { get; set; }
    public HorizontalAlignment HorizontalAlignment { get; set; }
    public ContextMenu ContextMenu { get; set; }
    public object ToolTip { get; set; }
    public DependencyObject Parent { get; }
    public bool IsInitialized { get; }
    public bool ForceCursor { get; set; }
    public Cursor Cursor { get; set; }
    public Style FocusVisualStyle { get; set; }
    public bool IsLoaded { get; }
    protected override int VisualChildrenCount { get; }
    protected internal InheritanceBehavior InheritanceBehavior { get; set; }
    protected internal virtual IEnumerator LogicalChildren { get; }
    protected internal object DefaultStyleKey { get; set; }
 
    public event ToolTipEventHandler ToolTipClosing;
    public event ToolTipEventHandler ToolTipOpening;
    public event RoutedEventHandler Unloaded;
    public event DependencyPropertyChangedEventHandler DataContextChanged;
    public event SizeChangedEventHandler SizeChanged;
    public event RequestBringIntoViewEventHandler RequestBringIntoView;
    public event EventHandler<DataTransferEventArgs> SourceUpdated;
    public event EventHandler<DataTransferEventArgs> TargetUpdated;
    public event RoutedEventHandler Loaded;
    public event EventHandler Initialized;
    public event ContextMenuEventHandler ContextMenuClosing;
    public event ContextMenuEventHandler ContextMenuOpening;
 
    public static FlowDirection GetFlowDirection(DependencyObject element);
    public static void SetFlowDirection(DependencyObject element, FlowDirection value);
    public bool ApplyTemplate();
    public virtual void BeginInit();
    public void BeginStoryboard(Storyboard storyboard, HandoffBehavior handoffBehavior, bool isControllable);
    public void BeginStoryboard(Storyboard storyboard);
    public void BeginStoryboard(Storyboard storyboard, HandoffBehavior handoffBehavior);
    public void BringIntoView();
    public void BringIntoView(Rect targetRectangle);
    public virtual void EndInit();
    public object FindName(string name);
    public object FindResource(object resourceKey);
    public BindingExpression GetBindingExpression(DependencyProperty dp);
    public sealed override bool MoveFocus(TraversalRequest request);
    public virtual void OnApplyTemplate();
    public sealed override DependencyObject PredictFocus(FocusNavigationDirection direction);
    public void RegisterName(string name, object scopedElement);
    public BindingExpressionBase SetBinding(DependencyProperty dp, BindingBase binding);
    public BindingExpression SetBinding(DependencyProperty dp, string path);
    public void SetResourceReference(DependencyProperty dp, object name);
    public bool ShouldSerializeResources();
    public bool ShouldSerializeStyle();
    public bool ShouldSerializeTriggers();
    public object TryFindResource(object resourceKey);
    public void UnregisterName(string name);
    public void UpdateDefaultStyle();
    protected sealed override void ArrangeCore(Rect finalRect);
    protected virtual Size ArrangeOverride(Size finalSize);
    protected override Geometry GetLayoutClip(Size layoutSlotSize);
    protected override Visual GetVisualChild(int index);
    protected sealed override Size MeasureCore(Size availableSize);
    protected virtual Size MeasureOverride(Size availableSize);
    protected virtual void OnContextMenuClosing(ContextMenuEventArgs e);
    protected virtual void OnContextMenuOpening(ContextMenuEventArgs e);
    protected override void OnGotFocus(RoutedEventArgs e);
    protected virtual void OnInitialized(EventArgs e);
    protected override void OnPropertyChanged(DependencyPropertyChangedEventArgs e);
    protected virtual void OnToolTipClosing(ToolTipEventArgs e);
    protected virtual void OnToolTipOpening(ToolTipEventArgs e);
    protected internal void AddLogicalChild(object child);
    protected internal DependencyObject GetTemplateChild(string childName);
    protected internal override DependencyObject GetUIParentCore();
    protected internal override void OnRenderSizeChanged(SizeChangedInfo sizeInfo);
    protected internal virtual void OnStyleChanged(Style oldStyle, Style newStyle);
    protected internal override void OnVisualParentChanged(DependencyObject oldParent);
    protected internal virtual void ParentLayoutInvalidated(UIElement child);
    protected internal void RemoveLogicalChild(object child);
 
}
```

***
# 属性分析

- layoutTransform属性
  获取或设置在执行布局时应应用于此元素的图形转换。这个属性与UIElement类中的RenderTransform属性有相似指出。两个属性都是Transform类型，而Transform是一个抽象类，这个类可以实现控件在平面中的各种转化
  1. 旋转 `System.Windows.Media.RotateTransform`
  2. 缩放 `System.Windows.Media.ScaleTransform`
  3. 倾斜 `System.Windows.Media.SkewTransform`
  4. 平移 `System.Windows.Media.TranslateTransform`
  LayoutTransTransform属性是在控件布局之间对控件进行变换，儿RenderTransform属性是在布局结束后执行的变换，LayoutTransform开销比RenderTransform要大，所以尽量使用RenderTransform属性去实现控件的变换
- Width属性
  表示控件的宽度，与以下属性相关
  1. ActualWidth 获取此元素的呈现宽度，只读属性
  2. MaxWidth 获取或设置一个空间的最大宽度
  3. MinWidth 获取或设置一个空间的最小宽度
- Height属性
  表示控件的高度，与以下属性相关
  1. ActualHeight 获取此元素的呈现高度，只读属性
  2. MaxHeight 获取或设置一个控件的最大高度
  3. MinHeight 获取或设置一个空间的最小高度
- Tag属性
  **object类型**，可以保存任意类型的对象值，通常将一些与控件相关的数据临时存放在Tag属性中，当把控件作为参数传递时，Tag属性同时传递
- Name属性
  获取或设置控件的标识名称。在同一窗体、页、用户控件中，Name标识是唯一的，设置了控件的名称后，可以在后端代码直接以这个标识引用控件
- Margin属性
  获取或设置控件的外边距

```xml
<Grid>
	<Button Content="Hello World" Margin="20 40 60 80" />
</Grid>
```


> [!NOTE] Padding
> Padding设置控件的内边距，但是Padding属性在Contro类中，**只有内容控件才有Padding**，Shape和Panel没有Padding属性


- HorizontalAlignment属性
  设置控件的水平对齐方式。这个对齐方式相对于父元素而言，例如Gride中有Button控件，Button控件的HorizonalAlignment属性可以将Button控件显示在Gride控件的左边、中间、右边
- VerticalAlignment属性
  垂直方向
- ToolTip属性
  获取或设置用户界面（UI）中为此元素显示的工具提示对象。指鼠标移到控件上方时显示的提示内容，是一个object类型，意味着可以显示任意布局外观
- Parent属性
  获取此元素的逻辑父元素，是一个只读属性

## WPF样式

- ***Style属性***
  ***WPF样式***，获取或设置此元素呈现时所使用的样式
- FocusVisualStyle属性
  控件在获取焦点时的样式

## WPF资源

ResourceDictionary类，提供一个哈希表/字典实现，其中包含组件所使用的WPF资源以及WPF应用程序的其他元素。可以把WPF的控件、窗体、Application应用所用到的一切资源放在其中，将多个ResourceDictionary元素合并起来形成一个ResourceDictionary元素（ResourceDictionary也是一个隐式集合）。

- Resource属性
  获取或设置本地定义的资源字典

## WPF数据上下文

在数据驱动模式中，控件的值绑定某个“变量”，当变量的值发生改变，控件的值也会改变。这个变量是一个属性，且**必须是一个属性**，存在于**ViewModel**中

将TextBox控件的Text属性和ViewModel实体中的Name属性建立绑定的必备条件为：**Viewmodel实体必须先赋值给View窗体的DataContext，ViewModel的Name才能绑定到TextBox控件的Text属性**

- DataContext属性
  获取或设置元素参与数据绑定时的数据上下文
- ContextMenu属性
  获取或设置控件的上下文菜单，即鼠标在控件右键时弹出的菜单
- Cursor属性
  获取或设置在鼠标指针位于此元素上时显示的光标

***

# 事件分析

FrameworkElement类提供了12个事件，常用的为Initialied、Loaded、Unloaded、SizeChanged等


***
# 方法成员

- `FindName(String)`
  标识查找某个元素
- `FindResource(Object)`
  查找某个资源，如果在调用对象上找不到该i资源，则接下来搜索逻辑树中的父元素，然后搜索应用程序、主题，最后搜索系统资源。实在找不到就抛出异常。
- `TryFindresource(Object)`
  尝试寻找某个资源
- `RegisterName(string, object)`
  注册控件的名称到父控件上

```cs
button2 = new Button();
button2.Name = "Button2";

// 注册button2的名称到myMainPanel控件上
myMainPanel.RegisterName(button2.Name, button2);
button2.COntent = "Button 2";
button2.Click += new RoutedEventHandler(button2Clicked);
myMainPanel.Children.Add(button2);
```

- `SetBinging(DependencyProperty, BindingBase)`和`SetBinding(DependencyProperty, String)`与绑定相关


***

# 子类


[Microsoft.Windows.Themes.BulletChrome](https://learn.microsoft.com/zh-cn/dotnet/api/microsoft.windows.themes.bulletchrome?view=windowsdesktop-7.0)  
[Microsoft.Windows.Themes.ScrollChrome](https://learn.microsoft.com/zh-cn/dotnet/api/microsoft.windows.themes.scrollchrome?view=windowsdesktop-7.0)  
[System.Windows.Controls.AccessText](https://learn.microsoft.com/zh-cn/dotnet/api/system.windows.controls.accesstext?view=windowsdesktop-7.0)  
[System.Windows.Controls.AdornedElementPlaceholder](https://learn.microsoft.com/zh-cn/dotnet/api/system.windows.controls.adornedelementplaceholder?view=windowsdesktop-7.0)  
[System.Windows.Controls.ContentPresenter](https://learn.microsoft.com/zh-cn/dotnet/api/system.windows.controls.contentpresenter?view=windowsdesktop-7.0)  
[System.Windows.Controls.Control](https://learn.microsoft.com/zh-cn/dotnet/api/system.windows.controls.control?view=windowsdesktop-7.0)  
[System.Windows.Controls.Decorator](https://learn.microsoft.com/zh-cn/dotnet/api/system.windows.controls.decorator?view=windowsdesktop-7.0)  
[System.Windows.Controls.Image](https://learn.microsoft.com/zh-cn/dotnet/api/system.windows.controls.image?view=windowsdesktop-7.0)  
[System.Windows.Controls.InkCanvas](https://learn.microsoft.com/zh-cn/dotnet/api/system.windows.controls.inkcanvas?view=windowsdesktop-7.0)  
[System.Windows.Controls.ItemsPresenter](https://learn.microsoft.com/zh-cn/dotnet/api/system.windows.controls.itemspresenter?view=windowsdesktop-7.0)  
[System.Windows.Controls.MediaElement](https://learn.microsoft.com/zh-cn/dotnet/api/system.windows.controls.mediaelement?view=windowsdesktop-7.0)  
[System.Windows.Controls.Page](https://learn.microsoft.com/zh-cn/dotnet/api/system.windows.controls.page?view=windowsdesktop-7.0)  
[System.Windows.Controls.Panel](https://learn.microsoft.com/zh-cn/dotnet/api/system.windows.controls.panel?view=windowsdesktop-7.0)  
[System.Windows.Controls.Primitives.DocumentPageView](https://learn.microsoft.com/zh-cn/dotnet/api/system.windows.controls.primitives.documentpageview?view=windowsdesktop-7.0)  
[System.Windows.Controls.Primitives.GridViewRowPresenterBase](https://learn.microsoft.com/zh-cn/dotnet/api/system.windows.controls.primitives.gridviewrowpresenterbase?view=windowsdesktop-7.0)  
[System.Windows.Controls.Primitives.Popup](https://learn.microsoft.com/zh-cn/dotnet/api/system.windows.controls.primitives.popup?view=windowsdesktop-7.0)  
[System.Windows.Controls.Primitives.TickBar](https://learn.microsoft.com/zh-cn/dotnet/api/system.windows.controls.primitives.tickbar?view=windowsdesktop-7.0)  
[System.Windows.Controls.Primitives.Track](https://learn.microsoft.com/zh-cn/dotnet/api/system.windows.controls.primitives.track?view=windowsdesktop-7.0)  
[System.Windows.Controls.TextBlock](https://learn.microsoft.com/zh-cn/dotnet/api/system.windows.controls.textblock?view=windowsdesktop-7.0)  
[System.Windows.Controls.ToolBarTray](https://learn.microsoft.com/zh-cn/dotnet/api/system.windows.controls.toolbartray?view=windowsdesktop-7.0)  
[System.Windows.Controls.Viewport3D](https://learn.microsoft.com/zh-cn/dotnet/api/system.windows.controls.viewport3d?view=windowsdesktop-7.0)  
[System.Windows.Documents.Adorner](https://learn.microsoft.com/zh-cn/dotnet/api/system.windows.documents.adorner?view=windowsdesktop-7.0)  
[System.Windows.Documents.AdornerLayer](https://learn.microsoft.com/zh-cn/dotnet/api/system.windows.documents.adornerlayer?view=windowsdesktop-7.0)  
[System.Windows.Documents.DocumentReference](https://learn.microsoft.com/zh-cn/dotnet/api/system.windows.documents.documentreference?view=windowsdesktop-7.0)  
[System.Windows.Documents.FixedPage](https://learn.microsoft.com/zh-cn/dotnet/api/system.windows.documents.fixedpage?view=windowsdesktop-7.0)  
[System.Windows.Documents.Glyphs](https://learn.microsoft.com/zh-cn/dotnet/api/system.windows.documents.glyphs?view=windowsdesktop-7.0)  
[System.Windows.Documents.PageContent](https://learn.microsoft.com/zh-cn/dotnet/api/system.windows.documents.pagecontent?view=windowsdesktop-7.0)  
[System.Windows.Interop.HwndHost](https://learn.microsoft.com/zh-cn/dotnet/api/system.windows.interop.hwndhost?view=windowsdesktop-7.0)  
[System.Windows.Shapes.Shape](https://learn.microsoft.com/zh-cn/dotnet/api/system.windows.shapes.shape?view=windowsdesktop-7.0)


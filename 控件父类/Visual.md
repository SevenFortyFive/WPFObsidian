***

WPF框架中的第三个父类，主要是为WPF中的呈现提供支持，包括命中测试、坐标转换、和边界框计算。位于`:PresentationCore.dll`库文件中，命名空间为`System.Windows.Media`

 Visual类是派生每个FrameworkElement对象的基本抽象。

# 作用

用作在WPF中编写新控件的入口点，在Win32应用程序模型中，该类在许多方面可视为窗口句柄（HWND）。Visual对象是一个核心WPF对象，它的主要作用是提供呈现支持。用户界面控件（Button等）派生自Visual类，并使用该类来保存呈现的数据

- 输出显示
  呈现视觉对象的持久、序列化的绘图内容
- 转换
  针对视觉对象执行转换
- 裁剪
  为视觉对象提供裁剪区域支持
- 命中测试
  确定坐标或几何形状是否包含在视觉对象的边界内
- 边框计算
  确定视觉对象的边框

```cs
public abstract class Visual : DependencyObject, IResource
{
    protected Visual();
 
    protected DependencyObject VisualParent { get; }
    protected virtual int VisualChildrenCount { get; }
    protected internal DoubleCollection VisualYSnappingGuidelines { get; protected set; }
    protected internal Vector VisualOffset { get; protected set; }
    protected internal Geometry VisualClip { get; protected set; }
    protected internal Rect? VisualScrollableAreaClip { get; protected set; }
    protected internal CacheMode VisualCacheMode { get; protected set; }
    protected internal BitmapEffectInput VisualBitmapEffectInput { get; protected set; }
    protected internal BitmapEffect VisualBitmapEffect { get; protected set; }
    protected internal Effect VisualEffect { get; protected set; }
    protected internal Transform VisualTransform { get; protected set; }
    protected internal BitmapScalingMode VisualBitmapScalingMode { get; protected set; }
    protected internal DoubleCollection VisualXSnappingGuidelines { get; protected set; }
    protected internal double VisualOpacity { get; protected set; }
    protected internal EdgeMode VisualEdgeMode { get; protected set; }
    protected internal ClearTypeHint VisualClearTypeHint { get; set; }
    protected internal TextRenderingMode VisualTextRenderingMode { get; set; }
    protected internal TextHintingMode VisualTextHintingMode { get; set; }
    protected internal Brush VisualOpacityMask { get; protected set; }
 
    public DependencyObject FindCommonVisualAncestor(DependencyObject otherVisual);
    public bool IsAncestorOf(DependencyObject descendant);
    public bool IsDescendantOf(DependencyObject ancestor);
    public Point PointFromScreen(Point point);
    public Point PointToScreen(Point point);
    public GeneralTransform2DTo3D TransformToAncestor(Visual3D ancestor);
    public GeneralTransform TransformToAncestor(Visual ancestor);
    public GeneralTransform TransformToDescendant(Visual descendant);
    public GeneralTransform TransformToVisual(Visual visual);
    protected void AddVisualChild(Visual child);
    protected virtual Visual GetVisualChild(int index);
    protected virtual GeometryHitTestResult HitTestCore(GeometryHitTestParameters hitTestParameters);
    protected virtual HitTestResult HitTestCore(PointHitTestParameters hitTestParameters);
    protected virtual void OnDpiChanged(DpiScale oldDpi, DpiScale newDpi);
    protected void RemoveVisualChild(Visual child);
    protected internal virtual void OnVisualChildrenChanged(DependencyObject visualAdded, DependencyObject visualRemoved);
    protected internal virtual void OnVisualParentChanged(DependencyObject oldParent);
 
}
```

- 继承了DependencyObject类，Visual是一个抽象类，不可以被实例化

## 属性

- VisualParent属性
  表示获取一个可视化父对象
- VisualCildrenCount属性
  获取当前对象的子元素数量
- VisualOffest
  指当前可视对象的偏移量值，被声明为`protected internal`，**只能由同一个程序集的其它类访问，或Visual的子类访问**
- VisualOpacity
  获取或设置Visual的不透明度
- VisualEffect
  获取或设置要应用于Visual的位图效果
- VisualTransform属性
  获取或设置Transofrm的Visual值

***这些属性被设计为`protected internal`，在实际过程中感知不到并且无法实操***

## 方法

- `DependencyObject FindCommonvisualAncestor(DependencyObject otherVisual);`
  返回两个可视对象的公共上级
- `bool IsAncestorOf(DependencyObject descendant);`
  确定可是对象是否为后代可视对象的上级
- `bool IsDescendantOf(DependencyObject ancestor);`
  确定可视对象是狗为上级可视对象的后代
- `Point PointFromScreen(Point point);`
  将屏幕坐标中的Point转换为表示Point的当前坐标系的Visual
- `Point PointToScreen(Point point);`
  将表示Point的当前坐标系的Visual转换为屏幕坐标中的Point
- `GeneralTransform2DTo3D TransformToAncestor9Visual3D ancestor);`
  返回一个转换，该转换可用于将Visual中的坐标转换为可视对象的执行Visual3D上级
- `GeneralTransform TransformToAncestor(Visual ancestor);`
  返回一个转换，该转换可用于将Visual中的坐标转换为可视对象的指定Visual上级
- `GeneralTransform TransformToDscendant(Visual descendant);`
  返回一个转换，该转换可用于将Visual中的坐标转换为指定的可视对象后代
- `GeneralTransform TransformToVisual(Visual visual);`
  返回一个转换，该转换可用于将Visual中的坐标住那换为指定的可视对象
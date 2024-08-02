***

位于程序集 `:PresentationCore.dll`中，命名控件`:System.Windows`

```cs
public class UIElement : Visual, IAnimatable, IInputElement
{
public static readonly RoutedEvent PreviewMouseDownEvent;
public static readonly DependencyProperty AreAnyTouchesOverProperty;
public static readonly DependencyProperty AreAnyTouchesDirectlyOverProperty;
public static readonly DependencyProperty IsKeyboardFocusedProperty;
public static readonly DependencyProperty IsStylusCaptureWithinProperty;
public static readonly DependencyProperty IsStylusCapturedProperty;
public static readonly DependencyProperty IsMouseCaptureWithinProperty;
public static readonly DependencyProperty IsMouseCapturedProperty;
public static readonly DependencyProperty IsKeyboardFocusWithinProperty;
public static readonly DependencyProperty IsStylusOverProperty;
public static readonly DependencyProperty IsMouseOverProperty;
public static readonly DependencyProperty IsMouseDirectlyOverProperty;
public static readonly RoutedEvent TouchLeaveEvent;
public static readonly RoutedEvent TouchEnterEvent;
public static readonly RoutedEvent LostTouchCaptureEvent;
public static readonly RoutedEvent GotTouchCaptureEvent;
public static readonly RoutedEvent TouchUpEvent;
public static readonly RoutedEvent PreviewTouchUpEvent;
public static readonly RoutedEvent TouchMoveEvent;
public static readonly RoutedEvent PreviewTouchMoveEvent;
public static readonly RoutedEvent TouchDownEvent;
public static readonly RoutedEvent PreviewTouchDownEvent;
public static readonly RoutedEvent DropEvent;
public static readonly RoutedEvent PreviewDropEvent;
public static readonly RoutedEvent DragLeaveEvent;
public static readonly RoutedEvent PreviewDragLeaveEvent;
public static readonly DependencyProperty AreAnyTouchesCapturedProperty;
public static readonly DependencyProperty AreAnyTouchesCapturedWithinProperty;
public static readonly DependencyProperty AllowDropProperty;
public static readonly DependencyProperty RenderTransformProperty;
public static readonly RoutedEvent ManipulationCompletedEvent;
public static readonly RoutedEvent ManipulationBoundaryFeedbackEvent;
public static readonly RoutedEvent ManipulationInertiaStartingEvent;
public static readonly RoutedEvent ManipulationDeltaEvent;
public static readonly RoutedEvent ManipulationStartedEvent;
public static readonly RoutedEvent ManipulationStartingEvent;
public static readonly DependencyProperty IsManipulationEnabledProperty;
public static readonly DependencyProperty FocusableProperty;
public static readonly DependencyProperty IsVisibleProperty;
public static readonly DependencyProperty IsHitTestVisibleProperty;
public static readonly DependencyProperty IsEnabledProperty;
public static readonly DependencyProperty IsFocusedProperty;
public static readonly RoutedEvent DragOverEvent;
public static readonly RoutedEvent LostFocusEvent;
public static readonly DependencyProperty SnapsToDevicePixelsProperty;
public static readonly DependencyProperty ClipProperty;
public static readonly DependencyProperty ClipToBoundsProperty;
public static readonly DependencyProperty VisibilityProperty;
public static readonly DependencyProperty UidProperty;
public static readonly DependencyProperty CacheModeProperty;
public static readonly DependencyProperty BitmapEffectInputProperty;
public static readonly DependencyProperty EffectProperty;
public static readonly DependencyProperty BitmapEffectProperty;
public static readonly DependencyProperty OpacityMaskProperty;
public static readonly DependencyProperty OpacityProperty;
public static readonly DependencyProperty RenderTransformOriginProperty;
public static readonly RoutedEvent GotFocusEvent;
public static readonly RoutedEvent PreviewDragOverEvent;
public static readonly DependencyProperty IsStylusDirectlyOverProperty;
public static readonly RoutedEvent PreviewDragEnterEvent;
public static readonly RoutedEvent StylusMoveEvent;
public static readonly RoutedEvent PreviewStylusMoveEvent;
public static readonly RoutedEvent StylusUpEvent;
public static readonly RoutedEvent PreviewStylusUpEvent;
public static readonly RoutedEvent StylusDownEvent;
public static readonly RoutedEvent PreviewStylusDownEvent;
public static readonly RoutedEvent QueryCursorEvent;
public static readonly RoutedEvent LostMouseCaptureEvent;
public static readonly RoutedEvent GotMouseCaptureEvent;
public static readonly RoutedEvent MouseLeaveEvent;
public static readonly RoutedEvent MouseEnterEvent;
public static readonly RoutedEvent MouseWheelEvent;
public static readonly RoutedEvent PreviewStylusInAirMoveEvent;
public static readonly RoutedEvent PreviewMouseWheelEvent;
public static readonly RoutedEvent PreviewMouseMoveEvent;
public static readonly RoutedEvent MouseRightButtonUpEvent;
public static readonly RoutedEvent PreviewMouseRightButtonUpEvent;
public static readonly RoutedEvent MouseRightButtonDownEvent;
public static readonly RoutedEvent PreviewMouseRightButtonDownEvent;
public static readonly RoutedEvent DragEnterEvent;
public static readonly RoutedEvent PreviewMouseLeftButtonUpEvent;
public static readonly RoutedEvent MouseLeftButtonDownEvent;
public static readonly RoutedEvent PreviewMouseLeftButtonDownEvent;
public static readonly RoutedEvent MouseUpEvent;
public static readonly RoutedEvent PreviewMouseUpEvent;
public static readonly RoutedEvent MouseDownEvent;
public static readonly RoutedEvent MouseMoveEvent;
public static readonly RoutedEvent StylusInAirMoveEvent;
public static readonly RoutedEvent MouseLeftButtonUpEvent;
public static readonly RoutedEvent StylusLeaveEvent;
public static readonly RoutedEvent StylusEnterEvent;
public static readonly RoutedEvent GiveFeedbackEvent;
public static readonly RoutedEvent PreviewGiveFeedbackEvent;
public static readonly RoutedEvent QueryContinueDragEvent;
public static readonly RoutedEvent TextInputEvent;
public static readonly RoutedEvent PreviewTextInputEvent;
public static readonly RoutedEvent LostKeyboardFocusEvent;
public static readonly RoutedEvent PreviewLostKeyboardFocusEvent;
public static readonly RoutedEvent GotKeyboardFocusEvent;
public static readonly RoutedEvent PreviewGotKeyboardFocusEvent;
public static readonly RoutedEvent KeyUpEvent;
public static readonly RoutedEvent PreviewKeyUpEvent;
public static readonly RoutedEvent KeyDownEvent;
public static readonly RoutedEvent PreviewQueryContinueDragEvent;
public static readonly RoutedEvent PreviewStylusButtonUpEvent;
public static readonly RoutedEvent PreviewKeyDownEvent;
public static readonly RoutedEvent StylusInRangeEvent;
public static readonly RoutedEvent PreviewStylusInRangeEvent;
public static readonly RoutedEvent StylusOutOfRangeEvent;
public static readonly RoutedEvent PreviewStylusSystemGestureEvent;
public static readonly RoutedEvent PreviewStylusOutOfRangeEvent;
public static readonly RoutedEvent GotStylusCaptureEvent;
public static readonly RoutedEvent LostStylusCaptureEvent;
public static readonly RoutedEvent StylusButtonDownEvent;
public static readonly RoutedEvent StylusButtonUpEvent;
public static readonly RoutedEvent PreviewStylusButtonDownEvent;
public static readonly RoutedEvent StylusSystemGestureEvent;
 
public UIElement();
 
public string Uid { get; set; }
public Visibility Visibility { get; set; }
public bool ClipToBounds { get; set; }
public Geometry Clip { get; set; }
public bool SnapsToDevicePixels { get; set; }
public bool IsFocused { get; }
public bool IsEnabled { get; set; }
public bool IsHitTestVisible { get; set; }
public bool IsVisible { get; }
public bool AreAnyTouchesCapturedWithin { get; }
public int PersistId { get; }
public bool IsManipulationEnabled { get; set; }
public bool AreAnyTouchesOver { get; }
public bool AreAnyTouchesDirectlyOver { get; }
public bool AreAnyTouchesCaptured { get; }
public IEnumerable<TouchDevice> TouchesCaptured { get; }
public IEnumerable<TouchDevice> TouchesCapturedWithin { get; }
public IEnumerable<TouchDevice> TouchesOver { get; }
public CacheMode CacheMode { get; set; }
public bool Focusable { get; set; }
public BitmapEffectInput BitmapEffectInput { get; set; }
public bool IsMouseDirectlyOver { get; }
public BitmapEffect BitmapEffect { get; set; }
public Size RenderSize { get; set; }
public bool IsArrangeValid { get; }
public bool IsMeasureValid { get; }
public Size DesiredSize { get; }
public bool AllowDrop { get; set; }
public CommandBindingCollection CommandBindings { get; }
public InputBindingCollection InputBindings { get; }
public bool HasAnimatedProperties { get; }
public bool IsMouseOver { get; }
public Effect Effect { get; set; }
public bool IsStylusOver { get; }
public bool IsMouseCaptured { get; }
public bool IsMouseCaptureWithin { get; }
public bool IsStylusDirectlyOver { get; }
public bool IsStylusCaptured { get; }
public bool IsStylusCaptureWithin { get; }
public bool IsKeyboardFocused { get; }
public bool IsInputMethodEnabled { get; }
public double Opacity { get; set; }
public Brush OpacityMask { get; set; }
public bool IsKeyboardFocusWithin { get; }
public IEnumerable<TouchDevice> TouchesDirectlyOver { get; }
public Point RenderTransformOrigin { get; set; }
public Transform RenderTransform { get; set; }
protected StylusPlugInCollection StylusPlugIns { get; }
protected virtual bool IsEnabledCore { get; }
protected internal virtual bool HasEffectiveKeyboardFocus { get; }
 
public event KeyEventHandler KeyUp;
public event EventHandler<TouchEventArgs> TouchMove;
public event EventHandler<TouchEventArgs> PreviewTouchMove;
public event EventHandler<TouchEventArgs> TouchDown;
public event EventHandler<TouchEventArgs> PreviewTouchDown;
public event DragEventHandler Drop;
public event DragEventHandler PreviewDrop;
public event DragEventHandler DragLeave;
public event DragEventHandler PreviewDragLeave;
public event DragEventHandler DragOver;
public event DragEventHandler PreviewDragOver;
public event DragEventHandler DragEnter;
public event DragEventHandler PreviewDragEnter;
public event GiveFeedbackEventHandler GiveFeedback;
public event GiveFeedbackEventHandler PreviewGiveFeedback;
public event QueryContinueDragEventHandler QueryContinueDrag;
public event QueryContinueDragEventHandler PreviewQueryContinueDrag;
public event TextCompositionEventHandler TextInput;
public event EventHandler<TouchEventArgs> PreviewTouchUp;
public event EventHandler<TouchEventArgs> TouchUp;
public event EventHandler<TouchEventArgs> LostTouchCapture;
public event TextCompositionEventHandler PreviewTextInput;
public event EventHandler<ManipulationInertiaStartingEventArgs> ManipulationInertiaStarting;
public event EventHandler<ManipulationDeltaEventArgs> ManipulationDelta;
public event EventHandler<ManipulationStartedEventArgs> ManipulationStarted;
public event EventHandler<ManipulationStartingEventArgs> ManipulationStarting;
public event DependencyPropertyChangedEventHandler FocusableChanged;
public event DependencyPropertyChangedEventHandler IsVisibleChanged;
public event DependencyPropertyChangedEventHandler IsHitTestVisibleChanged;
public event DependencyPropertyChangedEventHandler IsEnabledChanged;
public event RoutedEventHandler LostFocus;
public event EventHandler<TouchEventArgs> GotTouchCapture;
public event RoutedEventHandler GotFocus;
public event DependencyPropertyChangedEventHandler IsKeyboardFocusedChanged;
public event DependencyPropertyChangedEventHandler IsStylusCaptureWithinChanged;
public event DependencyPropertyChangedEventHandler IsStylusDirectlyOverChanged;
public event DependencyPropertyChangedEventHandler IsMouseCaptureWithinChanged;
public event DependencyPropertyChangedEventHandler IsMouseCapturedChanged;
public event DependencyPropertyChangedEventHandler IsKeyboardFocusWithinChanged;
public event DependencyPropertyChangedEventHandler IsMouseDirectlyOverChanged;
public event EventHandler<TouchEventArgs> TouchLeave;
public event EventHandler<TouchEventArgs> TouchEnter;
public event EventHandler LayoutUpdated;
public event KeyboardFocusChangedEventHandler LostKeyboardFocus;
public event KeyboardFocusChangedEventHandler PreviewLostKeyboardFocus;
public event KeyboardFocusChangedEventHandler GotKeyboardFocus;
public event StylusEventHandler PreviewStylusMove;
public event StylusEventHandler StylusMove;
public event StylusEventHandler PreviewStylusInAirMove;
public event StylusEventHandler StylusInAirMove;
public event StylusEventHandler StylusEnter;
public event StylusEventHandler StylusLeave;
public event StylusEventHandler PreviewStylusInRange;
public event StylusEventHandler StylusInRange;
public event StylusEventHandler PreviewStylusOutOfRange;
public event StylusEventHandler StylusOutOfRange;
public event StylusSystemGestureEventHandler PreviewStylusSystemGesture;
public event StylusSystemGestureEventHandler StylusSystemGesture;
public event StylusEventHandler GotStylusCapture;
public event StylusEventHandler LostStylusCapture;
public event StylusButtonEventHandler StylusButtonDown;
public event StylusButtonEventHandler StylusButtonUp;
public event StylusButtonEventHandler PreviewStylusButtonDown;
public event StylusButtonEventHandler PreviewStylusButtonUp;
public event KeyEventHandler PreviewKeyDown;
public event KeyEventHandler KeyDown;
public event KeyEventHandler PreviewKeyUp;
public event StylusEventHandler StylusUp;
public event KeyboardFocusChangedEventHandler PreviewGotKeyboardFocus;
public event StylusEventHandler PreviewStylusUp;
public event StylusDownEventHandler PreviewStylusDown;
public event MouseButtonEventHandler PreviewMouseDown;
public event MouseButtonEventHandler MouseDown;
public event MouseButtonEventHandler PreviewMouseUp;
public event MouseButtonEventHandler MouseUp;
public event MouseButtonEventHandler PreviewMouseLeftButtonDown;
public event MouseButtonEventHandler MouseLeftButtonDown;
public event MouseButtonEventHandler PreviewMouseLeftButtonUp;
public event MouseButtonEventHandler MouseLeftButtonUp;
public event MouseButtonEventHandler PreviewMouseRightButtonDown;
public event MouseButtonEventHandler MouseRightButtonDown;
public event MouseButtonEventHandler PreviewMouseRightButtonUp;
public event MouseButtonEventHandler MouseRightButtonUp;
public event MouseEventHandler PreviewMouseMove;
public event MouseEventHandler MouseMove;
public event MouseWheelEventHandler PreviewMouseWheel;
public event MouseWheelEventHandler MouseWheel;
public event MouseEventHandler MouseEnter;
public event MouseEventHandler MouseLeave;
public event MouseEventHandler GotMouseCapture;
public event MouseEventHandler LostMouseCapture;
public event QueryCursorEventHandler QueryCursor;
public event StylusDownEventHandler StylusDown;
public event DependencyPropertyChangedEventHandler IsStylusCapturedChanged;
public event EventHandler<ManipulationCompletedEventArgs> ManipulationCompleted;
public event EventHandler<ManipulationBoundaryFeedbackEventArgs> ManipulationBoundaryFeedback;
 
public void AddHandler(RoutedEvent routedEvent, Delegate handler);
public void AddHandler(RoutedEvent routedEvent, Delegate handler, bool handledEventsToo);
public void AddToEventRoute(EventRoute route, RoutedEventArgs e);
public void ApplyAnimationClock(DependencyProperty dp, AnimationClock clock, HandoffBehavior handoffBehavior);
public void ApplyAnimationClock(DependencyProperty dp, AnimationClock clock);
public void Arrange(Rect finalRect);
public void BeginAnimation(DependencyProperty dp, AnimationTimeline animation, HandoffBehavior handoffBehavior);
public void BeginAnimation(DependencyProperty dp, AnimationTimeline animation);
public bool CaptureMouse();
public bool CaptureStylus();
public bool CaptureTouch(TouchDevice touchDevice);
public bool Focus();
public object GetAnimationBaseValue(DependencyProperty dp);
public IInputElement InputHitTest(Point point);
public void InvalidateArrange();
public void InvalidateMeasure();
public void InvalidateVisual();
public void Measure(Size availableSize);
public virtual bool MoveFocus(TraversalRequest request);
public virtual DependencyObject PredictFocus(FocusNavigationDirection direction);
public void RaiseEvent(RoutedEventArgs e);
public void ReleaseAllTouchCaptures();
public void ReleaseMouseCapture();
public void ReleaseStylusCapture();
public bool ReleaseTouchCapture(TouchDevice touchDevice);
public void RemoveHandler(RoutedEvent routedEvent, Delegate handler);
public bool ShouldSerializeCommandBindings();
public bool ShouldSerializeInputBindings();
public Point TranslatePoint(Point point, UIElement relativeTo);
public void UpdateLayout();
protected virtual void ArrangeCore(Rect finalRect);
protected virtual Geometry GetLayoutClip(Size layoutSlotSize);
protected override HitTestResult HitTestCore(PointHitTestParameters hitTestParameters);
protected override GeometryHitTestResult HitTestCore(GeometryHitTestParameters hitTestParameters);
protected virtual Size MeasureCore(Size availableSize);
protected virtual void OnAccessKey(AccessKeyEventArgs e);
protected virtual void OnChildDesiredSizeChanged(UIElement child);
protected virtual AutomationPeer OnCreateAutomationPeer();
protected virtual void OnDragEnter(DragEventArgs e);
protected virtual void OnDragLeave(DragEventArgs e);
protected virtual void OnDragOver(DragEventArgs e);
protected virtual void OnDrop(DragEventArgs e);
protected virtual void OnGiveFeedback(GiveFeedbackEventArgs e);
protected virtual void OnGotFocus(RoutedEventArgs e);
protected virtual void OnGotKeyboardFocus(KeyboardFocusChangedEventArgs e);
protected virtual void OnGotMouseCapture(MouseEventArgs e);
protected virtual void OnGotStylusCapture(StylusEventArgs e);
protected virtual void OnGotTouchCapture(TouchEventArgs e);
protected virtual void OnIsKeyboardFocusedChanged(DependencyPropertyChangedEventArgs e);
protected virtual void OnIsKeyboardFocusWithinChanged(DependencyPropertyChangedEventArgs e);
protected virtual void OnIsMouseCapturedChanged(DependencyPropertyChangedEventArgs e);
protected virtual void OnIsMouseCaptureWithinChanged(DependencyPropertyChangedEventArgs e);
protected virtual void OnIsMouseDirectlyOverChanged(DependencyPropertyChangedEventArgs e);
protected virtual void OnIsStylusCapturedChanged(DependencyPropertyChangedEventArgs e);
protected virtual void OnIsStylusCaptureWithinChanged(DependencyPropertyChangedEventArgs e);
protected virtual void OnIsStylusDirectlyOverChanged(DependencyPropertyChangedEventArgs e);
protected virtual void OnKeyDown(KeyEventArgs e);
protected virtual void OnKeyUp(KeyEventArgs e);
protected virtual void OnLostFocus(RoutedEventArgs e);
protected virtual void OnLostKeyboardFocus(KeyboardFocusChangedEventArgs e);
protected virtual void OnLostMouseCapture(MouseEventArgs e);
protected virtual void OnLostStylusCapture(StylusEventArgs e);
protected virtual void OnLostTouchCapture(TouchEventArgs e);
protected virtual void OnManipulationBoundaryFeedback(ManipulationBoundaryFeedbackEventArgs e);
protected virtual void OnManipulationCompleted(ManipulationCompletedEventArgs e);
protected virtual void OnManipulationDelta(ManipulationDeltaEventArgs e);
protected virtual void OnManipulationInertiaStarting(ManipulationInertiaStartingEventArgs e);
protected virtual void OnManipulationStarted(ManipulationStartedEventArgs e);
protected virtual void OnManipulationStarting(ManipulationStartingEventArgs e);
protected virtual void OnMouseDown(MouseButtonEventArgs e);
protected virtual void OnMouseEnter(MouseEventArgs e);
protected virtual void OnMouseLeave(MouseEventArgs e);
protected virtual void OnMouseLeftButtonDown(MouseButtonEventArgs e);
protected virtual void OnMouseLeftButtonUp(MouseButtonEventArgs e);
protected virtual void OnMouseMove(MouseEventArgs e);
protected virtual void OnMouseRightButtonDown(MouseButtonEventArgs e);
protected virtual void OnMouseRightButtonUp(MouseButtonEventArgs e);
protected virtual void OnMouseUp(MouseButtonEventArgs e);
protected virtual void OnMouseWheel(MouseWheelEventArgs e);
protected virtual void OnPreviewDragEnter(DragEventArgs e);
protected virtual void OnPreviewDragLeave(DragEventArgs e);
protected virtual void OnPreviewDragOver(DragEventArgs e);
protected virtual void OnPreviewDrop(DragEventArgs e);
protected virtual void OnPreviewGiveFeedback(GiveFeedbackEventArgs e);
protected virtual void OnPreviewGotKeyboardFocus(KeyboardFocusChangedEventArgs e);
protected virtual void OnPreviewKeyDown(KeyEventArgs e);
protected virtual void OnPreviewKeyUp(KeyEventArgs e);
protected virtual void OnPreviewLostKeyboardFocus(KeyboardFocusChangedEventArgs e);
protected virtual void OnPreviewMouseDown(MouseButtonEventArgs e);
protected virtual void OnPreviewMouseLeftButtonDown(MouseButtonEventArgs e);
protected virtual void OnPreviewMouseLeftButtonUp(MouseButtonEventArgs e);
protected virtual void OnPreviewMouseMove(MouseEventArgs e);
protected virtual void OnPreviewMouseRightButtonDown(MouseButtonEventArgs e);
protected virtual void OnPreviewMouseRightButtonUp(MouseButtonEventArgs e);
protected virtual void OnPreviewMouseUp(MouseButtonEventArgs e);
protected virtual void OnPreviewMouseWheel(MouseWheelEventArgs e);
protected virtual void OnPreviewQueryContinueDrag(QueryContinueDragEventArgs e);
protected virtual void OnPreviewStylusButtonDown(StylusButtonEventArgs e);
protected virtual void OnPreviewStylusButtonUp(StylusButtonEventArgs e);
protected virtual void OnPreviewStylusDown(StylusDownEventArgs e);
protected virtual void OnPreviewStylusInAirMove(StylusEventArgs e);
protected virtual void OnPreviewStylusInRange(StylusEventArgs e);
protected virtual void OnPreviewStylusMove(StylusEventArgs e);
protected virtual void OnPreviewStylusOutOfRange(StylusEventArgs e);
protected virtual void OnPreviewStylusSystemGesture(StylusSystemGestureEventArgs e);
protected virtual void OnPreviewStylusUp(StylusEventArgs e);
protected virtual void OnPreviewTextInput(TextCompositionEventArgs e);
protected virtual void OnPreviewTouchDown(TouchEventArgs e);
protected virtual void OnPreviewTouchMove(TouchEventArgs e);
protected virtual void OnPreviewTouchUp(TouchEventArgs e);
protected virtual void OnQueryContinueDrag(QueryContinueDragEventArgs e);
protected virtual void OnQueryCursor(QueryCursorEventArgs e);
protected virtual void OnRender(DrawingContext drawingContext);
protected virtual void OnStylusButtonDown(StylusButtonEventArgs e);
protected virtual void OnStylusButtonUp(StylusButtonEventArgs e);
protected virtual void OnStylusDown(StylusDownEventArgs e);
protected virtual void OnStylusEnter(StylusEventArgs e);
protected virtual void OnStylusInAirMove(StylusEventArgs e);
protected virtual void OnStylusInRange(StylusEventArgs e);
protected virtual void OnStylusLeave(StylusEventArgs e);
protected virtual void OnStylusMove(StylusEventArgs e);
protected virtual void OnStylusOutOfRange(StylusEventArgs e);
protected virtual void OnStylusSystemGesture(StylusSystemGestureEventArgs e);
protected virtual void OnStylusUp(StylusEventArgs e);
protected virtual void OnTextInput(TextCompositionEventArgs e);
protected virtual void OnTouchDown(TouchEventArgs e);
protected virtual void OnTouchEnter(TouchEventArgs e);
protected virtual void OnTouchLeave(TouchEventArgs e);
protected virtual void OnTouchMove(TouchEventArgs e);
protected virtual void OnTouchUp(TouchEventArgs e);
protected internal virtual DependencyObject GetUIParentCore();
protected internal virtual void OnRenderSizeChanged(SizeChangedInfo info);
protected internal override void OnVisualParentChanged(DependencyObject oldParent);
 
}
```

***
# 路由事件

路由事件与xaml的可视化树概念相关

控件的事件被触发之后，会沿着这棵树广播，要么往树的根部广播，要么往树的枝叶广播，如果不广播就是直接事件

## 冒泡事件

从触发源为出发点，依次传递到父节点，直到最后的根节点

## 隧道事件

无论触发源，都从根节点触发，到子节点，直到触发节点

从空间上，冒泡事件和隧道事件成对出现。从时间来说，先触发隧道事件，然后触发冒泡事件。
隧道事件是以Preview开头的事件

**protected virtual表示可以被重载**

***
# 依赖属性

```cs
public Visibility Visibility {get; set}

public static readonly DependencyProperty VisibilityProperty;
```

Visibility是普通的属性成员，VisibilityProperty是WPF的依赖属性成员，以Property结尾的字样作为wpf的依赖属性命名规则。两者结合被称为一个完整的依赖属性

Visibility属性表示设置或者获取空间的可见性

```xml
<TextBlock Text="HelloWorld"
			Visibility="Visible"
			FontSize="48"
			HorizontalAlignment="Center"
			VerticalAlignment="Center"/>
```

Visibility包含Visible（显示）、Hidden（隐藏）、Collapsed（彻底隐藏，不占用布局位置）

**不可见元素不会参与命中测试，也不会接收输入事件，即使鼠标位于元素可见时所在的边界上也是如此**

### 常用属性

- Uid属性
  获取或设置控件的唯一标识符，默认为`string.Empty`
- Visibility属性
  获取或设置控件的可见性，默认为`Visible`
- ClipToBounds属性
  若为true，表示进行裁剪，以适配它的父控件
- Clip属性
  用于裁剪区域大小的几何图形，ClipToBounds裁剪控件本身，Clip裁剪控件内的内容

```xml
<Image
	source=""
	Width="200" Height="150" HorizontalAlignment="Left">
	<Image.Clip>
		<EllipseGeometry
			RadiusX="100"
			RadiusY="75"
			Center="100, 75"/>
	<Image.Clip>
</Image>
```

- SnapsToDevicePixels属性
  若为true，表示控件的呈现是否使用特定于设备的像素设置。开启后可以大限度防锯齿，默认为false
- IsFocused属性
  只读属性，表示当前控件是否有焦点
- IsEnabled属性
  若为true，表示禁用控件，反之启用
- IsHitTestVisibile属性
  获取或设置一个值，该值声明是否可以返回此元素作为其呈现内容的某些部分的点击测试结果
- IsVisible属性
  只读属性，表示当前控件是否显示
- Focusable属性
  若为true，表示控件可以得到焦点，大部分内容控件默认可以获取焦点
- IsKeyboardFocused属性
  表示该控件是否具有键盘焦点
- IsMouseOver属性
  表示鼠标是否在控件上
- IsStyleOver属性
  表示触笔指针是否在控件上方
- IsSealed属性
  表示当前类型是否为只读类
- Opacity属性
  设置控件的透明度，取值范围为0-1之间的double值
- OpacityMask属性
  设置一个画笔，作为控件的蒙版

```xml
<Image Height="150" Width="200" Source="">
	<Image.OpacityMask>
		<ImageBrush ImageSource="" />
	</Image.opacityMask>
</Image>
```

- AllowDrop属性
  表示控件是否允许拖拽操作
- RenderTransform属性
  设置空间的移动、缩放、旋转


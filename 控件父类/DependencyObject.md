***

# 事件驱动的开发模式

```cs
button1.Text = "OK"
```

```cs
button1.Text = "确定"
```

***

# 数据驱动模式

***控件的属性不再被直接复制，而是绑定另一个变量***，当变量改变时，控件的属性也会改变，这种属性成为***依赖属性***

DependencyObject类表示依赖属性系统的对象。属性系统的主要功能是计算属性的值，并提供有关已更改的值的系统通知。参与属性的另一个类DependencyProperty。**DependencyProperty允许将以来注册到属性系统，并提供有关每个依赖属性的标识和信息**，而DependencyObkect为基类，使对象能够使用此依赖属性。

INotifyPropertyChanged类用于通知UI刷新，注重的仅仅是数据更新后的通知。DependencyObject类用于给UI添加依赖和附加属性，注重数据和UI的关联。如果简单的数据通知，两者都可以实现。

```cs
public class DependencyObject : DispatcherObject
{
    public DependencyObject();
 
    public DependencyObjectType DependencyObjectType { get; }
    public bool IsSealed { get; }
 
    public void ClearValue(DependencyProperty dp);
    public void ClearValue(DependencyPropertyKey key);
    public void CoerceValue(DependencyProperty dp);
    public sealed override bool Equals(object obj);
    public sealed override int GetHashCode();
    public LocalValueEnumerator GetLocalValueEnumerator();
    public object GetValue(DependencyProperty dp);
    public void InvalidateProperty(DependencyProperty dp);
    public object ReadLocalValue(DependencyProperty dp);
    public void SetCurrentValue(DependencyProperty dp, object value);
    public void SetValue(DependencyProperty dp, object value);
    public void SetValue(DependencyPropertyKey key, object value);
    protected virtual void OnPropertyChanged(DependencyPropertyChangedEventArgs e);
    protected internal virtual bool ShouldSerializeProperty(DependencyProperty dp);
 
}
```

## GetValue
表示获取某一个依赖属性的值
返回一个object类型

## SetValue
表示设置某一个依赖属性的值
dp参数表示要设置的依赖，第二参数value表示新值

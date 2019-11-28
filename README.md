# WPFUnloadedTriggerTest
Unloaded/Loaded非预期触发的测试Demo

对WPF-Unloaded/Loaded的已知情况如下：
* FrameworkElement， 第一次加载显示时，会触发Loaded。元素被释放时，会触发Unloaded。窗口Show/Close时，视觉树变化都会触发加载事件
* MenuItem， 在FrameworkElement基础上，每次和隐藏MenuItem时，会额外触发Load/Unloaded
* TabControl，当你选中一个tabItem时会触发Loaded，当你取消选中一个tabItem时会触发Unloaded，所以切换Tab时必定有一个Loaded一个Unloaded。
* Expander，每次被Expanded扩展时会引发Loaded，但当隐藏时不会引发Unloaded。
* 修改屏幕DPI，会触发Unload重新布局
* 屏幕休眠唤醒后，会触发Unload重新布局

Android studio项目导入build.gradle文件不是导入文件夹

view的setSelected()方法设定布尔值设置控件是否被选中，在控件的background中设置@drawable/xxxx（xml文件）  更改控件是否选择时的颜色
style目录下的color文件定义用到的颜色，比在layout下定义好。

private static final String TAG = “xxx”  用于logcat调试输出

https://www.jianshu.com/p/9f22911ea630   串口工具文档

https://www.runoob.com/  菜鸟教程：各语言中文api

https://www.jianshu.com/p/07b87084337f  四大组件 Google公司大牛

dmrfcoder *github用户       F1ReKing  *Android-SerialPort串口调试库开发者

switch中break和return的区别，break是退出一层，return退出函数

多个RadioButton不用RadioGroup实现单选  先监听点击事件，写setRadioButtonCheck(v.getId())类，使用SparseArray数组。实现单选，看微信收藏笔记radiobutton

implementation 'me.jessyan:autosize:1.1.2' 屏幕适配（AndroidAutoSize）

获取ViewGroup------MainActivity activity;                               
返回View:       activity.getWindow().getDecorView()                  
返回ViewGroup： (ViewGroup)activity.getWindow().getDecorView()

2018 I/O大会Google强推androidx彻底弃用了Android.support.V7/V4  不过只有软件包和 Maven 工件名称发生了变化；类、方法和字段名称没有改变。

弹出式菜单 PopupMenu    弹出式窗口 PopupWindow  Toolbar可以自定义导航栏

（1）onCreate:create表示创建，这是Activity生命周期的第一个方法，也是我们在android开发中接触的最多的生命周期方法。它本身的作用是进行Activity的一些初始化工作，比如使用setContentView加载布局，对一些控件和变量进行初始化等。但也有很多人将很多与初始化无关的代码放在这，其实这是不规范的。此时Activity还在后台，不可见。所以动画不应该在这里初始化，因为看不到
（2）onStart:start表示启动，这是Activity生命周期的第二个方法。此时Activity已经可见了，但是还没出现在前台，我们还看不到，无法与Activity交互。其实将Activity的初始化工作放在这也没有什么问题，放在onCreate中是由于官方推荐的以及我们开发的习惯。
（3）onResume:resume表示继续、重新开始，这名字和它的职责也相同。此时Activity经过前两个阶段的初始化已经蓄势待发。Activity在这个阶段已经出现在前台并且可见了。这个阶段可以打开独占设备
（4）onPause:pause表示暂停，当Activity要跳到另一个Activity或应用正常退出时都会执行这个方法。此时Activity在前台并可见，我们可以进行一些轻量级的存储数据和去初始化的工作，不能太耗时，因为在跳转Activity时只有当一个Activity执行完了onPause方法后另一个Activity才会启动，而且android中指定如果onPause在500ms即0.5秒内没有执行完毕的话就会强制关闭Activity。从生命周期图中发现可以在这快速重启，但这种情况其实很罕见，比如用户切到下一个Activity的途中按back键快速得切回来。
（5）onStop：stop表示停止，此时Activity已经不可见了，但是Activity对象还在内存中，没有被销毁。这个阶段的主要工作也是做一些资源的回收工作。
（6）onDestroy：destroy表示毁灭，这个阶段Activity被销毁，不可见，我们可以又将还没释放的资源释放，以及进行一些回收工作。
（7）onRestart：restart表示重新开始，Activity在这时可见，当用户按Home键切换到桌面后切回来或者从后一个Activity切回前一个Activity就会触发这个方法。这里一般不做什么操作。

Java与数据库中的datetime Timestamp以及String之间的转换https://blog.csdn.net/weixin_43959046/article/details/90322346

Android studio满屏报错Duplicate class com.google.zxing.BarcodeFormat found in modules jetified-core-3.4.0.jar      这是应为重复导入jar包导致的，把implementation改为compileOnly就好了（改的是父包，不是重写/继承父包的那个包）

notes有配置as文件目录的方法，减少c盘占用。

Navigation  导航

简书：   https://www.jianshu.com/p/f4b5b1010a41
ldpi：240x320
mdpi：320x480
hdpi：480x800、480x854
xhdpi：至少960*720  720p
xxhdpi：1920×1080  1080p

xutils3绑定控件，控件监听，绑定函数....只能使用private！！！使用其它修饰符不起作用。

startActivity(new Intent(Settings.ACTION_BLUETOOTH_SETTINGS)); //打开蓝牙系统设置界面
startActivity(new Intent(Settings.ACTION_WIFI_SETTINGS)); //打开wifi网络系统设置界面
startActivity(new Intent(Settings.ACTION_DATE_SETTINGS));//打开时间系统设置界面

&& b：a和b同时为true 才返回 true， 否则返回false；            a || b：a或b任意一个为true 就返回true ， 否则返回false     判断多个输入框不为空要用||，只要有一个为空就是true，回进入if语句，用&&会导致有一个不是空，返回false，进不去if。或者把所有的&&框起来进行取反   ！

List<E>数组在用之前需要分配空间， list = new ArrayList<>();

判断字符串是否完全相同用equals，判断字符串是否包含在里面用contains，使用contains时两个字符串不完全相同但是有一部分相同的时候会返回true，谨慎使用。

使用adapter.notifyDataSetChanged()时，必须保证传进 Adapter的数据 List是同一个List
而不能是其他对象，否则无法更新 listview。
        即，你可以调用 List 的 add()， remove()， clear()，addAll() 等方法，这种情况下，List 指向的始终是你最开始 new 出来的 ArrayList ，然后调用 adapter.notifyDataSetChanged() 方法，可以更新 ListView；但是如果你重新 new 了一个 ArrayList（重新申请了堆内存），那么这时候，List 就指向了另外一个 ArrayLIst，这时调用 adapter.notifyDataSetChanged() 方法，就无法刷新 listview 了。

如果list的item里面包括button或者checkbox等控件，默认情况下listitem会失去焦点，导致无法响应item的事件，最常用的解决办法是在listitem的布局文件中设置descendantFocusability属性。自定义item在自定义的布局xml文件中设置然后监听那个layout或者其它的控件，在getview里面设置监听会自动获取点击的item非常好用。

自定义listview的item的时候可以自定义一个内部类public static class ViewHolder {}。初始化item的控件，convertView设置setTag(viewHolder);在开始的时候判断convertView是否为空不为空getTag（）复用上一个item非常方便，具体搜索listViw viewHolder教程很多优化listview加载。

点击adapter的item显示一个dialogfragment，可以使用fragment和adapter通信来完成，具体方法在notes两者通信中。csdn地址  https://blog.csdn.net/Jordas_Lee/article/details/103287252?utm_medium=distribute.pc_relevant_t0.none-task-blog-BlogCommendFromMachineLearnPai2-1.channel_param&depth_1-utm_source=distribute.pc_relevant_t0.none-task-blog-BlogCommendFromMachineLearnPai2-1.channel_param

xutils网络请求
  params.setAsJsonContent(true);//设置请求格式为json
  params.setBodyContent(json);//请求的参数，转换为字符串的json数据
  
使用Dialog的子类DialogFragment时，使用的contentView是Android自带样式和大小的Layout，用户自定义的view被加到mDecor上，所以在show()之前设置xml的大小是无效的，最后还是会在show中被覆盖成系统自带的格式，只有在show后面改变布局属性才会生效,DialogFragment在onCreate()和onCreateView()中设置布局大小无效，因为onCreate()和onCreateView()生命周期在onStart()生命周期之前，此时还未调用Dialog.show()方法   地址https://blog.csdn.net/u013309870/article/details/85162630

xutisl3使用手册  地址：https://www.cnblogs.com/steffen/p/6594958.html
Android xUtils3.0使用手册（二） - 数据库操作  地址： https://blog.csdn.net/weixin_30561425/article/details/97523107?utm_medium=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-1.channel_param&depth_1-utm_source=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-1.channel_param

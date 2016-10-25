# SwiftSmallNote
- UILabelView的自动获取高度(label.sizeThatFits()),这个函数虽然会自动获取label上文本的高度，但是英文和中文的字体高度是不同的，所以需注意
- UIImageView加载图片时，如果是用(named:"xxx")加载，那加载的图片会被放在缓存里，并且这块缓存区的数据，并不会遵循ARC内存管理方式，也就是说即使目前应用没有任何拥有该内存区域的对象了，这块内存区域也不会被释放，只有当应用周期结束（应用退出），该内存区域才会被释放。所以当加载不必要的图片时，建议使用(contentsOfFile:)
- 在tableView内容比较少时，可以不用重用机制http://www.faceye.net/search/82604.html#bottom-ad
- 图标问题，使用图标的时候，所选取的图标最好于app里的图标大小接近，否则可能会存在锯齿
- 虽然我比较喜欢使用tableView来做长内容的显示，但真相是，使用scrollerView可能会更优。
- storybord肯定是一个好工具，只是我还没会充分的使用
- tag是一个标记控件的好办法，这样可以让你更好的找到你想要找的控件
- 使用使用系统闭包反向传值会有延迟
- static 的属性和全局变量默认都是懒加载的
- struct(值传递)，class(引用类型)，往往使用引用类型会对性能有很大的提高(因为应用类型是引用地址)
- table的Cell的一致性可能会比较重要，如果其他的cell都是可以可以点击的，但是有一个cell是不可以点击的，那tablleView就可能回出项卡顿(是不是这个原因还有待排查)
- iOS蓝牙方面的文章，没仔细看，但是从评论上来看，应该写得不错，以后再看http://www.jianshu.com/p/87c30628ddaa
- 当控件加了阴影，并且你在执行的画的时候，可能回照成卡顿，解决的办法，可以在加阴影之前加上这一句来描述控件的边界xxx.layer.shadowPath = UIBezierPath(rect:self.bounds).cgPath http://blog.csdn.net/mkhgg/article/details/7286282
- 地图标注一定会有一个值是固定不变的，称为标注点。当我们自己重定义标注时，应注意偏移量。
- 地图请求路线的操作是一个回调闭包，是异步操作，顺序是由请求的服务器的响应时间决定的，不是由你请求的顺序决定的
- 在使用地图进行路线请求时，如果请求的点不在道路上，那就可能造成路线的点与标注点不重合。
- xcode8兼容8.0以下的系统http://blog.csdn.net/CodingFire/article/details/52638265 (但是有一个问题，就是你不是开发者账号，就是付费账号，你是不能添加新的设备)
- All interface orientations must be supported unless the app requires full screen.这个警告信息的解决方法是General->Deployment Info->勾选Requires full screen(http://stackoverflow.com/questions/31141806/xcode-7-beta-warnings-interface-orientations-and-launch-storyboard)

# ZZCarouselSwift

### Gif 来先解释

![ZZCarouselSwift](ZZCarouselSwift.gif)

### 轮播器优势：

- 可以自定义Cell
- 可以各种自定义，支持图文轮播。以及各种不服轮播！
- 支持Kingfisher加载图片
- 支持cocoapods
- 基于UICollectionView，无限轮播器
- 点击轮播器delegte方法执行

### 方法说明

```objective-c
// 注册UICollectionviewCell，自定义cell
registerCarouselCell(cellClass: AnyClass)
// 设置自动滚动间隔时间
setAutoScrollTimeInterval(timeInterval: Float)
// 数据源，AnyObject类型
setCarouselData(carouselData: [AnyObject])
// UIPageControl 颜色
setDefaultPageColor(color: UIColor)
// UIPageControl 颜色
setCurrentPageColor(color: UIColor)
// UIPageControl 对齐方式 ， 枚举类型：左、中、右
setPageControlAlignment(alignment: ZZCarouselPageAlignment)
// 是佛隐藏PageControl
setHiddenPageControl(hidden: Bool)
```

### 枚举说明

```
ZZCarouselPageAlignment  UIPageControl对齐方式设置
	case left      // 居左
    case right     // 居右
    case center    // 居中
    
ZZCarouselScrollDirection  Carousel滚动方向设置
	case left      // 从左到右
    case right     // 从右到左
    case top       // 从上到下
    case bottom    // 从下到上
```

### 使用方法

```objective-c
/// <#Description#>
///
/// - Parameters:
///   - frame: <#frame description#>
///   - direction: 指定滚动滚动方向
let carousel = ZZCarouselView.init(frame: CGRect(x: 0, y: 64, width: self.view.frame.size.width, height:self.view.frame.size.height / 3), direction: ZZCarouselScrollDirection.left)
// 注册自定义的Cell
carousel.registerCarouselCell(cellClass: Example1Cell.classForCoder())
carousel.setCurrentPageColor(color: UIColor.red)
carousel.setDefaultPageColor(color: UIColor.yellow)
carousel.delegate = self
// 设置自动滚动的间隔时间
carousel.setAutoScrollTimeInterval(timeInterval: 2)
carousel.setPageControlAlignment(alignment: ZZCarouselPageAlignment.right)
carousel.tag = 1001;
self.view.addSubview(carousel)
// 非常有必要，给实例的CarouselView传递数据，数组<任意Object>  
carousel.setCarouselData(carouselData: data as [AnyObject])
```

### 安装方法

- 手动安装：拖拽ZZCarouselSwift文件夹到工程内即可
- 自动安装：pod 'ZZCarouselSwift', '~> 1.0.5'

### PS

如有问题，可以给我各种贡献代码。逐步完善，还是需要各路ioser。


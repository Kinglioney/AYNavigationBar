# AYNavigationBar

## Overview
   ![snapshot](https://github.com/CodeABug/AYNavigationBar/blob/master/push-pop.gif)

## Installation

Use CocoaPods  

``` ruby
pod 'AYNavigationBar', '1.0.8'
```

## Usage

### To enable AYNavigationBar of a navigation controller

``` objc
UINavigationController *nav = [[UINavigationController alloc] initWithRootViewController:vc];
nav.ay_navigationBarEnabled = YES;
```

### Setting
``` objc
// 设置标题
self.ay_navigationItem.title = @"首页";

// 设置标题文本属性
// 设置整个导航控制器所有viewController的文本属性
self.navigationController.ay_titleTextAttributes = @{NSForegroundColorAttributeName: [UIColor blueColor]};
// 设置当前viewController的文本属性
self.ay_navigationItem.titleTextAttributes = @{NSForegroundColorAttributeName: [UIColor orangeColor]};

UIView *titleView = [[UIView alloc] initWithFrame:CGRectMake(0, 0, 1000, 30)];
titleView.layer.cornerRadius = 5;
titleView.layer.masksToBounds = YES;
titleView.backgroundColor = [UIColor yellowColor];

// 设置标题视图
self.ay_navigationItem.titleView = titleView;

// 设置标题视图的风格
self.ay_navigationItem.titleViewStyle = AYNavigationBarTitleViewStyleAutomatic;

// 设置导航栏背景色
self.navigationController.ay_barTintColor = [UIColor cyanColor];
self.ay_navigationBar.backgroundColor = [UIColor cyanColor];

// 设置导航栏底部阴影图片
UIImage *image = [[UIImage imageNamed:@"shadow"] imageWithRenderingMode:UIImageRenderingModeAlwaysOriginal];
self.navigationController.ay_barShadowImage = image;
self.ay_navigationBar.shadowImage = image;

// 设置导航栏背景图片
// self.ay_navigationBar.backgroundImage = [UIImage imageNamed:@"nav"];

UIButton *rightBtn = [UIButton buttonWithType:UIButtonTypeSystem];
rightBtn.frame = CGRectMake(0, 0, 44, 44);
[rightBtn setTitle:@"push" forState:UIControlStateNormal];
[rightBtn addTarget:self action:@selector(rightBtnAction) forControlEvents:UIControlEventTouchUpInside];

// 设置导航栏左右按钮
self.ay_navigationItem.rightBarButton = rightBtn;

UIButton *rightButton = [UIButton buttonWithType:UIButtonTypeInfoLight];
rightButton.frame = CGRectMake(0, 0, 44, 44);

// 设置导航栏左右items
self.ay_navigationItem.rightBarItems = @[rightBtn, rightButton];

// 支持大标题
self.ay_navigationBar.prefersLargeTitles = YES;
// 设置大标题文本属性
self.ay_navigationBar.largeTitleTextAttributes = @{NSFontAttributeName: [UIFont boldSystemFontOfSize:30]};

// 隐藏导航栏
[self.ay_navigationBar setHidden:YES animated:YES];
```

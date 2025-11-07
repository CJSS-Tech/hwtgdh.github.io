# Banner 图片目录

此目录用于存放网站的横幅（Banner）图片。

## 当前横幅列表

目前暂无横幅图片，请添加以下类型的横幅：

### 建议添加的横幅

1. **主页横幅** (`main-banner.jpg`)
   - 尺寸：1200x400px 或 1920x600px
   - 内容：网站主要介绍或品牌展示

2. **分类横幅**
   - `channels-banner.jpg` - 中文频道横幅
   - `groups-banner.jpg` - 行业交流群横幅
   - `jobs-banner.jpg` - 求职招聘横幅
   - `business-banner.jpg` - 海外商机横幅
   - `bots-banner.jpg` - 实用机器人横幅
   - `ads-banner.jpg` - 广告业务横幅

3. **活动横幅**
   - 节日活动横幅
   - 推广活动横幅
   - 特殊事件横幅

## 使用方法

横幅图片放置在此目录后，可以在网站中通过以下方式引用：

```html
<img src="assets/banners/main-banner.jpg" alt="主页横幅" />
```

或在CSS中作为背景：

```css
.banner-section {
    background-image: url('../assets/banners/main-banner.jpg');
}
```
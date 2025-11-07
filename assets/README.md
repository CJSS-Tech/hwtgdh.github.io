# 静态资源目录

## 目录结构

```
assets/
├── README.md          # 本说明文件
├── images/            # 通用图片资源
└── banners/           # 网页横幅图片
```

## 使用说明

### banners/ 目录
专门用于存放网站的横幅图片（Banner），包括：
- 主页横幅
- 分类页面横幅
- 活动横幅
- 广告横幅

### images/ 目录
用于存放其他图片资源，包括：
- 图标文件
- 背景图片
- 装饰性图片
- 其他UI元素

## 文件命名规范

### 横幅图片命名
- 主页横幅：`main-banner.jpg/png`
- 分类横幅：`{category}-banner.jpg/png`
- 活动横幅：`event-{name}-banner.jpg/png`
- 日期横幅：`banner-{YYYY-MM-DD}.jpg/png`

### 通用图片命名
- 小写字母和连字符
- 描述性命名
- 包含尺寸信息（如有需要）

## 支持的文件格式

- **图片格式**：JPG, PNG, WebP, SVG
- **推荐尺寸**：
  - 主横幅：1200x400px 或 1920x600px
  - 分类横幅：800x300px
  - 移动端横幅：750x300px

## 使用示例

```html
<!-- 在HTML中引用横幅 -->
<img src="assets/banners/main-banner.jpg" alt="主页横幅" />

<!-- 在CSS中引用背景图 -->
.hero-banner {
    background-image: url('assets/banners/main-banner.jpg');
}
```

## 注意事项

1. **文件大小**：尽量控制在500KB以内，保证加载速度
2. **版权**：确保所有图片都有使用权限
3. **备份**：重要图片建议在多个位置备份
4. **优化**：使用适当的压缩率平衡质量和文件大小
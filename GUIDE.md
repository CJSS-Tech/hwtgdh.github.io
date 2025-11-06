# 资源配置指南

## 📝 如何添加资源

所有资源都在 `resources.json` 文件中配置。编辑这个文件即可更新网站内容。

## 🗂️ 文件结构说明

### 一、有二级分类的栏目

**包括：中文频道、行业交流群、海外商机、求职&招聘**

格式示例：

```json
{
  "id": "channels",
  "name": "中文频道",
  "icon": "📢",
  "description": "精选优质中文频道",
  "hasSubcategories": true,
  "subcategories": [
    {
      "name": "资讯新闻",
      "resources": [
        {
          "title": "频道名称",
          "description": "频道简介",
          "link": "https://t.me/channel_name",
          "subscribers": "10K+"
        }
      ]
    }
  ]
}
```

**字段说明：**
- `title`: 频道/群组名称（必填）
- `description`: 简介描述（必填）
- `link`: Telegram链接（必填）
- `subscribers`: 订阅人数（可选，用于频道）
- `members`: 成员人数（可选，用于群组）

### 二、无二级分类的栏目

**包括：机器人、广告业务**

格式示例：

```json
{
  "id": "bots",
  "name": "机器人",
  "icon": "🤖",
  "description": "实用的Telegram机器人工具集合",
  "hasSubcategories": false,
  "resources": [
    {
      "title": "Bot名称",
      "description": "Bot功能描述",
      "link": "https://t.me/bot_name",
      "username": "@bot_name"
    }
  ]
}
```

**字段说明：**
- `title`: Bot/服务名称（必填）
- `description`: 功能/服务描述（必填）
- `link`: 链接（必填）
- `username`: 用户名（可选，用于机器人）
- `contact`: 联系方式（可选，用于广告业务）

## 📋 现有分类和二级分类

### 1. 中文频道 (channels)
二级分类：
- 资讯新闻
- 科技数码
- 影视娱乐
- 学习教育

### 2. 行业交流群 (groups)
二级分类：
- 互联网科技
- 金融投资
- 创业商业
- 设计创意
- 外语学习

### 3. 海外商机 (business)
二级分类：
- 跨境电商
- 国际贸易
- 海外投资
- 项目合作

### 4. 求职&招聘 (jobs)
二级分类：
- 技术岗位
- 设计岗位
- 运营市场
- 远程工作
- 实习机会

### 5. 机器人 (bots)
无二级分类，直接添加资源

### 6. 广告业务 (ads)
无二级分类，直接添加资源

## ✏️ 添加资源步骤

### 方法1：直接编辑 JSON 文件

1. 打开 `resources.json` 文件
2. 找到对应的分类
3. 在 `resources` 数组中添加新的资源对象
4. 保存文件
5. 提交到GitHub：
   ```bash
   git add resources.json
   git commit -m "添加新资源"
   git push
   ```

### 方法2：添加新的二级分类

如果需要添加新的二级分类（仅限有二级分类的栏目）：

```json
{
  "name": "新的二级分类名称",
  "resources": []
}
```

将其添加到对应栏目的 `subcategories` 数组中。

## 🎯 完整示例

### 添加一个频道到"中文频道 > 资讯新闻"：

```json
{
  "title": "科技资讯频道",
  "description": "每日推送最新科技新闻和行业动态",
  "link": "https://t.me/tech_news_channel",
  "subscribers": "25K+"
}
```

### 添加一个机器人到"机器人"：

```json
{
  "title": "翻译助手Bot",
  "description": "支持多语言实时翻译的机器人",
  "link": "https://t.me/translate_bot",
  "username": "@translate_bot"
}
```

## ⚠️ 注意事项

1. **JSON格式**：确保JSON格式正确，注意逗号、引号、括号的使用
2. **链接格式**：Telegram链接格式为 `https://t.me/用户名` 或 `https://t.me/joinchat/邀请码`
3. **特殊字符**：描述中如有引号，请使用 `\"` 转义
4. **测试**：修改后在本地浏览器打开 `index.html` 测试效果
5. **备份**：重大修改前建议备份 `resources.json` 文件

## 🔧 常见问题

**Q: 资源不显示怎么办？**
A: 检查JSON格式是否正确，可以用在线JSON验证工具验证。

**Q: 如何修改分类顺序？**
A: 在 `resources.json` 中调整 `categories` 数组中对象的顺序。

**Q: 如何删除某个资源？**
A: 直接从 `resources` 数组中删除对应的对象。

**Q: 可以添加图片吗？**
A: 目前不支持，如需添加可以在描述中使用emoji表情。

---

如有其他问题，请参考 README.md 或提交 Issue。

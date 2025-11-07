# 网站浏览数据分析设置指南

## 🎯 方案一：Google Analytics 4（推荐）⭐

### 为什么选择 Google Analytics？
- ✅ **完全免费**
- ✅ **功能强大**：实时访客、流量来源、用户行为分析
- ✅ **行业标准**：全球最广泛使用的网站分析工具
- ✅ **深度数据**：页面浏览量、停留时间、跳出率、转化率等

---

## 📊 设置步骤

### 1️⃣ 创建 Google Analytics 账号

1. 访问：https://analytics.google.com/
2. 登录 Google 账号
3. 点击 **"开始衡量"**
4. 填写信息：
   ```
   账号名称：Telegram中文资源导航
   属性名称：hwtg
   时区：中国
   货币：CNY - 人民币
   ```
5. 选择行业类别：**参考资料和其他**
6. 数据流设置：
   ```
   平台：网站
   网站网址：https://cjss-tech.github.io/hwtg/
   数据流名称：hwtg 主站
   ```

### 2️⃣ 获取衡量 ID

完成设置后，你会看到类似这样的代码：
```javascript
<!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

**重要**：记下 `G-XXXXXXXXXX` 这个 ID！

### 3️⃣ 添加跟踪代码到网站

将上面的完整代码添加到 `index.html` 的 `<head>` 标签内（在 `</head>` 之前）。

**具体位置**：在安全 meta 标签之后，在 `<link rel="stylesheet">` 之前。

### 4️⃣ 提交更新到 GitHub

```bash
git add index.html
git commit -m "添加 Google Analytics 跟踪代码"
git push origin main
```

### 5️⃣ 验证是否生效

1. 等待 3-5 分钟（GitHub Pages 部署时间）
2. 访问你的网站：https://cjss-tech.github.io/hwtg/
3. 返回 Google Analytics
4. 点击左侧菜单 **"报告" → "实时"**
5. 如果看到 **"1 位用户在线"**，说明配置成功！✅

---

## 📈 你能看到的数据

### 实时数据（即时）
- 🟢 **当前在线用户数**
- 📍 **用户地理位置**（国家、城市）
- 📱 **设备类型**（手机、电脑、平板）
- 📄 **正在浏览的页面**

### 历史数据（24小时后开始积累）
- 📊 **访问量趋势图**
- 👥 **用户数 vs 会话数**
- 🌐 **流量来源**（搜索引擎、社交媒体、直接访问）
- 🔍 **搜索关键词**（部分可见）
- ⏱️ **平均停留时间**
- 📉 **跳出率**
- 🔗 **用户路径分析**

### 高级数据
- 🎯 **转化跟踪**（点击"访问"按钮的次数）
- 📊 **用户留存率**
- 🗂️ **内容分析**（哪个分类最受欢迎）

---

## 🎯 方案二：简单的访客计数器

如果你觉得 Google Analytics 太复杂，可以使用简单的第三方计数器：

### A. Statcounter（免费版）
- 网站：https://statcounter.com/
- 优点：简单、免费额度够用
- 缺点：功能较少

### B. GoatCounter（开源、隐私友好）
- 网站：https://www.goatcounter.com/
- 优点：开源、尊重隐私、免费
- 缺点：功能相对基础

### C. Umami（自托管）
- 网站：https://umami.is/
- 优点：开源、美观、隐私友好
- 缺点：需要自己部署

---

## 🎯 方案三：GitHub Insights（基础数据）

GitHub 本身提供基础的流量数据：

### 查看方式：
1. 访问：https://github.com/CJSS-Tech/hwtg/graphs/traffic
2. 登录 GitHub 账号（需要是仓库所有者）
3. 可以看到：
   - 📈 **访问量**（Views）
   - 👤 **独立访客**（Unique visitors）
   - 🔗 **引荐来源**（Referrers）
   - 📄 **热门内容**（Popular content）

**限制**：
- ⏰ 只保留最近 14 天的数据
- 📊 数据较为基础
- 🚫 不能追踪用户行为细节

---

## 💡 推荐配置

### 最佳实践（同时使用多个工具）：

```
Google Analytics  ← 主要分析工具（详细数据）
     +
GitHub Insights  ← 快速查看（基础数据）
```

---

## 🔐 隐私考虑

### Google Analytics 隐私设置：
添加以下代码可以匿名化 IP 地址：
```javascript
gtag('config', 'G-XXXXXXXXXX', {
  'anonymize_ip': true,
  'cookie_flags': 'SameSite=None;Secure'
});
```

### 告知用户：
建议在页脚添加隐私声明：
```html
<p>本站使用 Google Analytics 分析访问数据，不会收集个人身份信息。</p>
```

---

## 📋 完成后的检查清单

- [ ] 创建 Google Analytics 账号
- [ ] 获取衡量 ID（G-XXXXXXXXXX）
- [ ] 添加跟踪代码到 index.html
- [ ] 提交并推送到 GitHub
- [ ] 等待 3-5 分钟部署
- [ ] 访问网站测试
- [ ] 在 GA 实时报告中验证
- [ ] 24小时后查看完整数据

---

## 🆘 需要帮助？

**如果你已经获得了 Google Analytics 的衡量 ID**，告诉我这个 ID，我可以直接帮你添加到网站代码中！

格式类似：`G-XXXXXXXXXX` 或 `UA-XXXXXXXXX-X`

---

## 📱 查看数据的方式

### 桌面端：
- 网址：https://analytics.google.com/

### 移动端：
- 下载 **Google Analytics** App
- iOS：https://apps.apple.com/app/google-analytics/id881599038
- Android：https://play.google.com/store/apps/details?id=com.google.android.apps.giant

### 快速查看：
- 设置邮件报告（每周/每月自动发送）
- 设置移动通知（流量异常时提醒）

---

**最后更新**：2025-11-07

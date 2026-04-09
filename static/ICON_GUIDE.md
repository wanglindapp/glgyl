# 图标和图片资源说明

## 问题分析

### 1. 底部导航栏图标缺失 ⚠️
pages.json 中配置了以下图标，但文件不存在：
- `static/tab-home.png` - 首页图标（未选中）
- `static/tab-home-active.png` - 首页图标（选中）
- `static/tab-mine.png` - 我的图标（未选中）
- `static/tab-mine-active.png` - 我的图标（选中）

### 2. uni-icons 图标检查 ✅
所有页面使用的 uni-icons 都是 uni-app 内置图标，应该能正常显示：

**登录/注册/忘记密码页面：**
- person, locked, eye, eye-slash, chatbubble

**我的页面：**
- right, calendar, loop, paperplane, checkbox, location, person-add, gear

**我的钱包相关页面：**
- list, add, minus, inbox, wallet, trending-up, trending-down, cash, gift

**充值页面：**
- scan, weixin, creditcard, checkbox-filled, circle, camera, inbox

**提现页面：**
- creditcard, checkbox-filled, circle, inbox

**首页：**
- sound, right, calendar

**采购组件：**
- up, calendar

**邀请页面：**
- gift, wallet, person-add, weixin, chatbubble, qrcode, link, copy

**地址页面：**
- compose, trash, location, plus

**订单页面：**
- inbox

这些图标都是 uni-app 内置的，应该能正常显示。

## 解决方案

### 方案一：创建底部导航图标（推荐）

请创建以下图标文件（尺寸建议：81px × 81px）：

**tab-home.png**
- 首页图标（未选中状态）
- 颜色：灰色 (#999999)
- 建议：房子图标

**tab-home-active.png**
- 首页图标（选中状态）
- 颜色：橙色 (#FF6B35)
- 建议：房子图标

**tab-mine.png**
- 我的图标（未选中状态）
- 颜色：灰色 (#999999)
- 建议：人物图标

**tab-mine-active.png**
- 我的图标（选中状态）
- 颜色：橙色 (#FF6B35)
- 建议：人物图标

### 方案二：临时解决方案（无图标文件时）

修改 pages.json，使用文字代替图标：

```json
"tabBar": {
	"color": "#999999",
	"selectedColor": "#FF6B35",
	"backgroundColor": "#FFFFFF",
	"borderStyle": "black",
	"list": [
		{
			"pagePath": "pages/index/index",
			"text": "首页"
		},
		{
			"pagePath": "pages/mine/mine",
			"text": "我的"
		}
	]
}
```

### 方案三：使用纯色块

创建纯色块作为临时图标：
- 灰色方块 (未选中)
- 橙色方块 (选中)

## 其他需要的图片资源

### 充值页面
- `static/qrcode.png` - 收款二维码（300×300px）

### 我的页面
- `static/avatar.png` - 用户头像（120×120px）

### 首页轮播图
- `static/banner1.png` - 轮播图1（750×400px）
- `static/banner2.png` - 轮播图2（750×400px）
- `static/banner3.png` - 轮播图3（750×400px）

### 采购项目图片
- `static/mango.png` - 芒果图片（360×360px）
- `static/melon.png` - 哈密瓜图片（360×360px）
- `static/apple.png` - 苹果图片（360×360px）
- `static/litchi.png` - 荔枝图片（360×360px）

### 邀请页面
- `static/invite-bg.png` - 邀请页面背景图（750×400px）

## 图标资源下载推荐

### 底部导航图标
可以从以下网站下载免费图标：
- Iconfont (阿里巴巴矢量图标库)
- Flaticon
- Icons8
- FontAwesome

搜索关键词：home, user, profile, person

### uni-icons 图标说明
uni-app 的 uni-icons 组件已经包含了大量内置图标，无需额外下载。

## 快速修复步骤

1. **立即修复底部导航**：使用方案二（文字代替图标）
2. **创建占位图片**：使用纯色块或文字图片
3. **准备正式图标**：从图标网站下载或设计图标
4. **替换图标文件**：将准备好的图标放入 static 目录
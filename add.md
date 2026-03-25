# 网站内容新增代码模板指南 (News, People, Event)

本指南总结了在本项目中新增 **News (新闻/文章)**、**People (团队成员)** 和 **Event (活动/会议)** 时所需的目录结构和 Markdown 文件 (Front Matter) 模板。

---

## 1. 新增 News (新闻 / 文章)

**目录位置**:  
`content/post/<自定义的文章文件夹名>/index.md`
> 注：建议按照此格式建文件夹，并将文章关联的封面图命名为 `featured.png` 或 `featured.jpg` 放在同一目录下。

**`index.md` 代码模板**:

```markdown
---
title: "文章标题，例如：[NEW PREPRINT] AIPatient..."
date: 2024-09-27
tags: ["标签1", "标签2", "Medical QA"]
image:
  focal_point: 'top'
---

🎉 这里填写文章或新闻的前言摘要...

**Paper**: [链接名称](链接地址)

---

## 正文标题

这里是具体的新闻或文章正文内容...
```

---

## 2. 新增 People (团队成员)

**目录位置**:  
`content/authors/<成员名拼音或英文>/_index.md`
> 注：这里必须是 `_index.md`。头像图片请命名为 `avatar.jpg` 并放在同一目录下。

**`_index.md` 代码模板**:

```markdown
---
# 显示名称
title: 中文名或英文名 (如 Guangxin Dai)

# 完整姓名 (用于 SEO)
first_name: Guangxin
last_name: Dai

# 职位与头衔 (选填，取消注释使用)
# role: Affiliated Researcher
# organizations:
#   - name: CUHK
#     url: ''

# 社交媒体或学术主页链接
social:
  - icon: envelope
    icon_pack: fas
    link: 'mailto:邮箱地址'
  # 也可添加 Google Scholar, GitHub 等链接...

# 用于显示 Gravatar 头像的邮箱 (选用)
email: ''

# 是否在列表主要位置高亮显示 (true/false)
highlight_name: false

# 归属的分组类别 (此项决定该人员显示在 People 页面的哪个板块下，如 Principal Investigators, Affiliated Researchers, Alumni 等)
user_groups:
  - Affiliated Researchers
---

这里可以填写一句话简介或详细介绍。例如：PhD Student @ SDU
```

---

## 3. 新增 Event (活动 / 会议)

**目录位置**:  
`content/event/<自定义的活动文件夹名>/index.md`
> 注：建议创建文件夹，并将活动的封面图片命名为 `featured.jpg` 存放在同一目录下。

**`index.md` 代码模板**:

```markdown
---
title: "活动/会议标题，例如：山东第一医科大学精神医学学术研讨会"

summary: 活动一句话概括，将展示在列表页中。

abstract: >
  此处填写详细的摘要或活动背景介绍。
  （由于使用了 ">"，这里支持多行长文本）

# 活动开始与结束时间 (UTC 时间，Z代表+0时区，请根据需要调整)
date: '2025-08-09T09:00:00Z'
date_end: '2025-08-09T17:00:00Z'
all_day: false

# 文章发布时间
publishDate: '2025-08-10T00:00:00Z'

authors: ["参与的团队成员，需与 authors 文件夹名一致能够直接索引"]
tags: ["学术研讨会", "人工智能", "医学影像"]

# 是否在主页推荐位显示
featured: true

# 封面大图设置
image:
  caption: '图片的署名或说明'
  focal_point: Right # 或 Center, Top 等

# 相关资源链接（如果留空，按钮将不会在页面显示）
url_code: ''
url_pdf: ''
url_slides: ''
url_video: ''

slides: ""
projects: []
---

## 📅 活动详情 / 研究分享

这里填写讲座、会议或活动的具体细节...
你也可以在正文中直接插入图片：
![图片描述](share.png)
```
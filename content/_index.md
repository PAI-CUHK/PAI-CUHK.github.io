---
# Leave the homepage title empty to use the site title
title:
date: 2022-10-24
type: landing

sections:
  - block: hero
    content:
      title: |
        Psychiatry & AI
        Research Group
      image:
        filename: welcome.png
      text: |
        <style>
          /* 核心调整：增加距离屏幕左右边缘的整体留白 */
          .wg-hero .container {
            max-width: 1200px;
          }
          .wg-hero .row {
            padding-left: 6%; /* 强行把包括大标题在内的文字群往右推，远离屏幕左侧 */
            padding-right: 4%;
          }
          
          .pai-hero-typography {
            max-width: 560px; /* 强制限制文本宽度，留出大面积留白区域 */
            margin-top: 1.5rem;
          }
          .pai-hero-typography p {
            font-size: 1.125rem;
            line-height: 1.85;
            color: #5f6368; /* Google Material Design 经典的护眼灰 */
            margin-bottom: 1.75rem;
            letter-spacing: 0.01em;
          }
          .pai-hero-typography strong {
            color: #202124; /* Material Design 面板黑，产生高级的层次对比 */
            font-weight: 600;
          }
          @media (max-width: 992px) {
            .wg-hero .row {
              padding-left: 0;
              padding-right: 0;
            }
            .pai-hero-typography {
              max-width: 100%; /* 移动端恢复正常占比 */
              margin-bottom: 2rem;
            }
          }
        </style>
        <div class="pai-hero-typography">
          <p>The <strong>CUHK Psychiatry & AI (PAI) Research Group</strong> is a cross-disciplinary research hub for Medical AI and Digital Health research in Psychiatry.</p>
          <p>Founded by Dr. Leo Lizhou Fan in 2025, this group at the Department of Psychiatry, Faculty of Medicine, CUHK now welcomes motivated talents in AI and digital health to join our synergy of research.</p>
        </div>
  
  - block: collection
    content:
      title: Latest News
      subtitle:
      text:
      count: 5
      filters:
        author: ''
        category: ''
        exclude_featured: false
        publication_type: ''
        tag: ''
      offset: 0
      order: desc
      page_type: post
    design:
      view: compact
      columns: '1'
  

  - block: markdown
    content:
      title:
      subtitle:
      text: |
        {{% cta cta_link="./people/" cta_text="Meet the team →" %}}
    design:
      columns: '1'
---

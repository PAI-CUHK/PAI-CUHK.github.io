---
title: Publications
type: landing

sections:
  - block: markdown
    id: pai-years
    content:
      title: ''
      text: |
        <style>
          #pai-years .pai-years-inner {
            max-width: 1120px;
            margin: 0 auto;
          }

          #pai-years .pai-years-title {
            margin: 0 0 1rem;
            color: #000;
            font-size: 1.4rem;
            font-weight: 700;
            text-transform: uppercase;
          }

          #pai-years .pai-years-list {
            display: flex;
            flex-wrap: wrap;
            column-gap: 2rem;
            row-gap: 0.5rem;
          }

          #pai-years .pai-years-list a {
            color: #007eaf;
            font-size: 1.1rem;
            font-weight: 400;
            line-height: 1.35;
            text-decoration: none;
          }

          #pai-years .pai-years-list a:hover,
          #pai-years .pai-years-list a:focus-visible {
            text-decoration: underline;
          }

          #pai-years .pai-years-list a[aria-current="true"] {
            color: #00577b;
            text-decoration: underline;
            text-underline-offset: 0.25rem;
          }

          @media (max-width: 767px) {
            #pai-years .pai-years-list {
              column-gap: 1.25rem;
            }
          }
        </style>

        <nav class="pai-years-inner" aria-label="Publication years">
          <h2 class="pai-years-title">Years</h2>
          <div class="pai-years-list"></div>
        </nav>
    design:
      columns: '1'
      background:
        color: '#ffffff'
      spacing:
        padding: ['40px', '20px', '0px', '20px']

  - block: collection
    id: pai-publications
    content:
      title: Publications
      text: |
        <style>
          #pai-publications .pai-paper-entry {
            display: grid;
            grid-template-columns: 1.5rem minmax(0, 1fr);
            gap: 0.25rem;
            max-width: 1120px;
            margin: 0 auto 1.25rem;
            color: #000;
            font-size: 0.8rem;
            line-height: 1.5;
          }

          #pai-publications .pai-paper-number {
            text-align: right;
          }

          #pai-publications .pai-paper-title a {
            color: #000;
            font-weight: 700;
          }

          #pai-publications .pai-paper-title a:hover {
            text-decoration: underline;
          }

          #pai-publications .pai-paper-authors {
            font-weight: 400;
          }

          #pai-publications .pai-paper-links a {
            color: #1769c2;
          }

          #pai-publications .pai-paper-entry[hidden] {
            display: none !important;
          }
    
        </style>
      count: 0
      filters:
        folders:
          - papers
    design:
      view: pai-paper
      columns: '1'
      background:
        color: '#ffffff'

---

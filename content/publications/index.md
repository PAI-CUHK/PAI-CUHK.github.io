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
            font-size: clamp(1.25rem, 2.5vw, 2rem);
            font-weight: 300;
            line-height: 1.35;
            text-decoration: none;
          }

          #pai-years .pai-years-list a:hover,
          #pai-years .pai-years-list a:focus-visible {
            text-decoration: underline;
          }

          :is(#pai-publications, #pai-preprints) .pai-paper-year {
            max-width: 1120px;
            margin: 2rem auto 1rem;
            color: #000;
            font-size: 1.4rem;
            font-weight: 600;
            scroll-margin-top: 6rem;
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
          :is(#pai-publications, #pai-preprints) .pai-paper-entry {
            display: grid;
            grid-template-columns: 1.5rem minmax(0, 1fr);
            gap: 0.25rem;
            max-width: 1120px;
            margin: 0 auto 1.25rem;
            color: #000;
            font-size: 0.8rem;
            line-height: 1.5;
          }

          :is(#pai-publications, #pai-preprints) .pai-paper-number {
            text-align: right;
          }

          :is(#pai-publications, #pai-preprints) .pai-paper-title a {
            color: #000;
            font-weight: 700;
          }

          :is(#pai-publications, #pai-preprints) .pai-paper-title a:hover {
            text-decoration: underline;
          }

          :is(#pai-publications, #pai-preprints) .pai-paper-authors {
            font-weight: 400;
          }

          :is(#pai-publications, #pai-preprints) .pai-paper-links a {
            color: #1769c2;
          }
    
          #pai-publications {
            padding-bottom: 0px !important;
          }
          
          #pai-preprints {
            padding-top: 16px !important;
          }
    
        </style>
      count: 0
      filters:
        folders:
          - papers
        publication_type: '2'
    design:
      view: pai-paper
      columns: '1'
      background:
        color: '#ffffff'

  - block: collection
    id: pai-preprints
    content:
      title: Preprints
      count: 0
      filters:
        folders:
          - papers
        publication_type: '3'
    design:
      view: pai-paper
      columns: '1'
      background:
        color: '#ffffff'
---

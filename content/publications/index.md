---
title: Publications
type: landing

sections:
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

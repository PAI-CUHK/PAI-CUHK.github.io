---
title: Welcoming
date: 2022-10-24
type: landing

sections:
  - block: hero
    content:
      title: |
        Welcome to the PAI Lab at CUHK
    
      text: |
        <style>
          @import url('https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@1,800&display=swap');

          #section-hero .hero-lead {
            max-width: 56ch;
            margin-inline: auto;
            font-family: 'Montserrat', Arial, sans-serif;
            font-size: clamp(1rem, 1.8vw, 1.15rem);
            font-weight: 800;
            font-style: italic;
            line-height: 1.55;
          }
        </style>
        Connecting Minds, Shaping Futures—Pioneering Digital Mental Wellness through Innovative Algorithms.
        
    design:
      background:
        color: '#666'
        text_color_light: true
        image:
          filename: lab4.png
          size: cover
          position: right
          parallax: false
          filters:
            brightness: 0.7
      spacing:
        padding: ['140px', '20px', '140px', '20px']
      css_style: 'text-align: center;'

  - block: markdown
    id: about
    content:
      title: ''
      subtitle: ''
      text: |
        <style>
          #about .pai-about-title {
            color: #000000;
            font-size: 1.4rem;
            font-weight: 700;
            margin-bottom: 0px;
            text-align: left;
          }

          #about .pai-about-layout {
            display: flex;
            align-items: center;
            gap: 50px;
          }

          #about .pai-about-logo {
            width: 300px;
            flex-shrink: 0;
          }

          #about .pai-about-logo img {
            display: block;
            width: 100%;
            height: auto;
          }

          #about .pai-about-text {
            flex: 1;
            min-width: 0;
            color: #333;
            font-size: 0.9rem;
            line-height: 1.7;
            text-align: left;
          }

          #about .pai-about-text p {
            margin-bottom: 24px;
          }
          #about .pai-about-text p:last-child {
            margin-bottom: 0;
          }

          #about .pai-about-text a {
            color: #000000;
          }
    
          #about .pai-about-text a.pai-founder-link {
            color: #4B2E83;
          }

          @media (max-width: 767px) {
            #about .pai-about-layout {
              flex-direction: column;
              gap: 25px;
            }
          }
        </style>

        <h2 class="pai-about-title">About Us</h2>

        <div class="pai-about-layout">
          <div class="pai-about-logo">
            <img src="icon.png" alt="PAI Lab logo">
          </div>
          <div class="pai-about-text">
            <p>
              The Psychiatry and AI (PAI) Lab is an interdisciplinary research hub in the
              Department of Psychiatry, Faculty of Medicine, at The Chinese University of
              Hong Kong (CUHK). Founded in 2025 by
              <a href="https://lizhouf.github.io/" class="pai-founder-link">Prof. Leo Lizhou Fan</a>, the lab brings
              together faculty members, postdoctoral researchers, and students to explore
              how medical AI and digital health technologies can advance psychiatric
              research and care. Our research spans foundation models, embodied AI, and
              other applications of AI in mental health.
            </p>
          </div>
        </div>
    design:
      columns: '1'
      background:
        color: '#ffffff'
        text_color_light: false
      spacing:
        padding: ['80px', '20px', '10px', '20px']

  - block: markdown
    id: pai-news
    content:
      title: ''
      subtitle: ''
      text: |
        <style>
          #pai-news .pai-news-title {
            color: #000;
            font-size: 1.4rem;
            font-weight: 700;
            margin-bottom: 20px;
            text-align: left;
          }

          #pai-news .pai-news-item + .pai-news-item {
            margin-top: 12px;
          }

          #pai-news .pai-news-item p {
            margin: 0;
            font-size: 0.9rem;
          }

          #pai-news .pai-news-item time {
            color: #000;
            font-size: 0.9rem;
            font-weight: 700;
          }
    
          #pai-news .pai-news-link {
            display: block;
            font-size: 0.9rem;
            color: inherit;
            text-decoration: none;
          }
          
          #pai-news .pai-news-link:hover,
          #pai-news .pai-news-link:focus-visible {
            color: inherit;
            text-decoration: underline;
          }
        </style>

        <h2 class="pai-news-title">PAI News</h2>

        <article class="pai-news-item">
          <p>
            <a class="pai-news-link" href="post/260416/">
              <time datetime="2026-04-16">April 16, 2026.</time>
              Congratulations to our research teams on winning First Prize for Excellent Paper for two projects at the 15th Chest Pain Center Conference!
            </a>
          </p>
        </article>

        <article class="pai-news-item">
          <p>
            <a class="pai-news-link" href="post/251101/">
              <time datetime="2025-11-01">November 1, 2025.</time>
              Congratulations to Ms. Huizi Yu on receiving the Outstanding Award for an oral presentation in science and engineering at the 2025 Greater Bay Area Graduate Research Forum!
            </a>
          </p>
        </article>
    
        <article class="pai-news-item">
          <p>
            <a class="pai-news-link" href="post/25-sdu/">
              <time datetime="2025-01-01">January 1, 2025.</time>
              Congratulations to our team on winning the Best Paper Award for
              “Enhancing Medical Diagnostic Reasoning with Chain-of-Thought in Large Language Models”!
            </a>
          </p>
        </article>

        <!-- Add your lab updates here. -->
    design:
      columns: '1'
      background:
        color: '#ffffff'
        text_color_light: false
      spacing:
        padding: ['10px', '20px', '80px', '20px']
   
---

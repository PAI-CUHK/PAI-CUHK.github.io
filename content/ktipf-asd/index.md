---
title: "KTIPF-ASD: SpectraHomeHelper"
date: 2024-11-14
type: landing

sections:
  - block: markdown
    content:
      title: ""
      text: |
        <style>
          /* Global Medical-Tech Styles */
          .med-page {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
            color: #0f172a;
            background-color: #ffffff;
            line-height: 1.6;
          }
          
          .med-badge {
            display: inline-block;
            background-color: #f3e8ff; /* Light purple */
            color: #7c3aed; /* Primary purple */
            padding: 6px 16px;
            border-radius: 9999px;
            font-size: 0.875rem;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 0.05em;
            margin-bottom: 1.5rem;
          }

          /* General Utility */
          .med-container {
            max-width: 1024px;
            margin: 0 auto;
            padding: 0 2rem;
          }
          
          .text-center { text-align: center; }
          .mb-1 { margin-bottom: 0.5rem; }
          .mb-2 { margin-bottom: 1rem; }
          .mb-4 { margin-bottom: 2rem; }
          .mb-8 { margin-bottom: 4rem; }
          
          .section-divider {
            height: 1px;
            background: linear-gradient(90deg, transparent, #e2e8f0, transparent);
            margin: 2.5rem 0;
            border: none;
          }

          /* Buttons */
          .btn-group {
            display: flex;
            justify-content: center;
            gap: 1rem;
            margin-top: 2rem;
          }
          .med-btn {
            padding: 12px 28px;
            border-radius: 8px;
            font-weight: 600;
            text-decoration: none;
            transition: all 0.2s ease-in-out;
            font-size: 1rem;
            box-shadow: 0 2px 4px rgba(0,0,0,0.05);
          }
          .med-btn-primary {
            background-color: #7c3aed; /* Primary purple */
            color: #ffffff !important;
            border: 2px solid #7c3aed;
          }
          .med-btn-primary:hover {
            background-color: #6d28d9; /* Darker purple */
            border-color: #6d28d9;
            transform: translateY(-2px);
            box-shadow: 0 4px 12px rgba(124, 58, 237, 0.2);
          }
          .med-btn-secondary {
            background-color: transparent;
            color: #4c1d95 !important; /* Deep navy purple */
            border: 2px solid #cbd5e1;
          }
          .med-btn-secondary:hover {
            border-color: #4c1d95;
            background-color: #f8fafc;
            transform: translateY(-2px);
          }

          /* Hero Section */
          .med-hero {
            background: linear-gradient(135deg, #faf5ff 0%, #ffffff 100%); /* Purple faint gradient */
            padding: 3rem 0;
            overflow: hidden;
            position: relative;
          }
          .med-hero-content {
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
            gap: 2.5rem;
          }
          .med-hero-text {
            flex: 1;
            z-index: 2;
          }
          .med-hero-text h1 {
            font-size: 2.75rem;
            font-weight: 800;
            color: #0f172a;
            line-height: 1.2;
            margin-bottom: 1.25rem;
            letter-spacing: -0.02em;
          }
          .med-hero-text h1 span {
            color: #7c3aed;
          }
          .med-hero-text p {
            font-size: 1.1rem;
            color: #475569;
            margin-bottom: 1.5rem;
          }
          .med-hero-img {
            flex: 1;
            display: flex;
            justify-content: center;
            z-index: 2;
            animation: float 6s ease-in-out infinite;
          }
          .med-hero-img img {
            max-width: 100%;
            height: auto;
            border-radius: 16px;
            box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
            object-fit: cover;
          }

          /* Triple Barrier Cards */
          .med-section {
            padding: 3rem 0;
          }
          .med-section-title {
            text-align: center;
            font-size: 2rem;
            font-weight: 700;
            color: #4c1d95;
            margin-bottom: 1rem;
          }
          .med-section-desc {
            text-align: center;
            color: #64748b;
            font-size: 1.05rem;
            max-width: 700px;
            margin: 0 auto 2rem auto;
          }
          .med-cards-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
          }
          .med-card {
            background-color: #f8fafc;
            border: 1px solid #f1f5f9;
            border-radius: 12px;
            padding: 2.5rem 2rem;
            text-align: left;
            transition: all 0.3s ease;
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
          }
          .med-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
            border-color: #e2e8f0;
          }
          .med-card-icon {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 48px;
            height: 48px;
            background-color: #f3e8ff;
            color: #7c3aed;
            border-radius: 12px;
            margin-bottom: 1.5rem;
          }
          .med-card-icon svg {
            width: 24px;
            height: 24px;
          }
          .med-card h3 {
            font-size: 1.25rem;
            font-weight: 600;
            color: #0f172a;
            margin-bottom: 1rem;
          }
          .med-card p {
            color: #475569;
            font-size: 0.95rem;
            line-height: 1.6;
          }

          /* Solution Showcase (Alternating Layout) */
          .med-feature {
            display: flex;
            align-items: center;
            gap: 2.5rem;
            margin-bottom: 3.5rem;
          }
          .med-feature:last-child {
            margin-bottom: 0;
          }
          .med-feature.reverse {
            flex-direction: row-reverse;
          }
          .med-feature-text {
            flex: 1;
          }
          .med-feature-text label {
            font-size: 0.875rem;
            font-weight: 700;
            color: #7c3aed;
            text-transform: uppercase;
            letter-spacing: 0.05em;
          }
          .med-feature-text h2 {
            font-size: 1.75rem;
            font-weight: 700;
            color: #4c1d95;
            margin: 0.5rem 0 1.25rem 0;
          }
          .med-feature-text p {
            font-size: 1.05rem;
            color: #475569;
            margin-bottom: 1rem;
          }
          .med-feature-text ul {
            list-style: none;
            padding: 0;
            margin-top: 1.5rem;
          }
          .med-feature-text li {
            position: relative;
            padding-left: 28px;
            margin-bottom: 1rem;
            color: #334155;
            font-size: 1rem;
          }
          .med-feature-text li::before {
            content: "✦";
            position: absolute;
            left: 0;
            color: #7c3aed;
            font-size: 1.2rem;
          }
          .med-feature-img {
            flex: 1;
            position: relative;
          }
          .med-feature-img img {
            width: 100%;
            height: auto;
            border-radius: 16px;
            box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.15);
          }

          /* Impact Statistics */
          .med-stats-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 2rem;
            text-align: center;
            background-color: #f8fafc;
            border-radius: 16px;
            padding: 2rem 1.5rem;
            margin-top: 2rem;
          }
          .med-stat-item h4 {
            font-size: 2.75rem;
            font-weight: 800;
            color: #7c3aed;
            margin-bottom: 0.5rem;
            line-height: 1;
          }
          .med-stat-item p {
            font-size: 0.95rem;
            font-weight: 600;
            color: #475569;
            margin: 0;
          }

          /* Animations */
          @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-15px); }
            100% { transform: translateY(0px); }
          }
          .fade-in-up {
            animation: fadeInUp 0.8s forwards ease-out;
            opacity: 0;
            transform: translateY(20px);
          }
          @keyframes fadeInUp {
            to { opacity: 1; transform: translateY(0); }
          }

          /* Responsive */
          @media (max-width: 992px) {
            .med-hero-content, .med-feature, .med-feature.reverse {
              flex-direction: column;
              text-align: center;
              gap: 2.5rem;
            }
            .med-hero-text h1 { font-size: 2.25rem; }
            .btn-group { justify-content: center; }
            .med-feature-text li { text-align: left; }
            .med-stats-grid { grid-template-columns: 1fr; gap: 3rem; }
          }
          @media (max-width: 600px) {
            .med-hero-text h1 { font-size: 1.75rem; }
          }

          /* Collaborators Marquee */
          .med-collaborators-marquee {
            overflow: hidden;
            white-space: nowrap;
            position: relative;
            margin-top: 3rem;
            padding: 1rem 0;
            -webkit-mask-image: linear-gradient(90deg, transparent, #000 10%, #000 90%, transparent);
            mask-image: linear-gradient(90deg, transparent, #000 10%, #000 90%, transparent);
          }
          .med-collaborators-track {
            display: inline-flex;
            align-items: center;
            gap: 5rem;
            animation: marquee 25s linear infinite;
          }
          .med-collaborators-track:hover {
            animation-play-state: paused;
          }
          .med-collaborators-logo {
            height: 70px;
            width: auto;
            max-width: 250px;
            object-fit: contain;
            transition: all 0.4s ease;
          }
          .med-collaborators-logo:hover {
            transform: scale(1.05);
          }
          @keyframes marquee {
            0% { transform: translateX(0); }
            100% { transform: translateX(calc(-50% - 2.5rem)); }
          }
          @media (max-width: 768px) {
            .med-collaborators-logo { height: 50px; }
            .med-collaborators-track { gap: 3rem; }
            @keyframes marquee {
              0% { transform: translateX(0); }
              100% { transform: translateX(calc(-50% - 1.5rem)); }
            }
          }
        </style>

        <div class="med-page">
          
        <!-- HERO SECTION -->
        <section class="med-hero">
        <div class="med-container med-hero-content">
        <div class="med-hero-text fade-in-up">
        <span class="med-badge">KTIPF-ASD Funded Innovation</span>
        <h1>SpectraHomeHelper</h1>
        <p style="font-weight: 600; color: #4c1d95; margin-bottom: 1rem;">Transforming Pediatric Autism Spectrum Disorders Healthcare with AI-powered Home Monitoring and Patient Navigation</p>
        <p style="font-size: 1.1rem; font-weight: 600; color: #6d28d9; margin-bottom: 1.5rem;">以AI驅動的家庭監測和患者導引系統重塑兒童自閉症譜系障礙的醫療服務</p>
        
        <div class="med-hero-img fade-in-up" style="animation-delay: 0.3s; margin-bottom: 2rem;">
        <img src="image3.jpg" alt="SpectraHomeHelper AI Healthcare Vision Dashboard">
        </div>

        <p>SpectraHomeHelper is an integrated digital health solution combining AI home monitoring that prioritizes data privacy with a bilingual patient navigator driven by large language models. It provides continuous behavioral assessment and structured resource guidance for autistic children, shifting care from episodic visits to continuous support focused entirely on the family.</p>
        <p style="color: #64748b; font-size: 1rem;">本項目致力於構建一個結合AI家庭行為監測與雙語大語言模型患者導引系統的創新數字醫療平台。它能夠為自閉症兒童提供連續的臨床級評估與結構化資源指導，以期待於實現高效、協調且以家庭為中心的普適化全面支持服務。</p>
        <div class="btn-group">
        <a href="#solution" class="med-btn med-btn-primary" style="padding: 16px 80px; font-size: 1.125rem; text-align: center;">Explore the Platform</a>
        </div>
        </div>
        </div>
        </section>

        <!-- THE ISSUE SECTION -->
        <section class="med-section med-container fade-in-up">
        <h2 class="med-section-title">The "Triple Barrier" in ASD Care</h2>
        <p class="med-section-desc mb-2" style="max-width: 900px; margin-bottom: 4rem;">Children with Autism Spectrum Disorder (ASD) in Hong Kong and mainland China encounter a persistent "triple barrier" when accessing care.<br>在香港和內地，自閉症兒童在獲取醫療服務時面臨嚴重的「三重障礙」。</p>
        
        <div class="med-hero-img fade-in-up" style="animation-delay: 0.2s; margin-bottom: 3rem;">
        <img src="image1.jpg" alt="The Triple Barrier Infographic">
        </div>
        
        <div class="med-cards-grid">
        <!-- Card 1 -->
        <div class="med-card">
        <div class="med-card-icon">
        <img src="icon/瓶颈.png" alt="Diagnostic Bottlenecks Icon" style="width: 24px; height: 24px; object-fit: contain;">
        </div>
        <h3>Prolonged Waits<br><span style="font-size: 1rem; color: #6d28d9;">診斷瓶頸</span></h3>
        <p>Specialist clinics face massive waitlists, leaving children waiting months or years for evaluation.<br>專科門診面臨巨大診斷瓶頸，導致候診名單極長，患兒往往需等待數月至數年才能確診。</p>
        </div>
        <!-- Card 2 -->
        <div class="med-card">
        <div class="med-card-icon">
        <svg fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3.055 11H5a2 2 0 012 2v1a2 2 0 002 2 2 2 0 012 2v2.945M8 3.935V5.5A2.5 2.5 0 0010.5 8h.5a2 2 0 012 2 2 2 0 104 0 2 2 0 012-2h1.064M15 20.488V18a2 2 0 012-2h3.064M21 12a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
        </div>
        <h3>Unequal Access<br><span style="font-size: 1rem; color: #6d28d9;">資源分布不均</span></h3>
        <p>Disproportionately impacts low-income and non-urban families, who struggle to afford frequent clinic visits and transport.<br>醫療資源獲取存在顯著不平等，低收入和非城市家庭難以承擔頻繁就診的交通與時間成本。</p>
        </div>
        <!-- Card 3 -->
        <div class="med-card">
        <div class="med-card-icon">
        <img src="icon/碎片.png" alt="Fragmented Coordination Icon" style="width: 24px; height: 24px; object-fit: contain;">
        </div>
        <h3>Fragmented Coordination<br><span style="font-size: 1rem; color: #6d28d9;">護理碎片化</span></h3>
        <p>Families independently navigate complex guidelines, subsidies, and disjointed care settings, missing day-to-day variability.<br>照顧者必須獨自摸索複雜的醫療指南和補貼，且短暫的門診難以捕捉兒童日常行為的真實變化。</p>
        </div>
        </div>

        <p class="text-center mt-4" style="color: #475569; max-width: 900px; margin: 2rem auto 0;">
        This leads to delayed diagnoses, inconsistent follow-ups, elevated caregiver stress, and widening disparities in developmental outcomes.<br>這種現狀不僅導致了診斷和治療的延誤，給家庭帶來了極大的精神和經濟壓力，也進一步拉大了自閉症兒童在早期發育結果上的巨大差距。
        </p>
        </section>

        <hr class="section-divider">

        <!-- SOLUTION SHOWCASE -->
        <section id="solution" class="med-section med-container fade-in-up">
        <h2 class="med-section-title">The Solution</h2>
        <p class="med-section-desc mb-8" style="max-width: 900px; margin-bottom: 5rem;">We propose a comprehensive solution combining AI-powered home monitoring with an LLM-based patient navigator.<br>我們致力於開發和驗證一套結合AI家庭監測與大語言模型患者導引系統的綜合解決方案。</p>

        <!-- Feature Block 1 -->
        <div class="med-feature">
        <div class="med-feature-text">
        <label>Continuous Clinical Assessment</label>
        <h2>AI Home Monitor<br><span style="font-size: 1.5rem; color: #7c3aed;">家庭監測器</span></h2>
        <p>Uses a smartphone and depth camera to record structured parent-child block-play sessions at home.<br>利用智能手機和深度攝像頭在家中記錄結構化的親子積木遊戲。</p>
        <ul>
        <li><strong>Privacy-preserving algorithms (端側算法):</strong> Extracts behavioral features safely while protecting family data.<br>通過保護隱私的端側算法安全提取行為特徵。</li>
        <li><strong>Multimodal Foundation Model (MFM):</strong> Generates continuous clinical dashboards directly for clinicians.<br>利用多模態基礎模型生成連續的臨床評估儀表板供醫生參考。</li>
        <li><strong>Clinical Grade (臨床級):</strong> Brings assessment into the home setting.<br>將臨床評估直接融入日常家庭場景。</li>
        </ul>
        </div>
        <div class="med-feature-img">
        <img src="image2.jpg" alt="AI Home Monitoring Setup">
        </div>
        </div>

        <!-- Feature Block 2 -->
        <div class="med-feature reverse mt-8 pt-8">
        <div class="med-feature-text">
        <label>24/7 Personalized Guidance</label>
        <h2>LLM Patient Navigator<br><span style="font-size: 1.5rem; color: #7c3aed;">患者導引系統</span></h2>
        <p>A bilingual AI assistant driven by retrieval-augmented generation (RAG) providing constant family support.<br>這是一個由檢索增強生成驅動的雙語助手，能為家庭提供全天候指導。</p>
        <ul>
        <li><strong>Resource Integration (資源整合):</strong> Integrates verified clinic directories, school services, and financial subsidies.<br>整合經過驗證的診所目錄、教育服務和經濟補貼資源。</li>
        <li><strong>Bilingual Accessible Support (雙語降維解答):</strong> Answers caregiver questions in accessible language.<br>用通俗語言和多種語言解答家庭的疑問。</li>
        <li><strong>Continuous Coordinated Care:</strong> Eliminates administrative fragmentation.<br>消除了醫療信息碎片化，保障協調支持。</li>
        </ul>
        </div>
        <div class="med-feature-img">
        <img src="image4.jpg" alt="LLM Patient Navigator">
        </div>
        </div>
        </section>

        <hr class="section-divider">

        <!-- IMPACT SECTION -->
        <section class="med-section med-container fade-in-up">
        <h2 class="med-section-title">Beneficiaries & Impact</h2>
        <p class="med-section-desc" style="max-width: 900px;">Transforming pediatric ASD care into a coordinated, long-term support network.<br>推動自閉症護理走向連續的長期支持模式。</p>

        <div class="med-stats-grid">
        <div class="med-stat-item">
        <h4>100</h4>
        <p>Children & Families<br><span style="font-size: 0.85rem; font-weight: 400; color: #64748b;">主要受益人 (Primary Beneficiary)</span></p>
        </div>
        <div class="med-stat-item">
        <h4>30</h4>
        <p>Clinicians<br><span style="font-size: 0.85rem; font-weight: 400; color: #64748b;">次要受益人 (Secondary Beneficiary)</span></p>
        </div>
        <div class="med-stat-item">
        <h4>5</h4>
        <p>Policymakers & Schools<br><span style="font-size: 0.85rem; font-weight: 400; color: #64748b;">其他受益人 (Other Beneficiaries)</span></p>
        </div>
        </div>
        
        <p class="text-center mt-8" style="color: #475569; max-width: 900px; margin: 2rem auto 0; font-size: 1.05rem;">
        SpectraHomeHelper significantly shortens time-to-evaluation and reduces administrative burdens for caregivers, particularly benefiting low-income or non-urban families. By delivering continuous behavioral insights, it enhances diagnostic confidence and efficiency for clinicians. Furthermore, the system provides health authorities with essential data to identify service gaps, facilitating equitable healthcare policies.<br><br>本項目大幅縮短了患兒評估等待時間，減輕了家長的行政與經濟負擔，尤其惠及低收入家庭。連續的家庭行為監測數據顯著提升了臨床醫生的診斷信心和效率。同時，系統為公共衛生部門提供了真實世界數據支持，有助於優化資源配置和制定公平的醫療政策。
        </p>

        <div class="mt-8 pt-8" style="margin-top: 6rem; padding-top: 4rem; border-top: 1px solid #e2e8f0;">
        <h3 class="text-center" style="font-size: 1.5rem; color: #4c1d95; margin-bottom: 1.5rem;">Collaborators</h3>
        <p class="text-center" style="max-width: 1200px; margin: 0 auto; color: #475569;">HATCH Cohort (The D.H. Chen Foundation Hub of Advanced Technology for Child Health), Shandong University Qilu Hospital Cohort, ASD NGOs, and University services.<br>
        <span style="font-size: 0.95rem;">香港中文大学陳廷驊基金會兒童醫學創科中心、山東大學齊魯醫院、自閉症相關非政府机构及高校服務機構等。</span>
        </p>

        <!-- Infinite Scrolling Collaborator Logos -->
        <div class="med-collaborators-marquee">
          <div class="med-collaborators-track">
            <!-- First Set -->
            <img class="med-collaborators-logo" src="collaborators/CUHK.png" alt="The Chinese University of Hong Kong">
            <img class="med-collaborators-logo" src="collaborators/medical_CUHK.png" alt="Faculty of Medicine, CUHK">
            <img class="med-collaborators-logo" src="collaborators/cuhk_hatch.png" alt="Faculty of Medicine, CUHK">
            <img class="med-collaborators-logo" src="collaborators/HATCH.png" alt="HATCH Foundation">
            <img class="med-collaborators-logo" src="collaborators/NGO.png" alt="NGO Partners">
            <img class="med-collaborators-logo" src="collaborators/齐鲁医院.png" alt="Qilu Hospital of Shandong University">
            <!-- Duplicated Set for Infinite Loop -->
            <img class="med-collaborators-logo" src="collaborators/CUHK.png" alt="The Chinese University of Hong Kong">
            <img class="med-collaborators-logo" src="collaborators/medical_CUHK.png" alt="Faculty of Medicine, CUHK">
            <img class="med-collaborators-logo" src="collaborators/HATCH.png" alt="HATCH Foundation">
            <img class="med-collaborators-logo" src="collaborators/NGO.png" alt="NGO Partners">
            <img class="med-collaborators-logo" src="collaborators/齐鲁医院.png" alt="Qilu Hospital of Shandong University">
          </div>
        </div>
        </div>

        <div class="text-center mb-8 pb-8" style="display: flex; justify-content: center; margin-top: 6rem;">
        <a href="/contact/" class="med-btn med-btn-primary" style="padding: 16px 40px; font-size: 1.125rem;">Contact Us 聯繫我們</a>
        </div>
        </section>

        </div>
---
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2026 AI/SW Career Portfolio</title>
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Pretendard:wght@400;700;900&display=swap" rel="stylesheet">
    <style>
        :root {
            --main-navy: #001D3D;
            --pure-white: #FFFFFF;
            --soft-gray: #F8F9FA;
            --accent-green: #3DFD44; /* 형광 그린 */
            --accent-blue: #00E5FF;  /* 형광 블루 */
            --text-dark: #1D1D1F;
            --text-light: #6E6E73;
            --transition: all 0.4s cubic-bezier(0.25, 1, 0.5, 1);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; scroll-behavior: smooth; }

        body {
            font-family: 'Pretendard', sans-serif;
            background-color: var(--pure-white);
            color: var(--text-dark);
            line-height: 1.6;
        }

        /* --- Navigation --- */
        nav {
            position: fixed;
            top: 0; width: 100%; height: 70px;
            background: rgba(255, 255, 255, 0.85);
            backdrop-filter: blur(20px);
            display: flex; justify-content: space-between; align-items: center;
            padding: 0 8%; z-index: 1000;
            border-bottom: 1px solid rgba(0, 0, 0, 0.05);
        }

        .logo { font-size: 1.4rem; font-weight: 900; color: var(--main-navy); }
        .nav-links { display: flex; list-style: none; }
        .nav-links li { margin-left: 2rem; }
        .nav-links a {
            text-decoration: none; color: var(--main-navy);
            font-weight: 600; font-size: 0.9rem; transition: 0.3s;
        }
        .nav-links a:hover { color: var(--accent-blue); }

        /* --- Hero Section --- */
        #hero {
            height: 80vh; display: flex; flex-direction: column;
            justify-content: center; align-items: center; text-align: center;
            background: radial-gradient(circle at top right, #f0f4f8, #ffffff);
            padding: 0 10%;
        }
        .hero-badge { background: var(--main-navy); color: var(--accent-green); padding: 5px 15px; border-radius: 50px; font-weight: 700; font-size: 0.8rem; margin-bottom: 20px; }
        #hero h1 { font-size: 3.5rem; font-weight: 900; color: var(--main-navy); line-height: 1.2; margin-bottom: 20px; }
        #hero p { font-size: 1.2rem; color: var(--text-light); max-width: 800px; }

        /* --- Global Layout --- */
        section { padding: 120px 10%; min-height: 100vh; }
        .section-title { font-size: 2.8rem; font-weight: 900; text-align: center; margin-bottom: 20px; color: var(--main-navy); }
        .section-desc { text-align: center; color: var(--text-light); margin-bottom: 60px; font-size: 1.1rem; }

        /* --- Section 1: 미래 유망 직무 (Visual Cards) --- */
        .job-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 2rem; }
        .job-card {
            background: var(--soft-gray); padding: 50px 40px; border-radius: 35px;
            transition: var(--transition); border: 1px solid transparent; text-align: center;
            position: relative; overflow: hidden;
        }
        .job-card:hover { transform: translateY(-15px); background: white; border-color: var(--accent-blue); box-shadow: 0 30px 60px rgba(0,0,0,0.08); }
        .job-visual { font-size: 4.5rem; margin-bottom: 25px; display: block; filter: drop-shadow(0 10px 10px rgba(0,0,0,0.1)); }
        .job-card h3 { font-size: 1.6rem; margin-bottom: 15px; color: var(--main-navy); }
        .job-card p { font-size: 0.95rem; color: var(--text-light); margin-bottom: 20px; }
        .job-tag { display: inline-block; padding: 4px 12px; background: var(--accent-blue); color: var(--main-navy); border-radius: 10px; font-size: 0.75rem; font-weight: 800; }

        /* --- Section 2: 핵심 필수 역량 (Graphic Layout) --- */
        #skills { background-color: var(--soft-gray); }
        .skill-container { display: flex; flex-direction: column; gap: 2rem; max-width: 1000px; margin: 0 auto; }
        .skill-box {
            background: white; padding: 40px; border-radius: 30px;
            display: grid; grid-template-columns: 100px 1fr auto; align-items: center; gap: 30px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.02);
        }
        .skill-graphic { width: 100px; height: 100px; background: var(--main-navy); border-radius: 20px; display: flex; align-items: center; justify-content: center; font-size: 2.5rem; }
        .skill-info h4 { font-size: 1.5rem; margin-bottom: 10px; color: var(--main-navy); }
        .skill-info p { color: var(--text-light); }
        .skill-status { writing-mode: vertical-lr; font-weight: 900; color: var(--accent-green); letter-spacing: 2px; }

        /* --- Section 3: 나의 4년 로드맵 (Vertical Timeline) --- */
        .timeline { position: relative; max-width: 900px; margin: 0 auto; }
        .timeline::after { content: ''; position: absolute; width: 6px; background: var(--main-navy); top: 0; bottom: 0; left: 50%; margin-left: -3px; border-radius: 10px; }
        .t-container { padding: 10px 50px; position: relative; width: 50%; }
        .t-container::after { content: ''; position: absolute; width: 24px; height: 24px; right: -12px; top: 20px; background: var(--accent-green); border: 5px solid var(--main-navy); border-radius: 50%; z-index: 1; }
        .left { left: 0; }
        .right { left: 50%; }
        .right::after { left: -12px; }
        .t-card { padding: 30px; background: var(--soft-gray); border-radius: 25px; transition: 0.3s; }
        .t-card:hover { background: var(--main-navy); color: white; transform: scale(1.02); }
        .year { font-weight: 900; color: var(--accent-blue); font-size: 1.3rem; display: block; margin-bottom: 10px; }
        .t-card:hover .year { color: var(--accent-green); }

        /* --- Section 4: 학과 선택 (Iconic Grid) --- */
        #departments { background: white; }
        .dept-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 1.5rem; }
        .dept-card {
            background: var(--soft-gray); padding: 40px 20px; border-radius: 30px; text-align: center;
            border: 2px solid transparent; transition: 0.3s;
        }
        .dept-card:hover { border-color: var(--accent-green); background: white; box-shadow: 0 15px 30px rgba(0,0,0,0.05); }
        .dept-icon { font-size: 3.5rem; margin-bottom: 20px; display: block; }
        .dept-card h4 { font-size: 1.3rem; margin-bottom: 10px; color: var(--main-navy); }
        .dept-label { display: inline-block; padding: 5px 15px; background: var(--main-navy); color: white; border-radius: 50px; font-size: 0.8rem; font-weight: 700; margin-top: 15px; }

        /* --- Footer --- */
        footer { padding: 60px 10%; background: var(--main-navy); color: white; text-align: center; }

        /* --- Responsive --- */
        @media (max-width: 768px) {
            .nav-links { display: none; }
            #hero h1 { font-size: 2.5rem; }
            .skill-box { grid-template-columns: 1fr; text-align: center; justify-items: center; }
            .skill-status { writing-mode: horizontal-tb; }
            .timeline::after { left: 31px; }
            .t-container { width: 100%; padding-left: 70px; padding-right: 20px; }
            .t-container::after { left: 19px; }
            .right { left: 0; }
        }
    </style>
</head>
<body>

    <nav>
        <div class="logo">CAREER ARCHITECT</div>
        <ul class="nav-links">
            <li><a href="#jobs">미래 직무</a></li>
            <li><a href="#skills">핵심 역량</a></li>
            <li><a href="#roadmap">성장 로드맵</a></li>
            <li><a href="#departments">학과 분석</a></li>
        </ul>
    </nav>

    <header id="hero">
        <div class="hero-badge">2026 AI/SW CAREER VISION</div>
        <h1>Navigate the<br>AI Blue Ocean</h1>
        <p>단순한 개발자를 넘어 시스템을 설계(Architect)하고, 지능을 결합(Synthesis)하며, 신뢰를 방어(Vanguard)하는 인재로 성장하는 여정입니다.</p>
    </header>

    <!-- Section 1: 미래 유망 직무 -->
    <section id="jobs">
        <h2 class="section-title">Future Promising Jobs</h2>
        <p class="section-desc">가트너 선정 2026 전략 기술 기반 고연봉 블루오션 직무 [1]</p>
        <div class="job-grid">
            <div class="job-card">
                <span class="job-visual">🧬</span>
                <span class="job-tag">MAS & RAG</span>
                <h3>AI 에이전트 오케스트레이터</h3>
                <p>다중 에이전트 시스템(MAS)을 설계하고 AI 간의 협업을 조율하여 복잡한 목표를 달성하는 전문가입니다 [1].</p>
            </div>
            <div class="job-card">
                <span class="job-visual">🛰️</span>
                <span class="job-tag">LLM Ops</span>
                <h3>AI 네이티브 & LLM Ops</h3>
                <p>AI 모델을 서비스에 결합하고 벡터 DB 인프라와 실시간 검색 파이프라인을 운영하는 엔지니어입니다 [2].</p>
            </div>
            <div class="job-card">
                <span class="job-visual">⚔️</span>
                <span class="job-tag">Digital Trust</span>
                <h3>AI 보안 및 신뢰 전문가</h3>
                <p>프롬프트 인젝션 등 AI 특화 위협에 대응하고 시스템의 무결성과 데이터 신뢰를 보장합니다 [3].</p>
            </div>
        </div>
    </section>

    <!-- Section 2: 핵심 필수 역량 -->
    <section id="skills">
        <h2 class="section-title">Core Competencies</h2>
        <p class="section-desc">2026년 채용 시장이 요구하는 대체 불가능한 3가지 무기 [4]</p>
        <div class="skill-container">
            <div class="skill-box">
                <div class="skill-graphic">🧠</div>
                <div class="skill-info">
                    <h4>지능형 오케스트레이션 설계</h4>
                    <p>단순 코딩을 넘어 AI가 스스로 판단하고 행동하게 만드는 '워크플로우 설계 능력'입니다 [4].</p>
                </div>
                <div class="skill-status">HIGH DEMAND</div>
            </div>
            <div class="skill-box">
                <div class="skill-graphic">⚙️</div>
                <div class="skill-info">
                    <h4>AI 네이티브 인프라 통합</h4>
                    <p>벡터 데이터를 관리하고 서로 다른 언어 모듈 간 통신(gRPC 등)을 최적화하는 아키텍처 역량입니다 [5].</p>
                </div>
                <div class="skill-status">ESSENTIAL</div>
            </div>
            <div class="skill-box">
                <div class="skill-graphic">🛡️</div>
                <div class="skill-info">
                    <h4>디지털 신뢰(Trust) 거버넌스</h4>
                    <p>AI 응답 품질을 자동 평가하고 기밀 컴퓨팅을 통해 시스템의 안전과 신뢰를 책임지는 능력입니다 [6].</p>
                </div>
                <div class="skill-status">VANGUARD</div>
            </div>
        </div>
    </section>

    <!-- Section 3: 나의 4년 로드맵 -->
    <section id="roadmap">
        <h2 class="section-title">4-Year Growth Roadmap</h2>
        <p class="section-desc">1학년 기초부터 4학년 실전 전문가까지의 단계적 성장 가이드 [7]</p>
        <div class="timeline">
            <div class="t-container left">
                <div class="t-card">
                    <span class="year">1학년: Foundation</span>
                    <p>CS 기초 확립 및 AI 도구를 활용한 개발 생산성 극대화 경험을 쌓습니다 [8].</p>
                </div>
            </div>
            <div class="t-container right">
                <div class="t-card">
                    <span class="year">2학년: Intelligent Agent</span>
                    <p>풀스택 기술 스택을 구축하고 작업을 수행하는 '에이전트형 AI' 연동을 시작합니다 [8].</p>
                </div>
            </div>
            <div class="t-container left">
                <div class="t-card">
                    <span class="year">3학년: Orchestration</span>
                    <p>다중 에이전트 시스템(MAS) 설계 및 RAG 기반 지식 베이스 구축 역량을 확보합니다 [9].</p>
                </div>
            </div>
            <div class="t-container right">
                <div class="t-card">
                    <span class="year">4학년: Vanguard Expert</span>
                    <p>LLM Ops 파이프라인 완성 및 디지털 신뢰 보안 기술을 실전에 적용합니다 [9].</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Section 4: 학과 선택 가이드 -->
    <section id="departments">
        <h2 class="section-title">Strategic Dept. Selection</h2>
        <p class="section-desc">목표 직무에 최적화된 전공 분석 및 선택 전략 [10]</p>
        <div class="dept-grid">
            <div class="dept-card">
                <span class="dept-icon">🤖</span>
                <h4>인공지능 (AI)</h4>
                <p>에이전트 설계 및 모델 구현 최적화 [10]</p>
                <span class="dept-label">성장성 최고</span>
            </div>
            <div class="dept-card">
                <span class="dept-icon">💻</span>
                <h4>소프트웨어 (SW)</h4>
                <p>인프라 주도권 및 시스템 아키텍처 [11]</p>
                <span class="dept-label">안정적 수요</span>
            </div>
            <div class="dept-card">
                <span class="dept-icon">📊</span>
                <h4>데이터사이언스</h4>
                <p>데이터 무결성 및 RAG 최적화 [11]</p>
                <span class="dept-label">신뢰의 핵심</span>
            </div>
            <div class="dept-card">
                <span class="dept-icon">🦾</span>
                <h4>지능형 IoT</h4>
                <p>피지컬 AI 및 물리 세계 연결 [12]</p>
                <span class="dept-label">미래 개척</span>
            </div>
        </div>
        <div style="text-align: center; margin-top: 60px;">
            <p>💡 <strong>Tip:</strong> 어떤 전공이든 <strong>SW 기초</strong>와 <strong>AI 응용력</strong>을 융합하는 것이 핵심입니다 [13].</p>
        </div>
    </section>

    <footer>
        <p>© 2024 AI/SW Career Portfolio. Based on 2026 Tech Trends Analysis.</p>
    </footer>

    <script>
        // Smooth Reveal Animation on Scroll
        const observerOptions = { threshold: 0.15 };
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = "1";
                    entry.target.style.transform = "translateY(0)";
                }
            });
        }, observerOptions);

        document.querySelectorAll('.job-card, .skill-box, .t-card, .dept-card').forEach(el => {
            el.style.opacity = "0";
            el.style.transform = "translateY(40px)";
            el.style.transition = "all 0.8s ease-out";
            observer.observe(el);
        });
    </script>
</body>
</html>

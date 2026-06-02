<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <meta name="description" content="Church Building Fund Progress Tracker. Partner with us in our church building project.">
    <meta name="theme-color" content="#2c3e50">
    <meta property="og:title" content="Building Fund Progress">
    <meta property="og:description" content="Track the progress of our church building fund campaign.">
    <meta property="og:type" content="website">

    <title>Building Fund Progress</title>

    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,400;14..32,500;14..32,600;14..32,700;14..32,800&family=Playfair+Display:ital,wght@0,500;0,700;1,500&display=swap" rel="stylesheet">

    <style>
        :root {
            --deep: #1e293b;
            --soft-white: #f8fafc;
            --card-bg: #ffffff;
            --gold: #c59b27;
            --gold-light: #f3e5ab;
            --gold-dark: #8a6914;
            --accent: #e2e8f0;
            --text-secondary: #475569;
            --shadow-sm: 0 1px 3px rgba(0,0,0,0.08);
            --shadow-card: 0 20px 35px -15px rgba(0,0,0,0.1), 0 0 0 1px rgba(0,0,0,0.03);
            --radius-lg: 28px;
            --radius-xl: 36px;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: linear-gradient(135deg, #f0f4f8 0%, #e6eef5 100%);
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            font-family: 'Inter', system-ui, -apple-system, sans-serif;
            padding: 2rem;
            line-height: 1.5;
        }

        @media (prefers-reduced-motion: reduce) {
            * {
                animation-duration: 0.01ms !important;
                transition-duration: 0.01ms !important;
            }
        }

        .poster {
            max-width: 780px;
            width: 100%;
            background: var(--card-bg);
            border-radius: var(--radius-xl);
            box-shadow: var(--shadow-card);
            overflow: hidden;
            border: 1px solid rgba(255,255,255,0.8);
        }

        .gold-bar {
            height: 8px;
            background: linear-gradient(90deg, var(--gold), #e0c068, var(--gold-dark), #dbb341);
            opacity: 0.8;
        }

        .poster-content {
            padding: 2.5rem 2.8rem;
            position: relative;
        }

        .verse-tag {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            background: #f1f5f9;
            color: var(--gold-dark);
            padding: 0.3rem 1.2rem;
            border-radius: 40px;
            font-size: 0.75rem;
            font-weight: 700;
            letter-spacing: 2px;
            text-transform: uppercase;
            margin-bottom: 1.8rem;
        }
        .verse-tag::before {
            content: "⛪";
            font-size: 1rem;
        }

        h1 {
            font-family: 'Playfair Display', serif;
            font-size: clamp(2.4rem, 8vw, 3.4rem);
            font-weight: 700;
            line-height: 1.1;
            color: var(--deep);
            margin-bottom: 0.7rem;
            letter-spacing: -0.01em;
        }

        .subhead {
            font-size: 1.15rem;
            color: var(--text-secondary);
            font-weight: 500;
            margin-bottom: 2rem;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }
        .subhead::before {
            content: "";
            display: inline-block;
            width: 4px;
            height: 1.8rem;
            background: var(--gold);
            border-radius: 4px;
            margin-right: 0.7rem;
        }

        .seed-quote {
            background: #faf6ed;
            border-radius: 28px;
            padding: 1.8rem 2rem;
            margin-bottom: 2.5rem;
            font-style: italic;
            font-size: 1.2rem;
            font-weight: 500;
            color: #3b4a3b;
            position: relative;
            border: 1px solid #f1e4c2;
            box-shadow: inset 0 1px 6px #fff9eb, 0 6px 10px -6px rgba(0,0,0,0.05);
        }
        .seed-quote::before {
            content: """;
            font-size: 3rem;
            color: var(--gold);
            line-height: 1;
            position: absolute;
            top: -10px;
            left: 15px;
        }
        .seed-quote::after {
            content: """;
            font-size: 3rem;
            color: var(--gold);
            line-height: 1;
            position: absolute;
            bottom: -20px;
            right: 15px;
        }

        .progress-card, .challenge-card {
            background: #ffffff;
            border: 1px solid #e9eef3;
            border-radius: var(--radius-lg);
            padding: 2rem;
            margin-bottom: 2.5rem;
            box-shadow: var(--shadow-sm);
        }

        .percentage-badge {
            background: var(--deep);
            color: #f1e7c9;
            padding: 0.5rem 1.8rem;
            border-radius: 50px;
            font-weight: 700;
            font-size: 1.1rem;
            display: inline-block;
            margin-bottom: 1.8rem;
            letter-spacing: 0.3px;
        }

        .stats-row {
            display: flex;
            justify-content: space-between;
            gap: 1.2rem;
            margin-bottom: 2.2rem;
        }

        .stat-item {
            flex: 1;
            background: #f8fafc;
            border-radius: 28px;
            padding: 1.2rem 0.5rem;
            text-align: center;
            border: 1px solid #eef2f6;
        }

        .stat-label {
            font-size: 0.7rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            font-weight: 700;
            color: #64748b;
            margin-bottom: 0.4rem;
        }

        .stat-number {
            font-size: 1.8rem;
            font-weight: 800;
            color: var(--deep);
            letter-spacing: -0.5px;
        }

        .graph-container {
            margin: 1.2rem 0 1rem;
        }

        .progress-bar-bg {
            background: #eaf0f6;
            border-radius: 100px;
            height: 32px;
            overflow: hidden;
            box-shadow: inset 0 1px 4px rgba(0,0,0,0.08);
        }

        .progress-fill {
            width: 0%;
            height: 100%;
            border-radius: 100px;
            display: flex;
            align-items: center;
            justify-content: flex-end;
            padding-right: 18px;
            font-weight: 700;
            font-size: 0.8rem;
            transition: width 0.7s cubic-bezier(0.4, 0, 0.2, 1), background 0.3s;
            box-shadow: 0 0 8px rgba(0,0,0,0.15) inset;
        }

        .progress-fill span {
            background: rgba(255,255,255,0.85);
            padding: 0.2rem 0.8rem;
            border-radius: 60px;
            font-weight: 700;
            font-size: 0.7rem;
            letter-spacing: 0.4px;
            color: #1e293b;
        }

        .progress-stats-note {
            display: flex;
            justify-content: space-between;
            margin-top: 0.6rem;
            font-size: 0.85rem;
            font-weight: 500;
            color: #526477;
        }

        .milestone-info {
            margin-top: 1.5rem;
            background: #f1f8f1;
            border-left: 5px solid var(--gold);
            padding: 1rem 1.4rem;
            border-radius: 20px;
            font-size: 0.95rem;
            color: #2d472d;
            font-weight: 500;
            display: flex;
            align-items: center;
            flex-wrap: wrap;
            gap: 0.5rem;
        }
        .milestone-info strong {
            color: #1e4620;
        }
        .milestone-badge {
            background: white;
            border: 1px solid var(--gold);
            color: var(--gold-dark);
            font-weight: 700;
            padding: 0.2rem 0.9rem;
            border-radius: 40px;
            font-size: 0.8rem;
        }

        .cta-section {
            text-align: center;
            margin-bottom: 2rem;
        }
        .cta-title {
            font-family: 'Playfair Display', serif;
            font-size: 1.6rem;
            font-weight: 700;
            color: var(--deep);
            background: linear-gradient(to right, #f9f3e0, #fff6eb);
            display: inline-block;
            padding: 0.5rem 2.2rem;
            border-radius: 60px;
            margin-bottom: 0.8rem;
            border: 1px solid #f3e3b8;
        }

        .bank-details {
            background: var(--deep);
            border-radius: 28px;
            padding: 2rem;
            color: #ecdfbb;
            margin-bottom: 2rem;
        }

        .bank-name {
            font-size: 1.8rem;
            font-weight: 800;
            color: #f5d772;
            margin-bottom: 1.2rem;
            letter-spacing: -0.3px;
        }

        .detail-row {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            padding: 0.7rem 0;
            border-bottom: 1px dashed #616e7c;
        }

        .detail-label {
            font-weight: 700;
            min-width: 120px;
            color: #cbd5e1;
        }

        .detail-value {
            font-family: 'Fira Code', 'Courier New', monospace;
            font-weight: 500;
            letter-spacing: 0.4px;
        }

        .ref-highlight {
            background: rgba(255,255,255,0.08);
            padding: 0.2rem 1rem;
            border-radius: 50px;
            font-weight: 700;
        }

        .contact {
            text-align: center;
            background: #f1f5f9;
            padding: 1.2rem;
            border-radius: 60px;
            font-weight: 500;
            color: #1e293b;
        }

        .contact a {
            color: #b0721a;
            font-weight: 700;
            text-decoration: none;
            transition: opacity 0.2s;
        }

        .contact a:hover {
            opacity: 0.8;
        }

        .footer-note {
            text-align: center;
            margin-top: 2rem;
            font-size: 0.8rem;
            color: #8897a8;
            border-top: 1px solid #e2e8f0;
            padding-top: 1.5rem;
        }

        /* pie chart and legend */
        .pie-chart-container {
            display: flex;
            flex-direction: column;
            align-items: center;
            margin-top: 2rem;
        }
        .pie-chart-svg {
            width: 200px;
            height: 200px;
            max-width: 100%;
            margin-bottom: 1rem;
        }
        .legend {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 1.2rem;
            font-size: 0.9rem;
            font-weight: 500;
            color: #1e293b;
        }
        .legend-item {
            display: flex;
            align-items: center;
            gap: 0.4rem;
        }
        .legend-color {
            width: 12px;
            height: 12px;
            border-radius: 4px;
        }

        @media (max-width: 768px) {
            .poster-content {
                padding: 1.8rem 1.5rem;
            }
            .stats-row {
                flex-direction: column;
            }
        }
        @media (max-width: 500px) {
            .poster-content {
                padding: 1.2rem;
            }
            h1 {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>
<div class="poster">
    <div class="gold-bar"></div>
    <div class="poster-content">
        <div class="verse-tag">Building for Breakthrough</div>
        <h1>BUILDING<br>FOR BREAKTHROUGH</h1>
        <div class="subhead">Partner with us — Sowing into a greater shelter</div>

        <div class="seed-quote">
            From a small seed, a greater shelter is built.
        </div>

        <!-- PROGRESS CARD – MEMBER PLEDGES (unchanged) -->
        <div class="progress-card">
            <div style="text-align: center;">
                <span class="percentage-badge">📈 MEMBERS GIVING PROGRESS</span>
            </div>
            <div class="stats-row">
                <div class="stat-item">
                    <div class="stat-label">🎯 Total Target (Members)</div>
                    <div class="stat-number" id="target-amount">R59,500</div>
                </div>
                <div class="stat-item">
                    <div class="stat-label">💰 Raised So Far</div>
                    <div class="stat-number" id="raised-amount">R8,850</div>
                </div>
                <div class="stat-item">
                    <div class="stat-label">📊 Completion</div>
                    <div class="stat-number" id="completion-percent">14.87%</div>
                </div>
            </div>

            <div class="graph-container">
                <div class="progress-bar-bg">
                    <div class="progress-fill" id="progress-bar" style="width: 14.87%;">
                        <span id="progress-text">14.87%</span>
                    </div>
                </div>
                <div class="progress-stats-note">
                    <span>⛁ Starting point</span>
                    <span id="remaining-text" style="font-weight:700;">⛭ R50,650 remaining</span>
                </div>
            </div>

            <div class="milestone-info" id="milestone-box">
                ✅ <strong>Faithful step:</strong> <span id="milestone-raised">R8,850</span> raised
                &nbsp;•&nbsp; <span class="milestone-badge" id="next-milestone">Next: 20%</span>
                &nbsp;•&nbsp; keep praying and giving
            </div>
        </div>

        <!-- NEW SECTION: JJ & JD CHALLENGE -->
        <div class="challenge-card" id="challenge-card">
            <div style="text-align: center;">
                <span class="percentage-badge" style="background:#2d472d;">🔥 JJ & JD CHALLENGE</span>
            </div>
            <div class="stats-row">
                <div class="stat-item">
                    <div class="stat-label">🌟 JD Group (Jul–Dec)</div>
                    <div class="stat-number" id="jd-amount">R4,500</div>
                </div>
                <div class="stat-item">
                    <div class="stat-label">🌟 JJ Group (Jan–Jun)</div>
                    <div class="stat-number" id="jj-amount">R3,000</div>
                </div>
                <div class="stat-item">
                    <div class="stat-label">💰 Combined Raised</div>
                    <div class="stat-number" id="challenge-raised">R7,500</div>
                </div>
            </div>

            <div class="graph-container">
                <div class="progress-bar-bg">
                    <div class="progress-fill" id="challenge-progress-bar" style="width: 25%;">
                        <span id="challenge-progress-text">25%</span>
                    </div>
                </div>
                <div class="progress-stats-note">
                    <span>🎯 Combined Target: <strong id="challenge-target">R30,000</strong></span>
                    <span id="challenge-remaining-text" style="font-weight:700;">⛭ R22,500 to go</span>
                </div>
            </div>

            <!-- Pie chart showing TOTAL raised from all sources -->
            <div class="pie-chart-container">
                <div style="font-weight:700; color:#1e293b; margin-bottom:0.5rem;">TOTAL RAISED SO FAR</div>
                <svg viewBox="0 0 200 200" class="pie-chart-svg" aria-label="Pie chart of total raised funds">
                    <circle cx="100" cy="100" r="80" fill="#f0f4f8" />
                    <!-- slices will be drawn by JavaScript -->
                    <path id="slice-members" fill="#c59b27" d="" />
                    <path id="slice-jd" fill="#4a90e2" d="" />
                    <path id="slice-jj" fill="#2a9d8f" d="" />
                    <circle cx="100" cy="100" r="45" fill="white" />
                    <text x="100" y="96" text-anchor="middle" font-weight="800" font-size="14" fill="#1e293b">TOTAL</text>
                    <text x="100" y="114" text-anchor="middle" font-weight="700" font-size="14" fill="#c59b27" id="pie-total-text">R16,350</text>
                </svg>
                <div class="legend">
                    <div class="legend-item"><span class="legend-color" style="background:#c59b27;"></span> Pledged Members</div>
                    <div class="legend-item"><span class="legend-color" style="background:#4a90e2;"></span> JD Group</div>
                    <div class="legend-item"><span class="legend-color" style="background:#2a9d8f;"></span> JJ Group</div>
                </div>
            </div>
        </div>

        <!-- partner CTA (unchanged) -->
        <div class="cta-section">
            <div class="cta-title">🤝 PARTNER WITH US</div>
            <div style="font-weight:500; color:#475569;">IN AID OF CHURCH BUILDING</div>
        </div>

        <div class="bank-details">
            <div class="bank-name">Standard Bank</div>
            <div class="detail-row">
                <span class="detail-label">ACC NUMBER:</span>
                <span class="detail-value" id="account-number">1021 9863 030</span>
            </div>
            <div class="detail-row">
                <span class="detail-label">REFERENCE:</span>
                <span class="detail-value ref-highlight" id="reference">BUILDING FUND/YOUR NAME</span>
            </div>
            <div style="font-size:0.75rem; margin-top:1rem; color:#cccbb5; text-align:center;">
                *Pledged offerings from church members — every seed counts
            </div>
        </div>

        <div class="contact">
            📞 FOR MORE INFO &nbsp;|&nbsp;
            <a href="tel:+27704246429">+27 70 424 6429</a>
        </div>

        <div class="footer-note">
            "From a small seed, a greater shelter is built." <br>
            Building for His Glory ✝️
        </div>
    </div>
    <div class="gold-bar" style="height:5px;"></div>
</div>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "name": "Church Building Fund",
  "description": "Building Fund Campaign - Partner with us in our church building project",
  "url": "https://github.com/LetsoFilm/Contribution-update",
  "contactPoint": {
    "@type": "ContactPoint",
    "telephone": "+27-70-424-6429",
    "contactType": "General Information"
  }
}
</script>

<script>
    // *************************************************************
    //   UPDATE THESE VALUES TO REFLECT THE LATEST CONTRIBUTIONS
    // *************************************************************
    const FUND_DATA = {
        target: 59500,                // members pledged target
        raised: 40000,                // members pledged raised so far
        contact: "+27704246429",
        accountNumber: "1021 9863 030",
        reference: "BUILDING FUND",
        milestones: [20, 40, 60, 80, 100]   // percentage milestones
    };

    // New data for JJ & JD challenge
    const CHALLENGE_DATA = {
        target: 20000,       // combined target for JJ & JD
        raised: 7500,        // current combined raised (JD+JJ)
        jd: 4500,            // JD group raised
        jj: 3000             // JJ group raised
    };

    function formatCurrency(amount) {
        return `R${amount.toLocaleString('en-ZA', { maximumFractionDigits: 0 })}`;
    }

    function getProgressColors(percentage) {
        if (percentage <= 30) return { bg: '#dc3545', text: '#ffffff' };
        if (percentage <= 60) return { bg: '#fd7e14', text: '#ffffff' };
        if (percentage <= 90) return { bg: '#ffc107', text: '#1e293b' };
        return { bg: '#28a745', text: '#ffffff' };
    }

    function getNextMilestone(percentage, milestones) {
        const sorted = milestones.slice().sort((a,b) => a - b);
        for (let m of sorted) {
            if (m > percentage) return m;
        }
        return null;
    }

    // Draw pie chart slices using SVG arcs
    function updatePieChart(membersRaised, jdRaised, jjRaised) {
        const total = membersRaised + jdRaised + jjRaised;
        if (total === 0) return;

        const angle = (value) => (value / total) * 360;
        let startAngle = 0;

        const sliceMembers = angle(membersRaised);
        const sliceJD = angle(jdRaised);
        const sliceJJ = angle(jjRaised);

        const slices = [
            { id: 'slice-members', value: membersRaised, color: '#c59b27', start: 0, end: sliceMembers },
            { id: 'slice-jd', value: jdRaised, color: '#4a90e2', start: sliceMembers, end: sliceMembers + sliceJD },
            { id: 'slice-jj', value: jjRaised, color: '#2a9d8f', start: sliceMembers + sliceJD, end: sliceMembers + sliceJD + sliceJJ }
        ];

        function describeArc(cx, cy, r, startAngle, endAngle) {
            const startRad = (startAngle - 90) * Math.PI / 180;
            const endRad = (endAngle - 90) * Math.PI / 180;
            const x1 = cx + r * Math.cos(startRad);
            const y1 = cy + r * Math.sin(startRad);
            const x2 = cx + r * Math.cos(endRad);
            const y2 = cy + r * Math.sin(endRad);
            const largeArc = (endAngle - startAngle) > 180 ? 1 : 0;
            return `M ${cx} ${cy} L ${x1} ${y1} A ${r} ${r} 0 ${largeArc} 1 ${x2} ${y2} Z`;
        }

        slices.forEach(s => {
            const path = document.getElementById(s.id);
            if (path) {
                path.setAttribute('d', describeArc(100, 100, 80, s.start, s.end));
                path.setAttribute('fill', s.color);
            }
        });

        document.getElementById('pie-total-text').textContent = formatCurrency(total);
    }

    function updateProgress() {
        // ----- members section (unchanged logic) -----
        const membersPerc = (FUND_DATA.raised / FUND_DATA.target) * 100;
        const percRounded = membersPerc.toFixed(2);
        const remaining = FUND_DATA.target - FUND_DATA.raised;
        const colors = getProgressColors(membersPerc);

        document.getElementById('target-amount').textContent = formatCurrency(FUND_DATA.target);
        document.getElementById('raised-amount').textContent = formatCurrency(FUND_DATA.raised);
        document.getElementById('completion-percent').textContent = `${percRounded}%`;
        document.getElementById('remaining-text').innerHTML = `⛭ ${formatCurrency(remaining)} remaining`;
        document.getElementById('milestone-raised').textContent = formatCurrency(FUND_DATA.raised);
        document.getElementById('account-number').textContent = FUND_DATA.accountNumber;
        document.getElementById('reference').textContent = FUND_DATA.reference;

        const bar = document.getElementById('progress-bar');
        const barText = document.getElementById('progress-text');
        bar.style.width = `${percRounded}%`;
        bar.style.background = colors.bg;
        bar.style.color = colors.text;
        barText.textContent = `${percRounded}%`;

        const next = getNextMilestone(membersPerc, FUND_DATA.milestones);
        const milestoneEl = document.getElementById('next-milestone');
        if (next !== null) {
            milestoneEl.textContent = `Next: ${next}%`;
        } else {
            milestoneEl.textContent = 'Goal reached! 🎉';
        }

        if (membersPerc >= 100) {
            document.getElementById('milestone-box').innerHTML =
                `🎉 <strong>Praise God!</strong> We have reached our building fund target! Thank you for every seed sown.`;
        }

        // ----- JJ & JD challenge section -----
        const challengePerc = (CHALLENGE_DATA.raised / CHALLENGE_DATA.target) * 100;
        const challengePercRounded = challengePerc.toFixed(1);
        const challengeRemaining = CHALLENGE_DATA.target - CHALLENGE_DATA.raised;
        const challengeColors = getProgressColors(challengePerc);

        document.getElementById('jd-amount').textContent = formatCurrency(CHALLENGE_DATA.jd);
        document.getElementById('jj-amount').textContent = formatCurrency(CHALLENGE_DATA.jj);
        document.getElementById('challenge-raised').textContent = formatCurrency(CHALLENGE_DATA.raised);
        document.getElementById('challenge-target').textContent = formatCurrency(CHALLENGE_DATA.target);
        document.getElementById('challenge-remaining-text').innerHTML = `⛭ ${formatCurrency(challengeRemaining)} to go`;

        const challengeBar = document.getElementById('challenge-progress-bar');
        const challengeBarText = document.getElementById('challenge-progress-text');
        challengeBar.style.width = `${challengePercRounded}%`;
        challengeBar.style.background = challengeColors.bg;
        challengeBar.style.color = challengeColors.text;
        challengeBarText.textContent = `${challengePercRounded}%`;

        // ----- combined pie chart (all raised funds) -----
        updatePieChart(FUND_DATA.raised, CHALLENGE_DATA.jd, CHALLENGE_DATA.jj);
    }

    document.addEventListener('DOMContentLoaded', updateProgress);
</script>
</body>
</html>

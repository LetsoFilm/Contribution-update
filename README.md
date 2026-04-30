<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <meta name="description" content="Church Building Fund Progress Tracker. Partner with us in our church building project.">
    <meta name="theme-color" content="#1a1a1a">
    <meta property="og:title" content="Building Fund Progress">
    <meta property="og:description" content="Track the progress of our church building fund campaign.">
    <meta property="og:type" content="website">
    
    <title>Building Fund Progress</title>
    
    <style>
        :root {
            --gold-primary: #d4af37;
            --gold-light: #f3e5ab;
            --gold-dark: #b88c2e;
            --dark-bg: #1a1a1a;
            --dark-text: #1e2a2f;
            --light-bg: #fef7e6;
            --cream: #fff4e0;
            --white: #ffffff;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: var(--dark-bg);
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            font-family: 'Segoe UI', 'Poppins', 'Montserrat', system-ui, -apple-system, BlinkMacSystemFont, 'Roboto', sans-serif;
            padding: clamp(1rem, 5vw, 24px);
        }

        /* Reduce motion for accessibility */
        @media (prefers-reduced-motion: reduce) {
            * {
                animation-duration: 0.01ms !important;
                animation-iteration-count: 1 !important;
                transition-duration: 0.01ms !important;
            }
        }

        /* POSTER CARD */
        .poster {
            max-width: 780px;
            width: 100%;
            background: linear-gradient(145deg, var(--light-bg) 0%, var(--cream) 100%);
            border-radius: 48px 32px 48px 32px;
            box-shadow: 0 30px 40px rgba(0, 0, 0, 0.25), 0 0 0 1px rgba(212, 175, 55, 0.3);
            overflow: hidden;
            transition: transform 0.2s ease;
        }

        /* decorative golden border top */
        .gold-bar {
            height: 12px;
            background: linear-gradient(90deg, var(--gold-primary), var(--gold-light), var(--gold-dark), var(--gold-primary));
        }

        /* content padding */
        .poster-content {
            padding: clamp(1.5rem, 4vw, 2rem) 2rem clamp(1.5rem, 4vw, 2.2rem);
        }

        /* header section */
        .verse-tag {
            text-transform: uppercase;
            letter-spacing: 3px;
            font-size: 0.75rem;
            font-weight: 600;
            color: var(--gold-dark);
            background: rgba(184, 140, 46, 0.1);
            display: inline-block;
            padding: 4px 14px;
            border-radius: 40px;
            margin-bottom: 20px;
        }

        h1 {
            font-size: clamp(2rem, 8vw, 3rem);
            font-weight: 800;
            line-height: 1.15;
            color: var(--dark-text);
            letter-spacing: -0.02em;
            margin-bottom: 12px;
        }

        .subhead {
            font-size: clamp(1rem, 2.5vw, 1.2rem);
            font-weight: 500;
            color: #7c6b3c;
            border-left: 4px solid var(--gold-primary);
            padding-left: 18px;
            margin-bottom: 28px;
        }

        .church-name {
            background: var(--dark-text);
            color: #f9eec1;
            display: inline-block;
            padding: 8px 20px;
            border-radius: 60px;
            font-weight: 600;
            font-size: 0.9rem;
            letter-spacing: 0.5px;
            margin-bottom: 28px;
            box-shadow: 0 2px 6px rgba(0,0,0,0.1);
        }

        /* QUOTE */
        .seed-quote {
            font-size: clamp(1rem, 2vw, 1.2rem);
            font-style: italic;
            background: #fff9ef;
            padding: 20px 24px;
            border-radius: 48px 16px 48px 16px;
            margin-bottom: 32px;
            color: #2b3b2c;
            font-weight: 500;
            box-shadow: inset 0 1px 4px #ffeecc, 0 8px 12px -8px rgba(0,0,0,0.1);
            border: 1px solid #f7e5c2;
        }

        .seed-quote::before {
            content: """;
            font-size: 2rem;
            color: var(--gold-primary);
            line-height: 1;
            margin-right: 6px;
            vertical-align: middle;
        }

        .seed-quote::after {
            content: """;
            font-size: 2rem;
            color: var(--gold-primary);
            line-height: 1;
            vertical-align: bottom;
            margin-left: 4px;
        }

        /* PROGRESS SECTION — GRAPH */
        .progress-card {
            background: var(--white);
            border-radius: 36px;
            padding: 1.5rem;
            margin-bottom: 32px;
            box-shadow: 0 12px 22px -12px rgba(0, 0, 0, 0.2);
            border: 1px solid #eeddb0;
        }

        .stats-row {
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 20px;
            margin-bottom: 24px;
        }

        .stat-item {
            flex: 1;
            min-width: 150px;
            text-align: center;
            background: #faf6ea;
            padding: 10px 12px;
            border-radius: 34px;
        }

        .stat-label {
            font-size: 0.75rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            font-weight: 600;
            color: #7a6a42;
        }

        .stat-number {
            font-size: clamp(1.3rem, 4vw, 1.9rem);
            font-weight: 800;
            color: var(--dark-text);
            line-height: 1.2;
            word-break: break-word;
        }

        .stat-number small {
            font-size: 0.9rem;
            font-weight: 500;
        }

        .percentage-badge {
            background: var(--dark-text);
            color: #f3e0a8;
            border-radius: 60px;
            padding: 8px 20px;
            font-weight: 700;
            font-size: clamp(1rem, 2vw, 1.5rem);
            text-align: center;
            display: inline-block;
            width: auto;
        }

        /* PROGRESS BAR (GRAPH VISUAL) */
        .graph-container {
            margin: 20px 0 10px;
        }

        .progress-bar-bg {
            background-color: #e9e0ce;
            border-radius: 60px;
            height: 36px;
            overflow: hidden;
            box-shadow: inset 0 1px 4px rgba(0,0,0,0.1);
        }

        .progress-fill {
            background: linear-gradient(90deg, #c7a43b, #e3c26f, #d6af4b);
            width: 0%;
            height: 100%;
            border-radius: 60px;
            display: flex;
            align-items: center;
            justify-content: flex-end;
            padding-right: 16px;
            color: #2a2418;
            font-weight: bold;
            font-size: 0.9rem;
            transition: width 0.6s ease-out;
            box-shadow: inset 0 0 2px rgba(255,255,200,0.8);
        }

        .progress-fill span {
            background: rgba(0,0,0,0.5);
            backdrop-filter: blur(2px);
            padding: 0 8px;
            border-radius: 40px;
            color: white;
            font-size: 0.75rem;
            letter-spacing: 0.5px;
        }

        .progress-stats-note {
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 10px;
            margin-top: 10px;
            font-weight: 500;
            font-size: 0.8rem;
            color: #5c4e2b;
        }

        .target-track {
            font-weight: 700;
            color: #2f4f36;
        }

        .milestone-info {
            margin-top: 18px;
            background: #f9efda;
            border-radius: 28px;
            padding: 12px 16px;
            font-size: 0.85rem;
            text-align: center;
            color: #4f3f1c;
        }

        /* CALL TO ACTION */
        .cta-title {
            font-size: clamp(1.2rem, 2.5vw, 1.5rem);
            font-weight: 700;
            color: var(--gold-primary);
            text-shadow: 0 1px 0 var(--dark-text);
            background: var(--dark-text);
            display: inline-block;
            padding: 6px 28px;
            border-radius: 60px;
            margin-bottom: 18px;
            letter-spacing: -0.2px;
        }

        .bank-details {
            background: var(--dark-text);
            border-radius: 28px;
            padding: 20px;
            color: #f5ebd2;
            margin-bottom: 28px;
        }

        .bank-name {
            font-size: clamp(1.3rem, 4vw, 1.7rem);
            font-weight: 800;
            letter-spacing: -0.5px;
            color: #f7d96b;
            margin-bottom: 12px;
        }

        .detail-row {
            font-size: 1rem;
            padding: 8px 0;
            border-bottom: 1px dashed #d4af3744;
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
        }

        .detail-label {
            font-weight: 600;
            min-width: 100px;
            color: #eedb9b;
        }

        .detail-value {
            font-weight: 500;
            font-family: monospace;
            letter-spacing: 0.5px;
        }

        .ref-highlight {
            background: #00000033;
            padding: 4px 12px;
            border-radius: 40px;
            font-weight: 700;
        }

        .contact {
            text-align: center;
            margin-top: 18px;
            font-size: 1rem;
            font-weight: 500;
            background: #fcf3e2;
            padding: 14px;
            border-radius: 50px;
            color: #2d3a3a;
        }

        .contact a {
            color: #b0721a;
            text-decoration: none;
            font-weight: 700;
            transition: opacity 0.2s ease;
        }

        .contact a:hover,
        .contact a:focus {
            opacity: 0.8;
            outline: 2px solid #b0721a;
            outline-offset: 2px;
            border-radius: 4px;
        }

        .contact a:focus {
            outline: 2px solid #b0721a;
        }

        .footer-note {
            text-align: center;
            margin-top: 24px;
            font-size: 0.7rem;
            color: #a79062;
            border-top: 1px solid #eedbba;
            padding-top: 18px;
        }

        .loading-spinner {
            display: inline-block;
            animation: spin 1s linear infinite;
        }

        @keyframes spin {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        @media (max-width: 768px) {
            .poster-content {
                padding: 1.5rem;
            }
            .stats-row {
                flex-direction: column;
            }
            .stat-item {
                min-width: auto;
            }
            .progress-stats-note {
                flex-direction: column;
                gap: 8px;
            }
        }

        @media (max-width: 550px) {
            .poster-content {
                padding: 1rem;
            }
            h1 {
                font-size: 1.8rem;
            }
            .stat-number {
                font-size: 1.3rem;
            }
            .bank-name {
                font-size: 1.2rem;
            }
        }

        @media print {
            body {
                background: white;
                padding: 0;
            }
            .poster {
                box-shadow: none;
                max-width: 100%;
            }
            .progress-fill {
                background: var(--gold-dark);
            }
        }
    </style>
</head>
<body>
<div class="poster">
    <div class="gold-bar"></div>
    <div class="poster-content">
        <!-- header -->
        <div class="verse-tag">#BUILDING FOR BREAKTHROUGH</div>
        <h1>BUILDING<br>FOR BREAKTHROUGH</h1>
        <div class="subhead">Partner with us — Sowing into a greater shelter</div>

        <!-- inspirational quote -->
        <div class="seed-quote">
            FROM A SMALL SEED, A GREATER SHELTER IS BUILT.
        </div>

        <!-- ========== UPDATE GRAPH SECTION (PROGRESS TOWARDS TARGET) ========= -->
        <div class="progress-card">
            <div style="text-align: center; margin-bottom: 16px;">
                <span class="percentage-badge">📈 MEMBERS GIVING PROGRESS</span>
            </div>
            <div class="stats-row">
                <div class="stat-item">
                    <div class="stat-label">🎯 TOTAL TARGET (MEMBERS)</div>
                    <div class="stat-number" id="target-amount">R59,500</div>
                </div>
                <div class="stat-item">
                    <div class="stat-label">💰 RAISED SO FAR</div>
                    <div class="stat-number" id="raised-amount">R8,850</div>
                </div>
                <div class="stat-item">
                    <div class="stat-label">📊 COMPLETION</div>
                    <div class="stat-number" id="completion-percent">14.87%</div>
                </div>
            </div>

            <!-- GRAPH : PROGRESS BAR VISUAL -->
            <div class="graph-container">
                <div class="progress-bar-bg">
                    <div class="progress-fill" id="progress-bar" style="width: 14.87%;">
                        <span id="progress-text">14.87%</span>
                    </div>
                </div>
                <div class="progress-stats-note">
                    <span>⛁ Starting point</span>
                    <span class="target-track" id="remaining-text">⛭ R50,650 remaining to reach goal</span>
                </div>
            </div>

            <!-- brief description of the milestone -->
            <div class="milestone-info">
                ✅ <strong>Faithful step:</strong> <span id="milestone-raised">R8,850</span> raised &nbsp;•&nbsp; Next milestone: 30% &nbsp;•&nbsp; keep praying and giving
            </div>
        </div>

        <!-- partner call + banking -->
        <div style="text-align: center;">
            <div class="cta-title">🤝 PARTNER WITH US</div>
            <div style="font-size: 1rem; font-weight: 500; margin-bottom: 16px; color: #4d3a1b;">
                IN AID OF CHURCH BUILDING
            </div>
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
            <div style="font-size: 0.75rem; margin-top: 12px; color: #e2cf9a; text-align: center;">
                *Pledged offerings from church members — every seed counts
            </div>
        </div>

        <div class="contact">
            📞 FOR MORE INFO &nbsp;|&nbsp; 
            <a href="tel:+27704246429" aria-label="Call us at +27 70 424 6429">+27 70 424 6429</a>
        </div>

        <div class="footer-note">
            "From a small seed, a greater shelter is built." <br>
            Building for His Glory ✝️
        </div>
    </div>
    <div class="gold-bar" style="height: 6px;"></div>
</div>

<!-- Rich schema markup for SEO -->
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

<!-- Dynamic Progress Update Script -->
<script>
// Configuration: Update these values to automatically refresh the progress
const FUND_DATA = {
    target: 59500,
    raised: 14850,
    contact: 
        "+27704246429",
    accountNumber: "1021 9863 030",
    reference: "BUILDING FUND"
};

/**
 * Formats currency to South African Rand format
 * @param {number} amount 
 * @returns {string}
 */
function formatCurrency(amount) {
    return `R${amount.toLocaleString('en-ZA', { maximumFractionDigits: 0 })}`;
}

/**
 * Calculates and updates progress
 */
function updateProgress() {
    const percentage = ((FUND_DATA.raised / FUND_DATA.target) * 100).toFixed(2);
    const remaining = FUND_DATA.target - FUND_DATA.raised;

    // Update DOM elements with calculated values
    document.getElementById('target-amount').textContent = formatCurrency(FUND_DATA.target);
    document.getElementById('raised-amount').textContent = formatCurrency(FUND_DATA.raised);
    document.getElementById('completion-percent').textContent = `${percentage}%`;
    document.getElementById('progress-bar').style.width = `${percentage}%`;
    document.getElementById('progress-text').textContent = `${percentage}%`;
    document.getElementById('remaining-text').textContent = `⛭ ${formatCurrency(remaining)} remaining to reach goal`;
    document.getElementById('milestone-raised').textContent = formatCurrency(FUND_DATA.raised);
    document.getElementById('account-number').textContent = FUND_DATA.accountNumber;
    document.getElementById('reference').textContent = FUND_DATA.reference;
}

// Initialize on page load
document.addEventListener('DOMContentLoaded', updateProgress);

/**
 * Optional: Fetch data from external JSON file
 * Uncomment to use: Create a 'data.json' file in the same directory
 */
// fetch('data.json')
//     .then(response => response.json())
//     .then(data => {
//         Object.assign(FUND_DATA, data);
//         updateProgress();
//     })
//     .catch(error => console.log('Using default data:', error));
</script>
</body>
</html>

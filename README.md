# Akil-X-Plus-Jarvis-
Jarvis Ai Assistant App




<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Akil X Plus | JARVIS AI</title>

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            min-height: 100vh;
            font-family: Arial, Helvetica, sans-serif;
            color: white;
            background:
                radial-gradient(circle at 20% 20%, #7c3aed 0, transparent 35%),
                radial-gradient(circle at 80% 80%, #06b6d4 0, transparent 35%),
                linear-gradient(135deg, #050816, #0f172a 50%, #111827);
            overflow-x: hidden;
        }

        /* Animated background */
        .orb {
            position: fixed;
            width: 250px;
            height: 250px;
            border-radius: 50%;
            filter: blur(10px);
            opacity: 0.25;
            animation: float 8s infinite ease-in-out;
            z-index: -1;
        }

        .orb.one {
            background: #8b5cf6;
            top: 5%;
            left: 5%;
        }

        .orb.two {
            background: #06b6d4;
            right: 5%;
            bottom: 10%;
            animation-delay: 2s;
        }

        @keyframes float {
            0%, 100% {
                transform: translateY(0) scale(1);
            }
            50% {
                transform: translateY(-35px) scale(1.1);
            }
        }

        header {
            width: 100%;
            padding: 25px 7%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: relative;
            z-index: 10;
        }

        .logo {
            font-size: 25px;
            font-weight: 800;
            letter-spacing: 1px;
        }

        .logo span {
            color: #a78bfa;
        }

        .status {
            padding: 9px 16px;
            border: 1px solid rgba(255,255,255,.15);
            background: rgba(255,255,255,.07);
            backdrop-filter: blur(15px);
            border-radius: 30px;
            font-size: 13px;
        }

        .status::before {
            content: "";
            display: inline-block;
            width: 8px;
            height: 8px;
            background: #22c55e;
            border-radius: 50%;
            margin-right: 7px;
            box-shadow: 0 0 12px #22c55e;
        }

        .hero {
            min-height: 85vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 40px 20px 80px;
        }

        .glass-card {
            width: min(950px, 100%);
            padding: 55px;
            text-align: center;
            border: 1px solid rgba(255,255,255,.15);
            background: rgba(255,255,255,.075);
            backdrop-filter: blur(25px);
            -webkit-backdrop-filter: blur(25px);
            border-radius: 35px;
            box-shadow:
                0 30px 100px rgba(0,0,0,.45),
                inset 0 1px 1px rgba(255,255,255,.15);
            transform-style: preserve-3d;
            animation: cardFloat 5s infinite ease-in-out;
        }

        @keyframes cardFloat {
            0%, 100% {
                transform: perspective(1200px) rotateX(0deg) rotateY(0deg);
            }
            50% {
                transform: perspective(1200px) rotateX(2deg) rotateY(-2deg);
            }
        }

        .ai-orb {
            width: 115px;
            height: 115px;
            margin: 0 auto 30px;
            border-radius: 50%;
            background:
                radial-gradient(circle at 35% 30%, #ffffff, #a78bfa 20%, #7c3aed 45%, #06b6d4 80%);
            box-shadow:
                0 0 35px #8b5cf6,
                0 0 80px rgba(6,182,212,.4);
            animation: pulse 3s infinite ease-in-out;
        }

        @keyframes pulse {
            0%, 100% {
                transform: scale(1);
                box-shadow: 0 0 35px #8b5cf6;
            }
            50% {
                transform: scale(1.08);
                box-shadow: 0 0 65px #8b5cf6;
            }
        }

        h1 {
            font-size: clamp(42px, 8vw, 78px);
            line-height: 1;
            margin-bottom: 18px;
            background: linear-gradient(90deg, #fff, #c4b5fd, #67e8f9);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .subtitle {
            color: #cbd5e1;
            font-size: 19px;
            max-width: 650px;
            margin: 0 auto 30px;
            line-height: 1.7;
        }

        .price {
            font-size: 38px;
            font-weight: 800;
            margin: 25px 0;
        }

        .price small {
            font-size: 15px;
            color: #94a3b8;
            font-weight: normal;
        }

        .features {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 15px;
            margin: 35px 0;
        }

        .feature {
            padding: 20px 12px;
            border-radius: 18px;
            background: rgba(255,255,255,.06);
            border: 1px solid rgba(255,255,255,.1);
            transition: .3s;
        }

        .feature:hover {
            transform: translateY(-6px);
            background: rgba(255,255,255,.11);
            border-color: rgba(167,139,250,.5);
        }

        .icon {
            font-size: 27px;
            margin-bottom: 10px;
        }

        .feature strong {
            display: block;
            margin-bottom: 5px;
        }

        .feature span {
            color: #94a3b8;
            font-size: 13px;
        }

        .whatsapp {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            padding: 16px 30px;
            border-radius: 15px;
            color: white;
            background: linear-gradient(135deg, #25D366, #128C7E);
            text-decoration: none;
            font-weight: 800;
            font-size: 16px;
            box-shadow: 0 12px 35px rgba(37,211,102,.25);
            transition: .3s;
        }

        .whatsapp:hover {
            transform: translateY(-4px) scale(1.02);
            box-shadow: 0 18px 45px rgba(37,211,102,.4);
        }

        .whatsapp-icon {
            font-size: 22px;
        }

        .contact {
            margin-top: 22px;
            color: #94a3b8;
            font-size: 14px;
        }

        .limitations {
            margin-top: 35px;
            padding: 18px;
            text-align: left;
            border-radius: 16px;
            background: rgba(245,158,11,.07);
            border: 1px solid rgba(245,158,11,.15);
            color: #cbd5e1;
            font-size: 13px;
            line-height: 1.6;
        }

        footer {
            text-align: center;
            padding: 25px;
            color: #64748b;
            font-size: 13px;
        }

        @media (max-width: 700px) {
            .glass-card {
                padding: 35px 20px;
                border-radius: 25px;
            }

            .features {
                grid-template-columns: 1fr;
            }

            .status {
                display: none;
            }

            .hero {
                padding-top: 20px;
            }

            .subtitle {
                font-size: 16px;
            }
        }
    </style>
</head>

<body>

    <div class="orb one"></div>
    <div class="orb two"></div>

    <header>
        <div class="logo">AKIL <span>X PLUS</span></div>
        <div class="status">JARVIS AI SYSTEM</div>
    </header>

    <main class="hero">

        <section class="glass-card">

            <div class="ai-orb"></div>

            <h1>Akil X Plus</h1>

            <p class="subtitle">
                Your next-generation JARVIS-style AI assistant
                designed to make everyday tasks smarter, faster and easier.
            </p>

            <div class="price">
                ₹699 <small>one-time price</small>
            </div>

            <div class="features">

                <div class="feature">
                    <div class="icon">📱</div>
                    <strong>Mobile Control</strong>
                    <span>Smart device interaction and controls.</span>
                </div>

                <div class="feature">
                    <div class="icon">▶️</div>
                    <strong>YouTube</strong>
                    <span>Useful YouTube-related tools and features.</span>
                </div>

                <div class="feature">
                    <div class="icon">💬</div>
                    <strong>WhatsApp</strong>
                    <span>Quick communication and messaging tools.</span>
                </div>

                <div class="feature">
                    <div class="icon">🔎</div>
                    <strong>Web Search</strong>
                    <span>Find information quickly on the web.</span>
                </div>

                <div class="feature">
                    <div class="icon">⚡</div>
                    <strong>Productivity</strong>
                    <span>Tools designed to save your time.</span>
                </div>

                <div class="feature">
                    <div class="icon">🤖</div>
                    <strong>AI Assistant</strong>
                    <span>A smart JARVIS-style experience.</span>
                </div>

            </div>

            <!-- DIRECT WHATSAPP BUTTON -->
            <a
                class="whatsapp"
                href="https://wa.me/917561012501?text=I%20want%20to%20buy%20the%20Akil%20X%20Plus%20JARVIS%20app%20for%20%E2%82%B9699.%20Please%20send%20me%20the%20details."
                target="_blank"
                rel="noopener noreferrer"
            >
                <span class="whatsapp-icon">💬</span>
                Buy Now on WhatsApp
            </a>

            <div class="contact">
                WhatsApp: +91 75610 12501
            </div>

            <div class="limitations">
                <strong>Important:</strong>
                Some device-level capabilities may depend on Android permissions,
                device hardware and system restrictions. Encrypted or protected
                information cannot be accessed without appropriate visibility
                and permission.
            </div>

        </section>

    </main>

    <footer>
        © 2026 Akil X Plus. All rights reserved.
    </footer>

</body>
</html>

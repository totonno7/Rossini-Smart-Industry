# Rossini-Smart-Industry
Soluzioni efficaci per la tua realtà. Sosteniamo le aziende nel loro percorso di trasformazione digitale ed energetica.
<!DOCTYPE html>
<html lang="it">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
    <title>Rossini - Smart Industry</title>
    
    <link rel="icon" type="image/png" href="img/Simbolo-rossini-b.png">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;600;700;800&display=swap" rel="stylesheet">

    <style>
        :root {
            --bg-deep: #1b1f2b;
            --bg-slate: #354658;
            --gold-brand: #c6a763;
            --gold-glow: rgba(198, 167, 99, 0.4);
            --custom-bg: #e4dacd;
            --grad-tl: linear-gradient(135deg, #25D366, #128C7E);
            --grad-pc: linear-gradient(135deg, #004a99, #001a33);
            --grad-em: linear-gradient(135deg, #ea4335, #c5221f);
            --angle: 0deg;
        }

        @property --angle { syntax: '<angle>'; initial-value: 0deg; inherits: false; }

        body, html {
            margin: 0; padding: 0; width: 100%; height: 100%;
            background-color: var(--custom-bg);
            font-family: 'Montserrat', sans-serif;
            overflow: hidden; -webkit-user-select: none; user-select: none;
        }

        #preloader { position: fixed; inset: 0; background-color: var(--bg-deep); display: flex; justify-content: center; align-items: center; z-index: 50000; transition: opacity 0.8s ease-out, visibility 0.8s; }
        .loader-wrap { position: relative; display: flex; justify-content: center; align-items: center; width: 150px; height: 150px; }
        .logo-mask-pre { width: 65px; height: 65px; background-color: #ffffff; -webkit-mask: url('img/Simbolo-rossini-b.png') center/contain no-repeat; mask: url('img/Simbolo-rossini-b.png') center/contain no-repeat; z-index: 2; animation: pulse 2s infinite alternate; }
        .back-glow-pre { position: absolute; width: 15px; height: 15px; background: var(--gold-brand); border-radius: 50%; box-shadow: 0 0 70px 35px var(--gold-glow); animation: glowPulse 3s infinite ease-in-out; }
        @keyframes pulse { from { transform: scale(1); opacity: 0.8; } to { transform: scale(1.08); opacity: 1; } }
        @keyframes glowPulse { 0%, 100% { opacity: 0.3; } 50% { opacity: 0.7; } }
        body.loaded #preloader { opacity: 0; visibility: hidden; }

        @media (min-width: 1025px) {
            .main-container { display: flex; width: 100%; height: 100vh; position: relative; z-index: 2; }
            .side-accent { width: 35%; background-color: var(--bg-deep); display: flex; flex-direction: column; justify-content: center; align-items: center; position: relative; z-index: 20; box-shadow: 15px 0 40px rgba(0,0,0,0.4); }
            .logo-main { width: 180px; margin-bottom: 12px; filter: brightness(0) invert(1); }
            .piva-text { font-size: 0.65rem; color: var(--gold-brand); letter-spacing: 2px; font-weight: 300; }
            .content-section { width: 65%; display: flex; flex-direction: column; justify-content: center; padding: 0 10%; box-sizing: border-box; background: transparent; position: relative; z-index: 5; }
            
            .anim-item { opacity: 0; transform: translateX(-50px); transition: all 0.8s cubic-bezier(0.22, 1, 0.36, 1); }
            body.loaded .anim-item { opacity: 1; transform: translateX(0); }
            body.loaded .delay-1 { transition-delay: 1.0s; }
            body.loaded .delay-2 { transition-delay: 1.2s; }
            body.loaded .delay-3 { transition-delay: 1.4s; }

            h1 { font-size: clamp(1.8rem, 4.5vw, 2.8rem); color: var(--bg-deep); text-transform: uppercase; margin: 0; line-height: 1.1; font-weight: 700; }
            .subtitle-top { font-size: 1.1rem; color: var(--bg-slate); margin: 15px 0 3vh; border-left: 3px solid var(--gold-brand); padding-left: 20px; }
            .section-title { font-size: 0.85rem; font-weight: 700; color: var(--gold-brand); text-transform: uppercase; letter-spacing: 2px; }
            .subtitle-main { font-size: 1rem; color: var(--bg-deep); margin: 8px 0 4vh; max-width: 480px; line-height: 1.5; }
            
            .btn-container { display: flex; gap: 20px; width: 100%; max-width: 800px; }
            .btn-desk { flex: 1; display: flex; flex-direction: column; align-items: center; justify-content: center; padding: 25px 15px; border: 1px solid rgba(27, 31, 43, 0.1); border-radius: 12px; background: rgba(255, 255, 255, 0.6); backdrop-filter: blur(10px); cursor: pointer; transition: all 0.4s cubic-bezier(0.165, 0.84, 0.44, 1); position: relative; overflow: hidden; }
            .btn-desk i { font-size: 1.4rem; margin-bottom: 12px; color: var(--bg-deep); transition: all 0.3s ease; }
            .btn-desk span { font-size: 0.75rem; font-weight: 700; letter-spacing: 1px; color: var(--bg-deep); transition: all 0.3s ease; }
            
            /* EFFETTO HOVER DESKTOP */
            .btn-desk:hover { transform: translateY(-10px); box-shadow: 0 20px 40px rgba(0,0,0,0.1); border-color: var(--gold-brand); background: white; }
            .btn-desk:hover i { transform: scale(1.1) rotate(8deg); color: var(--gold-brand); }
            .btn-desk:hover span { color: var(--gold-brand); }

            .standard-content-box { display: none; }
            .flip-container { width: 120px; height: 120px; }
            .flip-back i { font-size: 80px; }
        }

        @media (max-width: 1024px) {
            .main-container { display: none; }
            body { display: flex; justify-content: center; align-items: flex-start; }
            .bottom-pattern { position: fixed; bottom: 0; left: 0; right: 0; width: 100%; height: 25vh; background-image: url('img/pattern-1.png'); background-size: contain; background-position: bottom center; background-repeat: no-repeat; z-index: 1; pointer-events: none; }
            
            .standard-content-box { position: relative; z-index: 10; opacity: 0; width: 80% !important; height: 100vh; display: flex; flex-direction: column; align-items: stretch !important; padding-top: calc(4vh + env(safe-area-inset-top)); box-sizing: border-box; transition: all 1s cubic-bezier(0.22, 1, 0.36, 1) 1.5s; }
            body.loaded .standard-content-box { opacity: 1; }

            .logo-mobile { width: clamp(100px, 15vh, 130px); height: auto; align-self: flex-start; }
            .piva-mobile { font-size: 0.6rem; color: #888; margin-top: 5px; font-weight: 300; align-self: flex-start; }
            h1 { margin: 3vh 0 0; font-size: clamp(1.1rem, 3.2vh, 1.45rem); font-weight: 600; color: #000; text-transform: uppercase; line-height: 1.25; }
            .subtitle-top-mob { font-size: clamp(0.7rem, 1.7vh, 0.8rem); font-weight: 300; color: #666; margin: 2px 0 4vh; }
            .section-title-mob { font-size: clamp(0.75rem, 1.8vh, 0.8rem); font-weight: 600; color: #000; margin: 0; }
            .subtitle-main-mob { font-size: clamp(0.75rem, 1.8vh, 0.8rem); font-weight: 300; color: #000; line-height: 1.4; margin: 2px 0 4vh; }
            
            .btn-label { font-size: clamp(0.75rem, 1.8vh, 0.8rem); font-weight: 600; color: #000; margin-bottom: 8px; text-transform: lowercase; }
            .btn-container-mob { display: flex; flex-direction: column; gap: 1.2vh; width: 100% !important; }
            .btn-mob { position: relative; display: flex; align-items: center; justify-content: center; padding: 1.4vh 0; border-radius: 16px; border: 0.6px solid #000; background-color: var(--custom-bg); color: #000; font-size: 0.9rem; font-weight: 300; cursor: pointer; transition: 0.3s; z-index: 10; width: 100% !important; box-sizing: border-box !important; }
            .btn-mob i { margin-right: 12px; }

            .glow-cloud { position: absolute; inset: 0; border-radius: 16px; z-index: -2; opacity: 0; transition: 0.5s; }
            .neon-border { position: absolute; inset: -2px; border-radius: 18px; padding: 2px; z-index: -1; opacity: 0; overflow: hidden; -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0); mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0); -webkit-mask-composite: xor; mask-composite: exclude; }
            .neon-border::before { content: ''; position: absolute; width: 200%; height: 200%; top: -50%; left: -50%; background: conic-gradient(from var(--angle), var(--c1), var(--c2), var(--c1)); animation: rotateAngle 1.5s linear infinite; }
            @keyframes rotateAngle { to { --angle: 360deg; } }
            @keyframes neonMaster { 0%, 25%, 100% { opacity: 0; } 5%, 20% { opacity: 1; } }
            @keyframes glowCloudMaster { 0%, 25%, 100% { opacity: 0; } 5%, 20% { opacity: 1; box-shadow: 0 0 10px 3px var(--glow-color); } }
            body.loaded .btn-mob:nth-child(1) .neon-border { animation: neonMaster 9s infinite 3s; --c1: #25D366; --c2: #128C7E; }
            body.loaded .btn-mob:nth-child(1) .glow-cloud { animation: glowCloudMaster 9s infinite 3s; --glow-color: rgba(37, 211, 102, 0.25); }
            body.loaded .btn-mob:nth-child(2) .neon-border { animation: neonMaster 9s infinite 6s; --c1: #ea4335; --c2: #7b1b14; }
            body.loaded .btn-mob:nth-child(2) .glow-cloud { animation: glowCloudMaster 9s infinite 6s; --glow-color: rgba(234, 67, 53, 0.25); }
            body.loaded .btn-mob:nth-child(3) .neon-border { animation: neonMaster 9s infinite 9s; --c1: #004a99; --c2: #001a33; }
            body.loaded .btn-mob:nth-child(3) .glow-cloud { animation: glowCloudMaster 9s infinite 9s; --glow-color: rgba(0, 74, 153, 0.25); }

            .flip-container { width: 75px; height: 75px; }
            .flip-back i { font-size: 55px; }
        }

        #ripple { position: fixed; width: 1px; height: 1px; border-radius: 50%; pointer-events: none; z-index: 9998; transform: translate(-50%, -50%) scale(0); transition: transform 0.8s cubic-bezier(0.4, 0, 0.2, 1); }
        #ripple.expanding { transform: translate(-50%, -50%) scale(4500); }
        #overlay-content { position: fixed; inset: 0; display: none; justify-content: center; align-items: center; z-index: 10000; opacity: 0; transition: opacity 0.5s; background: rgba(0,0,0,0.1); }
        #overlay-content.active { display: flex; opacity: 1; }
        .close-overlay { position: absolute; top: 40px; right: 40px; color: white; font-size: 2.5rem; cursor: pointer; z-index: 10005; }
        .flip-container { position: relative; perspective: 1000px; z-index: 10000; opacity: 0; transform: scale(0.5); transition: all 0.5s ease; }
        .flip-container.show-logo { opacity: 1; transform: scale(1); }
        .flip-card { position: relative; width: 100%; height: 100%; transition: transform 1.0s cubic-bezier(0.645, 0.045, 0.355, 1); transform-style: preserve-3d; }
        .flip-card.is-flipped { transform: rotateY(180deg) scale(1.1); }
        .flip-face { position: absolute; width: 100%; height: 100%; backface-visibility: hidden; display: flex; justify-content: center; align-items: center; }
        .flip-front img { width: 100%; filter: brightness(0) invert(1); }
        .flip-back { transform: rotateY(180deg); }
        .flip-back i { color: white !important; }
        .clicked-state { border-color: transparent !important; color: #fff !important; }
    </style>
</head>
<body>

    <div id="preloader">
        <div class="loader-wrap">
            <div class="back-glow-pre"></div>
            <div class="logo-mask-pre"></div>
        </div>
    </div>
    
    <div id="ripple"></div>

    <div class="main-container">
        <div class="side-accent">
            <img src="img/logo-rossini-orizzontale.png" class="logo-main">
            <div class="piva-text">P.IVA 04235680362</div>
        </div>
        <div class="content-section">
            <div class="anim-item delay-1">
                <h1>SOLUZIONI EFFICACI<br>PER LA TUA REALTÀ</h1>
                <p class="subtitle-top">Innovazione e tecnologia per l'industria smart</p>
            </div>
            <div class="anim-item delay-2">
                <p class="section-title">Contatto Diretto</p>
                <p class="subtitle-main">Progettiamo e realizziamo la migliore soluzione su misura per la tua azienda industriale.</p>
            </div>
            <div class="btn-container anim-item delay-3">
                <div class="btn-desk" onclick="launchApp('tel:3470780437', 'var(--grad-tl)', 'fas fa-phone')">
                    <i class="fas fa-phone"></i><span>TELEFONO</span>
                </div>
                <div class="btn-desk" onclick="launchApp('mailto:rossinisalvatore7@gmail.com', 'var(--grad-em)', 'far fa-envelope')">
                    <i class="far fa-envelope"></i><span>EMAIL</span>
                </div>
                <div class="btn-desk" onclick="launchApp('mailto:rossinismart@pec.it', 'var(--grad-pc)', 'far fa-envelope-open')">
                    <i class="far fa-envelope-open"></i><span>PEC</span>
                </div>
            </div>
        </div>
    </div>

    <div class="standard-content-box">
        <div class="bottom-pattern"></div>
        <div class="header-block">
            <img src="img/logo-rossini-orizzontale.png" class="logo-mobile">
            <div class="piva-mobile">P.IVA 04235680362</div>
        </div>
        <div class="text-block-1">
            <h1>SOLUZIONI<br>EFFICACI PER LA<br>TUA REALTÀ</h1>
            <p class="subtitle-top-mob">Innovazione e tecnologia</p>
        </div>
        <div class="text-block-2">
            <p class="section-title-mob">Contatto Diretto</p>
            <p class="subtitle-main-mob">Realizziamo la migliore soluzione<br>per la tua azienda</p>
        </div>
        <div class="content-group">
            <div class="btn-label">contattami</div>
            <div class="btn-container-mob">
                <div class="btn-mob" onclick="launchApp('tel:3470780437', 'var(--grad-tl)', 'fas fa-phone')">
                    <div class="glow-cloud"></div><div class="neon-border"></div>
                    <i class="fas fa-phone"></i> TELEFONO
                </div>
                <div class="btn-mob" onclick="launchApp('mailto:rossinisalvatore7@gmail.com', 'var(--grad-em)', 'far fa-envelope')">
                    <div class="glow-cloud"></div><div class="neon-border"></div>
                    <i class="far fa-envelope"></i> EMAIL
                </div>
                <div class="btn-mob" onclick="launchApp('mailto:rossinismart@pec.it', 'var(--grad-pc)', 'far fa-envelope-open')">
                    <div class="glow-cloud"></div><div class="neon-border"></div>
                    <i class="far fa-envelope-open"></i> PEC
                </div>
            </div>
        </div>
    </div>

    <div id="overlay-content">
        <div class="close-overlay" onclick="resetPage()"><i class="fas fa-times"></i></div>
        <div class="flip-container" id="flip-cont">
            <div class="flip-card" id="card">
                <div class="flip-face flip-front"><img src="img/Simbolo-rossini-b.png"></div>
                <div class="flip-face flip-back"><i id="overlay-icon"></i></div>
            </div>
        </div>
    </div>

    <script>
        window.addEventListener('load', () => { setTimeout(() => { document.body.classList.add('loaded'); }, 2000); });
        let appTimer;
        function launchApp(url, gradient, iconClass) {
            const ripple = document.getElementById('ripple');
            const overlay = document.getElementById('overlay-content');
            const card = document.getElementById('card');
            const flipCont = document.getElementById('flip-cont');
            const overlayIcon = document.getElementById('overlay-icon');
            const e = window.event;
            const target = e.currentTarget;
            
            if(target.classList.contains('btn-mob')) {
                target.classList.add('clicked-state');
                const g = gradient.includes('tl') ? 'var(--grad-tl)' : gradient.includes('pc') ? 'var(--grad-pc)' : 'var(--grad-em)';
                target.style.background = g;
            }

            const gradValue = getComputedStyle(document.documentElement).getPropertyValue(gradient.replace('var(','').replace(')','')).trim();
            ripple.style.left = e.clientX + 'px';
            ripple.style.top = e.clientY + 'px';
            ripple.style.background = gradValue;
            ripple.classList.add('expanding');
            
            setTimeout(() => {
                overlay.style.display = 'flex';
                overlayIcon.className = iconClass;
                setTimeout(() => { 
                    overlay.classList.add('active'); 
                    flipCont.classList.add('show-logo'); 
                    setTimeout(() => {
                        card.classList.add('is-flipped');
                        appTimer = setTimeout(() => { window.location.href = url; }, 1500);
                    }, 1000); // 1s stasi logo fisso
                }, 50);
            }, 400);
        }

        function resetPage() {
            clearTimeout(appTimer);
            const overlay = document.getElementById('overlay-content');
            overlay.classList.remove('active');
            setTimeout(() => {
                overlay.style.display = 'none';
                document.getElementById('ripple').classList.remove('expanding');
                document.getElementById('card').classList.remove('is-flipped');
                document.getElementById('flip-cont').classList.remove('show-logo');
                document.querySelectorAll('.btn-mob').forEach(b => {
                    b.classList.remove('clicked-state');
                    b.style.background = 'var(--custom-bg)';
                });
            }, 500);
        }
    </script>
</body>
</html>

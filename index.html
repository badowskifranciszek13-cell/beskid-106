<!DOCTYPE html>
<html lang="pl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
  <meta name="author" content="Franciszek Badowski" />
  <title>FSM Beskid 106 i Klasyki PRL — Edycja Ultra Realistyczna</title>
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; user-select: none; -webkit-user-select: none; }
    html, body { width: 100%; height: 100%; overflow: hidden; background: #0f172a; font-family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif; color: #f8fafc; touch-action: none; }
    canvas { display: block; width: 100%; height: 100%; }

    /* HUD */
    #hud {
      position: fixed; top: 0; left: 0; right: 0;
      display: flex; justify-content: space-between; align-items: flex-start;
      padding: 10px 14px; pointer-events: none; z-index: 10; gap: 8px; flex-wrap: wrap;
    }
    .hud-group { display: flex; flex-wrap: wrap; gap: 6px; align-items: center; }
    .hud-badge {
      background: rgba(15, 23, 42, 0.88);
      border: 1.5px solid rgba(255, 255, 255, 0.16);
      border-radius: 10px;
      padding: 5px 9px;
      font-size: 12px;
      font-weight: 700;
      backdrop-filter: blur(6px);
      display: flex; align-items: center; gap: 5px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.42);
    }
    .mini-bar-wrap {
      width: 58px; height: 9px; background: #1e293b; border-radius: 5px; overflow: hidden; border: 1px solid #475569;
    }
    .mini-bar { height: 100%; width: 100%; transition: width 0.12s linear; }
    #fuelBar { background: linear-gradient(90deg, #ef4444, #f59e0b, #22c55e); }
    #tireBar { background: linear-gradient(90deg, #ef4444, #eab308, #38bdf8); }
    #engineBar { background: linear-gradient(90deg, #dc2626, #fb923c, #4ade80); }

    .hud-btn {
      pointer-events: auto;
      background: #e11d48;
      color: #fff;
      border: none;
      border-radius: 10px;
      padding: 7px 11px;
      font-size: 12px;
      font-weight: 800;
      cursor: pointer;
      box-shadow: 0 4px 12px rgba(225, 29, 72, 0.35);
    }
    .hud-btn:active { transform: scale(0.95); }
    .hud-btn.secondary { background: #2563eb; }
    .hud-btn.amber { background: #d97706; }

    /* Contract Banner */
    #contractBar {
      position: fixed; top: 58px; left: 50%; transform: translateX(-50%);
      background: rgba(15, 23, 42, 0.90);
      border: 1.5px solid #facc15;
      border-radius: 12px;
      padding: 5px 14px;
      font-size: 12px; font-weight: 700; color: #fef08a;
      z-index: 12; pointer-events: none; text-align: center;
      max-width: 94vw;
      backdrop-filter: blur(4px);
    }

    /* Station Banner */
    #stationBanner {
      position: fixed; top: 96px; left: 50%; transform: translateX(-50%);
      background: linear-gradient(135deg, #dc2626, #991b1b);
      border: 2px solid #fde047;
      border-radius: 14px;
      padding: 8px 16px;
      display: none; align-items: center; gap: 10px;
      z-index: 15; box-shadow: 0 8px 25px rgba(0,0,0,0.55);
    }
    #stationBanner button {
      background: #fde047; color: #111; border: none; border-radius: 8px;
      padding: 6px 12px; font-weight: 900; font-size: 12px; cursor: pointer;
    }

    /* Touch Controls */
    #controls {
      position: fixed; bottom: 18px; left: 16px; right: 16px;
      display: flex; justify-content: space-between; pointer-events: none; z-index: 10;
    }
    .pedal-btn {
      pointer-events: auto;
      width: 112px; height: 72px;
      border-radius: 16px;
      border: 2px solid rgba(255,255,255,0.25);
      background: rgba(15, 23, 42, 0.82);
      color: #fff;
      font-weight: 900; font-size: 14px;
      display: flex; flex-direction: column; align-items: center; justify-content: center; gap: 2px;
      backdrop-filter: blur(5px);
      box-shadow: 0 6px 18px rgba(0,0,0,0.48);
      cursor: pointer;
    }
    .pedal-btn.active, .pedal-btn:active {
      background: rgba(234, 179, 8, 0.92); color: #111; border-color: #fef08a; transform: scale(0.96);
    }
    .pedal-btn.brake.active, .pedal-btn.brake:active {
      background: rgba(239, 68, 68, 0.92); color: #fff; border-color: #fecaca;
    }

    #hudAuthor {
      position: fixed; bottom: 5px; left: 50%; transform: translateX(-50%);
      font-size: 11px; color: rgba(255,255,255,0.62); pointer-events: none; z-index: 9;
    }

    /* Overlays & Modals */
    .overlay {
      position: fixed; inset: 0;
      background: rgba(8, 12, 20, 0.88);
      backdrop-filter: blur(6px);
      display: flex; align-items: center; justify-content: center;
      padding: 14px; z-index: 30;
    }
    .hidden { display: none !important; }
    .modal {
      background: #161e2e;
      border: 2px solid #334155;
      border-radius: 18px;
      width: 100%; max-width: 590px; max-height: 90vh;
      overflow-y: auto;
      padding: 18px;
      box-shadow: 0 20px 50px rgba(0,0,0,0.65);
    }
    .modal-header {
      display: flex; justify-content: space-between; align-items: center;
      border-bottom: 1px solid #2e3a52; padding-bottom: 10px; margin-bottom: 12px;
    }
    .modal-header h2 { font-size: 19px; color: #facc15; }
    .close-btn {
      background: #334155; color: #fff; border: none; border-radius: 8px;
      padding: 6px 11px; font-weight: 700; cursor: pointer;
    }

    .title-logo { text-align: center; margin-bottom: 10px; }
    .title-logo .tag {
      display: inline-block; background: #dc2626; color: #fff; font-size: 11px; font-weight: 800;
      padding: 3px 10px; border-radius: 20px; letter-spacing: 0.8px; margin-bottom: 6px;
    }
    .title-logo h1 { font-size: 25px; color: #facc15; line-height: 1.15; }
    .title-logo p { font-size: 12px; color: #cbd5e1; margin-top: 4px; }
    .author-credit { text-align: center; font-size: 12px; color: #94a3b8; margin-top: 5px; }
    .author-credit strong { color: #f8fafc; }

    .section-title { font-size: 13px; color: #facc15; font-weight: 800; margin: 12px 0 6px; text-transform: uppercase; letter-spacing: 0.5px; }

    /* Season Selector */
    .season-grid { display: grid; grid-template-columns: repeat(4, 1fr); gap: 6px; }
    .season-btn {
      padding: 8px 4px; border-radius: 10px; border: 1.5px solid #334155;
      background: #0f172a; color: #e2e8f0; font-weight: 800; font-size: 12px;
      cursor: pointer; text-align: center;
    }
    .season-btn.active { border-color: #facc15; background: #1e293b; color: #fef08a; }

    /* Job Selector */
    .job-grid { display: grid; grid-template-columns: repeat(2, 1fr); gap: 7px; }
    .job-btn {
      padding: 9px 10px; border-radius: 10px; border: 1.5px solid #334155;
      background: #0f172a; color: #e2e8f0; text-align: left; cursor: pointer;
    }
    .job-btn.active { border-color: #4ade80; background: #132822; }
    .job-btn strong { display: block; font-size: 12px; color: #fff; }
    .job-btn span { font-size: 11px; color: #94a3b8; }

    .primary-cta {
      width: 100%; padding: 13px; border: none; border-radius: 12px;
      background: linear-gradient(135deg, #facc15, #eab308);
      color: #111827; font-size: 16px; font-weight: 900; cursor: pointer;
      margin-top: 12px; box-shadow: 0 6px 20px rgba(234, 179, 8, 0.35);
    }
    .secondary-cta {
      width: 100%; padding: 10px; border: 1.5px solid #475569; border-radius: 12px;
      background: #1e293b; color: #fff; font-size: 13px; font-weight: 800; cursor: pointer;
      margin-top: 8px;
    }

    /* Garage Fleet, Service & Upgrades */
    .vehicle-card, .upgrade-card {
      background: #0f172a; border: 1.5px solid #2e3a52; border-radius: 12px;
      padding: 10px 12px; margin-bottom: 8px;
      display: flex; justify-content: space-between; align-items: center; gap: 10px;
    }
    .vehicle-card.selected { border-color: #facc15; background: #1c2538; }
    .card-info h4 { font-size: 14px; color: #f8fafc; }
    .card-info p { font-size: 11px; color: #94a3b8; margin-top: 2px; }
    .cond-pill {
      display: inline-block; margin-top: 4px; font-size: 11px; font-weight: 800;
      padding: 2px 7px; border-radius: 6px; background: #1e293b; color: #e2e8f0;
    }
    .buy-btn {
      background: #16a34a; color: #fff; border: none; border-radius: 9px;
      padding: 8px 11px; font-weight: 800; font-size: 12px; cursor: pointer; white-space: nowrap;
    }
    .buy-btn.select-mode { background: #2563eb; }
    .buy-btn.active-veh { background: #eab308; color: #111; }
    .buy-btn.service-btn { background: #0284c7; }
    .buy-btn:disabled { background: #334155; color: #94a3b8; cursor: not-allowed; }

    .paint-grid { display: grid; grid-template-columns: repeat(2, 1fr); gap: 7px; margin-top: 6px; }
    .paint-btn {
      padding: 8px; border-radius: 9px; border: 2px solid #334155; background: #0f172a;
      color: #fff; font-weight: 700; font-size: 12px; cursor: pointer; display: flex; align-items: center; gap: 8px;
    }
    .paint-btn.selected { border-color: #facc15; background: #1e293b; }
    .swatch { width: 16px; height: 16px; border-radius: 50%; border: 1px solid #fff; flex-shrink: 0; }

    /* Scratchcard & Scores */
    .scores-box {
      background: #0f172a; border: 1px solid #2b354b; border-radius: 12px;
      padding: 10px 12px; margin-top: 10px;
    }
    .scores-box h3 { font-size: 12px; color: #94a3b8; margin-bottom: 6px; text-transform: uppercase; }
    .score-row {
      display: flex; justify-content: space-between; font-size: 12px; padding: 4px 0;
      border-bottom: 1px dashed #263044;
    }
    .score-row:last-child { border-bottom: none; }

    .scratch-tabs { display: flex; gap: 6px; margin-bottom: 10px; }
    .scratch-tab {
      flex: 1; padding: 7px; border-radius: 9px; border: 1.5px solid #334155;
      background: #0f172a; color: #cbd5e1; font-size: 11px; font-weight: 800; cursor: pointer; text-align: center;
    }
    .scratch-tab.active { border-color: #facc15; color: #facc15; background: #1e293b; }
    .scratch-stage {
      position: relative; width: 100%; max-width: 320px; height: 140px; margin: 0 auto;
      border-radius: 14px; overflow: hidden; border: 2px solid #facc15;
      background: linear-gradient(135deg, #fef08a, #fde047);
      display: flex; flex-direction: column; align-items: center; justify-content: center;
      color: #111827;
    }
    #scratchCanvas { position: absolute; inset: 0; width: 100%; height: 100%; cursor: crosshair; touch-action: none; }
    .modal-footer-author {
      margin-top: 12px; padding-top: 8px; border-top: 1px solid #2e3a52;
      text-align: center; font-size: 11px; color: #94a3b8;
    }
  </style>
</head>
<body>

  <canvas id="gameCanvas"></canvas>

  <!-- HUD -->
  <div id="hud">
    <div class="hud-group">
      <div class="hud-badge">💰 <span id="hudMoney">350</span> zł</div>
      <div class="hud-badge">🛣️ <span id="hudDist">0</span> m</div>
      <div class="hud-badge">🚗 <span id="hudVehicleName">FSM Beskid 106</span></div>
      <div class="hud-badge">
        ⛽
        <div class="mini-bar-wrap"><div class="mini-bar" id="fuelBar"></div></div>
      </div>
      <div class="hud-badge" title="Stan opon">
        🛞 <span id="hudTirePct">100%</span>
        <div class="mini-bar-wrap"><div class="mini-bar" id="tireBar"></div></div>
      </div>
      <div class="hud-badge" title="Stan silnika">
        ⚙️ <span id="hudEnginePct">100%</span>
        <div class="mini-bar-wrap"><div class="mini-bar" id="engineBar"></div></div>
      </div>
    </div>
    <div class="hud-group">
      <button class="hud-btn secondary" id="timeToggleBtn">☀️ Dzień</button>
      <button class="hud-btn amber" id="openGarageBtn">🔧 Garaż</button>
    </div>
  </div>

  <!-- Active Job / Contract Status -->
  <div id="contractBar">📦 Zlecenie: Wybierz trasę przed startem lub zbieraj monety i zdrapki CPN</div>

  <!-- Station Banner -->
  <div id="stationBanner">
    <div>
      <div style="font-weight:900; font-size:13px; color:#fef08a;">⛽ STACJA PALIW CPN</div>
      <div style="font-size:11px;">Zatankuj pojazd lub zdrap kupon!</div>
    </div>
    <button id="enterStationBtn">Wjedź na stację</button>
  </div>

  <div id="hudAuthor">Autor: Franciszek Badowski</div>

  <!-- Touch Controls -->
  <div id="controls">
    <button class="pedal-btn brake" id="btnBrake">
      <span>HAMULEC</span>
      <span style="font-size:10px; opacity:0.8;">◀ / A</span>
    </button>
    <button class="pedal-btn" id="btnGas">
      <span>GAZ</span>
      <span style="font-size:10px; opacity:0.8;">▶ / D</span>
    </button>
  </div>

  <!-- Start Screen -->
  <div class="overlay" id="startOverlay">
    <div class="modal">
      <div class="title-logo">
        <div class="tag">EDYCJA ULTRA REALISTYCZNA • POJAZDY, SPALINY, SŁUPKI, LASY I ZABUDOWA PRL</div>
        <h1>LEGENDY SZOS PRL 2D</h1>
        <p>Szczegółowe sylwetki z szybami, zderzakami, światłami, zawieszeniem i kołami oraz realistyczne otoczenie trasy!</p>
        <div class="author-credit">Autor gry: <strong>Franciszek Badowski</strong></div>
      </div>

      <div class="section-title">1. Wybierz porę roku przed startem</div>
      <div class="season-grid" id="seasonGrid">
        <button class="season-btn active" data-season="spring">🌱 Wiosna</button>
        <button class="season-btn" data-season="summer">☀️ Lato</button>
        <button class="season-btn" data-season="autumn">🍂 Jesień</button>
        <button class="season-btn" data-season="winter">❄️ Zima</button>
      </div>

      <div class="section-title">2. Wybierz zlecenie / formę zarobku</div>
      <div class="job-grid" id="jobGrid">
        <button class="job-btn active" data-job="free">
          <strong>🛣️ Wolna Jazda i Zdrapki</strong>
          <span>Monety, CPN i premia za dystans</span>
        </button>
        <button class="job-btn" data-job="bales">
          <strong>🌾 Transport Bel Słomy (Traktor)</strong>
          <span>Dowóz bel (najlepiej ciągnikiem) • +140 zł</span>
        </button>
        <button class="job-btn" data-job="grain">
          <strong>🌽 Skup Zboża (Przyczepa/Ciężarówka)</strong>
          <span>Dowóz ziarna do elewatora • +165 zł</span>
        </button>
        <button class="job-btn" data-job="bus">
          <strong>🚌 Linia Podmiejska (Autobusy)</strong>
          <span>Kurs pasażerski (Ogórek/Ikarus/Jelcz) • +155 zł</span>
        </button>
      </div>

      <button class="primary-cta" id="startGameBtn">🚀 RUSZAJ W TRASĘ</button>
      <button class="secondary-cta" id="startGarageBtn">🔧 GARAŻ, AUTA, CZĘŚCI I SERWIS</button>

      <div class="scores-box">
        <h3>🏆 Najlepsze przejazdy (Top 5)</h3>
        <div id="highScoresList"></div>
      </div>

      <div class="modal-footer-author">© Franciszek Badowski • Legendy Szos PRL 2D</div>
    </div>
  </div>

  <!-- Game Over Screen -->
  <div class="overlay hidden" id="gameOverOverlay">
    <div class="modal">
      <div class="title-logo">
        <div class="tag" id="gameOverReason">KONIEC PALIWA</div>
        <h1>KONIEC TRASY!</h1>
        <p id="gameOverSummary">Przejechałeś 0 m i zebrałeś 0 zł.</p>
        <div class="author-credit">Autor: <strong>Franciszek Badowski</strong></div>
      </div>

      <div class="scores-box">
        <h3>🏆 Tabela Najlepszych Wyników</h3>
        <div id="gameOverScoresList"></div>
      </div>

      <button class="primary-cta" id="restartBtn">🔄 WRÓĆ DO USTAWIEŃ STARTU</button>
      <button class="secondary-cta" id="gameOverGarageBtn">🔧 OTWÓRZ GARAŻ I SERWIS</button>
      <div class="modal-footer-author">© Franciszek Badowski</div>
    </div>
  </div>

  <!-- Garage Modal -->
  <div class="overlay hidden" id="garageOverlay">
    <div class="modal">
      <div class="modal-header">
        <h2>🔧 Garaż, Flota i Serwis PRL</h2>
        <div style="display:flex; align-items:center; gap:10px;">
          <span style="font-weight:800; color:#4ade80;">💰 <span id="garageMoney">0</span> zł</span>
          <button class="close-btn" id="closeGarageBtn">Zamknij ✕</button>
        </div>
      </div>

      <div class="section-title">Wymiana zużytych części (wybrany pojazd)</div>
      <div class="upgrade-card">
        <div class="card-info">
          <h4>🛞 Opony — Stan: <span id="garageTirePct">100%</span></h4>
          <p>Zużyte opony ślizgają się w błocie/śniegu i wydłużają hamowanie.</p>
        </div>
        <button class="buy-btn service-btn" id="replaceTiresBtn">Nowe opony (45 zł)</button>
      </div>

      <div class="upgrade-card">
        <div class="card-info">
          <h4>⚙️ Silnik i osprzęt — Stan: <span id="garageEnginePct">100%</span></h4>
          <p>Zużyty silnik traci moc i generuje więcej dymu z wydechu.</p>
        </div>
        <button class="buy-btn service-btn" id="serviceEngineBtn">Remont (60 zł)</button>
      </div>

      <div class="section-title">Wybór i zakup pojazdów</div>
      <div id="vehicleList"></div>

      <div class="section-title">Ulepszenia wybranego pojazdu</div>
      <div class="upgrade-card">
        <div class="card-info">
          <h4>Silnik i Rozpęd (Poz. <span id="lvlEngine">1</span>/5)</h4>
          <p>Większa moc, lepsze przyspieszenie i prędkość maksymalna.</p>
        </div>
        <button class="buy-btn" id="buyEngineBtn">100 zł</button>
      </div>

      <div class="upgrade-card">
        <div class="card-info">
          <h4>Hamulce i Przyczepność (Poz. <span id="lvlBrake">1</span>/5)</h4>
          <p>Krótsza droga hamowania i lepsze wyjście z błota/śniegu.</p>
        </div>
        <button class="buy-btn" id="buyBrakeBtn">90 zł</button>
      </div>

      <div class="upgrade-card">
        <div class="card-info">
          <h4>Zawieszenie i Zbiornik (Poz. <span id="lvlSusp">1</span>/5)</h4>
          <p>Lepsza amortyzacja wybojów i większy bak paliwa.</p>
        </div>
        <button class="buy-btn" id="buySuspBtn">85 zł</button>
      </div>

      <div class="section-title">Lakier Nadwozia</div>
      <div class="paint-grid" id="paintGrid"></div>

      <div class="modal-footer-author">Autor: Franciszek Badowski</div>
    </div>
  </div>

  <!-- CPN Gas Station & Scratchcard Modal -->
  <div class="overlay hidden" id="stationOverlay">
    <div class="modal">
      <div class="modal-header">
        <h2>⛽ Stacja Paliw CPN</h2>
        <div style="display:flex; align-items:center; gap:10px;">
          <span style="font-weight:800; color:#4ade80;">💰 <span id="stationMoney">0</span> zł</span>
          <button class="close-btn" id="closeStationBtn">Wyjedź ✕</button>
        </div>
      </div>

      <div class="upgrade-card">
        <div class="card-info">
          <h4>Dystrybutor Paliwa</h4>
          <p>Stan baku: <strong id="stationFuelPct">100%</strong> • Pełne tankowanie</p>
        </div>
        <button class="buy-btn" id="refuelBtn">Zatankuj (25 zł)</button>
      </div>

      <div class="section-title">🎟️ Kiosk RUCH-u: Zdrapki PRL</div>
      <div class="scratch-tabs">
        <button class="scratch-tab active" data-tier="0">Szybkie 50 zł<br><small>Koszt: 15 zł</small></button>
        <button class="scratch-tab" data-tier="1">Złoty Beskid<br><small>Koszt: 35 zł</small></button>
        <button class="scratch-tab" data-tier="2">Kilometr PRL<br><small>Koszt: 70 zł</small></button>
      </div>

      <div class="scratch-stage">
        <div style="font-size:11px; font-weight:800; text-transform:uppercase;">Twoja Wygrana:</div>
        <div id="scratchPrizeText" style="font-size:30px; font-weight:900; margin:3px 0;">0 zł</div>
        <div id="scratchSubText" style="font-size:11px; font-weight:700;">Kup zdrapkę i zdrap warstwę palcem!</div>
        <canvas id="scratchCanvas" width="320" height="140"></canvas>
      </div>

      <div style="display:flex; gap:8px; margin-top:10px;">
        <button class="primary-cta" style="margin-top:0; font-size:13px; padding:10px;" id="buyScratchBtn">🎟️ Kup nową zdrapkę</button>
        <button class="secondary-cta" style="margin-top:0; width:auto; padding:10px 14px;" id="revealScratchBtn">Zdrap wszystko</button>
      </div>

      <div class="modal-footer-author">Autor gry: Franciszek Badowski</div>
    </div>
  </div>

  <script>
    // --- VEHICLES ROSTER ---
    const VEHICLES = [
      { id: 'beskid', name: 'FSM Beskid 106', plate: 'BB 106-P', type: 'car', exhaust: 'blueish', price: 0, maxSpeed: 12.2, accel: 0.31, brakePower: 0.42, mudResist: 0.65, fuelBurn: 0.042, scale: 1.25, desc: 'Klinowy prototyp z Bielska-Białej — opadający tył, słupek B, lusterko i duża szyba.' },
      { id: 'mikrus', name: 'Mikrus MR-300', plate: 'RZ 03-00', type: 'car', exhaust: 'twoStroke', price: 120, maxSpeed: 10.6, accel: 0.29, brakePower: 0.38, mudResist: 0.48, fuelBurn: 0.032, scale: 1.05, desc: 'Zwinny mikrosamochód z Mielca z dwusuwowym dymkiem i chromowanym zderzakiem.' },
      { id: 'maluch', name: 'Fiat 126p Maluch', plate: 'KR 126-P', type: 'car', exhaust: 'light', price: 160, maxSpeed: 11.4, accel: 0.30, brakePower: 0.40, mudResist: 0.58, fuelBurn: 0.036, scale: 1.12, desc: 'Klasyczny Maluch — kanciasta bryła, tylne żaluzje, zderzaki, tablica i lampy.' },
      { id: 'syrena', name: 'FSM Syrena 105', plate: 'SO 105-L', type: 'car', exhaust: 'twoStroke', price: 220, maxSpeed: 11.8, accel: 0.32, brakePower: 0.39, mudResist: 0.66, fuelBurn: 0.048, scale: 1.22, desc: 'Dwusuwowy klasyk („skarpeta”) z chromowanym grillem i niebieskawymi spalinami.' },
      { id: 'warszawa', name: 'FSO Warszawa M20', plate: 'WA 20-51', type: 'car', exhaust: 'classic', price: 320, maxSpeed: 12.5, accel: 0.25, brakePower: 0.33, mudResist: 0.78, fuelBurn: 0.058, scale: 1.35, desc: 'Garbata limuzyna z Żerania — ciężka, stateczna, ze słupkiem B i chromami.' },
      { id: 'polonez', name: 'FSO Polonez 1500', plate: 'WA 15-80', type: 'car', exhaust: 'classic', price: 380, maxSpeed: 13.8, accel: 0.36, brakePower: 0.46, mudResist: 0.72, fuelBurn: 0.052, scale: 1.32, desc: 'Nowocześniejszy hatchback z lat 80., listwa boczna, wycieraczka i mocny silnik.' },
      { id: 'zuk', name: 'FSC Żuk A07', plate: 'LU 07-A', type: 'truck', exhaust: 'classic', price: 450, maxSpeed: 10.8, accel: 0.22, brakePower: 0.30, mudResist: 0.84, fuelBurn: 0.062, scale: 1.38, desc: 'Dostawczy Żuk z Lublina ze skrzynią ładunkową, deskami i nadkolami.' },
      { id: 'nysa', name: 'ZSD Nysa 522', plate: 'OP 522-T', type: 'truck', exhaust: 'classic', price: 500, maxSpeed: 11.0, accel: 0.23, brakePower: 0.31, mudResist: 0.82, fuelBurn: 0.060, scale: 1.40, desc: 'Furgon/mikrobus z Nysy z bocznym przetłoczeniem, szybami i chromowaną listwą.' },
      { id: 'star', name: 'Star 266 / 200', plate: 'RA 266-C', type: 'truck', exhaust: 'diesel', price: 680, maxSpeed: 10.2, accel: 0.19, brakePower: 0.26, mudResist: 0.94, fuelBurn: 0.075, scale: 1.52, desc: 'Ciężarówka ze Starachowic — skrzynia z burtami, zbiornik paliwa i diesel.' },
      { id: 'jelcz', name: 'Jelcz 315 / 325', plate: 'WR 315-D', type: 'truck', exhaust: 'diesel', price: 780, maxSpeed: 10.5, accel: 0.18, brakePower: 0.25, mudResist: 0.92, fuelBurn: 0.082, scale: 1.58, desc: 'Ciężka ciężarówka z Jelcza z masywną kabiną, kołem zapasowym i dymem z diesla.' },
      { id: 'ogorek', name: 'Jelcz 043 „Ogórek”', plate: 'KR 043-PKS', type: 'bus', exhaust: 'diesel', price: 620, maxSpeed: 10.6, accel: 0.20, brakePower: 0.27, mudResist: 0.76, fuelBurn: 0.070, scale: 1.50, desc: 'Obły autobus międzymiastowy PKS z listwami bocznymi, świetlikiem i kołpakami.' },
      { id: 'ikarus', name: 'Ikarus 260 / 280', plate: 'WA 260-MZK', type: 'bus', exhaust: 'diesel', price: 860, maxSpeed: 10.9, accel: 0.19, brakePower: 0.25, mudResist: 0.78, fuelBurn: 0.085, scale: 1.62, desc: 'Miejski/podmiejski autobus z drzwiowymi panelami, oknami i tablicą kierunkową.' },
      { id: 'traktor', name: 'Ursus C-360 (Traktor)', plate: 'BI 360-R', type: 'tractor', exhaust: 'tractorDiesel', price: 420, maxSpeed: 8.8, accel: 0.24, brakePower: 0.34, mudResist: 0.97, fuelBurn: 0.044, scale: 1.34, desc: '„Sześćdziesiątka” — pionowy komin, maska, kabina, wielkie tylne koło z bieżnikiem.' }
    ];

    const SEASONS = {
      spring: { label: '🌱 Wiosna', skyTop: '#38bdf8', skyBot: '#bbf7d0', hillFar: '#65a30d', hill: '#4d7c0f', ground: '#3f6212', mudChance: 0.35, slip: 0.96 },
      summer: { label: '☀️ Lato', skyTop: '#0284c7', skyBot: '#fef08a', hillFar: '#84cc16', hill: '#65a30d', ground: '#4d7c0f', mudChance: 0.15, slip: 1.00 },
      autumn: { label: '🍂 Jesień', skyTop: '#334155', skyBot: '#fb923c', hillFar: '#b45309', hill: '#9a3412', ground: '#7c2d12', mudChance: 0.45, slip: 0.92 },
      winter: { label: '❄️ Zima', skyTop: '#1e3a8a', skyBot: '#e2e8f0', hillFar: '#cbd5e1', hill: '#94a3b8', ground: '#f1f5f9', mudChance: 0.25, slip: 0.84 }
    };

    const JOBS = {
      free: { name: 'Wolna Jazda i Zdrapki', targetM: 0, reward: 0, bonusType: null },
      bales: { name: 'Transport Bel Słomy', targetM: 550, reward: 140, bonusType: 'tractor' },
      grain: { name: 'Skup Zboża do Elewatora', targetM: 700, reward: 165, bonusType: 'truck' },
      bus: { name: 'Linia Podmiejska (Pasażerowie)', targetM: 650, reward: 155, bonusType: 'bus' }
    };

    const PAINTS = [
      { name: 'Żółty Beskid', color: '#eab308', dark: '#a16207', light: '#fef08a' },
      { name: 'Czerwień PRL', color: '#dc2626', dark: '#991b1b', light: '#fca5a5' },
      { name: 'Błękit / Krem', color: '#38bdf8', dark: '#0369a1', light: '#bae6fd' },
      { name: 'Biały Rajdowy', color: '#f8fafc', dark: '#cbd5e1', light: '#ffffff' }
    ];

    function getPaintPalette() {
      return PAINTS.find(p => p.color === save.paint) || { color: save.paint, dark: '#1e293b', light: '#ffffff' };
    }

    // --- SAVE STATE ---
    const SAVE_KEY = 'prl_legendy_save_v6';
    const defaultState = {
      money: 350,
      ownedVehicles: ['beskid'],
      selectedVehicle: 'beskid',
      vehicleWear: { beskid: { tire: 100, engine: 100 } },
      engineLvl: 1,
      brakeLvl: 1,
      suspLvl: 1,
      paint: '#eab308',
      highScores: []
    };
    let save = Object.assign({}, defaultState, JSON.parse(localStorage.getItem(SAVE_KEY) || '{}'));
    if (!save.vehicleWear) save.vehicleWear = {};

    function ensureVehicleWear(id) {
      if (!save.vehicleWear[id]) {
        save.vehicleWear[id] = { tire: 100, engine: 100 };
      }
      return save.vehicleWear[id];
    }
    ensureVehicleWear(save.selectedVehicle);

    function persistSave() { localStorage.setItem(SAVE_KEY, JSON.stringify(save)); }
    function getCurrentVehicle() { return VEHICLES.find(v => v.id === save.selectedVehicle) || VEHICLES[0]; }
    function getCurrentWear() { return ensureVehicleWear(save.selectedVehicle); }

    // --- AUDIO ---
    let audioCtx = null;
    function playSound(type) {
      try {
        if (!audioCtx) audioCtx = new (window.AudioContext || window.webkitAudioContext)();
        if (audioCtx.state === 'suspended') audioCtx.resume();
        const osc = audioCtx.createOscillator();
        const gain = audioCtx.createGain();
        osc.connect(gain);
        gain.connect(audioCtx.destination);
        const now = audioCtx.currentTime;
        if (type === 'coin') {
          osc.type = 'sine';
          osc.frequency.setValueAtTime(660, now);
          osc.frequency.exponentialRampToValueAtTime(1180, now + 0.12);
          gain.gain.setValueAtTime(0.11, now);
          gain.gain.exponentialRampToValueAtTime(0.001, now + 0.14);
          osc.start(now); osc.stop(now + 0.14);
        } else if (type === 'buy' || type === 'win') {
          osc.type = 'triangle';
          osc.frequency.setValueAtTime(420, now);
          osc.frequency.exponentialRampToValueAtTime(840, now + 0.18);
          gain.gain.setValueAtTime(0.14, now);
          gain.gain.exponentialRampToValueAtTime(0.001, now + 0.24);
          osc.start(now); osc.stop(now + 0.24);
        }
      } catch (e) {}
    }

    // --- CANVAS & WORLD ---
    const canvas = document.getElementById('gameCanvas');
    const ctx = canvas.getContext('2d');
    let W = canvas.width = window.innerWidth;
    let H = canvas.height = window.innerHeight;
    window.addEventListener('resize', () => {
      W = canvas.width = window.innerWidth;
      H = canvas.height = window.innerHeight;
    });

    let selectedSeasonKey = 'spring';
    let selectedJobKey = 'free';
    let jobCompleted = false;

    const TIME_MODES = [
      { name: '☀️ Dzień', dark: 0.0, sunY: 0.18, stars: false },
      { name: '🌇 Zmierzch', dark: 0.38, sunY: 0.52, stars: true },
      { name: '🌙 Noc', dark: 0.72, sunY: 0.20, stars: true },
      { name: '🌅 Poranek', dark: 0.16, sunY: 0.44, stars: false }
    ];
    let timeIndex = 0;

    function getTerrainY(x) {
      const base = H * 0.72;
      const h1 = Math.sin(x * 0.0020) * 52;
      const h2 = Math.sin(x * 0.0058 + 1.1) * 20;
      const modStation = ((x % 4600) + 4600) % 4600;
      let flat = 1;
      if (x < 550) flat = Math.max(0, (x - 140) / 410);
      if (Math.abs(modStation - 2600) < 350) flat *= Math.min(1, Math.abs(modStation - 2600) / 350);
      return base + (h1 + h2) * flat;
    }

    function getTerrainSlope(x) {
      const dx = 6;
      return Math.atan2(getTerrainY(x + dx) - getTerrainY(x - dx), dx * 2);
    }

    let mudPatches = [];
    let nextMudX = 950;
    function spawnMudUpTo(limitX) {
      const s = SEASONS[selectedSeasonKey];
      while (nextMudX < limitX) {
        const modStation = ((nextMudX % 4600) + 4600) % 4600;
        if (Math.abs(modStation - 2600) > 420 && Math.random() < (0.55 + s.mudChance * 0.5)) {
          mudPatches.push({ startX: nextMudX, width: 220 + Math.random() * 160 });
        }
        nextMudX += 1100 + Math.random() * 750;
      }
    }

    function isInMud(x) {
      return mudPatches.some(m => x >= m.startX && x <= m.startX + m.width);
    }

    let running = false;
    let paused = false;
    let gasPressed = false;
    let brakePressed = false;
    let particles = [];
    let coins = [];
    let nextCoinX = 520;

    const car = {
      x: 180, y: 0, vx: 0, vy: 0,
      angle: 0, angVel: 0, wheelRot: 0, suspSquat: 0,
      fuel: 100, maxFuel: 100,
      runMoney: 0, distanceM: 0
    };

    function computeMaxFuel() {
      const v = getCurrentVehicle();
      const base = v.type === 'truck' || v.type === 'bus' ? 145 : (v.type === 'tractor' ? 120 : 100);
      return base + (save.suspLvl - 1) * 20;
    }

    function resetRun() {
      jobCompleted = false;
      car.x = 180;
      car.y = getTerrainY(180) - 34;
      car.vx = 0; car.vy = 0;
      car.angle = 0; car.angVel = 0; car.wheelRot = 0; car.suspSquat = 0;
      car.maxFuel = computeMaxFuel();
      car.fuel = car.maxFuel;
      car.runMoney = 0;
      car.distanceM = 0;
      particles = [];
      coins = [];
      mudPatches = [];
      nextCoinX = 480;
      nextMudX = 950;
      spawnCoinsUpTo(3200);
      spawnMudUpTo(3200);
      updateContractBar();
      updateHUD();
    }

    function spawnCoinsUpTo(limitX) {
      while (nextCoinX < limitX) {
        const count = 3 + Math.floor(Math.random() * 3);
        for (let i = 0; i < count; i++) {
          const cx = nextCoinX + i * 54;
          const cy = getTerrainY(cx) - 26;
          coins.push({ x: cx, y: cy, collected: false, val: 6 + Math.floor(cx / 7000) * 4 });
        }
        nextCoinX += 820 + Math.random() * 600;
      }
    }

    function updateContractBar() {
      const job = JOBS[selectedJobKey];
      const v = getCurrentVehicle();
      const bar = document.getElementById('contractBar');
      if (job.targetM <= 0) {
        bar.textContent = `🛣️ Wolna jazda (${SEASONS[selectedSeasonKey].label}) • Pilnuj paliwa, opon, silnika i CPN`;
        return;
      }
      if (jobCompleted) {
        bar.textContent = `✅ Zlecenie „${job.name}” ukończone! Jedź dalej po kolejne nagrody.`;
        return;
      }
      const matchBonus = job.bonusType === v.type ? ' (Premia +40 zł za właściwy pojazd!)' : '';
      bar.textContent = `📦 ${job.name}: ${car.distanceM} / ${job.targetM} m • Nagroda: ${job.reward} zł${matchBonus}`;
    }

    // Controls
    function bindHold(btn, setter) {
      const down = (e) => { e.preventDefault(); setter(true); btn.classList.add('active'); };
      const up = (e) => { e.preventDefault(); setter(false); btn.classList.remove('active'); };
      btn.addEventListener('touchstart', down, { passive: false });
      btn.addEventListener('touchend', up, { passive: false });
      btn.addEventListener('touchcancel', up, { passive: false });
      btn.addEventListener('mousedown', down);
      window.addEventListener('mouseup', () => { setter(false); btn.classList.remove('active'); });
    }
    bindHold(document.getElementById('btnGas'), (v) => gasPressed = v);
    bindHold(document.getElementById('btnBrake'), (v) => brakePressed = v);

    window.addEventListener('keydown', (e) => {
      if (e.key === 'ArrowRight' || e.key === 'd' || e.key === 'D') gasPressed = true;
      if (e.key === 'ArrowLeft' || e.key === 'a' || e.key === 'A') brakePressed = true;
    });
    window.addEventListener('keyup', (e) => {
      if (e.key === 'ArrowRight' || e.key === 'd' || e.key === 'D') gasPressed = false;
      if (e.key === 'ArrowLeft' || e.key === 'a' || e.key === 'A') brakePressed = false;
    });

    document.getElementById('timeToggleBtn').addEventListener('click', () => {
      timeIndex = (timeIndex + 1) % TIME_MODES.length;
      document.getElementById('timeToggleBtn').textContent = TIME_MODES[timeIndex].name;
    });

    // --- EXHAUST SMOKE ---
    function spawnExhaustSmoke(v, wear, rearX, rearGroundY, cosA, sinA) {
      const wornPenalty = Math.max(0, (80 - wear.engine) / 80);
      let exX = rearX - 8;
      let exY = rearGroundY - 12;
      let baseVx = -1.4 - car.vx * 0.15;
      let baseVy = -0.8 - Math.random() * 0.7;

      if (v.id === 'traktor') {
        exX = car.x + cosA * (26 * v.scale) - sinA * (-24 * v.scale);
        exY = car.y + sinA * (26 * v.scale) + cosA * (-24 * v.scale);
        baseVx = -0.6 - car.vx * 0.08;
        baseVy = -2.1 - Math.random() * 1.1;
      }

      let color = 'rgba(210, 218, 228, 0.36)';
      let maxSize = 6 + wornPenalty * 7;

      if (v.exhaust === 'twoStroke') {
        color = wornPenalty > 0.35 ? 'rgba(100, 116, 139, 0.58)' : 'rgba(186, 230, 253, 0.44)';
        maxSize = 7 + wornPenalty * 8;
      } else if (v.exhaust === 'diesel' || v.exhaust === 'tractorDiesel') {
        color = wornPenalty > 0.25 ? 'rgba(30, 41, 59, 0.72)' : 'rgba(71, 85, 105, 0.52)';
        maxSize = 8 + wornPenalty * 9;
      } else if (wornPenalty > 0.3) {
        color = 'rgba(71, 85, 105, 0.60)';
      }

      particles.push({
        x: exX, y: exY,
        vx: baseVx + (Math.random() - 0.5) * 0.6,
        vy: baseVy,
        life: 1,
        size: 3.5 + Math.random() * 2.5,
        grow: 0.14 + wornPenalty * 0.14,
        maxSize,
        color
      });
    }

    // --- PHYSICS ---
    function updatePhysics(dt) {
      if (!running || paused) return;

      const v = getCurrentVehicle();
      const s = SEASONS[selectedSeasonKey];
      const wear = getCurrentWear();
      const inMud = isInMud(car.x);

      const tireEff = 0.25 + (wear.tire / 100) * 0.75;
      const engineEff = 0.35 + (wear.engine / 100) * 0.65;

      const maxSpeed = (v.maxSpeed + (save.engineLvl - 1) * 1.45) * engineEff;
      const accel = (v.accel + (save.engineLvl - 1) * 0.045) * engineEff;
      const brakeForce = (v.brakePower + (save.brakeLvl - 1) * 0.06) * (0.55 + tireEff * 0.45);
      const mudFactor = inMud ? Math.min(0.98, (v.mudResist + (save.brakeLvl - 1) * 0.04 + (save.suspLvl - 1) * 0.03) * tireEff) : 1.0;

      const wheelBase = 44 * v.scale;
      const wheelRadius = 13 * v.scale;
      const rideHeight = 16 * v.scale;

      const cosA = Math.cos(car.angle);
      const sinA = Math.sin(car.angle);

      const rearX = car.x - cosA * wheelBase;
      const frontX = car.x + cosA * wheelBase;
      const rearGroundY = getTerrainY(rearX);
      const frontGroundY = getTerrainY(frontX);

      const rearWheelY = car.y + rideHeight - sinA * wheelBase + wheelRadius;
      const frontWheelY = car.y + rideHeight + sinA * wheelBase + wheelRadius;

      const grounded = (rearWheelY >= rearGroundY - 3) || (frontWheelY >= frontGroundY - 3);

      car.vy += 0.48;

      if (grounded) {
        const targetCenterY = (rearGroundY + frontGroundY) * 0.5 - wheelRadius - rideHeight;
        const targetAngle = Math.atan2(frontGroundY - rearGroundY, wheelBase * 2);
        const springK = 0.22 + (save.suspLvl - 1) * 0.025;
        const dy = targetCenterY - car.y;
        car.vy = car.vy * 0.55 + dy * springK;
        car.angle += (targetAngle - car.angle) * 0.22;
        car.angVel = 0;

        // Suspension pitch/squat on acceleration & braking
        const targetSquat = gasPressed ? -0.045 : (brakePressed ? 0.05 : 0);
        car.suspSquat += (targetSquat - car.suspSquat) * 0.18;

        const slope = getTerrainSlope(car.x);
        car.vx += Math.sin(slope) * 0.20;

        if (gasPressed && car.fuel > 0) {
          const effAccel = accel * (inMud ? (0.42 + mudFactor * 0.5) : 1.0) * s.slip * (0.7 + tireEff * 0.3);
          car.vx += effAccel * Math.cos(slope);

          const burnMult = (2.0 - engineEff * 0.7) * (inMud ? 1.35 : 1.0);
          car.fuel -= v.fuelBurn * burnMult;

          const tireWearRate = (inMud ? 0.055 : 0.016) * (selectedSeasonKey === 'winter' ? 1.25 : 1.0);
          const engineWearRate = 0.015 * (v.type === 'truck' || v.type === 'bus' ? 1.2 : 1.0);
          wear.tire = Math.max(5, wear.tire - tireWearRate);
          wear.engine = Math.max(5, wear.engine - engineWearRate);

          const smokeChance = v.exhaust === 'diesel' || v.exhaust === 'tractorDiesel' || v.exhaust === 'twoStroke' ? 0.58 : 0.34;
          if (Math.random() < smokeChance) {
            spawnExhaustSmoke(v, wear, rearX, rearGroundY, cosA, sinA);
          }

          if (inMud && Math.random() < 0.78) {
            particles.push({
              x: rearX - 10, y: rearGroundY - 5,
              vx: -1.6 - Math.random() * 1.4, vy: -2.2 - Math.random() * 2.2,
              life: 1, size: 4 + Math.random() * 4, grow: 0.02, maxSize: 9, color: '#5c3a21'
            });
          } else if (selectedSeasonKey === 'winter' && Math.random() < 0.38) {
            particles.push({
              x: rearX - 10, y: rearGroundY - 4,
              vx: -1.4 - Math.random() * 1.1, vy: -0.9 - Math.random() * 0.8,
              life: 1, size: 3.5 + Math.random() * 2.5, grow: 0.05, maxSize: 7, color: 'rgba(255,255,255,0.75)'
            });
          }
        }

        if (brakePressed) {
          car.vx -= brakeForce * (0.85 + s.slip * 0.15);
          if (Math.abs(car.vx) > 1.5) {
            wear.tire = Math.max(5, wear.tire - 0.025);
          }
        }

        const drag = inMud ? (0.94 + mudFactor * 0.03) : 0.986;
        car.vx *= drag;
        const cappedMax = inMud ? maxSpeed * (0.52 + mudFactor * 0.40) : maxSpeed;
        if (car.vx > cappedMax) car.vx = cappedMax;
        if (car.vx < -4.0) car.vx = -4.0;
      } else {
        car.suspSquat *= 0.9;
        if (gasPressed) car.angVel -= 0.0042;
        if (brakePressed) car.angVel += 0.0042;
        car.angVel *= 0.94;
        car.angle += car.angVel;
      }

      car.x += car.vx;
      car.y += car.vy;
      if (car.x < 90) { car.x = 90; car.vx = 0; }
      car.wheelRot += car.vx / Math.max(8, wheelRadius);

      const newDist = Math.max(car.distanceM, Math.floor((car.x - 180) / 14));
      if (newDist > car.distanceM) {
        car.distanceM = newDist;
        const job = JOBS[selectedJobKey];
        if (!jobCompleted && job.targetM > 0 && car.distanceM >= job.targetM) {
          jobCompleted = true;
          const extra = job.bonusType === v.type ? 40 : 0;
          const totalReward = job.reward + extra;
          save.money += totalReward;
          car.runMoney += totalReward;
          persistSave();
          playSound('win');
        }
        updateContractBar();
      }

      spawnCoinsUpTo(car.x + W + 900);
      spawnMudUpTo(car.x + W + 900);

      for (const c of coins) {
        if (!c.collected && Math.hypot(car.x - c.x, car.y - c.y) < 48) {
          c.collected = true;
          save.money += c.val;
          car.runMoney += c.val;
          persistSave();
          playSound('coin');
        }
      }

      const modStation = ((car.x % 4600) + 4600) % 4600;
      const nearStation = car.x > 1000 && Math.abs(modStation - 2600) < 175;
      document.getElementById('stationBanner').style.display = nearStation ? 'flex' : 'none';

      if (car.fuel <= 0) {
        car.fuel = 0;
        if (Math.abs(car.vx) < 0.25 && grounded) {
          persistSave();
          endGame('BRAK PALIWA W BAKU');
        }
      }

      for (let i = particles.length - 1; i >= 0; i--) {
        const p = particles[i];
        p.x += p.vx;
        p.y += p.vy;
        p.vy *= 0.96;
        p.size = Math.min(p.maxSize || 14, p.size + (p.grow || 0.08));
        p.life -= 0.024;
        if (p.life <= 0) particles.splice(i, 1);
      }

      updateHUD();
    }

    function updateHUD() {
      const wear = getCurrentWear();
      document.getElementById('hudMoney').textContent = save.money;
      document.getElementById('hudDist').textContent = car.distanceM;
      document.getElementById('hudVehicleName').textContent = getCurrentVehicle().name;

      const fuelPct = Math.max(0, Math.min(100, (car.fuel / car.maxFuel) * 100));
      document.getElementById('fuelBar').style.width = fuelPct + '%';

      const tirePct = Math.round(wear.tire);
      const engPct = Math.round(wear.engine);
      document.getElementById('hudTirePct').textContent = tirePct + '%';
      document.getElementById('tireBar').style.width = tirePct + '%';
      document.getElementById('hudEnginePct').textContent = engPct + '%';
      document.getElementById('engineBar').style.width = engPct + '%';
    }

    function endGame(reason) {
      running = false;
      document.getElementById('stationBanner').style.display = 'none';
      save.highScores.push({
        dist: car.distanceM,
        money: car.runMoney,
        veh: getCurrentVehicle().name,
        date: new Date().toLocaleDateString('pl-PL')
      });
      save.highScores.sort((a, b) => b.dist - a.dist);
      save.highScores = save.highScores.slice(0, 5);
      persistSave();

      document.getElementById('gameOverReason').textContent = reason;
      document.getElementById('gameOverSummary').textContent =
        `Przejechałeś ${car.distanceM} m (${getCurrentVehicle().name}) i zdobyłeś ${car.runMoney} zł.`;
      renderHighScores();
      document.getElementById('gameOverOverlay').classList.remove('hidden');
    }

    // --- ULTRA REALISTIC ENVIRONMENT RENDERING ---
    function drawEnvironmentProps(camX, isNight) {
      // 1. Road kilometer posts & roadside posts every 350px
      const postStep = 350;
      const firstPost = Math.floor((camX - 100) / postStep);
      const lastPost = Math.floor((camX + W + 100) / postStep);

      for (let i = firstPost; i <= lastPost; i++) {
        const wx = i * postStep;
        if (wx < 120) continue;
        const sx = wx - camX;
        const gy = getTerrainY(wx);
        const slope = getTerrainSlope(wx);

        ctx.save();
        ctx.translate(sx, gy);
        ctx.rotate(slope * 0.45);

        // Roadside delineator post with reflector
        ctx.fillStyle = isNight ? '#475569' : '#e2e8f0';
        ctx.fillRect(-2, -26, 4, 26);
        ctx.fillStyle = i % 3 === 0 ? '#ef4444' : '#facc15';
        ctx.fillRect(-3, -23, 6, 5);

        // Every 3rd post = distance marker sign
        if (i > 0 && i % 3 === 0) {
          const kmMeters = Math.floor((wx - 180) / 14);
          ctx.fillStyle = '#1e293b';
          ctx.fillRect(10, -44, 44, 18);
          ctx.strokeStyle = '#f8fafc';
          ctx.lineWidth = 1.2;
          ctx.strokeRect(10, -44, 44, 18);
          ctx.fillStyle = '#fef08a';
          ctx.font = 'bold 9px sans-serif';
          ctx.fillText(`${kmMeters}m`, 14, -32);
        }
        ctx.restore();
      }

      // 2. Trees, rural PRL cottages, PKS bus stops & power poles along the route
      const propStep = 520;
      const firstProp = Math.floor((camX - 280) / propStep);
      const lastProp = Math.floor((camX + W + 280) / propStep);

      let prevPole = null;

      for (let i = firstProp; i <= lastProp; i++) {
        const wx = i * propStep + 190;
        if (wx < 220) continue;
        const sx = wx - camX;
        const gy = getTerrainY(wx);
        const modStation = ((wx % 4600) + 4600) % 4600;
        if (Math.abs(modStation - 2600) < 230) continue;

        const kind = Math.abs(i) % 5;
        ctx.save();
        ctx.translate(sx, gy);

        if (kind === 0 || kind === 2) {
          // Layered deciduous/conifer tree adapted to season
          const trunkGrad = ctx.createLinearGradient(-4, 0, 4, 0);
          trunkGrad.addColorStop(0, '#3b1504');
          trunkGrad.addColorStop(0.5, '#6b2c0e');
          trunkGrad.addColorStop(1, '#2b0e02');
          ctx.fillStyle = trunkGrad;
          ctx.fillRect(-4.5, -36, 9, 36);

          if (selectedSeasonKey === 'winter') {
            ctx.fillStyle = isNight ? '#334155' : '#cbd5e1';
            ctx.beginPath(); ctx.arc(0, -44, 21, 0, Math.PI * 2); ctx.fill();
            ctx.fillStyle = isNight ? '#475569' : '#f8fafc';
            ctx.beginPath(); ctx.arc(0, -47, 18, Math.PI, Math.PI * 2); ctx.fill();
            ctx.beginPath(); ctx.arc(-12, -39, 14, 0, Math.PI * 2); ctx.fill();
            ctx.beginPath(); ctx.arc(12, -39, 14, 0, Math.PI * 2); ctx.fill();
          } else {
            const cDark = selectedSeasonKey === 'autumn' ? '#9a3412' : (selectedSeasonKey === 'summer' ? '#14532d' : '#15803d');
            const cMid = selectedSeasonKey === 'autumn' ? '#ea580c' : (selectedSeasonKey === 'summer' ? '#16a34a' : '#22c55e');
            const cHi = selectedSeasonKey === 'autumn' ? '#facc15' : '#4ade80';

            ctx.fillStyle = isNight ? '#0f291a' : cDark;
            ctx.beginPath(); ctx.arc(2, -45, 22, 0, Math.PI * 2); ctx.fill();

            ctx.fillStyle = isNight ? '#14532d' : cMid;
            ctx.beginPath(); ctx.arc(-11, -39, 15, 0, Math.PI * 2); ctx.fill();
            ctx.beginPath(); ctx.arc(11, -39, 15, 0, Math.PI * 2); ctx.fill();
            ctx.beginPath(); ctx.arc(-2, -50, 17, 0, Math.PI * 2); ctx.fill();

            if (!isNight) {
              ctx.fillStyle = cHi;
              ctx.beginPath(); ctx.arc(-6, -54, 7, 0, Math.PI * 2); ctx.fill();
            }
          }
        } else if (kind === 1) {
          // Rural PRL house with chimney, fence & glowing windows at dusk/night
          ctx.fillStyle = isNight ? '#334155' : '#e2e8f0';
          ctx.fillRect(-28, -36, 56, 36);
          ctx.strokeStyle = '#0f172a';
          ctx.lineWidth = 1.5;
          ctx.strokeRect(-28, -36, 56, 36);

          // Chimney
          ctx.fillStyle = '#7f1d1d';
          ctx.fillRect(14, -56, 7, 20);
          ctx.strokeRect(14, -56, 7, 20);

          // Pitched roof
          ctx.fillStyle = selectedSeasonKey === 'winter' ? '#f8fafc' : '#991b1b';
          ctx.beginPath();
          ctx.moveTo(-33, -36); ctx.lineTo(0, -56); ctx.lineTo(33, -36);
          ctx.closePath(); ctx.fill(); ctx.stroke();

          // Door & windows
          ctx.fillStyle = '#451a03';
          ctx.fillRect(-4, -18, 9, 18);

          const winColor = isNight ? '#fde047' : '#38bdf8';
          ctx.fillStyle = winColor;
          ctx.fillRect(-20, -25, 11, 10); ctx.strokeRect(-20, -25, 11, 10);
          ctx.fillRect(10, -25, 11, 10); ctx.strokeRect(10, -25, 11, 10);
        } else if (kind === 3) {
          // Classic PRL PKS Bus Shelter ("Przystanek PKS")
          ctx.fillStyle = '#64748b';
          ctx.fillRect(-24, -40, 4, 40);
          ctx.fillRect(20, -40, 4, 40);
          ctx.fillStyle = '#1e293b';
          ctx.fillRect(-28, -44, 56, 5);
          ctx.fillStyle = 'rgba(186, 230, 253, 0.45)';
          ctx.fillRect(-20, -36, 40, 22);
          // PKS sign pole
          ctx.fillStyle = '#cbd5e1';
          ctx.fillRect(32, -48, 3, 48);
          ctx.fillStyle = '#fef08a';
          ctx.fillRect(24, -56, 19, 10);
          ctx.strokeStyle = '#0f172a'; ctx.lineWidth = 1; ctx.strokeRect(24, -56, 19, 10);
          ctx.fillStyle = '#0f172a';
          ctx.font = 'bold 6px sans-serif';
          ctx.fillText('PKS', 27, -49);
        } else {
          // Wooden telegraph / power pole with sagging wires to previous pole
          ctx.fillStyle = '#57361d';
          ctx.fillRect(-3.5, -66, 7, 66);
          ctx.fillRect(-15, -60, 30, 4);
          ctx.fillStyle = '#38bdf8';
          ctx.fillRect(-12, -64, 4, 4);
          ctx.fillRect(8, -64, 4, 4);

          if (prevPole && Math.abs(sx - prevPole.sx) < 700) {
            ctx.save();
            ctx.strokeStyle = isNight ? 'rgba(148, 163, 184, 0.35)' : 'rgba(30, 41, 59, 0.45)';
            ctx.lineWidth = 1.1;
            const dx = prevPole.sx - sx;
            const dy = prevPole.gy - gy;
            ctx.beginPath();
            ctx.moveTo(-10, -62);
            ctx.quadraticCurveTo(dx * 0.5, dy - 52, dx - 10, dy - 62);
            ctx.moveTo(10, -62);
            ctx.quadraticCurveTo(dx * 0.5, dy - 52, dx + 10, dy - 62);
            ctx.stroke();
            ctx.restore();
          }
          prevPole = { sx, gy };
        }

        ctx.restore();
      }
    }

    function drawScene() {
      const s = SEASONS[selectedSeasonKey];
      const tm = TIME_MODES[timeIndex];
      const isNight = tm.dark > 0.45;

      const skyGrad = ctx.createLinearGradient(0, 0, 0, H);
      skyGrad.addColorStop(0, tm.dark > 0.55 ? '#020617' : s.skyTop);
      skyGrad.addColorStop(1, tm.dark > 0.55 ? '#0f172a' : s.skyBot);
      ctx.fillStyle = skyGrad;
      ctx.fillRect(0, 0, W, H);

      // Sun or Moon
      const celestialX = W * 0.76 - ((car.x * 0.008) % (W * 0.55));
      const celestialY = H * tm.sunY;
      ctx.save();
      if (isNight) {
        ctx.fillStyle = 'rgba(241, 245, 249, 0.92)';
        ctx.beginPath(); ctx.arc(celestialX, celestialY, 22, 0, Math.PI * 2); ctx.fill();
      } else {
        const sunGlow = ctx.createRadialGradient(celestialX, celestialY, 8, celestialX, celestialY, 68);
        sunGlow.addColorStop(0, 'rgba(254, 240, 138, 0.95)');
        sunGlow.addColorStop(0.4, 'rgba(253, 224, 71, 0.35)');
        sunGlow.addColorStop(1, 'rgba(253, 224, 71, 0)');
        ctx.fillStyle = sunGlow;
        ctx.beginPath(); ctx.arc(celestialX, celestialY, 68, 0, Math.PI * 2); ctx.fill();
      }
      ctx.restore();

      if (tm.stars) {
        ctx.fillStyle = 'rgba(255,255,255,0.78)';
        for (let i = 0; i < 45; i++) {
          const sx = ((i * 193 + car.x * 0.02) % W + W) % W;
          const sy = (i * 83) % (H * 0.42);
          ctx.fillRect(sx, sy, 2, 2);
        }
      }

      // Far parallax ridge
      ctx.fillStyle = tm.dark > 0.5 ? '#0f172a' : s.hillFar;
      ctx.beginPath();
      ctx.moveTo(0, H);
      for (let sx = 0; sx <= W + 40; sx += 40) {
        const wx = sx + car.x * 0.09;
        const hy = H * 0.50 + Math.sin(wx * 0.0011 + 0.7) * 52;
        ctx.lineTo(sx, hy);
      }
      ctx.lineTo(W, H);
      ctx.fill();

      // Mid parallax hills
      ctx.fillStyle = tm.dark > 0.5 ? '#1e293b' : s.hill;
      ctx.beginPath();
      ctx.moveTo(0, H);
      for (let sx = 0; sx <= W + 40; sx += 40) {
        const wx = sx + car.x * 0.18;
        const hy = H * 0.57 + Math.sin(wx * 0.0018) * 38;
        ctx.lineTo(sx, hy);
      }
      ctx.lineTo(W, H);
      ctx.fill();

      const camX = car.x - W * 0.28;

      // Environment props behind road
      drawEnvironmentProps(camX, isNight);

      // CPN stations
      const firstStationIdx = Math.max(0, Math.floor((camX - 400) / 4600));
      const lastStationIdx = Math.floor((camX + W + 400) / 4600);
      for (let idx = firstStationIdx; idx <= lastStationIdx; idx++) {
        const stWorldX = idx * 4600 + 2600;
        drawCPNStation(stWorldX - camX, getTerrainY(stWorldX));
      }

      // Ground fill
      ctx.beginPath();
      ctx.moveTo(0, H);
      for (let sx = 0; sx <= W + 16; sx += 16) {
        ctx.lineTo(sx, getTerrainY(camX + sx));
      }
      ctx.lineTo(W, H);
      ctx.fillStyle = tm.dark > 0.5 ? '#14261c' : s.ground;
      ctx.fill();

      // Road shoulder / base edge
      ctx.beginPath();
      for (let sx = 0; sx <= W + 16; sx += 16) {
        const y = getTerrainY(camX + sx) + 6;
        if (sx === 0) ctx.moveTo(sx, y);
        else ctx.lineTo(sx, y);
      }
      ctx.lineWidth = 6;
      ctx.strokeStyle = selectedSeasonKey === 'winter' ? '#94a3b8' : '#1e293b';
      ctx.stroke();

      // Road asphalt surface + center dashed line
      ctx.beginPath();
      for (let sx = 0; sx <= W + 16; sx += 16) {
        const y = getTerrainY(camX + sx);
        if (sx === 0) ctx.moveTo(sx, y);
        else ctx.lineTo(sx, y);
      }
      ctx.lineWidth = 15;
      ctx.strokeStyle = selectedSeasonKey === 'winter' ? '#cbd5e1' : '#334155';
      ctx.stroke();

      ctx.save();
      ctx.setLineDash([16, 16]);
      ctx.beginPath();
      for (let sx = 0; sx <= W + 16; sx += 16) {
        const y = getTerrainY(camX + sx);
        if (sx === 0) ctx.moveTo(sx, y);
        else ctx.lineTo(sx, y);
      }
      ctx.lineWidth = 2;
      ctx.strokeStyle = selectedSeasonKey === 'winter' ? '#64748b' : 'rgba(254, 240, 138, 0.60)';
      ctx.stroke();
      ctx.restore();

      // Mud patches
      for (const m of mudPatches) {
        if (m.startX + m.width < camX || m.startX > camX + W) continue;
        ctx.beginPath();
        for (let wx = m.startX; wx <= m.startX + m.width; wx += 12) {
          const sx = wx - camX;
          const y = getTerrainY(wx);
          if (wx === m.startX) ctx.moveTo(sx, y);
          else ctx.lineTo(sx, y);
        }
        ctx.lineWidth = 15;
        ctx.strokeStyle = '#5c3a21';
        ctx.stroke();
      }

      // Coins
      for (const c of coins) {
        if (c.collected) continue;
        const sx = c.x - camX;
        if (sx < -30 || sx > W + 30) continue;
        ctx.save();
        ctx.translate(sx, c.y);
        ctx.fillStyle = '#facc15';
        ctx.beginPath();
        ctx.arc(0, 0, 11, 0, Math.PI * 2);
        ctx.fill();
        ctx.strokeStyle = '#b45309';
        ctx.lineWidth = 2;
        ctx.stroke();
        ctx.fillStyle = '#78350f';
        ctx.font = 'bold 10px sans-serif';
        ctx.textAlign = 'center';
        ctx.textBaseline = 'middle';
        ctx.fillText('zł', 0, 1);
        ctx.restore();
      }

      // Exhaust & terrain particles
      for (const p of particles) {
        ctx.save();
        ctx.globalAlpha = Math.max(0, p.life);
        ctx.fillStyle = p.color;
        ctx.beginPath();
        ctx.arc(p.x - camX, p.y, p.size, 0, Math.PI * 2);
        ctx.fill();
        ctx.restore();
      }

      // Vehicle
      drawVehicle(car.x - camX, car.y, car.angle + car.suspSquat, tm.dark > 0.3);

      // Ambient darkness overlay
      if (tm.dark > 0) {
        ctx.fillStyle = `rgba(2, 6, 23, ${tm.dark * 0.42})`;
        ctx.fillRect(0, 0, W, H);
      }
    }

    function drawCPNStation(sx, gy) {
      if (sx < -220 || sx > W + 220) return;
      ctx.save();
      ctx.translate(sx, gy);
      ctx.fillStyle = '#cbd5e1';
      ctx.fillRect(-70, -88, 7, 88);
      ctx.fillRect(63, -88, 7, 88);
      ctx.fillStyle = '#dc2626';
      ctx.fillRect(-90, -104, 180, 18);
      ctx.fillStyle = '#fef08a';
      ctx.font = '900 13px sans-serif';
      ctx.textAlign = 'center';
      ctx.fillText('CPN • ZDRAPKI & PALIWO', 0, -91);
      ctx.fillStyle = '#ef4444';
      ctx.fillRect(-30, -34, 16, 34);
      ctx.fillRect(14, -34, 16, 34);
      ctx.restore();
    }

    // --- ULTRA REALISTIC RETRO VEHICLE SILHOUETTES ---
    function drawVehicle(sx, sy, angle, lightsOn) {
      const v = getCurrentVehicle();
      const pal = getPaintPalette();

      ctx.save();
      ctx.translate(sx, sy);
      ctx.rotate(angle);
      ctx.scale(v.scale, v.scale);

      // Volumetric headlight beam + glow
      if (lightsOn) {
        const grad = ctx.createLinearGradient(44, 0, 225, 8);
        grad.addColorStop(0, 'rgba(254, 249, 195, 0.62)');
        grad.addColorStop(0.5, 'rgba(254, 240, 138, 0.22)');
        grad.addColorStop(1, 'rgba(254, 249, 195, 0)');
        ctx.fillStyle = grad;
        ctx.beginPath();
        ctx.moveTo(44, -2);
        ctx.lineTo(225, -30);
        ctx.lineTo(225, 34);
        ctx.closePath();
        ctx.fill();
      }

      // Ground contact shadow
      ctx.fillStyle = 'rgba(2, 6, 23, 0.38)';
      ctx.beginPath();
      ctx.ellipse(0, 19, 46, 5.5, 0, 0, Math.PI * 2);
      ctx.fill();

      // Body paint gradient for depth
      const bodyGrad = ctx.createLinearGradient(0, -24, 0, 12);
      bodyGrad.addColorStop(0, pal.light || pal.color);
      bodyGrad.addColorStop(0.45, pal.color);
      bodyGrad.addColorStop(1, pal.dark || pal.color);

      const glassGrad = ctx.createLinearGradient(-25, -18, 25, 0);
      glassGrad.addColorStop(0, '#e0f2fe');
      glassGrad.addColorStop(0.5, '#7dd3fc');
      glassGrad.addColorStop(1, '#38bdf8');

      ctx.strokeStyle = '#0f172a';
      ctx.lineWidth = 1.7;

      if (v.id === 'beskid') {
        ctx.fillStyle = bodyGrad;
        ctx.beginPath();
        ctx.moveTo(-48, 8); ctx.lineTo(-49, -9); ctx.lineTo(-30, -19);
        ctx.lineTo(10, -19); ctx.lineTo(48, 2); ctx.lineTo(48, 8);
        ctx.closePath();
        ctx.fill(); ctx.stroke();

        // Glass + B pillar + wiper
        ctx.fillStyle = glassGrad;
        ctx.beginPath();
        ctx.moveTo(-27, -15); ctx.lineTo(9, -15); ctx.lineTo(38, 0); ctx.lineTo(-27, 0);
        ctx.closePath(); ctx.fill(); ctx.stroke();
        ctx.fillStyle = pal.color;
        ctx.fillRect(-10, -15, 4, 15);
        ctx.strokeStyle = '#1e293b'; ctx.lineWidth = 1.1;
        ctx.beginPath(); ctx.moveTo(29, -1); ctx.lineTo(20, -10); ctx.stroke();
        ctx.strokeStyle = '#0f172a'; ctx.lineWidth = 1.7;

        // Side mirror, plate & lights
        ctx.fillStyle = '#1e293b'; ctx.fillRect(12, -4, 5, 3);
        ctx.fillStyle = '#f8fafc'; ctx.fillRect(-12, 3, 18, 4.5);
        ctx.fillStyle = lightsOn ? '#fef9c3' : '#fef08a'; ctx.fillRect(43, 0, 4, 4);
        ctx.fillStyle = brakePressed ? '#ff1e1e' : '#b91c1c'; ctx.fillRect(-48, -3, 4, 6);
      } else if (v.id === 'maluch') {
        ctx.fillStyle = bodyGrad;
        ctx.beginPath();
        ctx.moveTo(-40, 8); ctx.lineTo(-40, -11); ctx.lineTo(-26, -20);
        ctx.lineTo(10, -20); ctx.lineTo(24, -9); ctx.lineTo(40, -5); ctx.lineTo(40, 8);
        ctx.closePath();
        ctx.fill(); ctx.stroke();

        ctx.fillStyle = glassGrad;
        ctx.fillRect(-22, -16, 28, 8);

        // Rear louvers
        ctx.strokeStyle = '#1e293b';
        for (let ly = -6; ly <= 2; ly += 4) {
          ctx.beginPath(); ctx.moveTo(-36, ly); ctx.lineTo(-28, ly); ctx.stroke();
        }
        // Chrome bumpers, mirror & lights
        ctx.fillStyle = '#e2e8f0';
        ctx.fillRect(-43, 4, 5, 3);
        ctx.fillRect(38, 4, 5, 3);
        ctx.fillStyle = '#1e293b'; ctx.fillRect(8, -11, 4, 3);
        ctx.fillStyle = brakePressed ? '#ff1e1e' : '#dc2626'; ctx.fillRect(-40, -2, 3, 5);
        ctx.fillStyle = '#fef08a'; ctx.fillRect(37, -2, 3, 5);
      } else if (v.id === 'mikrus') {
        ctx.fillStyle = bodyGrad;
        ctx.beginPath();
        ctx.roundRect(-36, -15, 72, 23, 9);
        ctx.fill(); ctx.stroke();
        ctx.fillStyle = glassGrad;
        ctx.beginPath();
        ctx.roundRect(-18, -12, 34, 9, 4);
        ctx.fill(); ctx.stroke();
        ctx.fillStyle = '#e2e8f0'; ctx.fillRect(-38, 4, 76, 2.5);
        ctx.fillStyle = '#fef08a'; ctx.beginPath(); ctx.arc(33, 1, 3, 0, Math.PI * 2); ctx.fill();
        ctx.fillStyle = brakePressed ? '#ff1e1e' : '#dc2626'; ctx.beginPath(); ctx.arc(-33, 1, 3, 0, Math.PI * 2); ctx.fill();
      } else if (v.id === 'syrena') {
        ctx.fillStyle = bodyGrad;
        ctx.beginPath();
        ctx.moveTo(-43, 8); ctx.lineTo(-43, -9); ctx.lineTo(-24, -18);
        ctx.lineTo(12, -18); ctx.lineTo(32, -7); ctx.lineTo(45, 0); ctx.lineTo(45, 8);
        ctx.closePath();
        ctx.fill(); ctx.stroke();

        ctx.fillStyle = glassGrad;
        ctx.fillRect(-20, -14, 28, 8);
        // Chrome grille & trim
        ctx.fillStyle = '#f1f5f9';
        ctx.fillRect(36, -3, 7, 5);
        ctx.fillRect(-45, 4, 92, 2.5);
        ctx.fillStyle = brakePressed ? '#ff1e1e' : '#dc2626'; ctx.fillRect(-43, -2, 4, 5);
      } else if (v.id === 'warszawa') {
        ctx.fillStyle = bodyGrad;
        ctx.beginPath();
        ctx.moveTo(-48, 8); ctx.lineTo(-48, -8); ctx.lineTo(-28, -21);
        ctx.lineTo(8, -21); ctx.lineTo(24, -8); ctx.lineTo(48, -3); ctx.lineTo(48, 8);
        ctx.closePath();
        ctx.fill(); ctx.stroke();

        ctx.fillStyle = glassGrad;
        ctx.fillRect(-24, -16, 30, 8);
        // B pillar & chrome bumpers
        ctx.fillStyle = pal.color;
        ctx.fillRect(-9, -16, 4, 8);
        ctx.fillStyle = '#f8fafc';
        ctx.fillRect(-52, 3, 7, 4);
        ctx.fillRect(45, 3, 7, 4);
        ctx.fillStyle = '#e2e8f0'; ctx.fillRect(-44, 0, 88, 2);
        ctx.fillStyle = brakePressed ? '#ff1e1e' : '#dc2626'; ctx.fillRect(-48, -3, 4, 5);
      } else if (v.id === 'polonez') {
        ctx.fillStyle = bodyGrad;
        ctx.beginPath();
        ctx.moveTo(-47, 8); ctx.lineTo(-47, -10); ctx.lineTo(-24, -19);
        ctx.lineTo(14, -19); ctx.lineTo(36, -8); ctx.lineTo(47, -5); ctx.lineTo(47, 8);
        ctx.closePath();
        ctx.fill(); ctx.stroke();

        ctx.fillStyle = glassGrad;
        ctx.beginPath();
        ctx.moveTo(-21, -15); ctx.lineTo(12, -15); ctx.lineTo(28, -7); ctx.lineTo(-21, -7);
        ctx.closePath(); ctx.fill(); ctx.stroke();

        // Side moulding & rear light strip
        ctx.fillStyle = '#1e293b';
        ctx.fillRect(-44, 1, 88, 2.5);
        ctx.fillStyle = brakePressed ? '#ff1e1e' : '#dc2626'; ctx.fillRect(-47, -5, 4, 6);
        ctx.fillStyle = '#fef08a'; ctx.fillRect(42, -3, 4, 4);
      } else if (v.id === 'traktor') {
        // Cab
        ctx.fillStyle = '#1d4ed8';
        ctx.beginPath();
        ctx.roundRect(-38, -22, 26, 28, 4);
        ctx.fill(); ctx.stroke();
        ctx.fillStyle = glassGrad;
        ctx.fillRect(-34, -18, 18, 9);
        // Hood & chassis
        ctx.fillStyle = bodyGrad;
        ctx.fillRect(-12, -11, 48, 17);
        ctx.strokeRect(-12, -11, 48, 17);
        // Vertical exhaust pipe
        ctx.fillStyle = '#334155';
        ctx.fillRect(24, -25, 6, 14);
        // Straw bales when job active
        if (selectedJobKey === 'bales') {
          ctx.fillStyle = '#eab308';
          ctx.fillRect(-76, -14, 28, 22); ctx.strokeRect(-76, -14, 28, 22);
          ctx.fillRect(-108, -14, 28, 22); ctx.strokeRect(-108, -14, 28, 22);
        }
      } else if (v.id === 'ogorek' || v.id === 'ikarus') {
        ctx.fillStyle = v.id === 'ogorek' ? bodyGrad : '#eab308';
        ctx.beginPath();
        if (v.id === 'ogorek') {
          ctx.roundRect(-56, -24, 112, 32, 13);
        } else {
          ctx.roundRect(-58, -24, 116, 32, 4);
        }
        ctx.fill(); ctx.stroke();

        // Roof AC / light bar
        ctx.fillStyle = '#94a3b8';
        ctx.fillRect(-24, -27, 48, 3);

        // Mid stripe
        ctx.fillStyle = v.id === 'ogorek' ? '#f8fafc' : '#dc2626';
        ctx.fillRect(-54, -4, 108, 4);

        // Windows + door divisions
        ctx.fillStyle = glassGrad;
        for (let wx = -45; wx <= 35; wx += 20) {
          ctx.fillRect(wx, -18, 14, 10);
          ctx.strokeRect(wx, -18, 14, 10);
        }
        ctx.fillStyle = brakePressed ? '#ff1e1e' : '#dc2626'; ctx.fillRect(-56, -2, 4, 6);
        ctx.fillStyle = '#fef08a'; ctx.fillRect(52, -2, 4, 6);
      } else {
        // Trucks: Star, Jelcz, Żuk, Nysa
        ctx.fillStyle = '#92400e';
        ctx.fillRect(-56, -22, 62, 28);
        ctx.strokeRect(-56, -22, 62, 28);

        // Cargo board slats & fuel tank
        ctx.strokeStyle = '#78350f';
        ctx.beginPath();
        ctx.moveTo(-56, -12); ctx.lineTo(6, -12);
        ctx.moveTo(-25, -22); ctx.lineTo(-25, 6);
        ctx.stroke();
        ctx.strokeStyle = '#0f172a';

        if (selectedJobKey === 'grain') {
          ctx.fillStyle = '#fde047';
          ctx.fillRect(-54, -26, 58, 5);
        }

        // Cab
        ctx.fillStyle = bodyGrad;
        ctx.fillRect(8, -19, 36, 25);
        ctx.strokeRect(8, -19, 36, 25);
        ctx.fillStyle = glassGrad;
        ctx.fillRect(22, -15, 16, 10);
        ctx.strokeRect(22, -15, 16, 10);

        // Fuel tank under chassis
        ctx.fillStyle = '#64748b';
        ctx.fillRect(-8, 3, 14, 6);
        ctx.strokeRect(-8, 3, 14, 6);

        ctx.fillStyle = brakePressed ? '#ff1e1e' : '#dc2626'; ctx.fillRect(-56, -3, 4, 6);
        ctx.fillStyle = '#fef08a'; ctx.fillRect(41, -3, 4, 5);
      }

      // Wheels with tire tread & hubcaps
      const rearR = v.id === 'traktor' ? 15 : (v.type === 'truck' || v.type === 'bus' ? 13 : 11);
      const frontR = v.id === 'traktor' ? 9 : (v.type === 'truck' || v.type === 'bus' ? 12 : 11);
      drawWheel(-32, 12, rearR, car.wheelRot);
      drawWheel(32, 12, frontR, car.wheelRot);

      ctx.restore();
    }

    function drawWheel(wx, wy, r, rot) {
      ctx.save();
      ctx.translate(wx, wy);
      ctx.rotate(rot);
      ctx.fillStyle = '#111827';
      ctx.beginPath(); ctx.arc(0, 0, r, 0, Math.PI * 2); ctx.fill();
      ctx.strokeStyle = '#030712'; ctx.lineWidth = 1.5; ctx.stroke();

      // Tire tread notches
      ctx.strokeStyle = '#374151';
      ctx.lineWidth = 1.6;
      for (let i = 0; i < 8; i++) {
        const a = (i * Math.PI) / 4;
        ctx.beginPath();
        ctx.moveTo(Math.cos(a) * (r * 0.72), Math.sin(a) * (r * 0.72));
        ctx.lineTo(Math.cos(a) * (r * 0.96), Math.sin(a) * (r * 0.96));
        ctx.stroke();
      }

      // Hubcap
      ctx.fillStyle = '#cbd5e1';
      ctx.beginPath(); ctx.arc(0, 0, r * 0.50, 0, Math.PI * 2); ctx.fill();
      ctx.strokeStyle = '#334155';
      ctx.lineWidth = 1.8;
      ctx.beginPath(); ctx.moveTo(-r * 0.42, 0); ctx.lineTo(r * 0.42, 0); ctx.stroke();
      ctx.beginPath(); ctx.moveTo(0, -r * 0.42); ctx.lineTo(0, r * 0.42); ctx.stroke();
      ctx.restore();
    }

    // --- LOOP ---
    let lastTime = performance.now();
    function loop(now) {
      const dt = Math.min(0.05, (now - lastTime) / 1000);
      lastTime = now;
      updatePhysics(dt);
      drawScene();
      requestAnimationFrame(loop);
    }

    // --- UI: HIGH SCORES ---
    function renderHighScores() {
      const lists = [document.getElementById('highScoresList'), document.getElementById('gameOverScoresList')];
      for (const el of lists) {
        if (!save.highScores.length) {
          el.innerHTML = '<div class="score-row"><span>Brak zapisanych przejazdów — ruszaj w trasę!</span></div>';
        } else {
          el.innerHTML = save.highScores.map((s, i) =>
            `<div class="score-row"><span>#${i + 1} • ${s.dist} m (${s.veh})</span><span>+${s.money} zł</span></div>`
          ).join('');
        }
      }
    }

    // --- UI: GARAGE & SERVICE ---
    function refreshGarageUI() {
      const wear = getCurrentWear();
      const tirePct = Math.round(wear.tire);
      const engPct = Math.round(wear.engine);

      document.getElementById('garageMoney').textContent = save.money;
      document.getElementById('garageTirePct').textContent = tirePct + '%';
      document.getElementById('garageEnginePct').textContent = engPct + '%';

      const tireCost = 45;
      const engServiceCost = 60;

      const btnTires = document.getElementById('replaceTiresBtn');
      btnTires.disabled = tirePct >= 99 || save.money < tireCost;
      btnTires.textContent = tirePct >= 99 ? 'Nowe opony' : `Nowe opony (${tireCost} zł)`;

      const btnService = document.getElementById('serviceEngineBtn');
      btnService.disabled = engPct >= 99 || save.money < engServiceCost;
      btnService.textContent = engPct >= 99 ? 'Stan idealny' : `Remont (${engServiceCost} zł)`;

      document.getElementById('lvlEngine').textContent = save.engineLvl;
      document.getElementById('lvlBrake').textContent = save.brakeLvl;
      document.getElementById('lvlSusp').textContent = save.suspLvl;

      const engCost = save.engineLvl * 100;
      const brkCost = save.brakeLvl * 90;
      const suspCost = save.suspLvl * 85;

      const btnEng = document.getElementById('buyEngineBtn');
      btnEng.textContent = save.engineLvl >= 5 ? 'MAX' : `${engCost} zł`;
      btnEng.disabled = save.engineLvl >= 5 || save.money < engCost;

      const btnBrk = document.getElementById('buyBrakeBtn');
      btnBrk.textContent = save.brakeLvl >= 5 ? 'MAX' : `${brkCost} zł`;
      btnBrk.disabled = save.brakeLvl >= 5 || save.money < brkCost;

      const btnSusp = document.getElementById('buySuspBtn');
      btnSusp.textContent = save.suspLvl >= 5 ? 'MAX' : `${suspCost} zł`;
      btnSusp.disabled = save.suspLvl >= 5 || save.money < suspCost;

      const listEl = document.getElementById('vehicleList');
      listEl.innerHTML = VEHICLES.map(v => {
        const owned = save.ownedVehicles.includes(v.id);
        const selected = save.selectedVehicle === v.id;
        const w = ensureVehicleWear(v.id);
        let btnHtml = '';
        if (selected) {
          btnHtml = `<button class="buy-btn active-veh" disabled>WYBRANY</button>`;
        } else if (owned) {
          btnHtml = `<button class="buy-btn select-mode" data-select="${v.id}">Wsiądź</button>`;
        } else {
          btnHtml = `<button class="buy-btn" data-buy="${v.id}" ${save.money < v.price ? 'disabled' : ''}>Kup (${v.price} zł)</button>`;
        }
        return `
          <div class="vehicle-card ${selected ? 'selected' : ''}">
            <div class="card-info">
              <h4>${v.name}</h4>
              <p>${v.desc}</p>
              ${owned ? `<span class="cond-pill">🛞 Opony: ${Math.round(w.tire)}% • ⚙️ Silnik: ${Math.round(w.engine)}%</span>` : ''}
            </div>
            ${btnHtml}
          </div>
        `;
      }).join('');

      listEl.querySelectorAll('[data-select]').forEach(btn => {
        btn.addEventListener('click', () => {
          save.selectedVehicle = btn.dataset.select;
          ensureVehicleWear(save.selectedVehicle);
          car.maxFuel = computeMaxFuel();
          car.fuel = car.maxFuel;
          persistSave(); playSound('buy'); refreshGarageUI(); updateHUD(); updateContractBar();
        });
      });

      listEl.querySelectorAll('[data-buy]').forEach(btn => {
        btn.addEventListener('click', () => {
          const v = VEHICLES.find(x => x.id === btn.dataset.buy);
          if (v && save.money >= v.price && !save.ownedVehicles.includes(v.id)) {
            save.money -= v.price;
            save.ownedVehicles.push(v.id);
            save.selectedVehicle = v.id;
            ensureVehicleWear(v.id);
            car.maxFuel = computeMaxFuel();
            car.fuel = car.maxFuel;
            persistSave(); playSound('buy'); refreshGarageUI(); updateHUD(); updateContractBar();
          }
        });
      });

      const paintEl = document.getElementById('paintGrid');
      paintEl.innerHTML = PAINTS.map(p => `
        <button class="paint-btn ${save.paint === p.color ? 'selected' : ''}" data-color="${p.color}">
          <span class="swatch" style="background:${p.color}"></span>
          <span>${p.name}</span>
        </button>
      `).join('');
      paintEl.querySelectorAll('.paint-btn').forEach(b => {
        b.addEventListener('click', () => {
          save.paint = b.dataset.color;
          persistSave(); playSound('buy'); refreshGarageUI();
        });
      });
    }

    document.getElementById('replaceTiresBtn').addEventListener('click', () => {
      const wear = getCurrentWear();
      if (save.money >= 45 && wear.tire < 99) {
        save.money -= 45;
        wear.tire = 100;
        persistSave(); playSound('buy'); refreshGarageUI(); updateHUD();
      }
    });

    document.getElementById('serviceEngineBtn').addEventListener('click', () => {
      const wear = getCurrentWear();
      if (save.money >= 60 && wear.engine < 99) {
        save.money -= 60;
        wear.engine = 100;
        persistSave(); playSound('buy'); refreshGarageUI(); updateHUD();
      }
    });

    document.getElementById('buyEngineBtn').addEventListener('click', () => {
      const c = save.engineLvl * 100;
      if (save.engineLvl < 5 && save.money >= c) { save.money -= c; save.engineLvl++; persistSave(); playSound('buy'); refreshGarageUI(); updateHUD(); }
    });
    document.getElementById('buyBrakeBtn').addEventListener('click', () => {
      const c = save.brakeLvl * 90;
      if (save.brakeLvl < 5 && save.money >= c) { save.money -= c; save.brakeLvl++; persistSave(); playSound('buy'); refreshGarageUI(); updateHUD(); }
    });
    document.getElementById('buySuspBtn').addEventListener('click', () => {
      const c = save.suspLvl * 85;
      if (save.suspLvl < 5 && save.money >= c) {
        save.money -= c; save.suspLvl++; car.maxFuel = computeMaxFuel(); car.fuel = car.maxFuel;
        persistSave(); playSound('buy'); refreshGarageUI(); updateHUD();
      }
    });

    // --- UI: SEASON & JOB SELECTORS ---
    document.querySelectorAll('.season-btn').forEach(btn => {
      btn.addEventListener('click', () => {
        document.querySelectorAll('.season-btn').forEach(b => b.classList.remove('active'));
        btn.classList.add('active');
        selectedSeasonKey = btn.dataset.season;
        updateContractBar();
      });
    });

    document.querySelectorAll('.job-btn').forEach(btn => {
      btn.addEventListener('click', () => {
        document.querySelectorAll('.job-btn').forEach(b => b.classList.remove('active'));
        btn.classList.add('active');
        selectedJobKey = btn.dataset.job;
        updateContractBar();
      });
    });

    // --- STATION & SCRATCHCARDS ---
    const SCRATCH_TIERS = [
      { cost: 15, prizes: [0, 0, 15, 25, 40, 60] },
      { cost: 35, prizes: [0, 20, 40, 70, 100, 140] },
      { cost: 70, prizes: [0, 40, 80, 140, 200, 280] }
    ];
    let selectedTier = 0;
    let activeCard = null;
    const sCanvas = document.getElementById('scratchCanvas');
    const sCtx = sCanvas.getContext('2d');
    let isScratching = false;

    function resetScratchLayer(locked) {
      sCtx.globalCompositeOperation = 'source-over';
      sCtx.fillStyle = locked ? '#475569' : '#94a3b8';
      sCtx.fillRect(0, 0, sCanvas.width, sCanvas.height);
      sCtx.fillStyle = '#0f172a';
      sCtx.font = '900 17px sans-serif';
      sCtx.textAlign = 'center';
      sCtx.fillText(locked ? 'KUP ZDRAPKĘ PONIŻEJ' : 'ZDRAP PALCEM TUTAJ!', sCanvas.width / 2, sCanvas.height / 2 + 5);
    }

    function refreshStationUI() {
      document.getElementById('stationMoney').textContent = save.money;
      const fuelPct = Math.round((car.fuel / car.maxFuel) * 100);
      document.getElementById('stationFuelPct').textContent = fuelPct + '%';
      const btn = document.getElementById('refuelBtn');
      btn.disabled = fuelPct >= 100 || save.money < 25;
      btn.textContent = fuelPct >= 100 ? 'Bak pełny' : 'Zatankuj (25 zł)';
    }

    document.querySelectorAll('.scratch-tab').forEach(tab => {
      tab.addEventListener('click', () => {
        document.querySelectorAll('.scratch-tab').forEach(t => t.classList.remove('active'));
        tab.classList.add('active');
        selectedTier = Number(tab.dataset.tier);
      });
    });

    document.getElementById('buyScratchBtn').addEventListener('click', () => {
      const tier = SCRATCH_TIERS[selectedTier];
      if (save.money < tier.cost) return;
      save.money -= tier.cost;
      persistSave(); refreshStationUI(); updateHUD();
      const prize = tier.prizes[Math.floor(Math.random() * tier.prizes.length)];
      activeCard = { prize, claimed: false };
      document.getElementById('scratchPrizeText').textContent = `${prize} zł`;
      document.getElementById('scratchSubText').textContent = prize > 0 ? 'Wygrana naliczona po zdrapaniu!' : 'Pusty los — spróbuj kolejnego!';
      resetScratchLayer(false);
    });

    function claimCard() {
      if (activeCard && !activeCard.claimed) {
        activeCard.claimed = true;
        if (activeCard.prize > 0) {
          save.money += activeCard.prize; car.runMoney += activeCard.prize;
          persistSave(); playSound('win'); refreshStationUI(); updateHUD();
        }
      }
    }

    function scratchAt(cx, cy) {
      if (!activeCard) return;
      const rect = sCanvas.getBoundingClientRect();
      const x = ((cx - rect.left) / rect.width) * sCanvas.width;
      const y = ((cy - rect.top) / rect.height) * sCanvas.height;
      sCtx.globalCompositeOperation = 'destination-out';
      sCtx.beginPath(); sCtx.arc(x, y, 22, 0, Math.PI * 2); sCtx.fill();
      claimCard();
    }

    sCanvas.addEventListener('mousedown', (e) => { isScratching = true; scratchAt(e.clientX, e.clientY); });
    window.addEventListener('mouseup', () => { isScratching = false; });
    sCanvas.addEventListener('mousemove', (e) => { if (isScratching) scratchAt(e.clientX, e.clientY); });
    sCanvas.addEventListener('touchstart', (e) => { e.preventDefault(); isScratching = true; scratchAt(e.touches[0].clientX, e.touches[0].clientY); }, { passive: false });
    sCanvas.addEventListener('touchmove', (e) => { e.preventDefault(); if (isScratching) scratchAt(e.touches[0].clientX, e.touches[0].clientY); }, { passive: false });

    document.getElementById('revealScratchBtn').addEventListener('click', () => {
      if (!activeCard) return;
      sCtx.clearRect(0, 0, sCanvas.width, sCanvas.height);
      claimCard();
    });

    document.getElementById('refuelBtn').addEventListener('click', () => {
      if (save.money >= 25 && car.fuel < car.maxFuel) {
        save.money -= 25; car.fuel = car.maxFuel;
        persistSave(); playSound('buy'); refreshStationUI(); updateHUD();
      }
    });

    // --- NAVIGATION ---
    document.getElementById('startGameBtn').addEventListener('click', () => {
      document.getElementById('startOverlay').classList.add('hidden');
      resetRun();
      running = true; paused = false;
    });

    document.getElementById('restartBtn').addEventListener('click', () => {
      document.getElementById('gameOverOverlay').classList.add('hidden');
      document.getElementById('startOverlay').classList.remove('hidden');
      resetRun();
    });

    function openGarage() { paused = true; refreshGarageUI(); document.getElementById('garageOverlay').classList.remove('hidden'); }
    document.getElementById('openGarageBtn').addEventListener('click', openGarage);
    document.getElementById('startGarageBtn').addEventListener('click', openGarage);
    document.getElementById('gameOverGarageBtn').addEventListener('click', () => {
      document.getElementById('gameOverOverlay').classList.add('hidden');
      openGarage();
    });
    document.getElementById('closeGarageBtn').addEventListener('click', () => {
      document.getElementById('garageOverlay').classList.add('hidden');
      if (running) paused = false;
    });

    document.getElementById('enterStationBtn').addEventListener('click', () => {
      paused = true; car.vx = 0; activeCard = null;
      resetScratchLayer(true); refreshStationUI();
      document.getElementById('stationOverlay').classList.remove('hidden');
    });
    document.getElementById('closeStationBtn').addEventListener('click', () => {
      document.getElementById('stationOverlay').classList.add('hidden');
      paused = false;
    });

    // Init
    renderHighScores();
    resetRun();
    requestAnimationFrame(loop);
  </script>
</body>
</html>

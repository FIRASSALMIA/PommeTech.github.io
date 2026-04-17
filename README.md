[index.html](https://github.com/user-attachments/files/26820799/index.html)
HI
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>PommeTech - Smart Irrigation</title>
  <meta name="description" content="PommeTech - Système d'irrigation intelligente basé sur l'IA et l'IoT pour une agriculture plus précise et durable." />

  <!-- Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Nunito:wght@400;600;700;800&family=Rubik:wght@400;500;600;700&display=swap" rel="stylesheet">

  <!-- Icons -->
  <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.10.0/css/all.min.css" rel="stylesheet">
  <link href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.11.3/font/bootstrap-icons.min.css" rel="stylesheet">

  <!-- Bootstrap -->
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">

  <!-- 3D model -->
  <script type="module" src="https://unpkg.com/@google/model-viewer/dist/model-viewer.min.js"></script>

  <style>
    :root {
      --primary: #06A3DA;
      --secondary: #34AD54;
      --light: #EEF9FF;
      --dark: #091E3E;
    }

    * {
      box-sizing: border-box;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      margin: 0;
      font-family: 'Rubik', sans-serif;
      color: #6B6A75;
      background: #fff;
    }

    h1, h2, h3, h4, h5, h6 {
      font-family: 'Nunito', sans-serif;
      color: var(--dark);
      font-weight: 800;
    }

    a {
      text-decoration: none;
    }

    .btn {
      font-family: 'Nunito', sans-serif;
      font-weight: 700;
      transition: .3s;
    }

    .btn-primary {
      background: var(--primary);
      border-color: var(--primary);
    }

    .btn-primary:hover {
      background: #058cbb;
      border-color: #058cbb;
    }

    .text-primary {
      color: var(--primary) !important;
    }

    .bg-primary {
      background-color: var(--primary) !important;
    }

    .bg-dark {
      background-color: var(--dark) !important;
    }

    .section-title::before {
      position: absolute;
      content: "";
      width: 120px;
      height: 2px;
      bottom: 0;
      left: 0;
      background: #E6E6E6;
    }

    .section-title::after {
      position: absolute;
      content: "";
      width: 40px;
      height: 4px;
      bottom: -1px;
      left: 0;
      background: var(--primary);
    }

    .section-title.text-center::before {
      left: 50%;
      transform: translateX(-50%);
    }

    .section-title.text-center::after {
      left: 50%;
      transform: translateX(-50%);
    }

    /* Spinner */
    #spinner {
      opacity: 1;
      visibility: visible;
      transition: .5s;
      z-index: 99999;
    }

    #spinner.hide {
      opacity: 0;
      visibility: hidden;
    }

    .spinner-box {
      width: 44px;
      height: 44px;
      background: var(--primary);
      animation: spinplane 1.2s infinite ease-in-out;
    }

    @keyframes spinplane {
      0% { transform: perspective(120px) rotateX(0deg) rotateY(0deg); }
      50% { transform: perspective(120px) rotateX(-180deg) rotateY(0deg); }
      100% { transform: perspective(120px) rotateX(-180deg) rotateY(-180deg); }
    }

    /* Topbar */
    .topbar small {
      font-size: 14px;
    }

    /* Navbar */
    .navbar-custom {
      transition: .35s ease;
      z-index: 1030;
    }

    .navbar-custom .navbar-brand h1 {
      color: #fff;
      font-size: 2rem;
      margin: 0;
    }

    .navbar-custom .nav-link {
      color: #fff !important;
      font-family: 'Nunito', sans-serif;
      font-weight: 700;
      margin-left: 18px;
      position: relative;
    }

    .navbar-custom .nav-link.active,
    .navbar-custom .nav-link:hover {
      color: var(--primary) !important;
    }

    .navbar-scrolled {
      background: #fff !important;
      box-shadow: 0 0 30px rgba(0,0,0,.08);
    }

    .navbar-scrolled .navbar-brand h1,
    .navbar-scrolled .nav-link {
      color: var(--dark) !important;
    }

    .navbar-toggler {
      border: none;
      box-shadow: none !important;
    }

    /* Hero */
    .hero-header {
      position: relative;
      min-height: 100vh;
      background:
        linear-gradient(rgba(9,30,62,.72), rgba(9,30,62,.72)),
        url("https://images.unsplash.com/photo-1464226184884-fa280b87c399?auto=format&fit=crop&w=1800&q=80") center center / cover no-repeat;
      display: flex;
      align-items: center;
    }

    .hero-badge {
      display: inline-block;
      padding: 10px 18px;
      border-radius: 999px;
      background: rgba(255,255,255,.12);
      border: 1px solid rgba(255,255,255,.15);
      color: #fff;
      font-weight: 700;
      margin-bottom: 18px;
      backdrop-filter: blur(8px);
    }

    .hero-header h1 {
      color: #fff;
      font-size: clamp(2.3rem, 6vw, 5.2rem);
      line-height: 1.1;
    }

    .hero-header p {
      color: rgba(255,255,255,.9);
      max-width: 780px;
      font-size: 1.1rem;
    }

    /* Facts */
    .facts-wrapper {
      margin-top: -75px;
      position: relative;
      z-index: 2;
    }

    .fact-box {
      min-height: 150px;
      box-shadow: 0 0 35px rgba(0,0,0,.08);
    }

    .fact-icon {
      width: 60px;
      height: 60px;
      border-radius: 10px;
      display: flex;
      align-items: center;
      justify-content: center;
      flex-shrink: 0;
    }

    /* About */
    .about-img {
      min-height: 520px;
      border-radius: 14px;
      background:
        url("https://images.unsplash.com/photo-1516253593875-bd7ba052fbc5?auto=format&fit=crop&w=1000&q=80") center center / cover no-repeat;
      box-shadow: 0 0 45px rgba(0,0,0,.08);
    }

    /* Features / 3D */
    .feature-card {
      padding: 24px;
      border-radius: 14px;
      box-shadow: 0 0 40px rgba(0,0,0,.06);
      height: 100%;
      background: #fff;
    }

    .feature-icon {
      width: 64px;
      height: 64px;
      border-radius: 12px;
      background: var(--primary);
      color: #fff;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 24px;
      margin-bottom: 18px;
    }

    .model-card {
      background: #fff;
      border-radius: 18px;
      box-shadow: 0 0 50px rgba(0,0,0,.08);
      padding: 18px;
      text-align: center;
    }

    .model-chip {
      display: inline-block;
      padding: 7px 14px;
      border-radius: 999px;
      background: var(--light);
      color: var(--primary);
      font-weight: 800;
      font-family: 'Nunito', sans-serif;
      margin-bottom: 14px;
    }

    model-viewer {
      width: 100%;
      height: 420px;
      background: #fff;
      border-radius: 14px;
      --poster-color: #fff;
    }

    .prototype-note {
      font-size: 14px;
      margin-top: 14px;
      margin-bottom: 10px;
    }

    /* Services */
    .service-item {
      background: var(--light);
      border-radius: 14px;
      padding: 40px 28px;
      height: 100%;
      text-align: center;
      box-shadow: 0 0 30px rgba(0,0,0,.03);
      transition: .3s;
    }

    .service-item:hover {
      transform: translateY(-6px);
    }

    .service-icon {
      width: 76px;
      height: 76px;
      border-radius: 50%;
      background: var(--primary);
      color: #fff;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      font-size: 28px;
      margin-bottom: 22px;
    }

    /* Contact */
    .contact-box {
      border-radius: 16px;
      background: var(--primary);
      padding: 36px;
      box-shadow: 0 0 40px rgba(0,0,0,.08);
    }

    .contact-box .form-control,
    .contact-box .form-select {
      min-height: 55px;
      border: none;
    }

    .contact-box textarea.form-control {
      min-height: 130px;
    }

    /* Testimonials */
    .testimonial-card {
      background: var(--light);
      border-radius: 14px;
      box-shadow: 0 0 30px rgba(0,0,0,.04);
      height: 100%;
      overflow: hidden;
    }

    .testimonial-body {
      padding: 24px 28px 30px;
    }

    .testimonial-head {
      padding: 24px 28px;
      border-bottom: 1px solid rgba(0,0,0,.06);
      display: flex;
      align-items: center;
      gap: 16px;
    }

    .testimonial-head img {
      width: 60px;
      height: 60px;
      border-radius: 10px;
      object-fit: cover;
    }

    /* Footer */
    .footer-about {
      background: var(--primary);
      border-radius: 0;
    }

    .footer-about .navbar-brand h1,
    .footer-about p {
      color: #fff;
    }

    .footer-link {
      color: #fff;
      display: block;
      margin-bottom: 10px;
    }

    .footer-link:hover {
      color: var(--primary);
    }

    /* Back to top */
    .back-to-top {
      position: fixed;
      right: 24px;
      bottom: 24px;
      z-index: 99;
      display: none;
      width: 48px;
      height: 48px;
      border-radius: 12px;
      align-items: center;
      justify-content: center;
    }

    @media (max-width: 991.98px) {
      .navbar-custom {
        background: #fff !important;
      }

      .navbar-custom .navbar-brand h1,
      .navbar-custom .nav-link {
        color: var(--dark) !important;
      }

      .hero-header {
        min-height: 90vh;
        padding-top: 90px;
      }

      .facts-wrapper {
        margin-top: 0;
      }

      model-viewer {
        height: 340px;
      }

      .about-img {
        min-height: 340px;
      }
    }
  </style>
</head>
<body>

  <!-- Spinner -->
  <div id="spinner" class="position-fixed top-50 start-50 translate-middle w-100 vh-100 bg-white d-flex align-items-center justify-content-center">
    <div class="spinner-box"></div>
  </div>

  <!-- Topbar -->
  <div class="container-fluid bg-dark px-5 d-none d-lg-block topbar">
    <div class="row gx-0">
      <div class="col-lg-8 text-center text-lg-start mb-2 mb-lg-0">
        <div class="d-inline-flex align-items-center" style="height: 45px;">
          <small class="me-3 text-light"><i class="fa fa-map-marker-alt me-2"></i>Algérie / North Africa</small>
          <small class="me-3 text-light"><i class="fa fa-phone-alt me-2"></i>+213 XX XX XX XX</small>
          <small class="text-light"><i class="fa fa-envelope-open me-2"></i>contact@pommetech.com</small>
        </div>
      </div>
      <div class="col-lg-4 text-center text-lg-end">
        <div class="d-inline-flex align-items-center" style="height: 45px;">
          <a class="btn btn-sm btn-outline-light btn-sm-square rounded-circle me-2" href="#"><i class="fab fa-linkedin-in fw-normal"></i></a>
          <a class="btn btn-sm btn-outline-light btn-sm-square rounded-circle me-2" href="#"><i class="fab fa-facebook-f fw-normal"></i></a>
          <a class="btn btn-sm btn-outline-light btn-sm-square rounded-circle me-2" href="#"><i class="fab fa-instagram fw-normal"></i></a>
          <a class="btn btn-sm btn-outline-light btn-sm-square rounded-circle" href="#"><i class="fab fa-youtube fw-normal"></i></a>
        </div>
      </div>
    </div>
  </div>

  <!-- Navbar -->
  <nav id="mainNav" class="navbar navbar-expand-lg navbar-custom position-fixed top-0 start-0 w-100 px-4 px-lg-5 py-3">
    <div class="container-fluid p-0">
      <a href="#home" class="navbar-brand p-0">
        <h1><i class="fa fa-microchip me-2"></i>PommeTech</h1>
      </a>

      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarCollapse">
        <span class="fa fa-bars text-primary"></span>
      </button>

      <div class="collapse navbar-collapse" id="navbarCollapse">
        <div class="navbar-nav ms-auto py-0">
          <a href="#home" class="nav-item nav-link active">Accueil</a>
          <a href="#about" class="nav-item nav-link">Projet</a>
          <a href="#features" class="nav-item nav-link">Technologie</a>
          <a href="#services" class="nav-item nav-link">Solutions</a>
          <a href="#contact" class="nav-item nav-link">Contact</a>
        </div>
        <a href="#contact" class="btn btn-primary py-2 px-4 ms-lg-3">Demander une démo</a>
      </div>
    </div>
  </nav>

  <!-- Hero -->
  <section id="home" class="hero-header">
    <div class="container">
      <div class="row justify-content-center text-center">
        <div class="col-lg-10">
          <span class="hero-badge">AI + IoT + Smart Irrigation</span>
          <h1 class="mb-4">
            Une irrigation intelligente pour une agriculture plus précise et durable
          </h1>
          <p class="mx-auto mb-5">
            PommeTech développe un système électronique AgriTech qui analyse les données du sol et de l'environnement en temps réel afin d'automatiser l'irrigation, réduire le gaspillage d'eau de plus de 50% et améliorer la qualité des cultures.
          </p>
          <div class="d-flex flex-column flex-sm-row gap-3 justify-content-center">
            <a href="#about" class="btn btn-primary py-3 px-5">Découvrir la solution</a>
            <a href="#features" class="btn btn-outline-light py-3 px-5">Voir le prototype 3D</a>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Facts -->
  <div class="container facts-wrapper">
    <div class="row g-0">
      <div class="col-lg-4">
        <div class="fact-box bg-primary d-flex align-items-center justify-content-center p-4">
          <div class="fact-icon bg-white text-primary">
            <i class="fa fa-tint"></i>
          </div>
          <div class="ps-4">
            <h5 class="text-white mb-1">Économie d'eau</h5>
            <h1 class="text-white mb-0"><span class="counter" data-target="50">0</span>%+</h1>
          </div>
        </div>
      </div>

      <div class="col-lg-4">
        <div class="fact-box bg-light d-flex align-items-center justify-content-center p-4">
          <div class="fact-icon bg-primary text-white">
            <i class="fa fa-brain"></i>
          </div>
          <div class="ps-4">
            <h5 class="text-primary mb-1">Décisions temps réel</h5>
            <h1 class="mb-0"><span class="counter" data-target="24">0</span>/7</h1>
          </div>
        </div>
      </div>

      <div class="col-lg-4">
        <div class="fact-box bg-primary d-flex align-items-center justify-content-center p-4">
          <div class="fact-icon bg-white text-primary">
            <i class="fa fa-layer-group"></i>
          </div>
          <div class="ps-4">
            <h5 class="text-white mb-1">Architecture modulaire</h5>
            <h1 class="text-white mb-0"><span class="counter" data-target="100">0</span>%</h1>
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- About -->
  <section id="about" class="container-fluid py-5">
    <div class="container py-5">
      <div class="row g-5 align-items-center">
        <div class="col-lg-7">
          <div class="section-title position-relative pb-3 mb-5">
            <h5 class="fw-bold text-primary text-uppercase">À propos de PommeTech</h5>
            <h1 class="mb-0">Un système de gestion intelligente de l'irrigation pour l'agriculture protégée</h1>
          </div>

          <p class="mb-4">
            PommeTech est une startup AgriTech qui combine intelligence artificielle, électronique embarquée et Internet des objets afin d'optimiser automatiquement l'irrigation dans les serres et les environnements agricoles contrôlés.
          </p>

          <p class="mb-4">
            Notre solution n'est pas un simple système de contrôle à distance. Elle analyse les données du sol, de l'humidité, de la température et des conditions ambiantes en temps réel pour déterminer les besoins hydriques avec précision, réduire la consommation d'eau, diminuer l'énergie utilisée et améliorer la performance des cultures.
          </p>

          <div class="row g-0 mb-4">
            <div class="col-sm-6">
              <h5 class="mb-3"><i class="fa fa-check text-primary me-3"></i>IA pour la décision automatique</h5>
              <h5 class="mb-3"><i class="fa fa-check text-primary me-3"></i>Capteurs IoT temps réel</h5>
            </div>
            <div class="col-sm-6">
              <h5 class="mb-3"><i class="fa fa-check text-primary me-3"></i>Prototype déjà testé</h5>
              <h5 class="mb-3"><i class="fa fa-check text-primary me-3"></i>Déploiement progressif</h5>
            </div>
          </div>

          <div class="d-flex align-items-center mb-4">
            <div class="fact-icon bg-primary text-white">
              <i class="fa fa-seedling"></i>
            </div>
            <div class="ps-4">
              <h5 class="mb-2">Vision durable et impact social</h5>
              <h4 class="text-primary mb-0">حل ذكي ومستدام لإدارة المياه الزراعية بدقة</h4>
            </div>
          </div>

          <a href="#contact" class="btn btn-primary py-3 px-5 mt-2">Demander une présentation</a>
        </div>

        <div class="col-lg-5">
          <div class="about-img w-100"></div>
        </div>
      </div>
    </div>
  </section>

  <!-- Features / 3D -->
  <section id="features" class="container-fluid py-5 bg-light">
    <div class="container py-5">
      <div class="section-title text-center position-relative pb-3 mb-5 mx-auto" style="max-width: 760px;">
        <h5 class="fw-bold text-primary text-uppercase">Technologie</h5>
        <h1 class="mb-0">Le prototype 3D au centre, avec le même esprit premium du template</h1>
      </div>

      <div class="row g-5 align-items-center">
        <div class="col-lg-4">
          <div class="feature-card mb-4">
            <div class="feature-icon"><i class="fa fa-microchip"></i></div>
            <h4>Électronique embarquée</h4>
            <p class="mb-0">
              Cartes, capteurs et actionneurs conçus pour piloter l'irrigation avec précision dans des environnements agricoles réels.
            </p>
          </div>

          <div class="feature-card">
            <div class="feature-icon"><i class="fa fa-robot"></i></div>
            <h4>Intelligence artificielle</h4>
            <p class="mb-0">
              Les algorithmes interprètent les données mesurées et déclenchent automatiquement les bonnes actions au bon moment.
            </p>
          </div>
        </div>

        <div class="col-lg-4">
          <div class="model-card">
            <span class="model-chip">Prototype 3D</span>

            <model-viewer
              src="prototype.glb"
              alt="Prototype PommeTech"
              auto-rotate
              auto-rotate-delay="0"
              rotation-per-second="20deg"
              camera-controls
              shadow-intensity="1"
              exposure="1.05"
              environment-image="neutral"
              tone-mapping="neutral">
            </model-viewer>

            <p class="prototype-note">
              Mets simplement le fichier <strong>prototype.glb</strong> dans le même dossier que ce fichier HTML.
            </p>

            <div class="d-flex gap-2 justify-content-center flex-wrap">
              <button class="btn btn-primary px-4" onclick="toggleRotation()">Start / Stop Rotation</button>
              <button class="btn btn-outline-primary px-4" onclick="resetView()">Reset View</button>
            </div>
          </div>
        </div>

        <div class="col-lg-4">
          <div class="feature-card mb-4">
            <div class="feature-icon"><i class="fa fa-satellite-dish"></i></div>
            <h4>Supervision connectée</h4>
            <p class="mb-0">
              Visualisation des données, suivi à distance et lecture des performances pour mieux piloter les opérations.
            </p>
          </div>

          <div class="feature-card">
            <div class="feature-icon"><i class="fa fa-layer-group"></i></div>
            <h4>Architecture modulaire</h4>
            <p class="mb-0">
              Le système peut démarrer à petite échelle puis être étendu progressivement selon les besoins du terrain.
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Services -->
  <section id="services" class="container-fluid py-5">
    <div class="container py-5">
      <div class="section-title text-center position-relative pb-3 mb-5 mx-auto" style="max-width: 760px;">
        <h5 class="fw-bold text-primary text-uppercase">Solutions</h5>
        <h1 class="mb-0">Des fonctions concrètes pour une agriculture plus intelligente</h1>
      </div>

      <div class="row g-4">
        <div class="col-lg-4 col-md-6">
          <div class="service-item">
            <div class="service-icon"><i class="fa fa-tint"></i></div>
            <h4 class="mb-3">Irrigation de précision</h4>
            <p class="m-0">Activation automatique de l'arrosage selon les besoins réels des plantes et non selon un calendrier fixe.</p>
          </div>
        </div>

        <div class="col-lg-4 col-md-6">
          <div class="service-item">
            <div class="service-icon"><i class="fa fa-chart-line"></i></div>
            <h4 class="mb-3">Analyse des données</h4>
            <p class="m-0">Lecture des variables critiques et transformation en recommandations ou en actions automatiques utiles.</p>
          </div>
        </div>

        <div class="col-lg-4 col-md-6">
          <div class="service-item">
            <div class="service-icon"><i class="fa fa-bolt"></i></div>
            <h4 class="mb-3">Optimisation énergétique</h4>
            <p class="m-0">Moins d'énergie gaspillée grâce à une gestion plus fine des cycles d'irrigation et des équipements.</p>
          </div>
        </div>

        <div class="col-lg-4 col-md-6">
          <div class="service-item">
            <div class="service-icon"><i class="fa fa-mobile-alt"></i></div>
            <h4 class="mb-3">Suivi connecté</h4>
            <p class="m-0">Accès simple aux données du système, visualisation claire et surveillance continue des conditions de culture.</p>
          </div>
        </div>

        <div class="col-lg-4 col-md-6">
          <div class="service-item">
            <div class="service-icon"><i class="fa fa-seedling"></i></div>
            <h4 class="mb-3">Amélioration du rendement</h4>
            <p class="m-0">Une meilleure précision hydrique permet d'améliorer la qualité et l'homogénéité des productions.</p>
          </div>
        </div>

        <div class="col-lg-4 col-md-6">
          <div class="service-item text-white" style="background: var(--primary);">
            <div class="service-icon" style="background: #fff; color: var(--primary);"><i class="fa fa-flask"></i></div>
            <h4 class="mb-3 text-white">Prototype en validation</h4>
            <p class="m-0">Les premiers tests montrent une bonne capacité de contrôle précis, d'économie d'eau et d'adaptation aux conditions ciblées.</p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Testimonials -->
  <section class="container-fluid py-5 bg-light">
    <div class="container py-5">
      <div class="section-title text-center position-relative pb-3 mb-5 mx-auto" style="max-width: 760px;">
        <h5 class="fw-bold text-primary text-uppercase">Témoignages</h5>
        <h1 class="mb-0">Les premiers retours autour du projet</h1>
      </div>

      <div class="row g-4">
        <div class="col-lg-4">
          <div class="testimonial-card">
            <div class="testimonial-head">
              <img src="https://randomuser.me/api/portraits/men/32.jpg" alt="">
              <div>
                <h5 class="text-primary mb-1">Responsable technique</h5>
                <small class="text-uppercase">Agriculture protégée</small>
              </div>
            </div>
            <div class="testimonial-body">
              Le prototype montre un vrai potentiel de précision. L'approche dépasse clairement un simple pilotage manuel à distance.
            </div>
          </div>
        </div>

        <div class="col-lg-4">
          <div class="testimonial-card">
            <div class="testimonial-head">
              <img src="https://randomuser.me/api/portraits/women/44.jpg" alt="">
              <div>
                <h5 class="text-primary mb-1">Partenaire innovation</h5>
                <small class="text-uppercase">AgriTech</small>
              </div>
            </div>
            <div class="testimonial-body">
              L'architecture modulaire est très intéressante. Elle permet une mise en œuvre progressive et réaliste dans différents contextes.
            </div>
          </div>
        </div>

        <div class="col-lg-4">
          <div class="testimonial-card">
            <div class="testimonial-head">
              <img src="https://randomuser.me/api/portraits/men/54.jpg" alt="">
              <div>
                <h5 class="text-primary mb-1">Jeune ingénieur</h5>
                <small class="text-uppercase">IoT & électronique</small>
              </div>
            </div>
            <div class="testimonial-body">
              Le projet crée une vraie passerelle entre innovation technologique, agriculture durable et opportunités d'emploi pour les jeunes.
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Contact -->
  <section id="contact" class="container-fluid py-5">
    <div class="container py-5">
      <div class="row g-5">
        <div class="col-lg-7">
          <div class="section-title position-relative pb-3 mb-5">
            <h5 class="fw-bold text-primary text-uppercase">Contact</h5>
            <h1 class="mb-0">Besoin d'une démo ou d'une présentation du prototype ?</h1>
          </div>

          <p class="mb-4">
            PommeTech propose une approche concrète de l'innovation agricole : gestion durable de l'eau, précision d'irrigation, optimisation énergétique et architecture scalable pour un déploiement progressif.
          </p>

          <div class="row gx-3">
            <div class="col-sm-6">
              <h5 class="mb-4"><i class="fa fa-reply text-primary me-3"></i>Réponse rapide</h5>
            </div>
            <div class="col-sm-6">
              <h5 class="mb-4"><i class="fa fa-users text-primary me-3"></i>Projet duplicable</h5>
            </div>
          </div>

          <div class="d-flex align-items-center mt-3">
            <div class="fact-icon bg-primary text-white">
              <i class="fa fa-envelope"></i>
            </div>
            <div class="ps-4">
              <h5 class="mb-2">Écris-nous</h5>
              <h4 class="text-primary mb-0">contact@pommetech.com</h4>
            </div>
          </div>
        </div>

        <div class="col-lg-5">
          <div class="contact-box">
            <form>
              <div class="row g-3">
                <div class="col-12">
                  <input type="text" class="form-control bg-light" placeholder="Votre nom">
                </div>
                <div class="col-12">
                  <input type="email" class="form-control bg-light" placeholder="Votre email">
                </div>
                <div class="col-12">
                  <select class="form-select bg-light">
                    <option selected>Choisir une demande</option>
                    <option>Démo du prototype</option>
                    <option>Partenariat</option>
                    <option>Présentation investisseur</option>
                  </select>
                </div>
                <div class="col-12">
                  <textarea class="form-control bg-light" placeholder="Votre message"></textarea>
                </div>
                <div class="col-12">
                  <button class="btn btn-dark w-100 py-3" type="submit">Envoyer la demande</button>
                </div>
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Footer -->
  <footer class="container-fluid bg-dark text-light mt-5">
    <div class="container">
      <div class="row gx-5">
        <div class="col-lg-4 col-md-6 footer-about">
          <div class="d-flex flex-column align-items-center justify-content-center text-center h-100 p-4">
            <a href="#home" class="navbar-brand">
              <h1 class="m-0 text-white"><i class="fa fa-microchip me-2"></i>PommeTech</h1>
            </a>
            <p class="mt-3 mb-4">
              Une startup AgriTech qui met l'intelligence artificielle et l'électronique au service d'une gestion durable, précise et intelligente de l'eau en agriculture.
            </p>
            <form class="w-100">
              <div class="input-group">
                <input type="text" class="form-control border-white p-3" placeholder="Votre email">
                <button class="btn btn-dark">S'inscrire</button>
              </div>
            </form>
          </div>
        </div>

        <div class="col-lg-8 col-md-6">
          <div class="row gx-5">
            <div class="col-lg-4 col-md-12 pt-5 mb-5">
              <h3 class="text-light mb-4">Coordonnées</h3>
              <div class="d-flex mb-2">
                <i class="bi bi-geo-alt text-primary me-2"></i>
                <p class="mb-0">Algérie</p>
              </div>
              <div class="d-flex mb-2">
                <i class="bi bi-envelope-open text-primary me-2"></i>
                <p class="mb-0">contact@pommetech.com</p>
              </div>
              <div class="d-flex mb-2">
                <i class="bi bi-telephone text-primary me-2"></i>
                <p class="mb-0">+213 XX XX XX XX</p>
              </div>
            </div>

            <div class="col-lg-4 col-md-12 pt-5 mb-5">
              <h3 class="text-light mb-4">Navigation</h3>
              <a class="footer-link" href="#home"><i class="bi bi-arrow-right text-primary me-2"></i>Accueil</a>
              <a class="footer-link" href="#about"><i class="bi bi-arrow-right text-primary me-2"></i>Projet</a>
              <a class="footer-link" href="#features"><i class="bi bi-arrow-right text-primary me-2"></i>Technologie</a>
              <a class="footer-link" href="#services"><i class="bi bi-arrow-right text-primary me-2"></i>Solutions</a>
              <a class="footer-link" href="#contact"><i class="bi bi-arrow-right text-primary me-2"></i>Contact</a>
            </div>

            <div class="col-lg-4 col-md-12 pt-5 mb-5">
              <h3 class="text-light mb-4">Points forts</h3>
              <a class="footer-link" href="#"><i class="bi bi-arrow-right text-primary me-2"></i>Réduction du gaspillage d'eau</a>
              <a class="footer-link" href="#"><i class="bi bi-arrow-right text-primary me-2"></i>Analyse en temps réel</a>
              <a class="footer-link" href="#"><i class="bi bi-arrow-right text-primary me-2"></i>Contrôle précis</a>
              <a class="footer-link" href="#"><i class="bi bi-arrow-right text-primary me-2"></i>Prototype modulaire</a>
              <a class="footer-link" href="#"><i class="bi bi-arrow-right text-primary me-2"></i>Impact social</a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </footer>

  <div class="container-fluid text-white" style="background: #061429;">
    <div class="container text-center">
      <div class="d-flex align-items-center justify-content-center" style="height: 75px;">
        <p class="mb-0">&copy; PommeTech. Tous droits réservés.</p>
      </div>
    </div>
  </div>

  <button class="btn btn-primary back-to-top" id="backToTop">
    <i class="bi bi-arrow-up"></i>
  </button>

  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"></script>

  <script>
    // Spinner
    window.addEventListener("load", function () {
      const spinner = document.getElementById("spinner");
      setTimeout(() => spinner.classList.add("hide"), 300);
    });

    // Sticky navbar
    const nav = document.getElementById("mainNav");
    const backToTop = document.getElementById("backToTop");

    function handleScroll() {
      if (window.scrollY > 45) {
        nav.classList.add("navbar-scrolled");
      } else {
        nav.classList.remove("navbar-scrolled");
      }

      if (window.scrollY > 200) {
        backToTop.style.display = "inline-flex";
      } else {
        backToTop.style.display = "none";
      }
    }

    window.addEventListener("scroll", handleScroll);
    handleScroll();

    // Back to top
    backToTop.addEventListener("click", function () {
      window.scrollTo({ top: 0, behavior: "smooth" });
    });

    // Active nav link on click
    document.querySelectorAll(".navbar-nav .nav-link").forEach(link => {
      link.addEventListener("click", function () {
        document.querySelectorAll(".navbar-nav .nav-link").forEach(l => l.classList.remove("active"));
        this.classList.add("active");
      });
    });

    // Counter animation
    const counters = document.querySelectorAll(".counter");
    let countersStarted = false;

    function animateCounters() {
      const sectionTop = document.querySelector(".facts-wrapper").getBoundingClientRect().top;
      if (sectionTop < window.innerHeight - 80 && !countersStarted) {
        countersStarted = true;

        counters.forEach(counter => {
          const target = +counter.getAttribute("data-target");
          let current = 0;
          const increment = Math.max(1, Math.ceil(target / 80));

          const update = () => {
            current += increment;
            if (current >= target) {
              counter.textContent = target;
            } else {
              counter.textContent = current;
              requestAnimationFrame(update);
            }
          };

          update();
        });
      }
    }

    window.addEventListener("scroll", animateCounters);
    window.addEventListener("load", animateCounters);

    // 3D controls
    const viewer = document.querySelector("model-viewer");

    function toggleRotation() {
      viewer.autoRotate = !viewer.autoRotate;
    }

    function resetView() {
      viewer.cameraOrbit = "0deg 75deg 110%";
      viewer.fieldOfView = "30deg";
    }
  </script>
</body>
</html>

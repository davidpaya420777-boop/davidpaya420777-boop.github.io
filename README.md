<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>América de Cali - El equipo de mis amores</title>
    <style>
        /* Reset y estilos generales */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #f5f5f5;
            color: #333;
            line-height: 1.6;
        }
        
        a {
            text-decoration: none;
        }
        
        /* Colores del equipo */
        :root {
            --rojo: #D40032;
            --rojo-oscuro: #A30026;
            --blanco: #FFFFFF;
            --negro: #000000;
            --gris: #F0F0F0;
        }
        
        /* Header */
        header {
            background: linear-gradient(135deg, var(--rojo-oscuro), var(--rojo));
            color: var(--blanco);
            padding: 1rem 0;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
        }
        
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            display: flex;
            align-items: center;
        }
        
        .logo img {
            height: 60px;
            margin-right: 1rem;
        }
        
        .logo-text {
            font-size: 1.5rem;
            font-weight: bold;
        }
        
        nav ul {
            display: flex;
            list-style: none;
        }
        
        nav ul li {
            margin-left: 1.5rem;
        }
        
        nav ul li a {
            color: var(--blanco);
            font-weight: 500;
            transition: color 0.3s;
            padding: 0.5rem 0;
            position: relative;
        }
        
        nav ul li a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--blanco);
            transition: width 0.3s;
        }
        
        nav ul li a:hover::after {
            width: 100%;
        }
        
        /* Hero Section */
        .hero {
            background: url('https://images.unsplash.com/photo-1574629810360-7efbbe195018?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80') no-repeat center center/cover;
            height: 80vh;
            display: flex;
            align-items: center;
            position: relative;
            color: var(--blanco);
        }
        
        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.6);
        }
        
        .hero-content {
            position: relative;
            z-index: 2;
            width: 60%;
        }
        
        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            text-transform: uppercase;
        }
        
        .hero p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
        }
        
        .btn {
            display: inline-block;
            background: var(--blanco);
            color: var(--rojo);
            padding: 0.8rem 1.5rem;
            border-radius: 30px;
            font-weight: bold;
            transition: all 0.3s;
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        
        .btn:hover {
            background: var(--rojo-oscuro);
            color: var(--blanco);
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }
        
        .btn-rojo {
            background: var(--rojo);
            color: var(--blanco);
        }
        
        .btn-rojo:hover {
            background: var(--rojo-oscuro);
        }
        
        /* Noticias */
        .noticias {
            padding: 4rem 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 3rem;
            position: relative;
        }
        
        .section-title h2 {
            font-size: 2.5rem;
            color: var(--rojo);
            display: inline-block;
            position: relative;
        }
        
        .section-title h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 3px;
            background: var(--rojo);
        }
        
        .section-title p {
            color: #666;
            margin-top: 1rem;
        }
        
        .noticias-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
        }
        
        .noticia-card {
            background: var(--blanco);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s;
        }
        
        .noticia-card:hover {
            transform: translateY(-10px);
        }
        
        .noticia-img {
            height: 200px;
            overflow: hidden;
        }
        
        .noticia-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
        }
        
        .noticia-card:hover .noticia-img img {
            transform: scale(1.1);
        }
        
        .noticia-info {
            padding: 1.5rem;
        }
        
        .noticia-info .fecha {
            color: var(--rojo);
            font-size: 0.9rem;
            margin-bottom: 0.5rem;
            display: block;
        }
        
        .noticia-info h3 {
            margin-bottom: 1rem;
            color: var(--negro);
        }
        
        .noticia-info p {
            color: #666;
            margin-bottom: 1rem;
            font-size: 0.9rem;
        }
        
        .leer-mas {
            color: var(--rojo);
            font-weight: bold;
            font-size: 0.9rem;
            display: flex;
            align-items: center;
        }
        
        .leer-mas::after {
            content: '→';
            margin-left: 5px;
            transition: margin-left 0.3s;
        }
        
        .leer-mas:hover::after {
            margin-left: 10px;
        }
        
        /* Plantilla */
        .plantilla {
            background: var(--rojo);
            color: var(--blanco);
            padding: 4rem 0;
        }
        
        .plantilla .section-title h2 {
            color: var(--blanco);
        }
        
        .plantilla .section-title h2::after {
            background: var(--blanco);
        }
        
        .jugadores-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 2rem;
        }
        
        .jugador-card {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            overflow: hidden;
            transition: all 0.3s;
            text-align: center;
        }
        
        .jugador-card:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: translateY(-5px);
        }
        
        .jugador-img {
            height: 200px;
            overflow: hidden;
        }
        
        .jugador-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .jugador-info {
            padding: 1rem;
        }
        
        .jugador-info .dorsal {
            display: inline-block;
            background: var(--blanco);
            color: var(--rojo);
            width: 30px;
            height: 30px;
            border-radius: 50%;
            line-height: 30px;
            font-weight: bold;
            margin-bottom: 0.5rem;
        }
        
        .jugador-info h3 {
            font-size: 1.2rem;
            margin-bottom: 0.3rem;
        }
        
        .jugador-info .posicion {
            color: var(--blanco);
            font-size: 0.9rem;
            opacity: 0.8;
        }
        
        /* Palmarés */
        .palmares {
            padding: 4rem 0;
        }
        
        .trofeos-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }
        
        .trofeo-card {
            background: var(--blanco);
            border-radius: 10px;
            padding: 2rem;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .trofeo-icon {
            font-size: 3rem;
            color: var(--rojo);
            margin-bottom: 1rem;
        }
        
        .trofeo-card h3 {
            color: var(--negro);
            margin-bottom: 0.5rem;
        }
        
        .trofeo-card .cantidad {
            font-size: 2.5rem;
            font-weight: bold;
            color: var(--rojo);
        }
        
        /* Estadio */
        .estadio {
            background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)), url('https://images.unsplash.com/photo-1543351611-58f69d7c1781?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80') no-repeat center center/cover;
            color: var(--blanco);
            padding: 4rem 0;
            text-align: center;
        }
        
        .estadio h2 {
            font-size: 2.5rem;
            margin-bottom: 1.5rem;
        }
        
        .estadio p {
            max-width: 800px;
            margin: 0 auto 2rem;
        }
        
        /* Footer */
        footer {
            background: var(--rojo-oscuro);
            color: var(--blanco);
            padding: 3rem 0 1rem;
        }
        
        .footer-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
        }
        
        .footer-col h3 {
            margin-bottom: 1.5rem;
            position: relative;
            padding-bottom: 0.5rem;
        }
        
        .footer-col h3::after {
            content: '';
            position: absolute;
            left: 0;
            bottom: 0;
            width: 50px;
            height: 2px;
            background: var(--blanco);
        }
        
        .footer-col ul {
            list-style: none;
        }
        
        .footer-col ul li {
            margin-bottom: 0.8rem;
        }
        
        .footer-col ul li a {
            color: #ddd;
            transition: color 0.3s;
        }
        
        .footer-col ul li a:hover {
            color: var(--blanco);
        }
        
        .social-links {
            display: flex;
            gap: 1rem;
        }
        
        .social-links a {
            display: inline-block;
            width: 40px;
            height: 40px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            text-align: center;
            line-height: 40px;
            color: var(--blanco);
            transition: all 0.3s;
        }
        
        .social-links a:hover {
            background: var(--blanco);
            color: var(--rojo);
            transform: translateY(-3px);
        }
        
        .copyright {
            text-align: center;
            padding-top: 2rem;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: #ddd;
            font-size: 0.9rem;
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                text-align: center;
            }
            
            nav ul {
                margin-top: 1rem;
            }
            
            nav ul li {
                margin: 0 0.5rem;
            }
            
            .hero-content {
                width: 100%;
                text-align: center;
            }
            
            .hero h1 {
                font-size: 2.5rem;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <div class="header-content">
                <div class="logo">
                    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/9f/Escudo_de_Am%C3%A9rica_de_Cali.svg/1200px-Escudo_de_Am%C3%A9rica_de_Cali.svg.png" alt="Escudo América de Cali">
                    <div class="logo-text">América de Cali</div>
                </div>
                <nav>
                    <ul>
                        <li><a href="#inicio">Inicio</a></li>
                        <li><a href="#noticias">Noticias</a></li>
                        <li><a href="#plantilla">Plantilla</a></li>
                        <li><a href="#palmares">Palmarés</a></li>
                        <li><a href="#estadio">Estadio</a></li>
                    </ul>
                </nav>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="inicio">
        <div class="container">
            <div class="hero-content">
                <h1>América de Cali</h1>
                <p>El equipo de mis amores, pasión de un pueblo que late al ritmo del fútbol.</p>
                <a href="#noticias" class="btn btn-rojo">Últimas noticias</a>
            </div>
        </div>
    </section>

    <!-- Noticias -->
    <section class="noticias" id="noticias">
        <div class="container">
            <div class="section-title">
                <h2>Últimas Noticias</h2>
                <p>Mantente al día con las novedades del equipo escarlata</p>
            </div>
            
            <div class="noticias-grid">
                <div class="noticia-card">
                    <div class="noticia-img">
                        <img src="https://www.americadecali.co.co/sites/default/files/styles/noticia_detalle/public/noticias/america-cali-partido.jpg" alt="Partido América de Cali">
                    </div>
                    <div class="noticia-info">
                        <span class="fecha">15 Junio 2023</span>
                        <h3>América consigue importante victoria como visitante</h3>
                        <p>El equipo escarlata logra tres puntos valiosos en su visita al Pascual Guerrero con goles de Adrián Ramos y Darwin Quintero.</p>
                        <a href="#" class="leer-mas">Leer más</a>
                    </div>
                </div>
                
                <div class="noticia-card">
                    <div class="noticia-img">
                        <img src="https://www.americadecali.co.co/sites/default/files/styles/noticia_detalle/public/noticias/estadio-america-cali.jpg" alt="Estadio América de Cali">
                    </div>
                    <div class="noticia-info">
                        <span class="fecha">10 Junio 2023</span>
                        <h3>América presenta mejoras en el Estadio Pascual Guerrero</h3>
                        <p>El club anuncia importantes obras de remodelación en su estadio para mejorar la experiencia de la hinchada.</p>
                        <a href="#" class="leer-mas">Leer más</a>
                    </div>
                </div>
                
                <div class="noticia-card">
                    <div class="noticia-img">
                        <img src="https://www.americadecali.co.co/sites/default/files/styles/noticia_detalle/public/noticias/nuevo-fichaje-america.jpg" alt="Nueva contratación">
                    </div>
                    <div class="noticia-info">
                        <span class="fecha">5 Junio 2023</span>
                        <h3>América anuncia el fichaje de volante creativo</h3>
                        <p>El mediocampista llega como refuerzo para el segundo semestre del torneo y promete dar alegrías a la afición.</p>
                        <a href="#" class="leer-mas">Leer más</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Plantilla -->
    <section class="plantilla" id="plantilla">
        <div class="container">
            <div class="section-title">
                <h2>Plantilla 2023</h2>
                <p>Conoce a los jugadores que defienden los colores escarlatas</p>
            </div>
            
            <div class="jugadores-grid">
                <div class="jugador-card">
                    <div class="jugador-img">
                        <img src="https://www.americadecali.co.co/sites/default/files/styles/jugador_detalle/public/jugadores/portero-america.jpg" alt="Portero América">
                    </div>
                    <div class="jugador-info">
                        <span class="dorsal">1</span>
                        <h3>Joel Graterol</h3>
                        <span class="posicion">Portero</span>
                    </div>
                </div>
                
                <div class="jugador-card">
                    <div class="jugador-img">
                        <img src="https://www.americadecali.co.co/sites/default/files/styles/jugador_detalle/public/jugadores/defensa-america.jpg" alt="Defensa América">
                    </div>
                    <div class="jugador-info">
                        <span class="dorsal">2</span>
                        <h3>Kevin Andrade</h3>
                        <span class="posicion">Defensa</span>
                    </div>
                </div>
                
                <div class="jugador-card">
                    <div class="jugador-img">
                        <img src="https://www.americadecali.co.co/sites/default/files/styles/jugador_detalle/public/jugadores/defensa-central-america.jpg" alt="Defensa Central América">
                    </div>
                    <div class="jugador-info">
                        <span class="dorsal">3</span>
                        <h3>Jorge Segura</h3>
                        <span class="posicion">Defensa</span>
                    </div>
                </div>
                
                <div class="jugador-card">
                    <div class="jugador-img">
                        <img src="https://www.americadecali.co.co/sites/default/files/styles/jugador_detalle/public/jugadores/mediocampista-america.jpg" alt="Mediocampista América">
                    </div>
                    <div class="jugador-info">
                        <span class="dorsal">10</span>
                        <h3>Darwin Quintero</h3>
                        <span class="posicion">Mediocampista</span>
                    </div>
                </div>
                
                <div class="jugador-card">
                    <div class="jugador-img">
                        <img src="https://www.americadecali.co.co/sites/default/files/styles/jugador_detalle/public/jugadores/delantero-america.jpg" alt="Delantero América">
                    </div>
                    <div class="jugador-info">
                        <span class="dorsal">9</span>
                        <h3>Adrián Ramos</h3>
                        <span class="posicion">Delantero</span>
                    </div>
                </div>
                
                <div class="jugador-card">
                    <div class="jugador-img">
                        <img src="https://www.americadecali.co.co/sites/default/files/styles/jugador_detalle/public/jugadores/capitán-america.jpg" alt="Capitán Am

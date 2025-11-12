<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AeroViajes - Vuelos a Destinos Paradisíacos</title>
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
            color: #0066cc;
        }
        
        /* Header */
        header {
            background: linear-gradient(135deg, #003366, #0066cc);
            color: white;
            padding: 1rem 0;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
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
            font-size: 1.8rem;
            font-weight: bold;
        }
        
        .logo span {
            color: #ffcc00;
        }
        
        nav ul {
            display: flex;
            list-style: none;
        }
        
        nav ul li {
            margin-left: 1.5rem;
        }
        
        nav ul li a {
            color: white;
            font-weight: 500;
            transition: color 0.3s;
        }
        
        nav ul li a:hover {
            color: #ffcc00;
        }
        
        /* Hero Section */
        .hero {
            background: url('https://images.unsplash.com/photo-1436491865332-7a61a109cc05?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80') no-repeat center center/cover;
            height: 80vh;
            display: flex;
            align-items: center;
            position: relative;
        }
        
        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.5);
        }
        
        .hero-content {
            position: relative;
            z-index: 2;
            color: white;
            width: 50%;
        }
        
        .hero h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
        }
        
        .hero p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
        }
        
        .btn {
            display: inline-block;
            background: #ffcc00;
            color: #003366;
            padding: 0.8rem 1.5rem;
            border-radius: 30px;
            font-weight: bold;
            transition: all 0.3s;
        }
        
        .btn:hover {
            background: #003366;
            color: white;
            transform: translateY(-3px);
        }
        
        /* Search Form */
        .search-form {
            background: white;
            padding: 2rem;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            margin-top: 2rem;
        }
        
        .form-group {
            margin-bottom: 1rem;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
        }
        
        .form-group input, 
        .form-group select {
            width: 100%;
            padding: 0.8rem;
            border: 1px solid #ddd;
            border-radius: 5px;
        }
        
        .form-row {
            display: flex;
            gap: 1rem;
        }
        
        .form-row .form-group {
            flex: 1;
        }
        
        /* Destinos */
        .destinos {
            padding: 4rem 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 3rem;
        }
        
        .section-title h2 {
            font-size: 2.5rem;
            color: #003366;
        }
        
        .section-title p {
            color: #666;
        }
        
        .destinos-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
        }
        
        .destino-card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s;
        }
        
        .destino-card:hover {
            transform: translateY(-10px);
        }
        
        .destino-img {
            height: 200px;
            overflow: hidden;
        }
        
        .destino-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
        }
        
        .destino-card:hover .destino-img img {
            transform: scale(1.1);
        }
        
        .destino-info {
            padding: 1.5rem;
        }
        
        .destino-info h3 {
            margin-bottom: 0.5rem;
            color: #003366;
        }
        
        .destino-info p {
            color: #666;
            margin-bottom: 1rem;
        }
        
        .precio {
            font-size: 1.5rem;
            font-weight: bold;
            color: #0066cc;
            margin-bottom: 1rem;
            display: block;
        }
        
        /* Servicios */
        .servicios {
            background: #003366;
            color: white;
            padding: 4rem 0;
        }
        
        .servicios .section-title h2 {
            color: white;
        }
        
        .servicios-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }
        
        .servicio-card {
            text-align: center;
            padding: 2rem;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            transition: all 0.3s;
        }
        
        .servicio-card:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: translateY(-5px);
        }
        
        .servicio-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
            color: #ffcc00;
        }
        
        /* Testimonios */
        .testimonios {
            padding: 4rem 0;
        }
        
        .testimonios-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }
        
        .testimonio-card {
            background: white;
            padding: 2rem;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .testimonio-text {
            font-style: italic;
            margin-bottom: 1rem;
        }
        
        .testimonio-author {
            display: flex;
            align-items: center;
        }
        
        .testimonio-author img {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            margin-right: 1rem;
            object-fit: cover;
        }
        
        /* Contacto */
        .contacto {
            padding: 4rem 0;
            background: #f9f9f9;
        }
        
        .contacto-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }
        
        .contacto-info {
            margin-bottom: 2rem;
        }
        
        .contacto-info h3 {
            margin-bottom: 1rem;
            color: #003366;
        }
        
        .contacto-form .form-group textarea {
            width: 100%;
            padding: 0.8rem;
            border: 1px solid #ddd;
            border-radius: 5px;
            min-height: 150px;
        }
        
        /* Footer */
        footer {
            background: #003366;
            color: white;
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
            background: #ffcc00;
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
            color: #ffcc00;
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
            color: white;
            transition: all 0.3s;
        }
        
        .social-links a:hover {
            background: #ffcc00;
            color: #003366;
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
            
            .form-row {
                flex-direction: column;
                gap: 0;
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
                    Aero<span>Viajes</span>
                </div>
                <nav>
                    <ul>
                        <li><a href="#inicio">Inicio</a></li>
                        <li><a href="#destinos">Destinos</a></li>
                        <li><a href="#servicios">Servicios</a></li>
                        <li><a href="#contacto">Contacto</a></li>
                    </ul>
                </nav>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="inicio">
        <div class="container">
            <div class="hero-content">
                <h1>Descubre los destinos más paradisíacos</h1>
                <p>Vuela a los lugares más hermosos de Colombia con las mejores tarifas y comodidades.</p>
                <a href="#destinos" class="btn">Explorar destinos</a>
                
                <div class="search-form">
                    <h3>Busca tu próximo viaje</h3>
                    <form>
                        <div class="form-row">
                            <div class="form-group">
                                <label for="origen">Origen</label>
                                <input type="text" id="origen" placeholder="Ciudad de origen">
                            </div>
                            <div class="form-group">
                                <label for="destino">Destino</label>
                                <select id="destino">
                                    <option value="">Selecciona un destino</option>
                                    <option value="san-andres">San Andrés</option>
                                    <option value="cartagena">Cartagena</option>
                                    <option value="santa-marta">Santa Marta</option>
                                    <option value="providencia">Providencia</option>
                                    <option value="barranquilla">Barranquilla</option>
                                </select>
                            </div>
                        </div>
                        <div class="form-row">
                            <div class="form-group">
                                <label for="fecha-salida">Fecha de salida</label>
                                <input type="date" id="fecha-salida">
                            </div>
                            <div class="form-group">
                                <label for="fecha-regreso">Fecha de regreso</label>
                                <input type="date" id="fecha-regreso">
                            </div>
                        </div>
                        <div class="form-group">
                            <label for="pasajeros">Pasajeros</label>
                            <select id="pasajeros">
                                <option value="1">1 pasajero</option>
                                <option value="2">2 pasajeros</option>
                                <option value="3">3 pasajeros</option>
                                <option value="4">4 pasajeros</option>
                                <option value="5+">5+ pasajeros</option>
                            </select>
                        </div>
                        <button type="submit" class="btn">Buscar vuelos</button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- Destinos -->
    <section class="destinos" id="destinos">
        <div class="container">
            <div class="section-title">
                <h2>Nuestros Destinos Populares</h2>
                <p>Descubre los lugares más visitados por nuestros clientes</p>
            </div>
            
            <div class="destinos-grid">
                <!-- San Andrés -->
                <div class="destino-card">
                    <div class="destino-img">
                        <img src="https://images.unsplash.com/photo-1580237763406-7d52a9a6e6c5?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="San Andrés">
                    </div>
                    <div class="destino-info">
                        <h3>San Andrés</h3>
                        <p>Isla paradisíaca con playas de arena blanca y aguas cristalinas.</p>
                        <span class="precio">Desde $450.000</span>
                        <a href="#" class="btn">Reservar ahora</a>
                    </div>
                </div>
                
                <!-- Cartagena -->
                <div class="destino-card">
                    <div class="destino-img">
                        <img src="https://images.unsplash.com/photo-1583422409516-2895a77efded?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Cartagena">
                    </div>
                    <div class="destino-info">
                        <h3>Cartagena</h3>
                        <p>Ciudad histórica con encanto colonial y playas caribeñas.</p>
                        <span class="precio">Desde $380.000</span>
                        <a href="#" class="btn">Reservar ahora</a>
                    </div>
                </div>
                
                <!-- Santa Marta -->
                <div class="destino-card">
                    <div class="destino-img">
                        <img src="https://images.unsplash.com/photo-1584697964358-3e16ca6e08a1?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Santa Marta">
                    </div>
                    <div class="destino-info">
                        <h3>Santa Marta</h3>
                        <p>Puerta de entrada a la Sierra Nevada y las playas de Tayrona.</p>
                        <span class="precio">Desde $350.000</span>
                        <a href="#" class="btn">Reservar ahora</a>
                    </div>
                </div>
                
                <!-- Providencia -->
                <div class="destino-card">
                    <div class="destino-img">
                        <img src="https://images.unsplash.com/photo-1582974114881-4d5e9c37b5c1?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Providencia">
                    </div>
                    <div class="destino-info">
                        <h3>Providencia</h3>
                        <p>Paraíso caribeño con una de las barreras coralinas más grandes del mundo.</p>
                        <span class="precio">Desde $520.000</span>
                        <a href="#" class="btn">Reservar ahora</a>
                    </div>
                </div>
                
                <!-- Barranquilla -->
                <div class="destino-card">
                    <div class="destino-img">
                        <img src="https://images.unsplash.com/photo-1584697964235-5856fd38e3b6?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Barranquilla">
                    </div>
                    <div class="destino-info">
                        <h3>Barranquilla</h3>
                        <p>Conoce la puerta de oro de Colombia y su famoso carnaval.</p>
                        <span class="precio">Desde $320.000</span>
                        <a href="#" class="btn">Reservar ahora</a>
                    </div>
                </div>
                
                <!-- Paquetes personalizados -->
                <div class="destino-card">
                    <div class="destino-img">
                        <img src="https://images.unsplash.com/photo-1506929562872-bb421503ef21?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Paquetes personalizados">
                    </div>
                    <div class="destino-info">
                        <h3>Paquetes Personalizados</h3>
                        <p>Crea tu propio itinerario con vuelo, hotel y actividades.</p>
                        <span class="precio">Desde $600.000</span>
                        <a href="#" class="btn">Personalizar viaje</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Servicios -->
    <section class="servicios" id="servicios">
        <div class="container">
            <div class="section-title">
                <h2>Nuestros Servicios</h2>
                <p>Todo lo que necesitas para un viaje perfecto</p>
            </div>
            
            <div class="servicios-grid">
                <div class="servicio-card">
                    <div class="servicio-icon">✈️</div>
                    <h3>Vuelos Directos</h3>
                    <p>Conectamos con los principales destinos turísticos del país con vuelos directos y frecuentes.</p>
                </div>
                
                <div class="servicio-card">
                    <div class="servicio-icon">🏨</div>
                    <h3>Paquetes Complejos</h3>
                    <p>Vuelo + hotel + traslados en un solo pago y con descuentos especiales.</p>
                </div>
                
                <div class="servicio-card">
                    <div class="servicio-icon">🛡️</div>
                    <h3>Seguro de Viaje</h3>
                    <p>Protección integral para 

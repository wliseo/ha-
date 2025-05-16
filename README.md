<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GeoAeroMéxico - CBTIS 38</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --color-primary: #2c3e50;
            --color-secondary: #3498db;
            --color-accent: #e74c3c;
            --color-warning: #e74c3c;
            --color-success: #2ecc71;
            --color-instagram: linear-gradient(45deg, #f09433 0%, #e6683c 25%, #dc2743 50%, #cc2366 75%, #bc1888 100%);
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            margin: 0;
            padding: 0;
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            color: #333;
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Animaciones */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }

        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
            100% { transform: translateY(0px); }
        }

        /* Pantalla de acceso */
        .password-screen {
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background: rgba(255, 255, 255, 0.95);
            padding: 40px;
            border-radius: 20px;
            text-align: center;
            color: var(--color-primary);
            box-shadow: 0 15px 35px rgba(0,0,0,0.2);
            z-index: 1000;
            width: 90%;
            max-width: 500px;
            animation: fadeIn 0.8s ease-out;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255,255,255,0.3);
        }

        .password-screen h1 {
            margin-bottom: 20px;
            font-size: 2rem;
            color: var(--color-primary);
        }

        .password-screen p {
            font-size: 1.2rem;
            margin-bottom: 25px;
        }

        .password-screen input {
            padding: 15px;
            font-size: 1.3rem;
            border: 2px solid var(--color-secondary);
            border-radius: 10px;
            margin: 15px auto;
            width: 120px;
            text-align: center;
            display: block;
            transition: all 0.3s;
        }

        .password-screen input:focus {
            border-color: var(--color-primary);
            box-shadow: 0 0 10px rgba(52, 152, 219, 0.5);
            outline: none;
        }

        /* Hero section */
        .hero {
            background: linear-gradient(rgba(0,0,0,0.7), rgba(0,0,0,0.7)), url('https://cdn.pixabay.com/photo/2017/10/10/07/48/earth-2835439_1280.jpg') center/cover no-repeat;
            height: 100vh;
            min-height: 600px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero-content {
            max-width: 800px;
            padding: 20px;
            z-index: 2;
            animation: fadeIn 1s ease-out;
        }

        .hero-content h1 {
            font-size: 3.5rem;
            margin-bottom: 20px;
            text-shadow: 2px 2px 8px rgba(0,0,0,0.7);
        }

        .hero-content p {
            font-size: 1.5rem;
            margin-bottom: 30px;
            text-shadow: 1px 1px 4px rgba(0,0,0,0.5);
        }

        /* Contenedor principal */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 40px 20px;
        }

        .section-title {
            text-align: center;
            margin-bottom: 50px;
            position: relative;
        }

        .section-title h1 {
            font-size: 2.5rem;
            color: var(--color-primary);
            display: inline-block;
            padding-bottom: 15px;
        }

        .section-title h1::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 4px;
            background: var(--color-secondary);
            border-radius: 2px;
        }

        /* Grid y cards */
        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 30px;
            margin: 50px 0;
        }

        .card {
            background: white;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 15px 30px rgba(0,0,0,0.1);
            transition: all 0.4s ease;
            position: relative;
            overflow: hidden;
            z-index: 1;
        }

        .card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: var(--color-secondary);
            transition: all 0.4s ease;
            z-index: -1;
        }

        .card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.15);
        }

        .card:hover::before {
            height: 100%;
            opacity: 0.1;
        }

        .card h2 {
            color: var(--color-primary);
            margin-top: 0;
            padding-bottom: 15px;
            border-bottom: 2px solid var(--color-secondary);
            font-size: 1.8rem;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .card h3 {
            color: var(--color-primary);
            margin: 20px 0 15px;
            font-size: 1.4rem;
        }

        .card ul {
            padding-left: 20px;
            margin-bottom: 20px;
        }

        .card li {
            margin-bottom: 10px;
            position: relative;
            padding-left: 15px;
        }

        .card li::before {
            content: '•';
            position: absolute;
            left: 0;
            color: var(--color-secondary);
            font-weight: bold;
        }

        /* Elementos especiales */
        .datos-curiosos {
            background: rgba(52, 152, 219, 0.1);
            padding: 20px;
            border-radius: 10px;
            margin: 25px 0;
            border-left: 5px solid var(--color-secondary);
            position: relative;
        }

        .datos-curiosos h4 {
            color: var(--color-primary);
            margin-top: 0;
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 1.2rem;
        }

        .aerolinea-tag {
            display: inline-block;
            background: var(--color-primary);
            color: white;
            padding: 4px 10px;
            border-radius: 20px;
            font-size: 0.8rem;
            margin-right: 8px;
            margin-bottom: 8px;
            transition: all 0.3s;
        }

        .aerolinea-tag:hover {
            transform: scale(1.05);
            box-shadow: 0 3px 10px rgba(0,0,0,0.2);
        }

        /* Tablas */
        table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            border-radius: 10px;
            overflow: hidden;
        }

        th, td {
            padding: 12px 15px;
            text-align: left;
            border-bottom: 1px solid #ddd;
        }

        th {
            background-color: var(--color-primary);
            color: white;
            font-weight: 600;
        }

        tr:nth-child(even) {
            background-color: #f8f9fa;
        }

        tr:hover {
            background-color: #f1f1f1;
        }

        /* Botones */
        .btn {
            display: inline-block;
            background: var(--color-secondary);
            color: white;
            padding: 15px 30px;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            font-size: 1.1rem;
            font-weight: 600;
            transition: all 0.3s;
            margin: 10px 5px;
            text-decoration: none;
            box-shadow: 0 4px 15px rgba(52, 152, 219, 0.3);
        }

        .btn:hover {
            background: #2980b9;
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(52, 152, 219, 0.4);
        }

        .btn:active {
            transform: translateY(1px);
        }

        .btn-outline {
            background: transparent;
            border: 2px solid var(--color-secondary);
            color: var(--color-secondary);
            box-shadow: none;
        }

        .btn-outline:hover {
            background: var(--color-secondary);
            color: white;
        }

        .btn-block {
            display: block;
            width: 100%;
            text-align: center;
        }

        /* Modal del cuestionario */
        .quiz-modal {
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background: white;
            padding: 40px;
            border-radius: 20px;
            box-shadow: 0 0 50px rgba(0,0,0,0.2);
            display: none;
            max-width: 800px;
            width: 90%;
            max-height: 90vh;
            overflow-y: auto;
            z-index: 1000;
            animation: fadeIn 0.5s;
        }

        .close-modal {
            position: absolute;
            top: 15px;
            right: 15px;
            background: transparent;
            border: none;
            font-size: 1.8rem;
            cursor: pointer;
            color: var(--color-primary);
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            transition: all 0.3s;
        }

        .close-modal:hover {
            background: #f1f1f1;
            transform: rotate(90deg);
        }

        .timer {
            position: fixed;
            top: 20px;
            right: 20px;
            background: var(--color-primary);
            color: white;
            padding: 10px 20px;
            border-radius: 50px;
            font-weight: bold;
            z-index: 1001;
            font-size: 1.2rem;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
        }

        /* Preguntas */
        .pregunta {
            margin: 25px 0;
            padding: 25px;
            background: #f8f9fa;
            border-radius: 15px;
            position: relative;
            overflow: hidden;
        }

        .pregunta::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 5px;
            height: 100%;
            background: var(--color-secondary);
        }

        .pregunta h3 {
            color: var(--color-primary);
            margin-top: 0;
            margin-bottom: 20px;
            font-size: 1.3rem;
        }

        .pregunta button {
            display: block;
            width: 100%;
            margin: 10px 0;
            text-align: left;
            background: white;
            color: var(--color-primary);
            border: 1px solid #ddd;
            padding: 15px;
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.3s;
            font-size: 1rem;
        }

        .pregunta button:hover:not(:disabled) {
            background: var(--color-secondary);
            color: white;
            border-color: var(--color-secondary);
            transform: translateX(5px);
        }

        .pregunta button:disabled {
            cursor: not-allowed;
        }

        .pregunta button.correcta {
            background: var(--color-success);
            color: white;
            border-color: var(--color-success);
        }

        .pregunta button.incorrecta {
            background: var(--color-warning);
            color: white;
            border-color: var(--color-warning);
        }

        /* Barra de progreso */
        .progress-container {
            margin: 40px 0;
            text-align: center;
        }

        .progress-bar {
            height: 12px;
            background: #ecf0f1;
            border-radius: 10px;
            margin: 20px 0;
            overflow: hidden;
            position: relative;
        }

        .progress {
            height: 100%;
            background: var(--color-secondary);
            width: 0%;
            transition: width 0.5s ease;
            position: relative;
        }

        .progress::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(90deg, rgba(255,255,255,0.1) 0%, rgba(255,255,255,0.3) 50%, rgba(255,255,255,0.1) 100%);
            animation: progressShine 2s infinite;
        }

        @keyframes progressShine {
            0% { transform: translateX(-100%); }
            100% { transform: translateX(100%); }
        }

        /* Trofeos */
        .trophy-case {
            display: flex;
            gap: 25px;
            justify-content: center;
            margin: 40px 0;
            flex-wrap: wrap;
        }

        .trophy {
            font-size: 50px;
            opacity: 0.3;
            transition: all 0.5s;
            filter: drop-shadow(0 4px 8px rgba(0,0,0,0.2));
            animation: float 3s ease-in-out infinite;
        }

        .trophy:nth-child(1) { animation-delay: 0s; }
        .trophy:nth-child(2) { animation-delay: 0.5s; }
        .trophy:nth-child(3) { animation-delay: 1s; }

        .trophy.active {
            opacity: 1;
            transform: scale(1.3);
            filter: drop-shadow(0 6px 12px rgba(255, 215, 0, 0.6));
        }

        /* Resultados */
        .resultados {
            text-align: center;
            margin-top: 40px;
            font-size: 1.2rem;
            animation: fadeIn 0.8s;
        }

        .resultados h3 {
            color: var(--color-primary);
            margin-bottom: 20px;
            font-size: 1.8rem;
        }

        .resultados p {
            margin-bottom: 20px;
        }

        /* Pantalla de éxito */
        .success-screen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--color-success);
            color: white;
            display: none;
            align-items: center;
            justify-content: center;
            text-align: center;
            flex-direction: column;
            z-index: 999;
            animation: fadeIn 0.5s;
            padding: 20px;
        }

        .success-screen h1 {
            font-size: 3rem;
            margin-bottom: 30px;
            text-shadow: 2px 2px 8px rgba(0,0,0,0.3);
            animation: pulse 2s infinite;
        }

        .success-screen p {
            font-size: 1.5rem;
            max-width: 800px;
            margin-bottom: 20px;
        }

        .success-screen small {
            font-size: 0.8rem;
            opacity: 0.8;
            margin-top: 30px;
        }

        /* Popup de Instagram */
        .instagram-popup {
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background: white;
            padding: 40px;
            border-radius: 20px;
            box-shadow: 0 15px 50px rgba(0,0,0,0.3);
            z-index: 1001;
            max-width: 400px;
            width: 90%;
            text-align: center;
            display: none;
            animation: fadeIn 0.5s;
            border-top: 5px solid var(--color-secondary);
        }

        .instagram-popup h3 {
            color: var(--color-primary);
            margin-bottom: 20px;
            font-size: 1.8rem;
        }

        .instagram-popup p {
            margin-bottom: 20px;
            font-size: 1.1rem;
            color: #555;
        }

        .instagram-link {
            display: inline-block;
            background: var(--color-instagram);
            color: white;
            padding: 12px 25px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: bold;
            font-size: 1.2rem;
            margin: 20px 0;
            transition: all 0.3s;
            box-shadow: 0 4px 15px rgba(220, 39, 67, 0.3);
        }

        .instagram-link:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(220, 39, 67, 0.4);
        }

        .instagram-link i {
            margin-right: 10px;
        }

        .close-popup {
            position: absolute;
            top: 15px;
            right: 15px;
            background: var(--color-primary);
            color: white;
            border: none;
            width: 30px;
            height: 30px;
            border-radius: 50%;
            font-size: 1rem;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s;
        }

        .close-popup:hover {
            transform: rotate(90deg);
            background: var(--color-warning);
        }

        /* Footer */
        footer {
            background: var(--color-primary);
            color: white;
            padding: 50px 20px;
            text-align: center;
            margin-top: 50px;
        }

        footer p {
            margin-bottom: 10px;
        }

        footer strong {
            font-weight: 600;
        }

        footer small {
            display: block;
            margin-top: 20px;
            font-size: 0.8rem;
            opacity: 0.8;
        }

        .warning-text {
            background: rgba(231, 76, 60, 0.1);
            padding: 15px;
            border-radius: 8px;
            margin: 30px auto 0;
            max-width: 800px;
            border-left: 4px solid var(--color-warning);
            font-size: 0.8rem;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hero-content h1 {
                font-size: 2.5rem;
            }

            .hero-content p {
                font-size: 1.2rem;
            }

            .password-screen {
                padding: 30px 20px;
            }

            .password-screen h1 {
                font-size: 1.8rem;
            }

            .card {
                padding: 25px 20px;
            }

            .section-title h1 {
                font-size: 2rem;
            }

            .quiz-modal {
                padding: 30px 20px;
            }

            .pregunta {
                padding: 20px 15px;
            }
        }

        @media (max-width: 480px) {
            .hero-content h1 {
                font-size: 2rem;
            }

            .grid {
                grid-template-columns: 1fr;
            }

            .btn {
                padding: 12px 25px;
                font-size: 1rem;
            }

            .trophy {
                font-size: 40px;
            }
        }
    </style>
</head>
<body>
    <!-- Pantalla de acceso -->
    <div class="password-screen" id="passwordScreen">
        <h1>¡Bienvenido a GeoAeroMéxico!</h1>
        <p>Resuelve: 4 × 4 = ?</p>
        <input type="number" id="password" placeholder="Respuesta">
        <button class="btn" onclick="checkPassword()">Acceder</button>
    </div>

    <!-- Hero section -->
    <div class="hero" id="heroSection" style="display: none;">
        <div class="hero-content">
            <h1>GeoAeroMéxico</h1>
            <p>Explorando la geometría esférica y su aplicación en la aviación mexicana</p>
        </div>
    </div>

    <!-- Pantalla de éxito -->
    <div class="success-screen" id="successScreen">
        <h1>🎉 ¡Eres muy inteligente!</h1>
        <p>¡Bienvenido al fascinante mundo de la geometría esférica y la aviación mexicana!</p>
        <small>Te recuerdo que esto es un proyecto en fase de prueba y puede contener errores</small>
    </div>

    <!-- Contenido principal -->
    <div class="container" id="mainContent" style="display: none;">
        <div class="section-title">
            <h1>GeoAeroMéxico</h1>
            <p>Explorando la geometría esférica y su aplicación en la aviación mexicana</p>
        </div>
        
        <div class="grid">
            <!-- Sección de Geometría Esférica -->
            <div class="card">
                <h2><i class="fas fa-globe-americas"></i> Geometría Esférica</h2>
                <p>La geometría esférica es el estudio de figuras en la superficie de una esfera, donde las "líneas rectas" son los círculos máximos.</p>
                
                <h3>Historia y Orígenes</h3>
                <ul>
                    <li><strong>Desarrollada por:</strong> Matemáticos griegos como Menelao de Alejandría (siglo I d.C.)</li>
                    <li><strong>Popularizada por:</strong> Bernhard Riemann en el siglo XIX con su geometría diferencial</li>
                    <li><strong>Año clave:</strong> 1854 - Riemann presenta su teoría de variedades dimensionales</li>
                </ul>
                
                <h3>Aplicaciones Modernas</h3>
                <ul>
                    <li>Fundamental para navegación aérea (rutas ortodrómicas)</li>
                    <li>Usada en sistemas satelitales y GPS</li>
                    <li>Esencial en meteorología para predicciones</li>
                    <li>Base para cartografía moderna (proyecciones)</li>
                    <li>Utilizada en astronomía para cálculos celestes</li>
                </ul>
                
                <div class="datos-curiosos">
                    <h4><i class="fas fa-lightbulb"></i> Datos Curiosos</h4>
                    <p>En una esfera, la suma de los ángulos de un triángulo siempre es mayor a 180° (a diferencia de la geometría plana).</p>
                    <p>Los aviones siguen rutas ortodrómicas (arcos de círculo máximo) porque son las distancias más cortas entre dos puntos en la Tierra.</p>
                </div>
            </div>

            <!-- Aeropuertos -->
            <div class="card">
                <h2><i class="fas fa-plane-departure"></i> Aeropuertos clave de México</h2>
                
                <h3>Aeropuerto Internacional de la Ciudad de México (AICM)</h3>
                <ul>
                    <li><strong>Aerolíneas principales:</strong> 
                        <span class="aerolinea-tag">Aeroméxico</span> 
                        <span class="aerolinea-tag">Volaris</span> 
                        <span class="aerolinea-tag">Viva Aerobus</span>
                    </li>
                    <li><strong>Rutas internacionales:</strong>
                        <ul>
                            <li>Nueva York (JFK) - Aeroméxico, Delta</li>
                            <li>Madrid (MAD) - Aeroméxico, Iberia</li>
                            <li>Los Ángeles (LAX) - Aeroméxico, Volaris, American</li>
                            <li>Tokio (NRT) - Aeroméxico (vía Tijuana)</li>
                        </ul>
                    </li>
                    <li><strong>Rutas nacionales más transitadas:</strong>
                        <ul>
                            <li>Ciudad de México - Cancún (Aeroméxico, Volaris, Viva)</li>
                            <li>Ciudad de México - Monterrey (todas las aerolíneas)</li>
                            <li>Ciudad de México - Guadalajara (todas las aerolíneas)</li>
                        </ul>
                    </li>
                    <li><strong>Dato curioso:</strong> Más de 50 millones de pasajeros anuales</li>
                </ul>

                <h3>Aeropuerto Internacional de Guadalajara (GDL)</h3>
                <ul>
                    <li><strong>Aerolíneas principales:</strong> 
                        <span class="aerolinea-tag">Volaris</span> 
                        <span class="aerolinea-tag">Aeroméxico</span> 
                        <span class="aerolinea-tag">American</span>
                    </li>
                    <li><strong>Rutas internacionales:</strong>
                        <ul>
                            <li>San Francisco (SFO) - Volaris, United</li>
                            <li>Vancouver (YVR) - Aeroméxico</li>
                            <li>Chicago (ORD) - Volaris, American</li>
                        </ul>
                    </li>
                    <li><strong>Rutas nacionales más transitadas:</strong>
                        <ul>
                            <li>Guadalajara - Tijuana (Volaris, Viva)</li>
                            <li>Guadalajara - Ciudad de México (todas)</li>
                            <li>Guadalajara - Cancún (Volaris, Viva)</li>
                        </ul>
                    </li>
                    <li><strong>Dato curioso:</strong> Hub para conexiones transpacíficas</li>
                </ul>

                <h3>Aeropuerto Internacional de Monterrey (MTY)</h3>
                <ul>
                    <li><strong>Aerolíneas principales:</strong> 
                        <span class="aerolinea-tag">Viva Aerobus</span> 
                        <span class="aerolinea-tag">Aeroméxico</span> 
                        <span class="aerolinea-tag">United</span>
                    </li>
                    <li><strong>Rutas internacionales:</strong>
                        <ul>
                            <li>Houston (IAH) - United, Aeroméxico</li>
                            <li>Dallas (DFW) - American</li>
                            <li>Panamá (PTY) - Copa Airlines</li>
                        </ul>
                    </li>
                    <li><strong>Rutas nacionales más transitadas:</strong>
                        <ul>
                            <li>Monterrey - Ciudad de México (todas)</li>
                            <li>Monterrey - Cancún (Viva, Volaris)</li>
                            <li>Monterrey - Tijuana (Viva, Volaris)</li>
                        </ul>
                    </li>
                    <li><strong>Dato curioso:</strong> Principal centro de carga aérea del norte de México</li>
                </ul>
            </div>
            
            <!-- Más información sobre geometría esférica -->
            <div class="card">
                <h2><i class="fas fa-calculator"></i> Matemáticas de la Geometría Esférica</h2>
                <h3>Fórmulas clave</h3>
                <ul>
                    <li><strong>Ley de los cosenos esférica:</strong> cos(a) = cos(b)cos(c) + sin(b)sin(c)cos(A)</li>
                    <li><strong>Ley de los senos esférica:</strong> sin(a)/sin(A) = sin(b)/sin(B) = sin(c)/sin(C)</li>
                    <li><strong>Área de un triángulo esférico:</strong> A = R²(E - π) donde E es el exceso angular</li>
                </ul>
                
                <h3>Comparación con geometría plana</h3>
                <table>
                    <tr>
                        <th>Propiedad</th>
                        <th>Plana</th>
                        <th>Esférica</th>
                    </tr>
                    <tr>
                        <td>Suma ángulos triángulo</td>
                        <td>180°</td>
                        <td>>180°</td>
                    </tr>
                    <tr>
                        <td>Rectas paralelas</td>
                        <td>Infinitas</td>
                        <td>0</td>
                    </tr>
                    <tr>
                        <td>Distancia más corta</td>
                        <td>Línea recta</td>
                        <td>Arco de círculo máximo</td>
                    </tr>
                </table>
                
                <div class="datos-curiosos">
                    <h4><i class="fas fa-plane"></i> Aplicación en aviación</h4>
                    <p>Los pilotos usan la geometría esférica para calcular rutas de gran círculo, que son las más cortas entre dos puntos en la Tierra. Por ejemplo, la ruta entre Tokio y Nueva York pasa cerca del Polo Norte, no a través del Océano Pacífico como podría parecer en un mapa plano.</p>
                </div>
            </div>
        </div>

        <!-- Botón del cuestionario -->
        <div class="progress-container">
            <div style="text-align: center; margin: 50px 0;">
                <button class="btn" onclick="startQuiz()"><i class="fas fa-rocket"></i> ¡Ponte a prueba! (Cuestionario de 20 preguntas)</button>
                <div class="trophy-case">
                    <div class="trophy">🏆</div>
                    <div class="trophy">🥈</div>
                    <div class="trophy">🥉</div>
                </div>
                <div class="progress-bar">
                    <div class="progress" id="quizProgress"></div>
                </div>
            </div>
        </div>
    </div>

    <!-- Modal del cuestionario -->
    <div class="quiz-modal" id="quizModal">
        <button class="close-modal" onclick="closeQuiz()">×</button>
        <div class="timer" id="timer">20:00</div>
        <h2><i class="fas fa-question-circle"></i> Cuestionario GeoAeroMéxico</h2>
        <div id="questions">
            <!-- Preguntas se insertan aquí mediante JS -->
        </div>
        <div class="resultados" id="resultados" style="display: none;">
            <h3>Resultados del Cuestionario</h3>
            <p id="puntaje"></p>
            <p id="mensaje"></p>
            <button class="btn" onclick="closeQuiz()">Volver al contenido</button>
        </div>
    </div>

    <!-- Popup de Instagram -->
    <div class="instagram-popup" id="instagramPopup">
        <button class="close-popup" onclick="closeInstagramPopup()">×</button>
        <h3>¡Sígueme en Instagram!</h3>
        <p>Me apoyas a seguir creando proyectos educativos como este</p>
        <a href="https://www.instagram.com/wliseo777/profilecard/?igsh=MW9tNmw5bWo5cG5p" target="_blank" class="instagram-link">
            <i class="fab fa-instagram"></i> @wliseo777
        </a>
        <p>¡Gracias por tu apoyo!<br>Sigamos aprendiendo juntos</p>
    </div>

    <!-- Footer -->
    <footer>
        <p>Desarrollado por <strong>Efraín Ulises González Sandoval</strong></p>
        <p>Josefa Ortiz de Domínguez CBTIS 38</p>
        <small>Uso exclusivo interno - Prohibido uso publicitario</small>
        <div class="warning-text">
            NOTA: Este es un proyecto educativo en fase de prueba. Puede contener errores o imprecisiones. La información presentada es para fines didácticos solamente.
        </div>
    </footer>

    <script>
        // Configuración del cuestionario ampliado
        const quizData = [
            {
                pregunta: "¿Qué matemático griego realizó importantes contribuciones tempranas a la geometría esférica?",
                opciones: ["Euclides", "Menelao de Alejandría", "Pitágoras", "Arquímedes"],
                correcta: 1,
                explicacion: "Menelao de Alejandría (siglo I d.C.) escribió 'Sphaerica', la obra más antigua conocida sobre geometría esférica."
            },
            {
                pregunta: "¿Qué aeropuerto mexicano maneja más tráfico de pasajeros internacionales?",
                opciones: ["Guadalajara (GDL)", "Ciudad de México (AICM)", "Cancún (CUN)", "Monterrey (MTY)"],
                correcta: 2,
                explicacion: "Aunque el AICM tiene más tráfico total, Cancún recibe más pasajeros internacionales debido al turismo."
            },
            {
                pregunta: "En geometría esférica, ¿cómo se llama la línea más corta entre dos puntos?",
                opciones: ["Línea recta", "Ortodrómica", "Loxodrómica", "Paralela"],
                correcta: 1,
                explicacion: "La ortodrómica es el arco de círculo máximo que conecta dos puntos en una esfera, representando la distancia más corta."
            },
            {
                pregunta: "¿Qué aerolínea mexicana tiene su hub principal en el AICM?",
                opciones: ["Volaris", "Viva Aerobus", "Aeroméxico", "Interjet"],
                correcta: 2,
                explicacion: "Aeroméxico tiene su centro de operaciones principal en el Aeropuerto Internacional de la Ciudad de México."
            },
            {
                pregunta: "¿Qué propiedad NO es cierta en geometría esférica?",
                opciones: ["La suma de ángulos de un triángulo > 180°", "No existen líneas paralelas", "π (pi) vale 3.1416", "Los círculos máximos son análogos a líneas rectas"],
                correcta: 2,
                explicacion: "El valor de π es el mismo en todas las geometrías. Lo que cambia son las propiedades de figuras como triángulos y líneas paralelas."
            },
            {
                pregunta: "¿Qué ruta aérea es la más transitada dentro de México?",
                opciones: ["Ciudad de México-Monterrey", "Ciudad de México-Guadalajara", "Ciudad de México-Cancún", "Monterrey-Tijuana"],
                correcta: 2,
                explicacion: "La ruta entre la Ciudad de México y Cancún es la más transitada debido al turismo, con más de 3 millones de pasajeros anuales."
            },
            {
                pregunta: "¿Qué proyección cartográfica preserva los ángulos pero distorsiona las áreas?",
                opciones: ["Mercator", "Peters", "Robinson", "Azimutal"],
                correcta: 0,
                explicacion: "La proyección de Mercator, desarrollada en 1569, preserva los ángulos (útil para navegación) pero exagera las áreas cerca de los polos."
            },
            {
                pregunta: "¿Qué aerolínea ofrece vuelos directos de México a Tokio?",
                opciones: ["Aeroméxico", "Japan Airlines", "ANA", "Todas las anteriores"],
                correcta: 0,
                explicacion: "Actualmente solo Aeroméxico ofrece vuelos directos (con escala en Tijuana) entre México y Tokio."
            },
            {
                pregunta: "En un triángulo esférico con ángulos de 90°, ¿cuánto suman sus ángulos?",
                opciones: ["180°", "270°", "360°", "Depende del tamaño"],
                correcta: 1,
                explicacion: "En geometría esférica, un triángulo con tres ángulos rectos (como uno formado por dos meridianos y el ecuador) suma 270°."
            },
            {
                pregunta: "¿Qué aeropuerto es el hub principal de Volaris?",
                opciones: ["AICM (Ciudad de México)", "GDL (Guadalajara)", "TIJ (Tijuana)", "MTY (Monterrey)"],
                correcta: 1,
                explicacion: "Volaris tiene su centro de operaciones principal en el Aeropuerto Internacional de Guadalajara."
            },
            {
                pregunta: "¿Qué científico formalizó la geometría esférica en el siglo XIX?",
                opciones: ["Albert Einstein", "Carl Friedrich Gauss", "Bernhard Riemann", "Leonhard Euler"],
                correcta: 2,
                explicacion: "Bernhard Riemann desarrolló la geometría diferencial en 1854, sentando las bases matemáticas formales para la geometría esférica."
            },
            {
                pregunta: "¿Qué ruta internacional tiene más vuelos desde México?",
                opciones: ["México-Los Ángeles", "México-Madrid", "México-Buenos Aires", "México-Toronto"],
                correcta: 0,
                explicacion: "La ruta entre la Ciudad de México y Los Ángeles es la más transitada internacionalmente, con más de 20 vuelos diarios."
            },
            {
                pregunta: "¿Qué propiedad comparten todas las proyecciones de mapas?",
                opciones: ["Preservan distancias", "Preservan áreas", "Preservan ángulos", "Todas distorsionan algo"],
                correcta: 3,
                explicacion: "Es imposible representar una esfera en un plano sin distorsión. Todas las proyecciones sacrifican al menos una propiedad (distancias, áreas o ángulos)."
            },
            {
                pregunta: "¿Qué aerolínea fue fundada primero?",
                opciones: ["Aeroméxico", "Mexicana de Aviación", "Aeromar", "Taesa"],
                correcta: 1,
                explicacion: "Mexicana de Aviación fue fundada en 1921, mientras que Aeroméxico (originalmente Aeronaves de México) en 1934."
            },
            {
                pregunta: "¿Qué instrumento de navegación usa principios de geometría esférica?",
                opciones: ["Sextante", "Brújula", "Altímetro", "Anemómetro"],
                correcta: 0,
                explicacion: "El sextante mide ángulos entre objetos celestes y el horizonte, usando principios de geometría esférica para determinar la posición."
            },
            {
                pregunta: "¿Qué aeropuerto tiene la pista más larga de México?",
                opciones: ["AICM (Ciudad de México)", "MMDO (Durango)", "MMGL (Guadalajara)", "MMUN (Cancún)"],
                correcta: 1,
                explicacion: "El Aeropuerto de Durango tiene la pista más larga con 3,900 metros, construida para emergencias de transbordadores espaciales."
            },
            {
                pregunta: "¿Qué matemático demostró que π es el mismo en geometría plana y esférica?",
                opciones: ["Euclides", "Arquímedes", "Legendre", "Ninguno, es diferente"],
                correcta: 3,
                explicacion: "La razón entre la circunferencia y el diámetro de un círculo en una esfera depende del tamaño del círculo, por lo que π no es constante en geometría esférica."
            },
            {
                pregunta: "¿Qué aerolínea mexicana tiene más rutas internacionales?",
                opciones: ["Volaris", "Aeroméxico", "Viva Aerobus", "Calafia Airlines"],
                correcta: 1,
                explicacion: "Aeroméxico tiene la red más extensa con vuelos a América, Europa y Asia."
            },
            {
                pregunta: "¿Qué concepto de geometría esférica es crucial para el GPS?",
                opciones: ["Triángulos esféricos", "Tetraedros", "Polígonos regulares", "Cónicas"],
                correcta: 0,
                explicacion: "El GPS usa triángulos esféricos formados por satélites para calcular posiciones con precisión."
            },
            {
                pregunta: "¿Qué ruta aérea era conocida como 'El Puente Aéreo' en México?",
                opciones: ["México-Monterrey", "México-Guadalajara", "México-Cancún", "México-Tijuana"],
                correcta: 1,
                explicacion: "La ruta entre la Ciudad de México y Guadalajara era llamada así por la alta frecuencia de vuelos (cada 15 minutos en su auge)."
            }
        ];

        // Variables globales
        let tiempoRestante = 1200; // 20 minutos en segundos
        let intervalo;
        let respuestasUsuario = [];
        let preguntaActual = 0;
        let quizActivo = false;

        // Mostrar popup de Instagram después de 20 segundos
        setTimeout(() => {
            if (document.getElementById('mainContent').style.display === 'block') {
                document.getElementById('instagramPopup').style.display = 'block';
            }
        }, 20000);

        function closeInstagramPopup() {
            document.getElementById('instagramPopup').style.display = 'none';
        }

        function checkPassword() {
            const passwordInput = document.getElementById('password');
            if (passwordInput.value === '16') {
                // Ocultar pantalla de acceso
                document.getElementById('passwordScreen').style.display = 'none';
                
                // Mostrar hero section
                document.getElementById('heroSection').style.display = 'flex';
                
                // Mostrar pantalla de éxito
                document.getElementById('successScreen').style.display = 'flex';
                
                setTimeout(() => {
                    // Ocultar pantalla de éxito después de 3 segundos
                    document.getElementById('successScreen').style.display = 'none';
                    
                    // Mostrar contenido principal
                    document.getElementById('mainContent').style.display = 'block';
                    
                    // Ocultar hero section después de 1 segundo más
                    setTimeout(() => {
                        document.getElementById('heroSection').style.display = 'none';
                    }, 1000);
                    
                    // Iniciar animaciones de las cards
                    animateCards();
                }, 3000);
            } else {
                // Efecto de error
                passwordInput.style.borderColor = 'var(--color-warning)';
                passwordInput.style.animation = 'shake 0.5s';
                setTimeout(() => {
                    passwordInput.style.animation = '';
                }, 500);
                
                // Mostrar mensaje de error
                alert("Respuesta incorrecta. Intenta nuevamente.");
                passwordInput.value = '';
                passwordInput.focus();
            }
        }

        function animateCards() {
            const cards = document.querySelectorAll('.card');
            cards.forEach((card, index) => {
                card.style.opacity = '0';
                card.style.transform = 'translateY(20px)';
                card.style.transition = 'all 0.5s ease ' + (index * 0.1) + 's';
                
                setTimeout(() => {
                    card.style.opacity = '1';
                    card.style.transform = 'translateY(0)';
                }, 100);
            });
        }

        function startQuiz() {
            // Mostrar modal
            document.getElementById('quizModal').style.display = 'block';
            document.getElementById('resultados').style.display = 'none';
            document.getElementById('questions').style.display = 'block';
            
            // Reiniciar variables
            tiempoRestante = 1200;
            respuestasUsuario = [];
            preguntaActual = 0;
            quizActivo = true;
            
            // Actualizar barra de progreso
            document.getElementById('quizProgress').style.width = '0%';
            
            // Iniciar temporizador
            updateTimer();
            intervalo = setInterval(updateTimer, 1000);
            
            // Cargar primera pregunta
            cargarPregunta();
        }

        function updateTimer() {
            tiempoRestante--;
            
            // Formatear tiempo como MM:SS
            const minutos = Math.floor(tiempoRestante / 60).toString().padStart(2, '0');
            const segundos = (tiempoRestante % 60).toString().padStart(2, '0');
            document.getElementById('timer').textContent = `${minutos}:${segundos}`;
            
            // Cambiar color cuando quede poco tiempo
            if (tiempoRestante <= 60) {
                document.getElementById('timer').style.background = 'var(--color-warning)';
            }
            
            // Finalizar quiz si se acaba el tiempo
            if (tiempoRestante <= 0) {
                finalizarQuiz();
            }
        }

        function cargarPregunta() {
            if (preguntaActual >= quizData.length) {
                finalizarQuiz();
                return;
            }
            
            const pregunta = quizData[preguntaActual];
            const contenedor = document.getElementById('questions');
            
            // Crear HTML de la pregunta
            contenedor.innerHTML = `
                <div class="pregunta">
                    <h3>${preguntaActual + 1}. ${pregunta.pregunta}</h3>
                    ${pregunta.opciones.map((opcion, i) => `
                        <button onclick="seleccionarRespuesta(${i})">${String.fromCharCode(65 + i)}. ${opcion}</button>
                    `).join('')}
                    <div class="progress-bar">
                        <div class="progress" style="width: ${((preguntaActual + 1) / quizData.length) * 100}%"></div>
                    </div>
                    <p style="text-align: center; margin-top: 10px;">Pregunta ${preguntaActual + 1} de ${quizData.length}</p>
                </div>
            `;
            
            // Actualizar barra de progreso general
            document.getElementById('quizProgress').style.width = `${(preguntaActual / quizData.length) * 100}%`;
        }

        function seleccionarRespuesta(respuestaIndex) {
            if (!quizActivo) return;
            
            const pregunta = quizData[preguntaActual];
            const esCorrecta = respuestaIndex === pregunta.correcta;
            
            // Guardar respuesta del usuario
            respuestasUsuario.push({
                preguntaIndex: preguntaActual,
                respuestaIndex: respuestaIndex,
                correcta: esCorrecta,
                explicacion: pregunta.explicacion
            });
            
            // Deshabilitar todos los botones
            const botones = document.querySelectorAll('.pregunta button');
            botones.forEach(btn => btn.disabled = true);
            
            // Marcar respuesta correcta e incorrecta
            botones[pregunta.correcta].classList.add('correcta');
            if (!esCorrecta) {
                botones[respuestaIndex].classList.add('incorrecta');
            }
            
            // Mostrar explicación después de un breve retraso
            setTimeout(() => {
                const preguntaDiv = document.querySelector('.pregunta');
                const explicacionDiv = document.createElement('div');
                explicacionDiv.className = 'datos-curiosos';
                explicacionDiv.innerHTML = `
                    <h4><i class="fas fa-info-circle"></i> Explicación</h4>
                    <p>${pregunta.explicacion}</p>
                `;
                preguntaDiv.appendChild(explicacionDiv);
                
                // Pasar a la siguiente pregunta después de 2 segundos
                setTimeout(() => {
                    preguntaActual++;
                    if (preguntaActual < quizData.length) {
                        cargarPregunta();
                    } else {
                        finalizarQuiz();
                    }
                }, 2000);
            }, 1000);
        }

        function finalizarQuiz() {
            // Detener temporizador
            clearInterval(intervalo);
            quizActivo = false;
            
            // Calcular resultados
            const correctas = respuestasUsuario.filter(r => r.correcta).length;
            const porcentaje = Math.round((correctas / quizData.length) * 100);
            
            // Mostrar resultados
            document.getElementById('questions').style.display = 'none';
            document.getElementById('resultados').style.display = 'block';
            document.getElementById('puntaje').textContent = `Obtuviste ${correctas} de ${quizData.length} correctas (${porcentaje}%)`;
            
            // Mostrar mensaje según el desempeño
            let mensaje = "";
            if (porcentaje >= 90) {
                mensaje = "¡Excelente! Dominas la geometría esférica y la aviación mexicana 🏆";
                document.querySelectorAll('.trophy')[0].classList.add('active');
                document.querySelectorAll('.trophy')[1].classList.add('active');
                document.querySelectorAll('.trophy')[2].classList.add('active');
            } else if (porcentaje >= 70) {
                mensaje = "Muy bien, pero puedes mejorar. Revisa los conceptos de geometría esférica 🥈";
                document.querySelectorAll('.trophy')[1].classList.add('active');
                document.querySelectorAll('.trophy')[2].classList.add('active');
            } else if (porcentaje >= 50) {
                mensaje = "Estás en el camino correcto, sigue estudiando 🥉";
                document.querySelectorAll('.trophy')[2].classList.add('active');
            } else {
                mensaje = "Te recomendamos repasar los materiales del curso. ¡Sigue intentándolo!";
            }
            
            document.getElementById('mensaje').textContent = mensaje;
            
            // Actualizar barra de progreso al 100%
            document.getElementById('quizProgress').style.width = '100%';
        }

        function closeQuiz() {
            // Ocultar modal
            document.getElementById('quizModal').style.display = 'none';
            
            // Reiniciar temporizador
            document.getElementById('timer').textContent = '20:00';
            document.getElementById('timer').style.background = 'var(--color-primary)';
        }

        // Permitir enviar la contraseña con Enter
        document.getElementById('password').addEventListener('keypress', function(e) {
            if (e.key === 'Enter') {
                checkPassword();
            }
        });

        // Efecto de shake para CSS
        const style = document.createElement('style');
        style.textContent = `
            @keyframes shake {
                0%, 100% { transform: translateX(0); }
                20%, 60% { transform: translateX(-5px); }
                40%, 80% { transform: translateX(5px); }
            }
        `;
        document.head.appendChild(style);
    </script>
</body>
</html>

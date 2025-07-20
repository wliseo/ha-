<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>La Carcacha - Sitio en Mantenimiento</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;900&family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --gold: #FFD700;
            --gold-dark: #C9A227;
            --gold-light: #fff9c4;
            --red: #E63946;
            --red-light: #ffcdd2;
            --dark: #1A1A1A;
            --light: #F8F9FA;
            --gray: #343A40;
            --transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(135deg, #0f0c29, #302b63, #24243e);
            color: var(--light);
            min-height: 100vh;
            overflow: hidden;
            position: relative;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 20px;
        }

        body::before {
            content: "";
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                radial-gradient(circle at 20% 30%, rgba(255, 215, 0, 0.05) 0%, transparent 40%),
                radial-gradient(circle at 80% 70%, rgba(230, 57, 70, 0.05) 0%, transparent 40%);
            z-index: -1;
            pointer-events: none;
        }

        /* Animación de fondo */
        .background-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -2;
            overflow: hidden;
        }

        .floating-element {
            position: absolute;
            border-radius: 50%;
            background: radial-gradient(circle, var(--gold) 0%, transparent 70%);
            opacity: 0.1;
            filter: blur(10px);
            animation: float 25s infinite linear;
        }

        @keyframes float {
            0% { transform: translateY(0) translateX(0) rotate(0deg); }
            100% { transform: translateY(-100vh) translateX(100px) rotate(360deg); }
        }

        .main-container {
            max-width: 1200px;
            width: 100%;
            position: relative;
            z-index: 10;
        }

        /* Header Premium */
        .header {
            text-align: center;
            margin-bottom: 60px;
            animation: fadeInDown 1s ease-out;
        }

        .logo {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 20px;
            margin-bottom: 30px;
        }

        .logo-icon {
            font-size: 5rem;
            color: var(--gold);
            text-shadow: 0 0 25px rgba(255, 215, 0, 0.8);
            animation: pulse 3s infinite;
        }

        .logo-text {
            font-family: 'Playfair Display', serif;
            font-size: 4.5rem;
            font-weight: 900;
            color: var(--gold);
            position: relative;
            letter-spacing: 3px;
            text-shadow: 0 0 20px rgba(255, 215, 0, 0.6);
        }

        .logo-text::after {
            content: "";
            position: absolute;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            width: 220px;
            height: 5px;
            background: var(--red);
            border-radius: 5px;
            box-shadow: 0 0 15px rgba(230, 57, 70, 0.7);
        }

        .tagline {
            font-size: 1.8rem;
            margin-top: 40px;
            color: var(--gold-light);
            font-weight: 300;
            letter-spacing: 1px;
            text-shadow: 0 0 10px rgba(255, 215, 0, 0.4);
        }

        /* Modal de Mantenimiento */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.9);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 1000;
            animation: fadeIn 0.8s ease-out;
        }

        .modal-content {
            background: linear-gradient(135deg, rgba(40, 40, 40, 0.95), rgba(26, 26, 26, 0.95));
            width: 90%;
            max-width: 800px;
            border-radius: 25px;
            border: 3px solid var(--gold);
            padding: 50px;
            position: relative;
            box-shadow: 0 0 50px rgba(255, 215, 0, 0.5);
            animation: scaleIn 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            overflow: hidden;
        }

        .modal-content::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                radial-gradient(circle at 20% 30%, rgba(255, 215, 0, 0.05) 0%, transparent 40%),
                radial-gradient(circle at 80% 70%, rgba(230, 57, 70, 0.05) 0%, transparent 40%);
            z-index: -1;
        }

        .modal-header {
            text-align: center;
            margin-bottom: 40px;
        }

        .modal-icon {
            font-size: 5rem;
            color: var(--red);
            margin-bottom: 25px;
            animation: pulse 2s infinite;
            text-shadow: 0 0 20px rgba(230, 57, 70, 0.7);
        }

        .modal-title {
            font-family: 'Playfair Display', serif;
            font-size: 3.5rem;
            color: var(--red-light);
            margin-bottom: 15px;
            text-shadow: 0 0 15px rgba(230, 57, 70, 0.5);
        }

        .modal-subtitle {
            font-size: 1.8rem;
            color: var(--gold);
            font-weight: 600;
            letter-spacing: 1px;
        }

        .modal-body {
            background: rgba(0, 0, 0, 0.4);
            border-radius: 20px;
            padding: 40px;
            border: 1px solid var(--gold);
            margin-bottom: 40px;
            position: relative;
        }

        .modal-body::before {
            content: "";
            position: absolute;
            top: 10px;
            left: 10px;
            right: 10px;
            bottom: 10px;
            border: 1px solid rgba(255, 215, 0, 0.3);
            border-radius: 15px;
            pointer-events: none;
        }

        .maintenance-message {
            font-size: 1.6rem;
            line-height: 1.8;
            text-align: center;
            color: var(--light);
        }

        .maintenance-message strong {
            color: var(--gold);
            font-weight: 600;
        }

        .maintenance-message .highlight {
            display: inline-block;
            background: rgba(255, 215, 0, 0.2);
            padding: 0 10px;
            border-radius: 5px;
            color: var(--gold);
            font-weight: 600;
            margin: 10px 0;
        }

        .modal-footer {
            text-align: center;
        }

        .modal-btn {
            display: inline-block;
            padding: 18px 45px;
            background: linear-gradient(to right, var(--gold-dark), var(--gold));
            color: var(--dark);
            text-decoration: none;
            border-radius: 50px;
            font-weight: 700;
            font-size: 1.5rem;
            transition: var(--transition);
            border: 2px solid transparent;
            box-shadow: 0 5px 20px rgba(255, 215, 0, 0.4);
            cursor: pointer;
        }

        .modal-btn:hover {
            background: transparent;
            color: var(--gold);
            border-color: var(--gold);
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(255, 215, 0, 0.6);
        }

        /* Sección de Acciones */
        .actions-section {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin: 60px 0;
        }

        .action-card {
            background: rgba(40, 40, 40, 0.7);
            border-radius: 25px;
            padding: 40px 30px;
            text-align: center;
            border: 2px solid var(--gold);
            transition: var(--transition);
            position: relative;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.4);
            animation: fadeInUp 0.8s ease-out;
            animation-fill-mode: backwards;
        }

        .action-card:nth-child(1) { animation-delay: 0.2s; }
        .action-card:nth-child(2) { animation-delay: 0.4s; }
        .action-card:nth-child(3) { animation-delay: 0.6s; }

        .action-card:hover {
            transform: translateY(-15px);
            box-shadow: 0 20px 40px rgba(255, 215, 0, 0.3);
            border-color: var(--red);
        }

        .action-card::before {
            content: "";
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255, 215, 0, 0.1), transparent);
            transform: rotate(45deg);
            transition: var(--transition);
            z-index: 0;
        }

        .action-card:hover::before {
            transform: rotate(45deg) translate(10%, 10%);
        }

        .action-icon {
            font-size: 5rem;
            margin-bottom: 30px;
            color: var(--gold);
            transition: var(--transition);
            position: relative;
            z-index: 1;
        }

        .action-card:hover .action-icon {
            color: var(--red);
            transform: scale(1.1);
        }

        .action-title {
            font-size: 2rem;
            color: var(--gold);
            margin-bottom: 20px;
            font-weight: 700;
            position: relative;
            z-index: 1;
        }

        .action-description {
            font-size: 1.2rem;
            margin-bottom: 30px;
            line-height: 1.6;
            position: relative;
            z-index: 1;
        }

        .action-btn {
            display: inline-block;
            padding: 15px 35px;
            background: linear-gradient(to right, var(--red), #ff6b6b);
            color: var(--light);
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            font-size: 1.2rem;
            transition: var(--transition);
            border: 2px solid transparent;
            position: relative;
            z-index: 1;
        }

        .action-btn:hover {
            background: transparent;
            color: var(--red);
            border-color: var(--red);
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(230, 57, 70, 0.4);
        }

        /* Sección de Redes Sociales */
        .social-section {
            background: linear-gradient(135deg, rgba(26, 26, 26, 0.8), rgba(52, 58, 64, 0.8));
            border-radius: 25px;
            padding: 60px 40px;
            margin-top: 80px;
            position: relative;
            border: 2px solid var(--gold);
            overflow: hidden;
            box-shadow: 0 20px 50px rgba(0, 0, 0, 0.5);
            animation: fadeInUp 1s ease-out;
        }

        .social-section::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                radial-gradient(circle at 20% 30%, rgba(255, 215, 0, 0.05) 0%, transparent 40%),
                radial-gradient(circle at 80% 70%, rgba(230, 57, 70, 0.05) 0%, transparent 40%);
            z-index: -1;
        }

        .social-title {
            font-family: 'Playfair Display', serif;
            font-size: 3.5rem;
            text-align: center;
            color: var(--gold);
            margin-bottom: 20px;
            text-shadow: 0 0 15px rgba(255, 215, 0, 0.4);
        }

        .social-subtitle {
            font-size: 1.8rem;
            text-align: center;
            margin-bottom: 50px;
            max-width: 800px;
            margin-left: auto;
            margin-right: auto;
            line-height: 1.6;
            color: var(--gold-light);
        }

        .social-subtitle span {
            color: var(--gold);
            font-weight: 600;
            display: inline-block;
            position: relative;
        }

        .social-subtitle span::after {
            content: "";
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 100%;
            height: 2px;
            background: var(--gold);
        }

        .social-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .social-card {
            background: rgba(30, 30, 30, 0.7);
            border-radius: 20px;
            padding: 35px;
            text-align: center;
            border: 1px solid var(--gold);
            transition: var(--transition);
            position: relative;
            overflow: hidden;
        }

        .social-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 35px rgba(255, 215, 0, 0.2);
        }

        .social-icon {
            font-size: 4.5rem;
            margin-bottom: 25px;
            transition: var(--transition);
        }

        .social-card.instagram .social-icon {
            color: #E1306C;
        }

        .social-card.tiktok .social-icon {
            color: #69C9D0;
        }

        .social-card:hover .social-icon {
            transform: scale(1.2);
        }

        .social-name {
            font-size: 2.2rem;
            margin-bottom: 20px;
            font-weight: 700;
        }

        .social-link {
            display: inline-block;
            padding: 12px 30px;
            background: rgba(255, 255, 255, 0.1);
            color: var(--light);
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            font-size: 1.2rem;
            transition: var(--transition);
            border: 1px solid var(--gold);
        }

        .social-link:hover {
            background: var(--gold);
            color: var(--dark);
            transform: translateY(-3px);
        }

        /* Footer */
        .footer {
            text-align: center;
            padding: 50px 0;
            margin-top: 80px;
            border-top: 1px solid rgba(255, 215, 0, 0.2);
            animation: fadeInUp 1.2s ease-out;
        }

        .footer-text {
            font-size: 1.4rem;
            max-width: 700px;
            margin: 0 auto 30px;
            line-height: 1.8;
            color: var(--gold-light);
        }

        .copyright {
            font-size: 1.1rem;
            opacity: 0.7;
            margin-top: 30px;
        }

        /* Animaciones */
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes scaleIn {
            from { transform: scale(0.8); opacity: 0; }
            to { transform: scale(1); opacity: 1; }
        }

        @keyframes fadeInDown {
            from { opacity: 0; transform: translateY(-50px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(50px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Responsive */
        @media (max-width: 992px) {
            .logo-text {
                font-size: 3.8rem;
            }
            
            .maintenance-message {
                font-size: 1.4rem;
            }
        }

        @media (max-width: 768px) {
            .logo {
                flex-direction: column;
                gap: 10px;
            }
            
            .logo-text {
                font-size: 3.2rem;
            }
            
            .logo-icon {
                font-size: 4rem;
            }
            
            .tagline {
                font-size: 1.5rem;
            }
            
            .modal-title {
                font-size: 2.8rem;
            }
            
            .modal-subtitle {
                font-size: 1.5rem;
            }
            
            .social-title {
                font-size: 2.8rem;
            }
            
            .social-subtitle {
                font-size: 1.5rem;
            }
        }

        @media (max-width: 480px) {
            .logo-text {
                font-size: 2.5rem;
            }
            
            .tagline {
                font-size: 1.2rem;
            }
            
            .modal-content {
                padding: 30px;
            }
            
            .modal-title {
                font-size: 2.2rem;
            }
            
            .modal-subtitle {
                font-size: 1.2rem;
            }
            
            .maintenance-message {
                font-size: 1.2rem;
            }
            
            .modal-btn {
                padding: 15px 35px;
                font-size: 1.2rem;
            }
            
            .social-title {
                font-size: 2.2rem;
            }
            
            .social-subtitle {
                font-size: 1.2rem;
            }
        }
    </style>
</head>
<body>
    <!-- Animación de fondo -->
    <div class="background-animation" id="background-animation"></div>
    
    <!-- Modal de Mantenimiento -->
    <div class="modal-overlay" id="maintenance-modal">
        <div class="modal-content">
            <div class="modal-header">
                <div class="modal-icon">
                    <i class="fas fa-tools"></i>
                </div>
                <h2 class="modal-title">SITIO EN MANTENIMIENTO</h2>
                <p class="modal-subtitle">Disculpe las molestias - Estamos trabajando para usted</p>
            </div>
            
            <div class="modal-body">
                <p class="maintenance-message">
                    <span class="highlight">¡Apreciable cliente!</span><br><br>
                    
                    Al ingresar, le pedimos una sincera disculpa por los grandes inconvenientes que pueda ocasionarle esta situación. 
                    Nuestro sitio web se encuentra actualmente en reparación para poder ofrecerle el mejor servicio posible, 
                    tal y como siempre lo hemos deseado y usted merece.<br><br>
                    
                    <strong>Sin embargo, queremos asegurarle que hemos habilitado acceso a todo lo primordial</strong> 
                    para que pueda disfrutar de nuestra deliciosa oferta gastronómica. 
                    Agradecemos profundamente su comprensión y paciencia durante este proceso de mejora.<br><br>
                    
                    ¡Estamos trabajando incansablemente para superar sus expectativas!
                </p>
            </div>
            
            <div class="modal-footer">
                <button class="modal-btn" id="accept-btn">
                    <i class="fas fa-check-circle"></i> Entendido, continuar
                </button>
            </div>
        </div>
    </div>
    
    <!-- Contenido Principal -->
    <div class="main-container">
        <header class="header">
            <div class="logo">
                <div class="logo-icon">
                    <i class="fas fa-hamburger"></i>
                </div>
                <h1 class="logo-text">LA CARCACHA</h1>
            </div>
            <p class="tagline">El mejor restaurante de comida rápida en Guadalajara</p>
        </header>
        
        <!-- Sección de Acciones -->
        <div class="actions-section">
            <div class="action-card">
                <div class="action-icon">
                    <i class="fas fa-book-open"></i>
                </div>
                <h3 class="action-title">Nuestro Menú</h3>
                <p class="action-description">
                    Descubre nuestras deliciosas especialidades, combos exclusivos y las mejores promociones
                </p>
                <a href="https://drive.google.com/file/d/1W42uHR91ff9PEoBplefpU9u44ut6V20W/view?usp=drivesdk" 
                   target="_blank" 
                   class="action-btn">
                    Ver Menú Completo
                </a>
            </div>
            
            <div class="action-card">
                <div class="action-icon">
                    <i class="fas fa-map-marked-alt"></i>
                </div>
                <h3 class="action-title">Nuestra Ubicación</h3>
                <p class="action-description">
                    Visítanos en nuestro acogedor restaurante en el corazón de Guadalajara
                </p>
                <a href="https://maps.app.goo.gl/ynMMJPxupkG9XRPk7?g_st=iwb" 
                   target="_blank" 
                   class="action-btn">
                    Ver en Google Maps
                </a>
            </div>
            
            <div class="action-card">
                <div class="action-icon">
                    <i class="fas fa-phone-alt"></i>
                </div>
                <h3 class="action-title">Contáctanos</h3>
                <p class="action-description">
                    Realiza tu pedido por teléfono o solicita información sobre nuestros servicios
                </p>
                <a href="tel:+523311234567" class="action-btn">
                    Llamar Ahora
                </a>
            </div>
        </div>
        
        <!-- Sección de Redes Sociales -->
        <div class="social-section">
            <h2 class="social-title">¡SIGUENOS EN REDES SOCIALES!</h2>
            <p class="social-subtitle">
                Descubre las <span>mejores promociones</span>, <span>sorpresas exclusivas</span> 
                y <span>contenido especial</span> que tenemos preparado para ti
            </p>
            
            <div class="social-grid">
                <div class="social-card instagram">
                    <div class="social-icon">
                        <i class="fab fa-instagram"></i>
                    </div>
                    <h3 class="social-name">Instagram</h3>
                    <a href="https://www.instagram.com/la_carcacha_oficial?igsh=NXlsdHQxYTN1NWMx" 
                       target="_blank" 
                       class="social-link">
                        @la_carcacha_oficial
                    </a>
                </div>
                
                <div class="social-card tiktok">
                    <div class="social-icon">
                        <i class="fab fa-tiktok"></i>
                    </div>
                    <h3 class="social-name">TikTok</h3>
                    <a href="https://www.tiktok.com/@lacarcacha.oficial?_t=ZS-8yBELrKoHpY&_r=1" 
                       target="_blank" 
                       class="social-link">
                        @lacarcacha.oficial
                    </a>
                </div>
            </div>
        </div>
        
        <!-- Footer -->
        <footer class="footer">
            <p class="footer-text">
                En La Carcacha, nos enorgullece ofrecer la auténtica experiencia de comida rápida de Guadalajara, 
                con sabores tradicionales y un servicio excepcional.
            </p>
            <p class="copyright">
                © 2023 La Carcacha. Todos los derechos reservados. Sitio en mantenimiento.
            </p>
        </footer>
    </div>
    
    <script>
        // Crear elementos flotantes de fondo
        document.addEventListener('DOMContentLoaded', function() {
            const animationContainer = document.getElementById('background-animation');
            const elementCount = 15;
            
            for (let i = 0; i < elementCount; i++) {
                const element = document.createElement('div');
                element.classList.add('floating-element');
                
                // Tamaño aleatorio
                const size = Math.random() * 200 + 50;
                element.style.width = `${size}px`;
                element.style.height = `${size}px`;
                
                // Posición inicial aleatoria
                element.style.left = `${Math.random() * 100}%`;
                element.style.top = `${Math.random() * 100}%`;
                
                // Duración de animación aleatoria
                const duration = Math.random() * 30 + 20;
                element.style.animationDuration = `${duration}s`;
                
                // Retraso inicial aleatorio
                const delay = Math.random() * 10;
                element.style.animationDelay = `${delay}s`;
                
                animationContainer.appendChild(element);
            }
            
            // Cerrar modal
            const modal = document.getElementById('maintenance-modal');
            const acceptBtn = document.getElementById('accept-btn');
            
            acceptBtn.addEventListener('click', function() {
                modal.style.animation = 'fadeOut 0.8s ease-out forwards';
                setTimeout(() => {
                    modal.style.display = 'none';
                }, 800);
            });
            
            // Agregar animación fadeOut
            const style = document.createElement('style');
            style.innerHTML = `
                @keyframes fadeOut {
                    from { opacity: 1; }
                    to { opacity: 0; }
                }
            `;
            document.head.appendChild(style);
        });
    </script>
</body>
</html>

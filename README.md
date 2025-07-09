<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>La Carcacha - Hamburguesas Premium | Guadalajara</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        /* Estilos Premium */
        :root {
            --primary: #c62828;
            --primary-dark: #8e0000;
            --primary-light: #ff5f52;
            --gold: #ffd700;
            --text: #333;
            --light-bg: #f9f5f0;
            --dark-bg: #1a1a1a;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Montserrat', 'Arial', sans-serif;
        }
        
        @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500;600;700&display=swap');
        
        body {
            background-color: var(--light-bg);
            color: var(--text);
            line-height: 1.7;
            overflow-x: hidden;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        /* Header de Lujo */
        header {
            background: linear-gradient(rgba(0,0,0,0.7), rgba(0,0,0,0.7)), url('https://images.unsplash.com/photo-1513104890138-7c749659a591?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80');
            background-size: cover;
            background-position: center;
            color: white;
            padding: 40px 0;
            text-align: center;
            position: relative;
            margin-bottom: 60px;
        }
        
        header::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(to bottom, rgba(0,0,0,0.2), rgba(0,0,0,0.7));
        }
        
        .header-content {
            position: relative;
            z-index: 2;
        }
        
        .logo {
            max-width: 250px;
            margin-bottom: 20px;
            border-radius: 50%;
            border: 5px solid var(--gold);
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
            transition: transform 0.5s;
        }
        
        .logo:hover {
            transform: rotate(15deg) scale(1.05);
        }
        
        h1 {
            font-size: 3.5rem;
            margin-bottom: 15px;
            text-shadow: 2px 2px 5px rgba(0,0,0,0.5);
            letter-spacing: 2px;
        }
        
        header p {
            font-size: 1.3rem;
            max-width: 700px;
            margin: 0 auto 20px;
        }
        
        /* Menú Premium */
        .menu-section {
            margin: 60px 0;
            position: relative;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 50px;
            color: var(--primary);
            font-size: 2.5rem;
            position: relative;
            font-weight: 600;
        }
        
        .section-title::after {
            content: "";
            display: block;
            width: 150px;
            height: 4px;
            background: linear-gradient(to right, var(--primary), var(--gold));
            margin: 15px auto;
            border-radius: 2px;
        }
        
        .menu-items {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 40px;
            margin-top: 40px;
        }
        
        .menu-item {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 15px 30px rgba(0,0,0,0.1);
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0, 1);
            position: relative;
        }
        
        .menu-item:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.2);
        }
        
        .item-image {
            width: 100%;
            height: 250px;
            object-fit: cover;
            transition: transform 0.5s;
        }
        
        .menu-item:hover .item-image {
            transform: scale(1.05);
        }
        
        .item-info {
            padding: 25px;
            position: relative;
        }
        
        .item-name {
            font-size: 1.8rem;
            margin-bottom: 15px;
            color: var(--primary);
            font-weight: 600;
        }
        
        .item-description {
            color: #666;
            margin-bottom: 20px;
            font-size: 1.05rem;
        }
        
        .item-price {
            font-weight: bold;
            font-size: 1.5rem;
            color: var(--text);
            display: flex;
            align-items: center;
            justify-content: space-between;
        }
        
        .add-bacon {
            background-color: var(--primary);
            color: white;
            border: none;
            padding: 8px 15px;
            border-radius: 30px;
            font-size: 0.9rem;
            cursor: pointer;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            gap: 5px;
        }
        
        .add-bacon:hover {
            background-color: var(--primary-dark);
            transform: translateY(-2px);
        }
        
        .add-bacon i {
            color: var(--gold);
        }
        
        /* Modal Premium */
        .modal {
            display: none;
            position: fixed;
            z-index: 1000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0,0,0,0.9);
            overflow: auto;
            animation: fadeIn 0.4s;
        }
        
        @keyframes fadeIn {
            from {opacity: 0;}
            to {opacity: 1;}
        }
        
        .modal-content {
            background-color: #fff;
            margin: 5% auto;
            padding: 40px;
            border-radius: 15px;
            width: 80%;
            max-width: 700px;
            position: relative;
            animation: slideIn 0.5s cubic-bezier(0.175, 0.885, 0, 1);
            box-shadow: 0 30px 60px rgba(0,0,0,0.3);
            border: 2px solid var(--gold);
        }
        
        @keyframes slideIn {
            from {transform: translateY(-100px); opacity: 0;}
            to {transform: translateY(0); opacity: 1;}
        }
        
        .close {
            position: absolute;
            right: 25px;
            top: 25px;
            font-size: 32px;
            font-weight: bold;
            color: #aaa;
            cursor: pointer;
            transition: color 0.3s;
        }
        
        .close:hover {
            color: var(--primary);
        }
        
        .modal-image {
            width: 100%;
            max-height: 350px;
            object-fit: cover;
            border-radius: 10px;
            margin-bottom: 25px;
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
        }
        
        .modal-title {
            color: var(--primary);
            margin-bottom: 20px;
            font-size: 2.2rem;
            font-weight: 700;
        }
        
        .modal-description {
            margin-bottom: 25px;
            line-height: 1.8;
            font-size: 1.1rem;
        }
        
        .modal-price {
            font-weight: bold;
            font-size: 1.8rem;
            color: var(--text);
            margin-top: 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .modal-extras {
            margin-top: 20px;
            padding-top: 20px;
            border-top: 1px dashed #ddd;
        }
        
        .modal-extras p {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 10px;
            color: #555;
        }
        
        .modal-extras i {
            color: var(--gold);
        }
        
        /* Welcome Modal Premium */
        .welcome-modal {
            display: none;
            position: fixed;
            z-index: 2000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0,0,0,0.95);
            overflow: auto;
        }
        
        .welcome-content {
            background: linear-gradient(135deg, var(--primary), var(--primary-dark));
            color: white;
            margin: 10% auto;
            padding: 50px;
            border-radius: 15px;
            width: 80%;
            max-width: 800px;
            text-align: center;
            position: relative;
            animation: welcomeIn 0.6s cubic-bezier(0.175, 0.885, 0, 1);
            box-shadow: 0 30px 60px rgba(0,0,0,0.5);
            border: 3px solid var(--gold);
        }
        
        @keyframes welcomeIn {
            from {transform: scale(0.8); opacity: 0;}
            to {transform: scale(1); opacity: 1;}
        }
        
        .welcome-close {
            position: absolute;
            right: 30px;
            top: 30px;
            font-size: 36px;
            font-weight: bold;
            color: white;
            cursor: pointer;
            transition: color 0.3s;
        }
        
        .welcome-close:hover {
            color: var(--gold);
        }
        
        .welcome-logo {
            width: 200px;
            height: 200px;
            object-fit: cover;
            border-radius: 50%;
            border: 5px solid var(--gold);
            margin: 0 auto 30px;
            box-shadow: 0 15px 30px rgba(0,0,0,0.3);
            animation: pulse 2s infinite;
        }
        
        @keyframes pulse {
            0% {transform: scale(1);}
            50% {transform: scale(1.05);}
            100% {transform: scale(1);}
        }
        
        .welcome-title {
            font-size: 3rem;
            margin-bottom: 20px;
            text-shadow: 2px 2px 5px rgba(0,0,0,0.3);
            letter-spacing: 1px;
        }
        
        .welcome-message {
            font-size: 1.4rem;
            line-height: 1.8;
            max-width: 600px;
            margin: 0 auto 30px;
        }
        
        .welcome-button {
            background-color: var(--gold);
            color: var(--dark-bg);
            border: none;
            padding: 15px 40px;
            border-radius: 50px;
            font-size: 1.2rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }
        
        .welcome-button:hover {
            background-color: white;
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.3);
        }
        
        /* Contacto Premium */
        .contact-section {
            text-align: center;
            margin: 80px 0;
            background-color: white;
            padding: 50px;
            border-radius: 15px;
            box-shadow: 0 15px 30px rgba(0,0,0,0.05);
        }
        
        .social-icons {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin: 40px 0;
        }
        
        .social-icon {
            font-size: 2.5rem;
            color: var(--primary);
            transition: all 0.3s;
            background: white;
            width: 70px;
            height: 70px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        
        .social-icon:hover {
            color: white;
            background: var(--primary);
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0,0,0,0.2);
        }
        
        .phone {
            font-size: 1.5rem;
            margin: 30px 0;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
        }
        
        .phone i {
            color: var(--primary);
        }
        
        .delivery-platforms {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin: 50px 0;
            flex-wrap: wrap;
        }
        
        .delivery-logo {
            height: 60px;
            object-fit: contain;
            transition: all 0.3s;
            filter: grayscale(100%);
            opacity: 0.7;
        }
        
        .delivery-logo:hover {
            filter: grayscale(0%);
            opacity: 1;
            transform: scale(1.1);
        }
        
        .payment-methods {
            margin-top: 50px;
            padding-top: 50px;
            border-top: 1px solid #eee;
        }
        
        .payment-title {
            font-size: 1.3rem;
            margin-bottom: 20px;
            color: #666;
        }
        
        .payment-icons {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
        }
        
        .payment-icon {
            height: 40px;
            object-fit: contain;
        }
        
        /* Footer Premium */
        footer {
            background-color: var(--dark-bg);
            color: white;
            text-align: center;
            padding: 40px 0;
            margin-top: 80px;
        }
        
        .footer-content {
            max-width: 800px;
            margin: 0 auto;
        }
        
        .footer-logo {
            max-width: 150px;
            margin-bottom: 20px;
            opacity: 0.8;
        }
        
        .rights {
            font-size: 1rem;
            opacity: 0.7;
            margin-top: 20px;
        }
        
        /* Efectos especiales */
        .floating {
            animation: floating 3s ease-in-out infinite;
        }
        
        @keyframes floating {
            0% {transform: translateY(0px);}
            50% {transform: translateY(-15px);}
            100% {transform: translateY(0px);}
        }
        
        /* Responsive */
        @media (max-width: 992px) {
            h1 {
                font-size: 2.8rem;
            }
            
            .welcome-title {
                font-size: 2.5rem;
            }
            
            .menu-items {
                grid-template-columns: 1fr;
            }
        }
        
        @media (max-width: 768px) {
            h1 {
                font-size: 2.2rem;
            }
            
            header p {
                font-size: 1.1rem;
            }
            
            .section-title {
                font-size: 2rem;
            }
            
            .modal-content, .welcome-content {
                width: 90%;
                padding: 30px;
            }
            
            .welcome-title {
                font-size: 2rem;
            }
            
            .welcome-message {
                font-size: 1.2rem;
            }
            
            .social-icons {
                gap: 15px;
            }
            
            .social-icon {
                width: 50px;
                height: 50px;
                font-size: 1.8rem;
            }
        }
        
        @media (max-width: 480px) {
            h1 {
                font-size: 1.8rem;
            }
            
            .logo {
                max-width: 180px;
            }
            
            .section-title {
                font-size: 1.6rem;
            }
            
            .item-name {
                font-size: 1.5rem;
            }
            
            .phone {
                font-size: 1.2rem;
            }
            
            .delivery-logo {
                height: 40px;
            }
        }
    </style>
</head>
<body>
    <!-- Welcome Modal Premium -->
    <div id="welcomeModal" class="welcome-modal">
        <div class="welcome-content">
            <span class="welcome-close">&times;</span>
            <img src="https://p16-sign-sg.tiktokcdn.com/tos-alisg-avt-0068/a91347bde32c95049cd5d47fc87fe3e7~tplv-tiktokx-cropcenter:1080:1080.jpeg?dr=14579&refresh_token=681f122f&x-expires=1752210000&x-signature=jr%2Bs18vryICY84KA19jJ8Umbx0o%3D&t=4d5b0474&ps=13740610&shp=a5d48078&shcp=81f88b70&idc=maliva" alt="Logo La Carcacha" class="welcome-logo floating">
            <h2 class="welcome-title">¡BIENVENIDO A LA CARCACHA!</h2>
            <p class="welcome-message">El negocio de comida rápida más delicioso y premiado de Guadalajara. Disfruta de nuestras hamburguesas y hot dogs preparados con ingredientes premium y certificaciones de calidad.</p>
            <button class="welcome-button" onclick="closeModal('welcomeModal')">VER MENÚ</button>
        </div>
    </div>

    <header>
        <div class="header-content">
            <img src="https://p16-sign-sg.tiktokcdn.com/tos-alisg-avt-0068/a91347bde32c95049cd5d47fc87fe3e7~tplv-tiktokx-cropcenter:1080:1080.jpeg?dr=14579&refresh_token=681f122f&x-expires=1752210000&x-signature=jr%2Bs18vryICY84KA19jJ8Umbx0o%3D&t=4d5b0474&ps=13740610&shp=a5d48078&shcp=81f88b70&idc=maliva" alt="La Carcacha Logo" class="logo">
            <h1>LA CARCACHA</h1>
            <p>Hamburguesas Artesanales & Hot Dogs Premium</p>
        </div>
    </header>
    
    <main class="container">
        <section class="menu-section">
            <h2 class="section-title">HAMBURGUESAS PREMIUM</h2>
            <div class="menu-items">
                <!-- Hamburguesa Premium -->
                <div class="menu-item" onclick="openModal('premiumModal')">
                    <img src="https://photos.tryotter.com/cdn-cgi/image/fit=crop,width=492,height=267,quality=60,format=auto/menu-photos/e0384d19-feb6-4387-a4ad-93cd055a0775.jpeg" alt="Hamburguesa Premium" class="item-image">
                    <div class="item-info">
                        <h3 class="item-name">Hamburguesa Premium</h3>
                        <p class="item-description">Carne Arrachera certificada DIF, queso artesanal, vegetales frescos y nuestra salsa secreta.</p>
                        <div class="item-price">
                            <span>$65.00 MXN</span>
                            <button class="add-bacon" onclick="event.stopPropagation();">
                                <i class="fas fa-plus"></i> +$2 (Tocino)
                            </button>
                        </div>
                    </div>
                </div>
                
                <!-- Hamburguesa Sencilla -->
                <div class="menu-item" onclick="openModal('sencillaModal')">
                    <img src="https://file.adomicil.io/carlsjr.adomicil.io/_files/images/product/lanzamientosteamburger-sencilla-0315367632226724.jpg" alt="Hamburguesa Sencilla" class="item-image">
                    <div class="item-info">
                        <h3 class="item-name">Hamburguesa Sencilla</h3>
                        <p class="item-description">Carne de res certificada TIF, queso americano, lechuga, tomate y mayonesa casera.</p>
                        <div class="item-price">
                            <span>$45.00 MXN</span>
                            <button class="add-bacon" onclick="event.stopPropagation();">
                                <i class="fas fa-plus"></i> +$2 (Tocino)
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        
        <section class="menu-section">
            <h2 class="section-title">HOT DOGS GOURMET</h2>
            <div class="menu-items">
                <!-- Hot Dog Premium -->
                <div class="menu-item" onclick="openModal('hotdogPremiumModal')">
                    <img src="https://images.unsplash.com/photo-1619740455993-9e612b1af08a?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80" alt="Hot Dog Premium" class="item-image">
                    <div class="item-info">
                        <h3 class="item-name">Hot Dog Premium</h3>
                        <p class="item-description">Salchicha de pavo premium con toppings gourmet y salsas artesanales.</p>
                        <div class="item-price">
                            <span>$25.00 MXN</span>
                        </div>
                    </div>
                </div>
                
                <!-- Hot Dog Sencillo -->
                <div class="menu-item" onclick="openModal('hotdogSencilloModal')">
                    <img src="https://images.unsplash.com/photo-1619740455993-9e612b1af08a?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80" alt="Hot Dog Sencillo" class="item-image">
                    <div class="item-info">
                        <h3 class="item-name">Hot Dog Sencillo</h3>
                        <p class="item-description">Salchicha tipo viñeta (mezcla de cerdo, ave y res) con toppings clásicos.</p>
                        <div class="item-price">
                            <span>$25.00 MXN</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        
        <section class="contact-section">
            <h2 class="section-title">CONTÁCTANOS</h2>
            <div class="social-icons">
                <a href="https://www.instagram.com/la_carcacha_oficial?igsh=MWN6dW45bTh6bndreA%3D%3D&utm_source=qr" class="social-icon" target="_blank"><i class="fab fa-instagram"></i></a>
                <a href="https://www.tiktok.com/@lacarcacha.oficial" class="social-icon" target="_blank"><i class="fab fa-tiktok"></i></a>
                <a href="tel:3317549392" class="social-icon"><i class="fas fa-phone"></i></a>
            </div>
            
            <p class="phone">
                <i class="fas fa-phone-alt"></i> Teléfono para pedidos y eventos: <strong>33 1754 9392</strong>
            </p>
            
            <h3 class="section-title">PIDE A DOMICILIO</h3>
            <div class="delivery-platforms">
                <a href="#" target="_blank"><img src="https://s3-eu-west-1.amazonaws.com/tpd/logos/589998870000ff00059c3ce1/0x0.png" alt="Uber Eats" class="delivery-logo"></a>
                <a href="#" target="_blank"><img src="https://img0.didiglobal.com/static/soda_static/c/webapp/img/logo-dark.a997bfad.svg" alt="DiDi Food" class="delivery-logo"></a>
                <a href="#" target="_blank"><img src="https://logosenvector.com/logo/img/rappi-37277.png" alt="Rappi" class="delivery-logo"></a>
            </div>
            
            <div class="payment-methods">
                <h3 class="payment-title">ACEPTAMOS TODOS LOS MEDIOS DE PAGO</h3>
                <div class="payment-icons">
                    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5e/Visa_Inc._logo.svg/2560px-Visa_Inc._logo.svg.png" alt="Visa" class="payment-icon">
                    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/2/2a/Mastercard-logo.svg/1280px-Mastercard-logo.svg.png" alt="Mastercard" class="payment-icon">
                    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/a4/Mexico_Elektra-logo.svg/1200px-Mexico_Elektra-logo.svg.png" alt="Vales de despensa" class="payment-icon">
                    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/8/89/BBVA_2019.svg/1200px-BBVA_2019.svg.png" alt="Transferencia" class="payment-icon">
                </div>
            </div>
        </section>
    </main>
    
    <!-- Modales Premium -->
    <!-- Hamburguesa Premium Modal -->
    <div id="premiumModal" class="modal">
        <div class="modal-content">
            <span class="close" onclick="closeModal('premiumModal')">&times;</span>
            <img src="https://photos.tryotter.com/cdn-cgi/image/fit=crop,width=492,height=267,quality=60,format=auto/menu-photos/e0384d19-feb6-4387-a4ad-93cd055a0775.jpeg" alt="Hamburguesa Premium" class="modal-image">
            <h3 class="modal-title">Hamburguesa Premium</h3>
            <p class="modal-description">Nuestra hamburguesa premium es una obra maestra culinaria elaborada con la mejor Arrachera de México, con certificación DIF. Cada bocado es una explosión de sabores gracias a nuestra cuidadosa selección de ingredientes premium: carne jugosa, queso artesanal derretido, vegetales frescos de la región y nuestra famosa salsa secreta que le da ese toque único que nos distingue.</p>
            <div class="modal-extras">
                <p><i class="fas fa-check-circle"></i> Carne Arrachera 200g certificada DIF</p>
                <p><i class="fas fa-check-circle"></i> Pan brioche artesanal</p>
                <p><i class="fas fa-check-circle"></i> Queso manchego maduro</p>
                <p><i class="fas fa-check-circle"></i> Vegetales frescos de temporada</p>
                <p><i class="fas fa-plus-circle"></i> <strong>Opción:</strong> Agregar tocino crujiente +$2</p>
            </div>
            <p class="modal-price">$65.00 MXN</p>
        </div>
    </div>
    
    <!-- Hamburguesa Sencilla Modal -->
    <div id="sencillaModal" class="modal">
        <div class="modal-content">
            <span class="close" onclick="closeModal('sencillaModal')">&times;</span>
            <img src="https://file.adomicil.io/carlsjr.adomicil.io/_files/images/product/lanzamientosteamburger-sencilla-0315367632226724.jpg" alt="Hamburguesa Sencilla" class="modal-image">
            <h3 class="modal-title">Hamburguesa Sencilla</h3>
            <p class="modal-description">La clásica hamburguesa que nunca pasa de moda, pero elevada a otro nivel. Elaborada con carne de res 100% certificada TIF, garantizando la más alta calidad y sabor. Disfruta de la combinación perfecta: jugosa carne de res, queso americano derretido, lechuga fresca, tomate recién cortado y nuestra mayonesa casera con un toque especial.</p>
            <div class="modal-extras">
                <p><i class="fas fa-check-circle"></i> Carne de res 150g certificada TIF</p>
                <p><i class="fas fa-check-circle"></i> Pan clásico tostado</p>
                <p><i class="fas fa-check-circle"></i> Queso americano premium</p>
                <p><i class="fas fa-check-circle"></i> Lechuga y tomate frescos</p>
                <p><i class="fas fa-plus-circle"></i> <strong>Opción:</strong> Agregar tocino crujiente +$2</p>
            </div>
            <p class="modal-price">$45.00 MXN</p>
        </div>
    </div>
    
    <!-- Hot Dog Premium Modal -->
    <div id="hotdogPremiumModal" class="modal">
        <div class="modal-content">
            <span class="close" onclick="closeModal('hotdogPremiumModal')">&times;</span>
            <img src="https://images.unsplash.com/photo-1619740455993-9e612b1af08a?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80" alt="Hot Dog Premium" class="modal-image">
            <h3 class="modal-title">Hot Dog Premium</h3>
            <p class="modal-description">Nuestro Hot Dog Premium es una experiencia gourmet con salchicha de pavo de la más alta calidad. Cada pieza es cuidadosamente preparada con ingredientes selectos: pan suave ligeramente tostado, salchicha jugosa de pavo, cebolla caramelizada, pimientos asados y nuestra selección de salsas artesanales que lo hacen único en Guadalajara.</p>
            <div class="modal-extras">
                <p><i class="fas fa-check-circle"></i> Salchicha de pavo premium</p>
                <p><i class="fas fa-check-circle"></i> Pan brioche especial para hot dog</p>
                <p><i class="fas fa-check-circle"></i> Cebolla caramelizada</p>
                <p><i class="fas fa-check-circle"></i> Pimientos asados</p>
                <p><i class="fas fa-check-circle"></i> Salsas artesanales</p>
            </div>
            <p class="modal-price">$25.00 MXN</p>
        </div>
    </div>
    
    <!-- Hot Dog Sencillo Modal -->
    <div id="hotdogSencilloModal" class="modal">
        <div class="modal-content">
            <span class="close" onclick="closeModal('hotdogSencilloModal')">&times;</span>
            <img src="https://images.unsplash.com/photo-1619740455993-9e612b1af08a?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80" alt="Hot Dog Sencillo" class="modal-image">
            <h3 class="modal-title">Hot Dog Sencillo</h3>
            <p class="modal-description">El clásico hot dog que todos aman, pero con nuestro toque especial. Preparado con salchicha tipo viñeta (una deliciosa mezcla de cerdo, ave y res) que garantiza un sabor tradicional pero con calidad premium. Acompañado de cebolla picada, tomate fresco, jalapeños en vinagre y tus salsas favoritas para personalizarlo a tu gusto.</p>
            <div class="modal-extras">
                <p><i class="fas fa-check-circle"></i> Salchicha tipo viñeta (cerdo, ave y res)</p>
                <p><i class="fas fa-check-circle"></i> Pan clásico para hot dog</p>
                <p><i class="fas fa-check-circle"></i> Cebolla y tomate frescos</p>
                <p><i class="fas fa-check-circle"></i> Jalapeños en vinagre</p>
                <p><i class="fas fa-check-circle"></i> Variedad de salsas</p>
            </div>
            <p class="modal-price">$25.00 MXN</p>
        </div>
    </div>
    
    <footer>
        <div class="footer-content">
            <img src="https://p16-sign-sg.tiktokcdn.com/tos-alisg-avt-0068/a91347bde32c95049cd5d47fc87fe3e7~tplv-tiktokx-cropcenter:1080:1080.jpeg?dr=14579&refresh_token=681f122f&x-expires=1752210000&x-signature=jr%2Bs18vryICY84KA19jJ8Umbx0o%3D&t=4d5b0474&ps=13740610&shp=a5d48078&shcp=81f88b70&idc=maliva" alt="Logo La Carcacha" class="footer-logo">
            <p>Hamburguesas Artesanales & Hot Dogs Premium</p>
            <p class="rights">© 2025 LA CARCACHA. TODOS LOS DERECHOS RESERVADOS.</p>
        </div>
    </footer>

    <script>
        // Función para abrir modales
        function openModal(modalId) {
            document.getElementById(modalId).style.display = "block";
            document.body.style.overflow = "hidden";
        }
        
        // Función para cerrar modales
        function closeModal(modalId) {
            document.getElementById(modalId).style.display = "none";
            document.body.style.overflow = "auto";
        }
        
        // Cerrar modal al hacer clic fuera del contenido
        window.onclick = function(event) {
            if (event.target.className ===

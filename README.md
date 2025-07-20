<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>El Mejor Restaurante de Guadalajara</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Arial', sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #ff9a00, #ff2d00);
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 20px;
        }
        
        .container {
            background-color: rgba(255, 255, 255, 0.95);
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            padding: 40px;
            max-width: 600px;
            width: 100%;
        }
        
        h1 {
            color: #d35400;
            font-size: 2.5rem;
            margin-bottom: 20px;
            text-shadow: 1px 1px 2px rgba(0,0,0,0.1);
        }
        
        .aviso {
            background-color: #fff8e1;
            border-left: 5px solid #ff9800;
            padding: 20px;
            margin: 30px 0;
            border-radius: 0 8px 8px 0;
            text-align: left;
            font-size: 1.1rem;
            color: #333;
        }
        
        .buttons {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            justify-content: center;
            margin-top: 30px;
        }
        
        .btn {
            flex: 1;
            min-width: 200px;
            padding: 18px 30px;
            border: none;
            border-radius: 50px;
            font-size: 1.2rem;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
            box-shadow: 0 4px 8px rgba(0,0,0,0.2);
        }
        
        .btn-menu {
            background: linear-gradient(to right, #27ae60, #2ecc71);
            color: white;
        }
        
        .btn-mapa {
            background: linear-gradient(to right, #2980b9, #3498db);
            color: white;
        }
        
        .btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 15px rgba(0,0,0,0.3);
        }
        
        .logo {
            width: 100px;
            margin-bottom: 20px;
            filter: drop-shadow(2px 2px 2px rgba(0,0,0,0.2));
        }
        
        @media (max-width: 480px) {
            .container {
                padding: 25px;
            }
            
            h1 {
                font-size: 2rem;
            }
            
            .btn {
                min-width: 100%;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Logo simulado con texto -->
        <div class="logo">🍔🌭🍟</div>
        
        <h1>Bienvenido al mejor restaurante de comida rápida de Guadalajara</h1>
        
        <div class="aviso">
            ⚠️ Por el momento estamos realizando reparaciones en nuestra página web. 
            Disculpa las molestias. ¡Pero aún puedes acceder a nuestro menú y ubicación!
        </div>
        
        <div class="buttons">
            <a href="https://drive.google.com/file/d/1W42uHR91ff9PEoBplefpU9u44ut6V20W/view?usp=drivesdk" target="_blank" class="btn btn-menu">
                VER MENÚ
            </a>
            
            <a href="https://maps.app.goo.gl/ynMMJPxupkG9XRPk7?g_st=iwb" target="_blank" class="btn btn-mapa">
                UBICACIÓN
            </a>
        </div>
    </div>
</body>
</html>

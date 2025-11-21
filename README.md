<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TVS – Neón Digital</title>
    <style>
        /* ====================================================
        1. VARIABLES Y ESTILOS BASE
        ==================================================== */
        :root {
            /* Colores Neón Principal (Cian) */
            --color-neon: #00F0FF; /* Cian brillante */
            --color-neon-shadow: rgba(0, 240, 255, 0.7);
            
            /* Colores Neón Secundario (Rojo/Magenta) */
            --color-red: #FF0077; 
            --color-red-shadow: rgba(255, 0, 119, 0.7);

            /* Colores para la animación de tonalidades */
            --color-neon-alt1: #00FF7F; /* Verde esmeralda */
            --color-neon-alt2: #FFFF00; /* Amarillo */
            --color-neon-alt3: #FF00FF; /* Magenta */

            --color-dark-bg: #0A0A1F; /* Azul muy oscuro, casi negro */
            --color-text-primary: #FFFFFF;
        }

        body {
            margin: 0;
            padding: 0;
            background-color: var(--color-dark-bg);
            color: var(--color-text-primary);
            font-family: 'Montserrat', sans-serif;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            overflow-x: hidden;
        }

        /* ----------------------------------------------------
        2. FONDO DE GRADIENTE FLUÍDO EN MOVIMIENTO
        ---------------------------------------------------- */
        .background-3d-effect {
            position: fixed;
            top: 0;
            left: 0;
            width: 400%;
            height: 400%;
            z-index: -1;
            opacity: 0.7;
            
            background: linear-gradient(
                135deg, 
                var(--color-dark-bg) 0%, 
                #121230 25%, 
                #0A0A1F 50%, 
                #121230 75%, 
                var(--color-dark-bg) 100%
            );
            
            background-size: 200% 200%;
            animation: move-fluid-gradient 30s ease infinite alternate;
        }

        /* Animación: Movimiento de gradiente en diagonal */
        @keyframes move-fluid-gradient {
            0% {
                background-position: 0% 50%;
            }
            100% {
                background-position: 100% 50%;
            }
        }

        /* ----------------------------------------------------
        3. ESTILOS NEÓN Y ANIMACIÓN DE TÍTULO
        ---------------------------------------------------- */
        /* Estilo Neón Cian (Predeterminado) */
        .neon-effect {
            color: var(--color-neon);
            text-shadow: 
                0 0 5px var(--color-neon-shadow),
                0 0 10px var(--color-neon-shadow),
                0 0 20px var(--color-neon);
        }
        
        /* Estilo Neón Rojo */
        .red-neon-effect {
            color: var(--color-red);
            text-shadow: 
                0 0 5px var(--color-red-shadow),
                0 0 10px var(--color-red-shadow),
                0 0 20px var(--color-red);
        }
        
        /* Estilo para el enlace mailto */
        .neon-link {
            color: var(--color-neon);
            text-decoration: none;
            transition: color 0.3s, text-shadow 0.3s;
        }
        
        .neon-link:hover {
            color: var(--color-text-primary);
            text-shadow: 0 0 10px var(--color-neon);
        }

        /* ESTILO Y ANIMACIÓN PARA EL TÍTULO H1 */
        h1.neon-title-animated {
            font-size: 4em;
            text-transform: uppercase;
            margin-bottom: 10px;
            color: var(--color-neon); 
            animation: animate-h1-neon 8s infinite alternate;
        }

        h1.neon-title-animated .animated-text {
            color: inherit; 
        }

        /* Animación para el efecto 3D y cambio de tonalidades en el H1 */
        @keyframes animate-h1-neon {
            0% {
                text-shadow: 
                    1px 1px var(--color-neon), 
                    2px 2px var(--color-neon), 
                    3px 3px var(--color-neon-shadow),
                    0 0 10px var(--color-neon), 
                    0 0 20px var(--color-neon), 
                    0 0 40px rgba(0, 240, 255, 0.5);
                color: var(--color-neon);
            }
            25% {
                text-shadow: 
                    1px 1px var(--color-neon-alt1), 
                    2px 2px var(--color-neon-alt1), 
                    3px 3px rgba(0, 255, 127, 0.7),
                    0 0 10px var(--color-neon-alt1), 
                    0 0 20px var(--color-neon-alt1), 
                    0 0 40px rgba(0, 255, 127, 0.5); 
                color: var(--color-neon-alt1);
            }
            50% {
                text-shadow: 
                    1px 1px var(--color-neon-alt2), 
                    2px 2px var(--color-neon-alt2), 
                    3px 3px rgba(255, 255, 0, 0.7),
                    0 0 10px var(--color-neon-alt2), 
                    0 0 20px var(--color-neon-alt2), 
                    0 0 40px rgba(255, 255, 0, 0.5); 
                color: var(--color-neon-alt2);
            }
            75% {
                text-shadow: 
                    1px 1px var(--color-neon-alt3), 
                    2px 2px var(--color-neon-alt3), 
                    3px 3px rgba(255, 0, 255, 0.7),
                    0 0 10px var(--color-neon-alt3), 
                    0 0 20px var(--color-neon-alt3), 
                    0 0 40px rgba(255, 0, 255, 0.5); 
                color: var(--color-neon-alt3);
            }
            100% {
                text-shadow: 
                    1px 1px var(--color-neon), 
                    2px 2px var(--color-neon), 
                    3px 3px var(--color-neon-shadow),
                    0 0 10px var(--color-neon), 
                    0 0 20px var(--color-neon), 
                    0 0 40px rgba(0, 240, 255, 0.5);
                color: var(--color-neon);
            }
        }


        /* ----------------------------------------------------
        4. ESTRUCTURA Y COMPONENTES
        ---------------------------------------------------- */
        header {
            background-color: rgba(0, 0, 0, 0.4);
            backdrop-filter: blur(5px);
            padding: 15px 50px;
            box-shadow: 0 4px 15px var(--color-neon-shadow);
            position: sticky;
            top: 0;
            z-index: 20;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 2em;
            font-weight: bold;
            text-transform: uppercase;
        }

        nav a {
            color: var(--color-text-primary);
            text-decoration: none;
            margin-left: 35px;
            font-size: 1.1em;
            padding: 5px 0;
            border-bottom: 2px solid transparent;
            transition: color 0.3s, border-bottom 0.3s;
        }

        nav a:hover, nav a.active {
            color: var(--color-neon);
            border-bottom: 2px solid var(--color-neon);
            text-shadow: 0 0 8px var(--color-neon-shadow);
        }

        main {
            flex-grow: 1;
            padding: 80px 50px;
            z-index: 10;
        }

        .hero-section {
            text-align: center;
            padding: 100px 0;
            background-color: rgba(0, 0, 0, 0.6);
            border: 1px solid var(--color-neon);
            border-radius: 10px;
            box-shadow: 0 0 30px var(--color-neon-shadow);
            animation: pulse-neon 4s infinite alternate;
        }

        @keyframes pulse-neon {
            0% { box-shadow: 0 0 15px var(--color-neon-shadow); }
            100% { box-shadow: 0 0 30px var(--color-neon-shadow); }
        }

        .hero-section p {
            font-size: 1.4em;
        }

        .call-to-action {
            display: inline-block;
            margin-top: 40px;
            padding: 15px 35px;
            border: 2px solid var(--color-neon);
            background-color: rgba(0, 240, 255, 0.1);
            color: var(--color-neon);
            text-decoration: none;
            font-weight: bold;
            letter-spacing: 2px;
            border-radius: 5px;
            box-shadow: 0 0 15px var(--color-neon-shadow);
            transition: background-color 0.3s, box-shadow 0.3s, transform 0.3s;
        }

        .call-to-action:hover {
            background-color: rgba(0, 240, 255, 0.3);
            box-shadow: 0 0 25px var(--color-neon);
            transform: scale(1.05);
        }

        section.proyectos {
            margin-top: 80px;
            padding: 40px;
            background-color: rgba(0, 0, 0, 0.7);
            border: 1px solid var(--color-neon); 
            border-radius: 10px;
            box-shadow: 0 0 10px var(--color-neon-shadow);
        }
        
        section.proyectos h2 {
            font-size: 2.5em;
            text-align: center;
            margin-bottom: 40px;
            text-transform: uppercase;
        }

        section.proyectos ul {
            list-style: none;
            padding: 0;
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 20px;
        }
        
        section.proyectos li {
            width: 280px;
            padding: 15px;
            background-color: rgba(0, 0, 0, 0.8);
            border: 1px solid var(--color-neon); 
            border-radius: 8px;
            transition: box-shadow 0.3s, transform 0.3s;
            text-align: center; 
            box-shadow: 0 0 5px var(--color-neon-shadow);
        }

        section.proyectos li:hover {
            box-shadow: 0 0 25px var(--color-neon);
            transform: translateY(-5px);
        }

        section.proyectos a {
            display: block;
            color: var(--color-text-primary);
            text-decoration: none;
            font-size: 1.1em;
            font-weight: bold;
            transition: color 0.3s;
        }
        
        section.proyectos a:hover {
            color: var(--color-neon);
            text-shadow: 0 0 5px var(--color-neon-shadow);
        }

        footer {
            text-align: center;
            padding: 25px;
            background-color: rgba(0, 0, 0, 0.8);
            border-top: 2px solid var(--color-neon);
            font-size: 1em;
            z-index: 10;
        }
        
        /* Media Queries para Responsividad */
        @media (max-width: 768px) {
            header {
                flex-direction: column;
                padding: 15px 20px;
            }
            nav {
                margin-top: 15px;
            }
            nav a {
                margin: 0 10px;
            }
            h1 {
                font-size: 3em;
            }
            .hero-section {
                padding: 50px 0;
            }
        }
    </style>
</head>
<body>
    
    <div class="background-3d-effect"></div>

    <header>
        <div class="logo neon-effect">TVS</div>
        <nav>
            <a href="#inicio" class="active">Inicio</a>
            <a href="#proyectos">Proyectos</a>
            <a href="#contacto">Contacto</a>
        </nav>
    </header>

    <main>
        <section id="inicio" class="hero-section">
            <h1 class="neon-title-animated">
                <span class="red-neon-effect">C</span><span class="animated-text">reaciones</span> 
                <span class="red-neon-effect">D</span><span class="animated-text">igitales</span>
            </h1>
            <p>Proyectos Web con diseño y funcionalidad de vanguardia.</p>
            <a href="#proyectos" class="call-to-action">VER PROYECTOS</a>
        </section>

        <section id="proyectos" class="proyectos">
            <h2 class="neon-effect">Proyectos Web</h2>
            <ul>
                <li><a href="https://sites.google.com/view/farmabalear/inicio" class="neon-link" target="_blank">FARMABALEAR</a></li>
                <li><a href="https://sites.google.com/view/schnitzelhaus-eltoro/inicio" class="neon-link" target="_blank">SCHNITZELHAUS</a></li>
                <li><a href="https://sites.google.com/view/mujerpractica/inicio" class="neon-link" target="_blank">MUJER PRACTICA</a></li>
                <li><a href="https://sites.google.com/view/barchiky/inicio" class="neon-link" target="_blank">BAR CHIKY</a></li>
                <li><a href="https://sedeelectronics.es/" class="neon-link" target="_blank">SEDE ELECTRONICS</a></li>
                <li><a href="https://sites.google.com/view/bar-tapas-dali/inicio" class="neon-link" target="_blank">BAR TAPAS DALI</a></li>
                <li><a href="https://sites.google.com/view/doner-kebab-pizza/inicio" class="neon-link" target="_blank">DONER KEBAB PIZZA</a></li>
                <li><a href="https://gestionautoespana.neocities.org/" class="neon-link" target="_blank">GESTION AUTO ESPAÑA</a></li>
            </ul>
        </section>

        <section id="contacto" style="margin-top: 80px; text-align: center;">
            <h2 class="neon-effect" style="font-size: 2em; margin-bottom: 20px;">Contacto</h2>
			<p style="font-size: 1.2em;">Email: 
                <a href="mailto:tvstvs1@gmail.com" class="neon-link red-neon-effect">TVS</a>
            </p>
            <p>&copy; 2025 TVS</p>
        </section>
    </main>

    <footer>
        <p class="neon-effect">&copy; 2025 TVS – Creaciones Digitales</p>
    </footer>
</body>
</html>

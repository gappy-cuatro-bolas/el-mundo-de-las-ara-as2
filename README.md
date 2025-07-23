<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>🕷️ El Mundo de las Arañas | Exploración Arácnida</title> 
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&family=Roboto+Condensed:wght@400;700&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <style>
    :root {
      --primary: #FF4D6D;
      --primary-dark: #D90429;
      --secondary: #6A4C93;
      --dark: #0F0F0F;
      --darker: #080808;
      --light: #F8F9FA;
      --gray: #495057;
      --success: #52B788;
      --warning: #F4A261;
      --danger: #E63946;
      --comment-bg: rgba(30, 30, 30, 0.8);
      --bg-gradient: linear-gradient(135deg, var(--darker), var(--dark));
      --header-bg: linear-gradient(135deg, rgba(15, 15, 15, 0.9), rgba(30, 30, 30, 0.9));
      --card-bg: linear-gradient(145deg, rgba(30, 30, 30, 0.8), rgba(20, 20, 20, 0.9));
      --text-color: #F8F9FA;
      --input-bg: rgba(255, 255, 255, 0.1);
    }

    /* Tema claro */
    body.theme-light {
      --primary: #D90429;
      --primary-dark: #A5011B;
      --secondary: #5E35B1;
      --dark: #F8F9FA;
      --darker: #E9ECEF;
      --light: #212529;
      --gray: #6C757D;
      --success: #2E7D32;
      --warning: #F77F00;
      --danger: #C1121F;
      --comment-bg: rgba(255, 255, 255, 0.9);
      --bg-gradient: linear-gradient(135deg, #E9ECEF, #F8F9FA);
      --header-bg: linear-gradient(135deg, rgba(248, 249, 250, 0.9), rgba(233, 236, 239, 0.9));
      --card-bg: linear-gradient(145deg, rgba(255, 255, 255, 0.9), rgba(240, 240, 240, 0.95));
      --text-color: #212529;
      --input-bg: rgba(33, 37, 41, 0.1);
    }

    /* Tema verde oscuro */
    body.theme-dark-green {
      --primary: #52B788;
      --primary-dark: #2D6A4F;
      --secondary: #40916C;
      --dark: #081C15;
      --darker: #05120D;
      --light: #D8F3DC;
      --success: #52B788;
      --warning: #F4A261;
      --danger: #E76F51;
      --comment-bg: rgba(8, 28, 21, 0.8);
      --bg-gradient: linear-gradient(135deg, var(--darker), var(--dark));
      --header-bg: linear-gradient(135deg, rgba(8, 28, 21, 0.9), rgba(13, 43, 32, 0.9));
      --card-bg: linear-gradient(145deg, rgba(13, 43, 32, 0.8), rgba(8, 28, 21, 0.9));
      --text-color: #D8F3DC;
      --input-bg: rgba(216, 243, 220, 0.1);
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      margin: 0;
      background: var(--bg-gradient);
      color: var(--text-color);
      font-family: 'Poppins', sans-serif;
      min-height: 100vh;
      overflow-x: hidden;
      transition: background 0.5s ease, color 0.3s ease;
    }

    /* Selector de temas */
    .theme-selector {
      position: fixed;
      top: 20px;
      right: 20px;
      z-index: 1000;
      display: flex;
      gap: 10px;
      background: rgba(15, 15, 15, 0.7);
      backdrop-filter: blur(10px);
      padding: 10px;
      border-radius: 50px;
      box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
      border: 1px solid rgba(255, 255, 255, 0.1);
    }

    .theme-light .theme-selector,
    .theme-dark-green .theme-selector {
      background: rgba(0, 0, 0, 0.5);
    }

    .theme-btn {
      width: 30px;
      height: 30px;
      border-radius: 50%;
      border: none;
      cursor: pointer;
      transition: transform 0.3s ease, box-shadow 0.3s ease;
      display: flex;
      align-items: center;
      justify-content: center;
      color: white;
    }

    .theme-btn:hover {
      transform: scale(1.1);
      box-shadow: 0 0 10px rgba(255, 255, 255, 0.5);
    }

    .theme-btn i {
      font-size: 14px;
    }

    .theme-btn.active {
      transform: scale(1.1);
      box-shadow: 0 0 0 2px white, 0 0 10px rgba(255, 255, 255, 0.5);
    }

    #theme-dark {
      background: linear-gradient(135deg, #0F0F0F, #080808);
    }

    #theme-light {
      background: linear-gradient(135deg, #F8F9FA, #E9ECEF);
      color: #212529;
    }

    #theme-dark-green {
      background: linear-gradient(135deg, #081C15, #05120D);
    }

    /* Efecto de partículas */
    .particles {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: -1;
      pointer-events: none;
    }

    .particle {
      position: absolute;
      background: rgba(255, 77, 109, 0.5);
      border-radius: 50%;
      pointer-events: none;
    }

    /* Header con efecto de neón */
    header {
      background: var(--header-bg);
      padding: 5rem 1rem 3rem;
      text-align: center;
      position: relative;
      overflow: hidden;
      backdrop-filter: blur(5px);
      border-bottom: 1px solid rgba(255, 77, 109, 0.3);
    }

    header::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 5px;
      background: linear-gradient(90deg, transparent, var(--primary), transparent);
      animation: headerGlow 3s infinite;
    }

    @keyframes headerGlow {
      0%, 100% { opacity: 0.3; }
      50% { opacity: 1; }
    }

    header h1 {
      font-size: 3.5rem;
      font-family: 'Roboto Condensed', sans-serif;
      color: var(--primary);
      margin: 0;
      text-shadow: 0 0 10px var(--primary), 0 0 20px rgba(255, 77, 109, 0.5);
      letter-spacing: 2px;
      animation: textGlow 2s ease-in-out infinite alternate;
    }

    @keyframes textGlow {
      from { text-shadow: 0 0 10px var(--primary), 0 0 20px rgba(255, 77, 109, 0.5); }
      to { text-shadow: 0 0 15px var(--primary), 0 0 30px rgba(255, 77, 109, 0.7), 0 0 40px rgba(255, 77, 109, 0.3); }
    }

    header p {
      font-size: 1.4rem;
      color: var(--text-color);
      margin-top: 1rem;
      max-width: 700px;
      margin-left: auto;
      margin-right: auto;
      opacity: 0.9;
    }

    /* Galería de arañas */
    .gallery-section {
      max-width: 1300px;
      margin: 3rem auto;
      padding: 0 2rem;
    }

    .gallery-title {
      color: var(--primary);
      font-size: 2rem;
      margin-bottom: 1.5rem;
      text-align: center;
      position: relative;
      display: inline-block;
      left: 50%;
      transform: translateX(-50%);
    }

    .gallery-title::after {
      content: '';
      position: absolute;
      bottom: -10px;
      left: 50%;
      transform: translateX(-50%);
      width: 80px;
      height: 3px;
      background: var(--primary);
      border-radius: 3px;
    }

    .spider-gallery {
      display: flex;
      overflow-x: auto;
      gap: 1.5rem;
      padding: 1.5rem 0.5rem;
      scroll-snap-type: x mandatory;
      scrollbar-width: thin;
      scrollbar-color: var(--primary) rgba(255, 255, 255, 0.1);
    }

    .spider-gallery::-webkit-scrollbar {
      height: 8px;
    }

    .spider-gallery::-webkit-scrollbar-track {
      background: rgba(255, 255, 255, 0.1);
      border-radius: 10px;
    }

    .spider-gallery::-webkit-scrollbar-thumb {
      background-color: var(--primary);
      border-radius: 10px;
    }

    .gallery-item {
      min-width: 280px;
      max-width: 280px;
      scroll-snap-align: start;
      background: var(--card-bg);
      border-radius: 15px;
      overflow: hidden;
      box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
      transition: all 0.3s ease;
      border: 1px solid rgba(255, 255, 255, 0.05);
    }

    .gallery-item:hover {
      transform: translateY(-5px);
      box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
    }

    .gallery-img {
      width: 100%;
      height: 180px;
      object-fit: cover;
      border-bottom: 1px solid rgba(255, 255, 255, 0.1);
    }

    .gallery-info {
      padding: 1.2rem;
    }

    .gallery-info h3 {
      color: var(--primary);
      font-size: 1.2rem;
      margin-bottom: 0.5rem;
    }

    .gallery-info p {
      font-size: 0.85rem;
      color: var(--text-color);
      opacity: 0.9;
      line-height: 1.5;
    }

    .gallery-nav {
      display: flex;
      justify-content: center;
      gap: 1rem;
      margin-top: 1rem;
    }

    .gallery-nav-btn {
      width: 40px;
      height: 40px;
      border-radius: 50%;
      background: var(--primary);
      color: white;
      border: none;
      display: flex;
      align-items: center;
      justify-content: center;
      cursor: pointer;
      transition: all 0.3s ease;
    }

    .gallery-nav-btn:hover {
      transform: scale(1.1);
      box-shadow: 0 0 15px var(--primary);
    }

    .gallery-nav-btn:disabled {
      opacity: 0.5;
      cursor: not-allowed;
      transform: none;
      box-shadow: none;
    }

    /* Filtros con efecto de vidrio */
    #filtros {
      max-width: 800px;
      margin: 3rem auto;
      display: flex;
      flex-wrap: wrap;
      gap: 1.5rem;
      justify-content: center;
      padding: 1.5rem;
      background: rgba(15, 15, 15, 0.5);
      border-radius: 20px;
      backdrop-filter: blur(10px);
      border: 1px solid rgba(255, 255, 255, 0.1);
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
      transition: all 0.3s ease;
    }

    #filtros:hover {
      box-shadow: 0 15px 40px rgba(0, 0, 0, 0.4);
      border-color: rgba(255, 77, 109, 0.3);
    }

    #filtros input,
    #filtros select {
      padding: 1rem 1.5rem;
      border-radius: 50px;
      border: none;
      background: var(--input-bg);
      color: var(--text-color);
      font-size: 1rem;
      flex: 1 1 250px;
      outline: none;
      transition: all 0.3s ease;
      box-shadow: inset 0 2px 5px rgba(0, 0, 0, 0.2);
    }

    #filtros input::placeholder {
      color: rgba(255, 255, 255, 0.6);
    }

    #filtros input:focus,
    #filtros select:focus {
      background: rgba(255, 255, 255, 0.15);
      box-shadow: 0 0 0 2px var(--primary), inset 0 2px 5px rgba(0, 0, 0, 0.2);
    }

    /* Contenedor de tarjetas */
    #arañas-db {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 2.5rem;
      max-width: 1300px;
      margin: 3rem auto;
      padding: 0 2rem;
    }

    /* Tarjetas con efecto 3D */
    .tarjeta {
      background: var(--card-bg);
      border-radius: 20px;
      overflow: hidden;
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
      display: flex;
      flex-direction: column;
      transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
      position: relative;
      border: 1px solid rgba(255, 255, 255, 0.05);
      transform-style: preserve-3d;
      perspective: 1000px;
    }

    .tarjeta::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: linear-gradient(45deg, transparent, rgba(255, 77, 109, 0.1), transparent);
      opacity: 0;
      transition: opacity 0.3s ease;
    }

    .tarjeta:hover {
      transform: translateY(-10px) scale(1.02) rotateX(2deg) rotateY(2deg);
      box-shadow: 0 15px 40px rgba(255, 77, 109, 0.3), 0 5px 15px rgba(0, 0, 0, 0.5);
    }

    .tarjeta:hover::before {
      opacity: 1;
    }

    .tarjeta img {
      width: 100%;
      height: 220px;
      object-fit: cover;
      transition: transform 0.5s ease;
      border-bottom: 1px solid rgba(255, 255, 255, 0.1);
    }

    .tarjeta:hover img {
      transform: scale(1.05);
    }

    .tarjeta-content {
      padding: 1.5rem;
      flex-grow: 1;
      display: flex;
      flex-direction: column;
    }

    .tarjeta h3 {
      color: var(--primary);
      margin: 0.5rem 0;
      font-size: 1.5rem;
      font-weight: 700;
      position: relative;
      display: inline-block;
    }

    .tarjeta h3::after {
      content: '';
      position: absolute;
      bottom: -5px;
      left: 0;
      width: 50px;
      height: 2px;
      background: var(--primary);
      transition: width 0.3s ease;
    }

    .tarjeta:hover h3::after {
      width: 100px;
    }

    .tarjeta h4 {
      font-style: italic;
      color: var(--secondary);
      margin-bottom: 1rem;
      font-weight: 400;
      font-size: 0.95rem;
    }

    .tarjeta p {
      font-size: 0.95rem;
      line-height: 1.6;
      margin-bottom: 1rem;
      color: var(--text-color);
      opacity: 0.9;
    }

    .tarjeta .familia {
      display: inline-block;
      background: rgba(106, 76, 147, 0.2);
      color: var(--secondary);
      padding: 0.3rem 0.8rem;
      border-radius: 50px;
      font-size: 0.8rem;
      margin-top: auto;
      align-self: flex-start;
      border: 1px solid rgba(106, 76, 147, 0.3);
    }

    .btn-ver {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      margin-top: 1.5rem;
      padding: 0.8rem 1.5rem;
      background: linear-gradient(135deg, var(--primary), var(--primary-dark));
      color: white;
      border-radius: 50px;
      font-weight: 600;
      text-decoration: none;
      transition: all 0.3s ease;
      box-shadow: 0 4px 15px rgba(255, 77, 109, 0.4);
      position: relative;
      overflow: hidden;
      border: none;
      cursor: pointer;
    }

    .btn-ver::before {
      content: '';
      position: absolute;
      top: 0;
      left: -100%;
      width: 100%;
      height: 100%;
      background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
      transition: 0.5s;
    }

    .btn-ver:hover {
      transform: translateY(-3px);
      box-shadow: 0 7px 20px rgba(255, 77, 109, 0.6);
    }

    .btn-ver:hover::before {
      left: 100%;
    }

    .btn-ver i {
      margin-left: 8px;
      transition: transform 0.3s ease;
    }

    .btn-ver:hover i {
      transform: translateX(3px);
    }

    /* Sección de comentarios */
    .comentarios-section {
      max-width: 800px;
      margin: 4rem auto;
      padding: 0 2rem;
    }

    .comentarios-container {
      background: var(--comment-bg);
      border-radius: 15px;
      padding: 2rem;
      backdrop-filter: blur(10px);
      border: 1px solid rgba(255, 77, 109, 0.2);
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
    }

    .comentarios-title {
      color: var(--primary);
      font-size: 1.8rem;
      margin-bottom: 1.5rem;
      text-align: center;
      position: relative;
    }

    .comentarios-title::after {
      content: '';
      position: absolute;
      bottom: -10px;
      left: 50%;
      transform: translateX(-50%);
      width: 80px;
      height: 3px;
      background: var(--primary);
      border-radius: 3px;
    }

    .comentario-form {
      margin-bottom: 2rem;
    }

    .form-group {
      margin-bottom: 1.5rem;
    }

    .form-group label {
      display: block;
      margin-bottom: 0.5rem;
      color: var(--text-color);
      font-weight: 500;
    }

    .form-control {
      width: 100%;
      padding: 0.8rem 1rem;
      border-radius: 8px;
      border: 1px solid rgba(255, 255, 255, 0.1);
      background: rgba(15, 15, 15, 0.7);
      color: var(--text-color);
      font-family: 'Poppins', sans-serif;
      transition: all 0.3s ease;
    }

    .form-control:focus {
      outline: none;
      border-color: var(--primary);
      box-shadow: 0 0 0 2px rgba(255, 77, 109, 0.3);
    }

    textarea.form-control {
      min-height: 120px;
      resize: vertical;
    }

    .btn-enviar {
      background: linear-gradient(135deg, var(--primary), var(--primary-dark));
      color: white;
      border: none;
      padding: 0.8rem 1.8rem;
      border-radius: 50px;
      font-weight: 600;
      cursor: pointer;
      transition: all 0.3s ease;
      box-shadow: 0 4px 15px rgba(255, 77, 109, 0.4);
      display: inline-flex;
      align-items: center;
      justify-content: center;
    }

    .btn-enviar:hover {
      transform: translateY(-2px);
      box-shadow: 0 7px 20px rgba(255, 77, 109, 0.6);
    }

    .btn-enviar i {
      margin-left: 8px;
    }

    .lista-comentarios {
      margin-top: 2rem;
    }

    .comentario {
      background: rgba(20, 20, 20, 0.6);
      border-radius: 10px;
      padding: 1.5rem;
      margin-bottom: 1.5rem;
      border-left: 3px solid var(--primary);
      transition: all 0.3s ease;
    }

    .comentario:hover {
      transform: translateX(5px);
      box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
    }

    .comentario-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 0.8rem;
    }

    .comentario-autor {
      font-weight: 600;
      color: var(--primary);
    }

    .comentario-fecha {
      font-size: 0.8rem;
      color: rgba(255, 255, 255, 0.6);
    }

    .comentario-texto {
      color: var(--text-color);
      opacity: 0.9;
      line-height: 1.6;
    }

    /* Footer con efecto de onda */
    footer {
      background: linear-gradient(to bottom, rgba(15, 15, 15, 0.9), rgba(8, 8, 8, 0.95));
      color: var(--light);
      padding: 4rem 1rem 2rem;
      text-align: center;
      position: relative;
      margin-top: 5rem;
    }

    footer::before {
      content: '';
      position: absolute;
      top: -50px;
      left: 0;
      width: 100%;
      height: 50px;
      background: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 1200 120' preserveAspectRatio='none'%3E%3Cpath d='M0,0V46.29c47.79,22.2,103.59,32.17,158,28,70.36-5.37,136.33-33.31,206.8-37.5C438.64,32.43,512.34,53.67,583,72.05c69.27,18,138.3,24.88,209.4,13.08,36.15-6,69.85-17.84,104.45-29.34C989.49,25,1113-14.29,1200,52.47V0Z' opacity='.25' fill='%23ff4d6d'/%3E%3Cpath d='M0,0V15.81C13,36.92,27.64,56.86,47.69,72.05,99.41,111.27,165,111,224.58,91.58c31.15-10.15,60.09-26.07,89.67-39.8,40.92-19,84.73-46,130.83-49.67,36.26-2.85,70.9,9.42,98.6,31.56,31.77,25.39,62.32,62,103.63,73,40.44,10.79,81.35-6.69,119.13-24.28s75.16-39,116.92-43.05c59.73-5.85,113.28,22.88,168.9,38.84,30.2,8.66,59,6.17,87.09-7.5,22.43-10.89,48-26.93,60.65-49.24V0Z' opacity='.5' fill='%23ff4d6d'/%3E%3Cpath d='M0,0V5.63C149.93,59,314.09,71.32,475.83,42.57c43-7.64,84.23-20.12,127.61-26.46,59-8.63,112.48,12.24,165.56,35.4C827.93,77.22,886,95.24,951.2,90c86.53-7,172.46-45.71,233.88-58.29,119.39-18.62,182.79-49.13,248.8-84.81C1206.43,29.34,1200,0,1200,0Z' fill='%23ff4d6d'/%3E%3C/svg%3E");
      background-size: cover;
      background-repeat: no-repeat;
    }

    footer h2 {
      color: var(--primary);
      margin-bottom: 1.5rem;
      font-size: 2rem;
      position: relative;
      display: inline-block;
    }

    footer h2::after {
      content: '';
      position: absolute;
      bottom: -10px;
      left: 50%;
      transform: translateX(-50%);
      width: 80px;
      height: 3px;
      background: var(--primary);
      border-radius: 3px;
    }

    footer p {
      max-width: 600px;
      margin: 0 auto 2rem;
      opacity: 0.8;
      line-height: 1.6;
    }

    .social-icons {
      display: flex;
      justify-content: center;
      gap: 1.5rem;
      margin-bottom: 2rem;
    }

    .social-icons a {
      width: 50px;
      height: 50px;
      display: flex;
      align-items: center;
      justify-content: center;
      background: rgba(255, 255, 255, 0.1);
      color: var(--light);
      border-radius: 50%;
      font-size: 1.5rem;
      transition: all 0.3s ease;
      position: relative;
      overflow: hidden;
      border: 1px solid rgba(255, 255, 255, 0.1);
    }

    .social-icons a::before {
      content: '';
      position: absolute;
      top: 0;
      left: -100%;
      width: 100%;
      height: 100%;
      background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
      transition: 0.5s;
    }

    .social-icons a:hover {
      background: var(--primary);
      transform: translateY(-5px) rotate(5deg);
      box-shadow: 0 5px 15px rgba(255, 77, 109, 0.5);
    }

    .social-icons a:hover::before {
      left: 100%;
    }

    .footer-bottom {
      margin-top: 2rem;
      font-size: 0.9rem;
      color: rgba(255, 255, 255, 0.6);
      padding-top: 1.5rem;
      border-top: 1px solid rgba(255, 255, 255, 0.1);
    }

    /* Efecto de carga */
    .loading {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100px;
    }

    .spinner {
      width: 50px;
      height: 50px;
      border: 5px solid rgba(255, 77, 109, 0.3);
      border-radius: 50%;
      border-top-color: var(--primary);
      animation: spin 1s ease-in-out infinite;
    }

    @keyframes spin {
      to { transform: rotate(360deg); }
    }

    /* Mensaje de no resultados */
    .no-results {
      grid-column: 1 / -1;
      text-align: center;
      padding: 3rem;
      background: rgba(255, 77, 109, 0.1);
      border-radius: 20px;
      border: 1px dashed var(--primary);
    }

    .no-results i {
      font-size: 3rem;
      color: var(--primary);
      margin-bottom: 1rem;
    }

    .no-results h3 {
      color: var(--primary);
      margin-bottom: 0.5rem;
    }

    /* Efecto de scroll revelado */
    .reveal {
      opacity: 0;
      transform: translateY(30px);
      transition: all 0.6s ease;
    }

    .reveal.active {
      opacity: 1;
      transform: translateY(0);
    }

    /* Responsive design */
    @media (max-width: 768px) {
      header h1 {
        font-size: 2.5rem;
      }
      
      header p {
        font-size: 1.1rem;
      }
      
      #arañas-db {
        grid-template-columns: 1fr;
        padding: 0 1rem;
      }
      
      .tarjeta {
        max-width: 400px;
        margin: 0 auto;
      }

      .comentarios-section {
        padding: 0 1rem;
      }

      .comentarios-container {
        padding: 1.5rem;
      }

      .theme-selector {
        top: 10px;
        right: 10px;
      }
    }

    @media (max-width: 480px) {
      header {
        padding: 3rem 1rem 2rem;
      }
      
      header h1 {
        font-size: 2rem;
      }
      
      #filtros {
        flex-direction: column;
        gap: 1rem;
      }
      
      #filtros input,
      #filtros select {
        width: 100%;
      }

      .comentario-header {
        flex-direction: column;
        align-items: flex-start;
        gap: 0.5rem;
      }

      .comentario-fecha {
        margin-left: 0;
      }

      .gallery-item {
        min-width: 250px;
        max-width: 250px;
      }
    }
  </style>
</head>
<body class="">
  <!-- Selector de temas -->
  <div class="theme-selector">
    <button id="theme-dark" class="theme-btn active" title="Modo oscuro"><i class="fas fa-moon"></i></button>
    <button id="theme-light" class="theme-btn" title="Modo claro"><i class="fas fa-sun"></i></button>
    <button id="theme-dark-green" class="theme-btn" title="Modo verde oscuro"><i class="fas fa-leaf"></i></button>
  </div>

  <!-- Efecto de partículas -->
  <div class="particles" id="particles"></div>

  <header>
    <h1>🕷️ El Mundo de las Arañas</h1>
    <p>Explora el fascinante universo de los arácnidos. Descubre especies increíbles, sus características y curiosidades.</p>
  </header>

  <!-- Galería de arañas -->
  <section class="gallery-section reveal">
    <h2 class="gallery-title">Galería de Arañas</h2>
    <div class="spider-gallery" id="spider-gallery">
      <!-- Las imágenes se cargarán dinámicamente -->
    </div>
    <div class="gallery-nav">
      <button class="gallery-nav-btn" id="gallery-prev" aria-label="Anterior"><i class="fas fa-chevron-left"></i></button>
      <button class="gallery-nav-btn" id="gallery-next" aria-label="Siguiente"><i class="fas fa-chevron-right"></i></button>
    </div>
  </section>

  <!-- Filtros de búsqueda -->
  <div id="filtros">
    <input type="text" id="buscar" placeholder="Buscar por nombre o científico..." />
    <select id="familia">
      <option value="">Todas las familias</option>
    </select>
  </div>

  <!-- Base de datos de arañas -->
  <div id="arañas-db"></div>

  <!-- Sección de Comentarios -->
  <section class="comentarios-section reveal">
    <div class="comentarios-container">
      <h2 class="comentarios-title">Comparte tu Experiencia</h2>
      
      <form class="comentario-form" id="form-comentario">
        <div class="form-group">
          <label for="nombre">Nombre</label>
          <input type="text" id="nombre" class="form-control" required>
        </div>
        
        <div class="form-group">
          <label for="email">Email (no se mostrará)</label>
          <input type="email" id="email" class="form-control" required>
        </div>
        
        <div class="form-group">
          <label for="comentario">Tu comentario</label>
          <textarea id="comentario" class="form-control" required></textarea>
        </div>
        
        <button type="submit" class="btn-enviar">
          Enviar Comentario <i class="fas fa-paper-plane"></i>
        </button>
      </form>
      
      <div class="lista-comentarios" id="lista-comentarios">
        <!-- Los comentarios se cargarán aquí dinámicamente -->
        <div class="loading"><div class="spinner"></div></div>
      </div>
    </div>
  </section>

  <footer>
    <h2>Conéctate con nosotros</h2>
    <p>Síguenos para más contenido fascinante sobre el mundo arácnido. Comparte tus propias observaciones y descubrimientos.</p>
    <div class="social-icons">
      <a href="https://facebook.com" target="_blank" aria-label="Facebook"><i class="fab fa-facebook-f"></i></a>
      <a href="https://twitter.com" target="_blank" aria-label="Twitter"><i class="fab fa-twitter"></i></a>
      <a href="https://instagram.com" target="_blank" aria-label="Instagram"><i class="fab fa-instagram"></i></a>
      <a href="https://youtube.com" target="_blank" aria-label="YouTube"><i class="fab fa-youtube"></i></a>
      <a href="mailto:info@aracnopedia.org" aria-label="Correo"><i class="fas fa-envelope"></i></a>
    </div>
    <div class="footer-bottom">
      &copy; 2025 El Mundo de las Arañas. Todos los derechos reservados. | Diseñado con pasión por los arácnidos
    </div>
  </footer>

  <script>
    // Datos de las arañas con los enlaces originales
    const arañas = [
      { 
        nombre: 'Viuda negra', 
        nombreCientifico: 'Latrodectus mactans', 
        familia: 'Theridiidae', 
        descripcion: 'Famosa por su veneno neurotóxico. Las hembras son reconocibles por su marca de reloj de arena rojo en el abdomen. Aunque su veneno es potente, rara vez atacan a humanos.', 
        imagen: 'https://cdnwine.diario1.com/wp-content/uploads/2023/08/Viuda-Negra.jpg', 
        enlace: 'https://gappy-cuatro-bolas.github.io/ara-as/',
        peligrosidad: 'Alta'
      },
      { 
        nombre: 'Araña de rincón', 
        nombreCientifico: 'Loxosceles laeta', 
        familia: 'Loxosceles', 
        descripcion: 'Pequeña y nocturna, su mordedura puede causar loxoscelismo, una condición que en algunos casos produce necrosis en la piel. Prefiere lugares oscuros y secos.', 
        imagen: 'https://www.cuidomidespensa.com/hubfs/Imported_Blog_Media/loxosceles-g56d5a9b2f_1920-1.jpg', 
        enlace: 'https://gappy-cuatro-bolas.github.io/ara-as-que-ara-an/',
        peligrosidad: 'Alta'
      },
      { 
        nombre: 'Tarántula Goliat', 
        nombreCientifico: 'Theraphosa blondi', 
        familia: 'Theraphosidae', 
        descripcion: 'La araña más grande del mundo por masa. Puede alcanzar 30 cm de envergadura. A pesar de su aspecto intimidante, su veneno no es peligroso para humanos.', 
        imagen: 'https://www.reptilmadrid.com/wp-content/uploads/2022/09/como-cuidar-una-tarantula.jpg', 
        enlace: 'https://gappy-cuatro-bolas.github.io/el-mundo-de-las-ara-as1/',
        peligrosidad: 'Baja'
      },
      { 
        nombre: 'Araña saltarina', 
        nombreCientifico: 'Phidippus audax', 
        familia: 'Salticidae', 
        descripcion: 'Conocida por sus impresionantes saltos (hasta 50 veces su longitud corporal) y su excelente visión. Son curiosas y a veces siguen el movimiento de los humanos.', 
        imagen: 'https://upload.wikimedia.org/wikipedia/commons/thumb/c/cb/Flickr_-_Lukjonis_-_Jumping_spider_-_Sitticus_floricola_%28set_of_pictures%29.jpg/960px-Flickr_-_Lukjonis_-_Jumping_spider_-_Sitticus_floricola_%28set_of_pictures%29.jpg', 
        enlace: 'https://gappy-cuatro-bolas.github.io/el-mundo-de-las-ara-as/',
        peligrosidad: 'Nula'
      },
      { 
        nombre: 'Araña lobo', 
        nombreCientifico: 'Lycosidae', 
        familia: 'Lycosidae', 
        descripcion: 'Cazadoras rápidas y nocturnas que no construyen telarañas. Las hembras cargan sus sacos de huevos y luego a sus crías en el abdomen.', 
        imagen: 'https://lahuertinadetoni.es/wp-content/uploads/2015/01/233-163-Copiar.jpg', 
        enlace: 'https://gappy-cuatro-bolas.github.io/ara-a-lobo/',
        peligrosidad: 'Baja'
      },
      { 
        nombre: 'Araña cangrejo', 
        nombreCientifico: 'Misumena vatia', 
        familia: 'Thomisidae', 
        descripcion: 'Maestras del camuflaje que pueden cambiar de color para mezclarse con las flores donde acechan a sus presas. Tienen patas delanteras más largas como los cangrejos.', 
        imagen: 'https://inaturalist-open-data.s3.amazonaws.com/photos/38263287/original.jpeg', 
        enlace: 'https://gappy-cuatro-bolas.github.io/ara-a-cangrejo/',
        peligrosidad: 'Nula'
      },
      { 
        nombre: 'Araña bananera', 
        nombreCientifico: 'Phoneutria nigriventer', 
        familia: 'Ctenidae', 
        descripcion: 'Considerada una de las arañas más venenosas del mundo. Es agresiva y su veneno puede ser fatal sin tratamiento. Habita en Sudamérica.', 
        imagen: 'https://cdn.dl.uy//solimg/894x503/8/8790.jpg', 
        enlace: 'https://gappy-cuatro-bolas.github.io/ara-a-bananera/',
        peligrosidad: 'Muy alta'
      },
      { 
        nombre: 'Araña pavo real', 
        nombreCientifico: 'Maratus volans', 
        familia: 'Salticidae', 
        descripcion: 'Pequeñas y coloridas, los machos realizan elaboradas danzas de cortejo mostrando sus brillantes colores para atraer a las hembras.', 
        imagen: 'https://static.nationalgeographic.es/files/styles/image_3200/public/02-peacock-spider-9678_9679_9680.webp?w=1190&h=911.jpg', 
        enlace: 'https://gappy-cuatro-bolas.github.io/ara-a-pavo-real/',
        peligrosidad: 'Nula'
      },
      { 
        nombre: 'Araña de seda dorada', 
        nombreCientifico: 'Trichonephila clavipes', 
        familia: 'Araneidae', 
        descripcion: 'Tejedoras de enormes telarañas con seda que brilla dorado al sol. Sus redes pueden alcanzar más de 1 metro de diámetro.', 
        imagen: 'https://encrypted-tbn2.gstatic.com/images?q=tbn:ANd9GcTqAG3X_zgF_DJ0Yii9QbMtZgHjep_-pJX8py9r7oUuk3vbPrN5vzlGRsLFPcj1aZXKHBjxKgZZPi5VNsLNCASDSA', 
        enlace: 'https://gappy-cuatro-bolas.github.io/ara-a-seda-dorada/',
        peligrosidad: 'Baja'
      },
      { 
        nombre: 'Araña cazadora gigante', 
        nombreCientifico: 'Heteropoda maxima', 
        familia: 'Sparassidae', 
        descripcion: 'La araña con mayor envergadura de patas (hasta 30 cm). Es rápida y ágil, cazando activamente por la noche en las selvas de Laos.', 
        imagen: 'https://cloudfront-us-east-1.images.arcpublishing.com/infobae/HP6S6VSSLRF6TFMGDGM4VNV56I.webp', 
        enlace: 'https://gappy-cuatro-bolas.github.io/ara-a-cazadora-gigante/',
        peligrosidad: 'Baja'
      }
    ];

    // Datos para la galería (con imágenes adicionales)
    const gallerySpiders = [
      {
        nombre: 'Araña de jardín europea',
        nombreCientifico: 'Araneus diadematus',
        descripcion: 'Común en jardines, teje grandes telarañas orbiculares con un distintivo patrón en cruz en su abdomen.',
        imagen: 'https://upload.wikimedia.org/wikipedia/commons/thumb/e/ee/Araneus_diadematus_%28aka%29.jpg/1200px-Araneus_diadematus_%28aka%29.jpg'
      },
      {
        nombre: 'Araña camello',
        nombreCientifico: 'Solifugae',
        descripcion: 'Aunque no es una verdadera araña, es un arácnido veloz que habita en desiertos y puede alcanzar 15 cm.',
        imagen: 'https://www.nationalgeographic.com.es/medio/2022/08/09/araña-camello_8d8d5e9e_1280x720.jpg'
      },
      {
        nombre: 'Araña de espalda roja',
        nombreCientifico: 'Latrodectus hasselti',
        descripcion: 'Pariente australiana de la viuda negra, con una distintiva marca roja en su espalda y veneno neurotóxico.',
        imagen: 'https://www.australiangeographic.com.au/wp-content/uploads/2018/06/redback-spider.jpg'
      },
      {
        nombre: 'Araña de tela en embudo',
        nombreCientifico: 'Atrax robustus',
        descripcion: 'Una de las arañas más peligrosas del mundo, nativa de Australia. Su veneno puede ser fatal para humanos.',
        imagen: 'https://upload.wikimedia.org/wikipedia/commons/thumb/2/2d/Atrax_robustus.jpg/1200px-Atrax_robustus.jpg'
      },
      {
        nombre: 'Araña pescadora',
        nombreCientifico: 'Dolomedes',
        descripcion: 'Puede caminar sobre el agua y bucear para capturar pequeños peces y otros animales acuáticos.',
        imagen: 'https://www.thoughtco.com/thmb/4Z2ZQ9Z9X9Z9X9Z9X9Z9X9Z9X9Z9=/1500x0/filters:no_upscale():max_bytes(150000):strip_icc()/fishing-spider-5c5a9a4b46e0fb0001f5e5a5.jpg'
      },
      {
        nombre: 'Araña de cara de ogro',
        nombreCientifico: 'Deinopidae',
        descripcion: 'Tiene visión nocturna excepcional y construye una red que lanza sobre sus presas como una red de caza.',
        imagen: 'https://www.science.org/do/10.1126/science.aaz9455/abs/spider_1280p_0.jpg'
      },
      {
        nombre: 'Araña de agua',
        nombreCientifico: 'Argyroneta aquatica',
        descripcion: 'La única araña que pasa toda su vida bajo el agua, creando una campana de aire para respirar.',
        imagen: 'https://upload.wikimedia.org/wikipedia/commons/thumb/5/5a/Argyroneta_aquatica.jpg/1200px-Argyroneta_aquatica.jpg'
      }
    ];

    // Elementos del DOM
    const dbContainer = document.getElementById('arañas-db');
    const inputBusqueda = document.getElementById('buscar');
    const selectFamilia = document.getElementById('familia');
    const particlesContainer = document.getElementById('particles');
    const formComentario = document.getElementById('form-comentario');
    const listaComentarios = document.getElementById('lista-comentarios');
    const spiderGallery = document.getElementById('spider-gallery');
    const galleryPrevBtn = document.getElementById('gallery-prev');
    const galleryNextBtn = document.getElementById('gallery-next');
    const themeDarkBtn = document.getElementById('theme-dark');
    const themeLightBtn = document.getElementById('theme-light');
    const themeDarkGreenBtn = document.getElementById('theme-dark-green');

    // Cargar comentarios desde localStorage
    function cargarComentarios() {
      const comentariosGuardados = localStorage.getItem('comentariosAranas');
      if (comentariosGuardados) {
        return JSON.parse(comentariosGuardados);
      }
      return [
        {
          id: 1,
          nombre: "Carlos Araña",
          email: "carlos@example.com",
          comentario: "¡Increíble colección! Siempre me han fascinado las arañas, especialmente las saltarinas. Su capacidad de salto es asombrosa.",
          fecha: new Date().toISOString()
        },
        {
          id: 2,
          nombre: "María López",
          email: "maria@example.com",
          comentario: "Tuve un encuentro con una viuda negra en mi jardín. Gracias a esta página pude identificarla y saber cómo actuar. ¡Muy útil!",
          fecha: new Date(Date.now() - 86400000).toISOString() // Hace 1 día
        },
        {
          id: 3,
          nombre: "Biólogo Andrés",
          email: "andres@example.com",
          comentario: "Como profesional, valoro mucho la precisión de la información presentada. Sería genial agregar más sobre su rol en los ecosistemas.",
          fecha: new Date(Date.now() - 172800000).toISOString() // Hace 2 días
        }
      ];
    }

    // Guardar comentarios en localStorage
    function guardarComentarios(comentarios) {
      localStorage.setItem('comentariosAranas', JSON.stringify(comentarios));
    }

    // Inicializar comentarios
    let comentarios = cargarComentarios();

    // Crear partículas
    function createParticles() {
      const particleCount = Math.floor(window.innerWidth / 10);
      
      for (let i = 0; i < particleCount; i++) {
        const particle = document.createElement('div');
        particle.classList.add('particle');
        
        const size = Math.random() * 2 + 1;
        particle.style.width = `${size}px`;
        particle.style.height = `${size}px`;
        particle.style.left = `${Math.random() * 100}%`;
        particle.style.top = `${Math.random() * 100}%`;
        particle.style.opacity = Math.random() * 0.5 + 0.1;
        
        const duration = Math.random() * 20 + 10;
        const delay = Math.random() * 5;
        particle.style.animation = `float ${duration}s linear ${delay}s infinite`;
        
        const direction = Math.random() > 0.5 ? 'normal' : 'reverse';
        particle.style.animationDirection = direction;
        
        particlesContainer.appendChild(particle);
      }
    }

    // Animación de flotación para partículas
    const style = document.createElement('style');
    style.textContent = `
      @keyframes float {
        0% {
          transform: translate(0, 0);
        }
        25% {
          transform: translate(${Math.random() * 100 - 50}px, ${Math.random() * 100 - 50}px);
        }
        50% {
          transform: translate(${Math.random() * 100 - 50}px, ${Math.random() * 100 - 50}px);
        }
        75% {
          transform: translate(${Math.random() * 100 - 50}px, ${Math.random() * 100 - 50}px);
        }
        100% {
          transform: translate(0, 0);
        }
      }
    `;
    document.head.appendChild(style);

    // Crear lista única de familias para el filtro
    function setupFamiliaFilter() {
      const familiasUnicas = Array.from(new Set(arañas.map(a => a.familia))).sort();
      familiasUnicas.forEach(fam => {
        const option = document.createElement('option');
        option.value = fam;
        option.textContent = fam;
        selectFamilia.appendChild(option);
      });
    }

    // Mostrar galería de arañas
    function mostrarGaleria() {
      spiderGallery.innerHTML = '';
      
      gallerySpiders.forEach((araña, index) => {
        const item = document.createElement('div');
        item.className = 'gallery-item reveal';
        item.style.transitionDelay = `${index * 0.1}s`;
        item.innerHTML = `
          <img src="${araña.imagen}" alt="${araña.nombre}" class="gallery-img" loading="lazy" />
          <div class="gallery-info">
            <h3>${araña.nombre}</h3>
            <p><em>${araña.nombreCientifico}</em></p>
            <p>${araña.descripcion}</p>
          </div>
        `;
        spiderGallery.appendChild(item);
      });
      
      setupGalleryNavigation();
      revealElements();
    }

    // Configurar navegación de la galería
    function setupGalleryNavigation() {
      galleryPrevBtn.addEventListener('click', () => {
        spiderGallery.scrollBy({
          left: -300,
          behavior: 'smooth'
        });
      });
      
      galleryNextBtn.addEventListener('click', () => {
        spiderGallery.scrollBy({
          left: 300,
          behavior: 'smooth'
        });
      });
      
      spiderGallery.addEventListener('scroll', updateGalleryButtons);
      updateGalleryButtons();
    }

    // Actualizar estado de los botones de navegación de la galería
    function updateGalleryButtons() {
      galleryPrevBtn.disabled = spiderGallery.scrollLeft <= 10;
      galleryNextBtn.disabled = spiderGallery.scrollLeft >= spiderGallery.scrollWidth - spiderGallery.clientWidth - 10;
    }

    // Mostrar tarjetas de arañas
    function mostrarArañas(datos) {
      dbContainer.innerHTML = '';
      
      if (datos.length === 0) {
        dbContainer.innerHTML = `
          <div class="no-results reveal">
            <i class="fas fa-spider"></i>
            <h3>No se encontraron arañas</h3>
            <p>Intenta con otros términos de búsqueda o selecciona una familia diferente</p>
          </div>
        `;
        revealElements();
        return;
      }
      
      datos.forEach((araña, index) => {
        const tarjeta = document.createElement('div');
        tarjeta.className = 'tarjeta reveal';
        tarjeta.style.transitionDelay = `${index * 0.1}s`;
        
        let peligroColor = 'var(--success)';
        if (araña.peligrosidad === 'Alta') peligroColor = 'var(--warning)';
        if (araña.peligrosidad === 'Muy alta') peligroColor = 'var(--danger)';
        
        tarjeta.innerHTML = `
          <img src="${araña.imagen}" alt="${araña.nombre}" loading="lazy" />
          <div class="tarjeta-content">
            <h3>${araña.nombre}</h3>
            <h4><em>${araña.nombreCientifico}</em></h4>
            <p>${araña.descripcion}</p>
            <div style="display: flex; justify-content: space-between; align-items: center; margin-top: auto;">
              <span class="familia">${araña.familia}</span>
              <span style="font-size: 0.8rem; background: ${peligroColor}; padding: 0.3rem 0.8rem; border-radius: 50px; color: white;">
                ${araña.peligrosidad}
              </span>
            </div>
            <a class="btn-ver" href="${araña.enlace}" target="_blank" rel="noopener noreferrer">
              Ver más <i class="fas fa-arrow-right"></i>
            </a>
          </div>
        `;
        dbContainer.appendChild(tarjeta);
      });
      
      revealElements();
    }

    // Filtrar arañas según búsqueda
    function filtrarArañas() {
      const texto = inputBusqueda.value.toLowerCase();
      const familia = selectFamilia.value;

      const filtradas = arañas.filter((a) => {
        const coincideTexto =
          a.nombre.toLowerCase().includes(texto) ||
          a.nombreCientifico.toLowerCase().includes(texto);
        const coincideFamilia = familia === '' || a.familia === familia;
        return coincideTexto && coincideFamilia;
      });

      mostrarArañas(filtradas);
    }

    // Formatear fecha para mostrar
    function formatFecha(fechaISO) {
      const opciones = { year: 'numeric', month: 'long', day: 'numeric', hour: '2-digit', minute: '2-digit' };
      return new Date(fechaISO).toLocaleDateString('es-ES', opciones);
    }

    // Mostrar comentarios
    function mostrarComentarios() {
      if (comentarios.length === 0) {
        listaComentarios.innerHTML = `
          <div class="no-results">
            <i class="far fa-comment-dots"></i>
            <h3>No hay comentarios aún</h3>
            <p>Sé el primero en compartir tu experiencia con arañas</p>
          </div>
        `;
        return;
      }
      
      comentarios.sort((a, b) => new Date(b.fecha) - new Date(a.fecha));
      
      listaComentarios.innerHTML = '';
      comentarios.forEach(comentario => {
        const comentarioElement = document.createElement('div');
        comentarioElement.className = 'comentario reveal';
        comentarioElement.innerHTML = `
          <div class="comentario-header">
            <span class="comentario-autor">${comentario.nombre}</span>
            <span class="comentario-fecha">${formatFecha(comentario.fecha)}</span>
          </div>
          <p class="comentario-texto">${comentario.comentario}</p>
        `;
        listaComentarios.appendChild(comentarioElement);
      });
      
      revealElements();
    }

    // Manejar envío de comentarios
    function manejarEnvioComentario(e) {
      e.preventDefault();
      
      const nombre = document.getElementById('nombre').value.trim();
      const email = document.getElementById('email').value.trim();
      const comentarioTexto = document.getElementById('comentario').value.trim();
      
      if (!nombre || !email || !comentarioTexto) {
        alert('Por favor completa todos los campos');
        return;
      }
      
      if (!email.includes('@') || !email.includes('.')) {
        alert('Por favor ingresa un email válido');
        return;
      }
      
      const nuevoComentario = {
        id: Date.now(),
        nombre,
        email,
        comentario: comentarioTexto,
        fecha: new Date().toISOString()
      };
      
      comentarios.unshift(nuevoComentario);
      guardarComentarios(comentarios);
      mostrarComentarios();
      
      formComentario.reset();
      
      const mensajeExito = document.createElement('div');
      mensajeExito.className = 'comentario';
      mensajeExito.style.backgroundColor = 'rgba(82, 183, 136, 0.2)';
      mensajeExito.style.borderLeftColor = 'var(--success)';
      mensajeExito.innerHTML = `
        <p style="color: var(--success); font-weight: 500;">
          <i class="fas fa-check-circle"></i> ¡Gracias por tu comentario!
        </p>
      `;
      listaComentarios.insertBefore(mensajeExito, listaComentarios.firstChild);
      
      setTimeout(() => {
        mensajeExito.style.opacity = '0';
        mensajeExito.style.transform = 'translateY(-10px)';
        setTimeout(() => {
          mensajeExito.remove();
        }, 300);
      }, 3000);
    }

    // Cambiar tema
    function cambiarTema(tema) {
      document.body.classList.remove('theme-light', 'theme-dark-green');
      
      if (tema) {
        document.body.classList.add(`theme-${tema}`);
      }
      
      themeDarkBtn.classList.remove('active');
      themeLightBtn.classList.remove('active');
      themeDarkGreenBtn.classList.remove('active');
      
      if (tema === 'light') {
        themeLightBtn.classList.add('active');
      } else if (tema === 'dark-green') {
        themeDarkGreenBtn.classList.add('active');
      } else {
        themeDarkBtn.classList.add('active');
      }
    }

    // Efecto de scroll revelado
    function revealElements() {
      const reveals = document.querySelectorAll('.reveal');
      
      const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
          if (entry.isIntersecting) {
            entry.target.classList.add('active');
          }
        });
      }, { threshold: 0.1 });
      
      reveals.forEach(reveal => {
        observer.observe(reveal);
      });
    }

    // Event listeners
    inputBusqueda.addEventListener('input', filtrarArañas);
    selectFamilia.addEventListener('change', filtrarArañas);
    formComentario.addEventListener('submit', manejarEnvioComentario);
    themeDarkBtn.addEventListener('click', () => cambiarTema(''));
    themeLightBtn.addEventListener('click', () => cambiarTema('light'));
    themeDarkGreenBtn.addEventListener('click', () => cambiarTema('dark-green'));

    // Inicialización
    window.addEventListener('load', () => {
      createParticles();
      setupFamiliaFilter();
      mostrarGaleria();
      mostrarArañas(arañas);
      mostrarComentarios();
      
      dbContainer.innerHTML = '<div class="loading"><div class="spinner"></div></div>';
      setTimeout(() => {
        mostrarArañas(arañas);
      }, 800);
    });

    // Recrear partículas al redimensionar
    window.addEventListener('resize', () => {
      particlesContainer.innerHTML = '';
      createParticles();
    });
  </script>
</body>
</html>

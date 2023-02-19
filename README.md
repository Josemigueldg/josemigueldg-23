<!DOCTYPE html>
<html>
  <head>
    <title>Mi sitio web</title>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="estilos.css">
    <style>
      body {
        background-image: url("galaxy-background.jpg");
        font-family: 'Lato', sans-serif;
      }
      #investment-container {
        border: 2px solid silver;
        padding: 20px;
        border-radius: 10px;
        background-color: white;
        margin-top: 20px;
      }
      h1, h2, h3, h4, h5, h6 {
        font-family: 'Orbitron', sans-serif;
        text-shadow: 2px 2px #ff00ff;
      }
    </style>
  </head>
  <body>
    <header>
      <h1>Mi sitio web</h1>
      <nav>
        <ul>
          <li><a href="#">Inicio</a></li>
          <li><a href="#">Qué es Farming</a></li>
          <li><a href="#">Cómo invertir</a></li>
          <li><a href="#">Mejores prácticas</a></li>
          <li><a href="#">Contacto</a></li>
        </ul>
      </nav>
    </header>
    <main>
      <section>
        <h2>Bienvenidos</h2>
        <p>¡Gracias por visitar mi sitio web!</p>
      </section>
      <section>
        <h2>Acerca de mi</h2>
        <p>Soy un desarrollador web apasionado por la creación de soluciones tecnológicas que faciliten la vida de las personas. </p>
      </section>
      <section>
        <h2>Inversión</h2>
        <div id="investment-container">
          <p>Ingrese el monto que desea invertir en BNB:</p>
          <input type="number" id="investment-amount">
          <button>Inversión</button>
        </div>
      </section>
    </main>
    <footer>
      <p>&copy; 2023 Mi sitio web. Todos los derechos reservados.</p>
    </footer>
    <script src="script.js"></script>
  </body>
</html>

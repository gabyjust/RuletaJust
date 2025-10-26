# RuletaJust
Juga y gana premios Just
```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial‑scale=1.0" />
  <title>Ruleta de Premios Just</title>
  <style>
    body {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
      background: #f6f9fc;
      font-family: Arial, sans‑serif;
    }
    #wheel {
      width: 300px;
      height: 300px;
      border: 10px solid #fff;
      border-radius: 50%;
      position: relative;
      overflow: hidden;
      box-shadow: 0 0 10px rgba(0,0,0,0.15);
      transition: transform 4s ease‑out;
    }
    .segment {
      width: 50%;
      height: 50%;
      position: absolute;
      transform‑origin: 100% 100%;
      clip‑path: polygon(0 0, 100% 0, 100% 100%);
      background: lightcoral;
      color: #fff;
      display: flex;
      justify‑content: flex‑end;
      align‑items: center;
      padding‑right: 10px;
      box‑sizing: border‑box;
    }
.segment:nth‑child(1) { background: #FFB900; transform: rotate(0deg)   skewY(-30deg); }
    .segment:nth‑child(2) { background: #FF8A00; transform: rotate(60deg)  skewY(-30deg); }
    .segment:nth‑child(3) { background: #FF3E3E; transform: rotate(120deg) skewY(-30deg); }
    .segment:nth‑child(4) { background: #00C2FF; transform: rotate(180deg) skewY(-30deg); }
    .segment:nth‑child(5) { background: #00D68F; transform: rotate(240deg) skewY(-30deg); }
    .segment:nth‑child(6) { background: #A76EFF; transform: rotate(300deg) skewY(-30deg); }
    #spinButton {
      margin-top: 20px;
      padding: 10px 20px;
      font-size: 16px;
      cursor: pointer;
    }
    #form {
      margin-top: 30px;
      text-align: center;
    }
    #form input {
      padding: 8px;
      margin: 5px;
    }
    #contact {
      position: absolute;
      bottom: 10px;
      width: 100%;
      text-align: center;
      font-size: 14px;
      color: #555;
    }
  </style>
</head>
<body>

  <div>
    <div id="wheel">
      <div class="segment">10% Descuento</div>
      <div class="segment">20% Descuento</div>
      <div class="segment">25% Descuento</div>
      <div class="segment">Spa de Manos</div>
      <div class="segment">Spa de Rostro</div>
      <div class="segment">Spa de Pies</div>
<div class="segment">Set de Muestras</div>
      <div class="segment">Set de Muestras</div>
    </div>

    <button id="spinButton">Girar Ruleta</button>

    <div id="form">
      <input type="text" id="name" placeholder="Tu nombre" required><br>
      <input type="text" id="phone" placeholder="Tu teléfono/WhatsApp" required><br>
      <button id="submitData">Enviar Datos</button>
    </div>

    <div id="contact">
      @gabysuescunjust • 2494343125
    </div>
  </div>

  <script>
    const wheel = document.getElementById('wheel');
    const button = document.getElementById('spinButton');
    let spinning = false;

    button.addEventListener('click', () => {
      if (spinning) return;
      spinning = true;
      const randDeg = Math.floor(Math.random() * 360) + 720; // al menos 2 vueltas
      wheel.style.transform = `rotate(${randDeg}deg)`;
      setTimeout(() => {
        spinning = false;
        alert('¡Ganaste! Contactame para reclamar tu premio.');
      }, 4000);
    });

    document.getElementById('submitData').addEventListener('click', () => {
      const name =
document.getElementById('name').value;
      const phone = document.getElementById('phone').value;
      if (!name || !phone) {
        alert('Por favor completá tus datos.');
        return;
      }
console.log(`Datos: Nombre:{name}, Tel: ${phone}`);
      alert('Gracias por registrarte, pronto nos contactamos.');
      // Aquí podés conectar a un backend o Google Sheet para guardar datos.
    });
  </script>
</body>
</html>
```

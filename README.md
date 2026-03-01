<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Suporte pelo WhatsApp</title>

  <style>
    body {
      margin: 0;
      min-height: 100vh;
      font-family: Arial, sans-serif;
      background: linear-gradient(135deg, #0f172a, #020617);
      color: #e5e7eb;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .card {
      background: rgba(15, 23, 42, 0.9);
      border-radius: 20px;
      padding: 40px 30px;
      max-width: 420px;
      width: 100%;
      text-align: center;
      box-shadow: 0 20px 40px rgba(0,0,0,0.4);
      border: 1px solid rgba(255,255,255,0.05);
    }

    .logo {
      width: 90px;
      height: 90px;
      margin: 0 auto 20px;
      border-radius: 50%;
      background: linear-gradient(135deg, #22c55e, #16a34a);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 36px;
      font-weight: bold;
      color: #052e16;
    }

    h1 {
      margin: 0 0 10px;
      font-size: 26px;
    }

    p {
      margin: 0 0 25px;
      color: #9ca3af;
      font-size: 15px;
      line-height: 1.5;
    }

    button {
      width: 100%;
      padding: 16px;
      font-size: 18px;
      font-weight: bold;
      border: none;
      border-radius: 12px;
      cursor: pointer;
      background: linear-gradient(135deg, #22c55e, #16a34a);
      color: #052e16;
      transition: transform 0.15s ease, box-shadow 0.15s ease;
      box-shadow: 0 10px 20px rgba(34, 197, 94, 0.3);
    }

    button:hover {
      transform: translateY(-2px);
      box-shadow: 0 14px 26px rgba(34, 197, 94, 0.45);
    }

    .footer {
      margin-top: 18px;
      font-size: 12px;
      color: #64748b;
    }
  </style>
</head>
<body>

  <div class="card">
    <div class="logo">💬</div>
    <h1>Atendimento via WhatsApp</h1>
    <p>Clique no botão abaixo para falar com nosso suporte agora mesmo.</p>

    <button onclick="abrirWhatsapp()">Falar no WhatsApp</button>

    <div class="footer">
      Atendimento rápido • Direto no WhatsApp
    </div>
  </div>

  <script>
    const numeros = [
      "5511978761833", // SEU WHATSAPP
      "5511992564902"  // WHATSAPP DO SEU AMIGO
    ];

    function abrirWhatsapp() {
      let ultimo = localStorage.getItem("ultimoAtendido");
      let proximo = ultimo === "0" ? 1 : 0;

      localStorage.setItem("ultimoAtendido", proximo);

      let numero = numeros[proximo];

      const msg = encodeURIComponent("Oi! Vim pelo Instagram e gostaria de atendimento.");
      window.location.href = `https://wa.me/${numero}?text=${msg}`;
    }
  </script>

</body>
</html>

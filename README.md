
<html lang="it">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Modulo di ricontatto</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f6f7fb;
      color: #111;
      display: flex;
      align-items: center;
      justify-content: center;
      min-height: 100vh;
      margin: 0;
    }
    .card {
      background: #fff;
      padding: 22px;
      border-radius: 10px;
      box-shadow: 0 6px 18px rgba(25, 30, 50, 0.08);
      width: 380px;
    }
    h1 {
      font-size: 20px;
      margin-bottom: 14px;
      text-align: center;
    }
    label {
      display: block;
      font-size: 14px;
      margin-top: 10px;
    }
    input[type="text"],
    input[type="tel"],
    textarea {
      width: 100%;
      padding: 8px 10px;
      margin-top: 6px;
      border: 1px solid #d7dce9;
      border-radius: 6px;
      font-size: 14px;
    }
    textarea {
      min-height: 100px;
      resize: vertical;
    }
    .row {
      display: flex;
      gap: 8px;
    }
    .row .half {
      flex: 1;
    }
    .btn {
      margin-top: 14px;
      display: block;
      width: 100%;
      padding: 10px;
      background: #2563eb;
      color: #fff;
      border: none;
      border-radius: 6px;
      cursor: pointer;
      font-size: 15px;
    }
    .msg {
      margin-top: 10px;
      font-size: 14px;
      text-align: center;
    }
    .success {
      color: #166534;
    }
    .error {
      color: #b91c1c;
    }
  </style>
</head>
<body>
  <div class="card">
    <h1>Richiedi un ricontatto</h1>

    <!--https://formspree.io/f/xldaekze-->
    <form id="contactForm" action="https://formspree.io/f/xldaekze" method="POST">
      <div class="row">
        <div class="half">
          <label for="nome">Nome</label>
          <input id="nome" name="nome" type="text" placeholder="Mario" required />
        </div>
        <div class="half">
          <label for="cognome">Cognome</label>
          <input id="cognome" name="cognome" type="text" placeholder="Rossi" required />
        </div>
      </div>

      <label for="posizione">Dove ti trovi</label>
      <input id="posizione" name="posizione" type="text" placeholder="Città o zona" required />

      <label for="telefono">Recapito telefonico</label>
      <input id="telefono" name="telefono" type="tel" placeholder="+39 333 1234567" required />

      <label for="messaggio">Descrivi in breve il tuo problema</label>
      <textarea id="messaggio" name="messaggio" placeholder="Scrivi qui..." required></textarea>

      <input type="hidden" name="_subject" value="Richiesta di ricontatto dal sito" />

      <button class="btn" type="submit">Invia richiesta</button>
      <div id="feedback" class="msg" aria-live="polite"></div>
    </form>
  </div>

  <script>
    // Semplice feedback visuale (non obbligatorio)
    const form = document.getElementById('contactForm');
    const feedback = document.getElementById('feedback');

    form.addEventListener('submit', () => {
      feedback.textContent = 'Invio in corso...';
      feedback.className = 'msg';
    });
  </script>
</body>
</html>

<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Eleição Grêmio - Conexão</title>
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; }
    body { background: #121212; color: #fff; display: flex; align-items: center; justify-content: center; min-height: 100vh; padding: 20px; }
    .card { background: #1e1e1e; padding: 30px; border-radius: 12px; width: 100%; max-width: 400px; box-shadow: 0 10px 25px rgba(0,0,0,0.5); border: 1px solid #333; text-align: center; }
    h1 { font-size: 1.5rem; margin-bottom: 20px; color: #00e676; }
    p { font-size: 0.9rem; color: #aaa; margin-bottom: 20px; }
    input { width: 100%; padding: 12px; border-radius: 6px; border: 1px solid #444; background: #2a2a2a; color: #fff; font-size: 1.2rem; text-align: center; font-weight: bold; letter-spacing: 2px; margin-bottom: 20px; text-transform: uppercase; }
    .btn-group { display: flex; flex-direction: column; gap: 12px; }
    button { padding: 14px; border: none; border-radius: 6px; font-weight: bold; font-size: 1rem; cursor: pointer; transition: 0.2s; }
    .btn-urna { background: #1b5e20; color: #fff; }
    .btn-mesario { background: #0d47a1; color: #fff; }
    button:hover { opacity: 0.9; transform: translateY(-1px); }
  </style>
</head>
<body>
  <div class="card">
    <h1>Grêmio Estudantil</h1>
    <p>Digite o Código da Sala/Eleição para conectar os dois aparelhos:</p>
    
    <input type="text" id="roomCode" placeholder="Ex: GREMIO2026" maxlength="15">
    
    <div class="btn-group">
      <button class="btn-urna" onclick="entrar('urna')">📱 Abrir como URNA (Celular 1)</button>
      <button class="btn-mesario" onclick="entrar('mesario')">📋 Abrir como MESÁRIO (Celular 2)</button>
    </div>
  </div>

  <script>
    function entrar(tipo) {
      const room = document.getElementById('roomCode').value.trim().toUpperCase();
      if (!room) {
        alert('Por favor, digite um código para a sala da eleição!');
        return;
      }
      window.location.href = `${tipo}.html?room=${encodeURIComponent(room)}`;
    }
  </script>
</body>
</html>

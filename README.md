<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Login Simples</title>
  <style>
    body {
      background: linear-gradient(135deg, #000, #222);
      font-family: Arial, sans-serif;
      color: white;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }
    .login-box {
      background: #111;
      padding: 30px;
      border-radius: 10px;
      box-shadow: 0 0 15px rgba(255, 0, 0, 0.3);
      width: 300px;
      text-align: center;
    }
    h2 {
      color: #e50914;
      margin-bottom: 20px;
    }
    input {
      width: 100%;
      padding: 10px;
      margin: 8px 0;
      border: none;
      border-radius: 5px;
      background: #222;
      color: white;
    }
    button {
      width: 100%;
      padding: 10px;
      border: none;
      border-radius: 5px;
      background: #e50914;
      color: white;
      font-weight: bold;
      cursor: pointer;
      margin-top: 10px;
    }
    button:hover {
      background: #f40612;
    }
    .erro {
      color: #ff6b6b;
      font-size: 14px;
      margin-top: 10px;
    }
  </style>
</head>
<body>
  <div class="login-box">
    <h2>Login</h2>
    <input type="text" id="email" placeholder="Email">
    <input type="password" id="senha" placeholder="Senha">
    <button onclick="login()">Entrar</button>
    <p id="erro" class="erro"></p>
  </div>

  <script>
    function login() {
      const email = document.getElementById('email').value;
      const senha = document.getElementById('senha').value;
      const erro = document.getElementById('erro');

      if (!email || !senha) {
        erro.textContent = 'Preencha todos os campos.';
        return;
      }

      if (senha === '1234') {
        localStorage.setItem('usuario', email);
        alert('Login bem-sucedido!');
        window.location.href = 'home.html'; // muda para sua página inicial
      } else {
        erro.textContent = 'Senha incorreta (dica: use 1234).';
      }
    }
  </script>
</body>
</html>

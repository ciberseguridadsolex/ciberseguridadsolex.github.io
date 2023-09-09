
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Iniciar Sesión</title>
</head>
<body>
    <h1>Iniciar Sesión</h1>
    <form id="loginForm">
        <label for="email">Correo Electrónico:</label>
        <input type="email" id="email" name="email" required><br><br>
        <label for="password">Contraseña:</label>
        <input type="password" id="password" name="password" required><br><br>
        <button type="submit">Iniciar Sesión</button>
    </form>
    <p id="userEmail"></p>

    <script>
        // JavaScript para manejar el formulario de inicio de sesión y mostrar el correo del usuario
        document.getElementById("loginForm").addEventListener("submit", function (event) {
            event.preventDefault(); // Evita el envío del formulario
            var email = document.getElementById("email").value;

            // Aquí debes verificar las credenciales del usuario, por ejemplo, en una base de datos
            // Si las credenciales son correctas, puedes mostrar el correo del usuario
            // de esta manera o utilizando el método que prefieras.
            document.getElementById("userEmail").textContent = "Correo del usuario: " + email;
        });
    </script>
</body>
</html>

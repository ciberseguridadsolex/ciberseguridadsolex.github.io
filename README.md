<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="refresh" content="5;url=https://solexbiz318.sharepoint.com/:p:/r/sites/Ciberseguridad/_layouts/15/Doc.aspx?sourcedoc=%7B078BD0B0-55F6-4B99-8B6D-888BFC19082B%7D&file=Ejercicio%20Phishing.ppsx&action=edit&mobileredirect=true&DefaultItemOpen=1&login_hint=sergio.sanmartin%40solex.biz&ct=1694219734845&wdOrigin=OFFICECOM-WEB.MAIN.REC&cid=6d23ba0f-554e-4b59-97dc-fdf6d64ef493&wdPreviousSessionSrc=HarmonyWeb&wdPreviousSession=a1e714c2-db3d-4860-9794-09cf1e056b9b">
    <title>Has mordido el anzuelo</title>
    <style>
        body {
            background-color: black;
            color: white;
        }
    </style>
</head>
<body>
    <header>
        <h1>Has mordido el anzuelo</h1>
    </header>

    <main>
        <section>
            <p>Lamentamos informarte que has sido víctima de un intento de phishing. Tu información ha sido comprometida. Por favor, <a href="https://solexbiz318.sharepoint.com/:p:/r/sites/Ciberseguridad/_layouts/15/Doc.aspx?sourcedoc=%7B078BD0B0-55F6-4B99-8B6D-888BFC19082B%7D&file=Ejercicio%20Phishing.ppsx&action=edit&mobileredirect=true&DefaultItemOpen=1&login_hint=sergio.sanmartin%40solex.biz&ct=1694219734845&wdOrigin=OFFICECOM-WEB.MAIN.REC&cid=6d23ba0f-554e-4b59-97dc-fdf6d64ef493&wdPreviousSessionSrc=HarmonyWeb&wdPreviousSession=a1e714c2-db3d-4860-9794-09cf1e056b9b">
              <img src="https://drive.google.com/uc?id=1wchi4XR7w5Tuh2Qx-54_RuSbFhfltr4R" alt="Imagen de phishing" />
            </a> para tomar medidas inmediatas.</p>
        </section>
        <section>
            <p id="visitorNumber">Número de visitante:</p>
            <p id="userEmail">Cuenta de correo:</p>
        </section>
    </main>

    <footer>
        <p>&copy; Ciberseguridad Solex 2023</p>
    </footer>

    <script>
        // JavaScript para obtener y mostrar el número de visitante y la cuenta de correo
        var visitorNumber = localStorage.getItem('visitorNumber');
        var userEmail = localStorage.getItem('userEmail');

        // Incrementa el número de visitante
        if (!visitorNumber) {
            visitorNumber = 1;
        } else {
            visitorNumber = parseInt(visitorNumber) + 1;
        }

        // Obtiene la cuenta de correo (puedes ajustar cómo la obtienes)
        var currentUserEmail = "correo@example.com"; // Reemplaza esto con la lógica real para obtener el correo del usuario

        // Almacena el número de visitante y la cuenta de correo en el almacenamiento local
        localStorage.setItem('visitorNumber', visitorNumber);
        localStorage.setItem('userEmail', currentUserEmail);

        // Muestra el número de visitante y la cuenta de correo en el HTML
        document.getElementById('visitorNumber').textContent += ' ' + visitorNumber;
        document.getElementById('userEmail').textContent += ' ' + currentUserEmail;
    </script>
</body>
</html>

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
            <p>Número de visitante: <span id="visitorNumber"></span></p>
            <p>Dirección IPv4 pública del visitante: <span id="visitorIPv4"></span></p>
            <p>Hora de la visita: <span id="visitTime"></span></p>
        </section>
    </main>

    <footer>
        <p>&copy; Ciberseguridad Solex 2023</p>
    </footer>

    <script>
        // JavaScript para obtener y mostrar el número de visitante, dirección IPv4 pública y hora de la visita
        var visitorNumber = localStorage.getItem('visitorNumber');
        var visitorIPv4 = "";

        // Incrementa el número de visitante
        if (!visitorNumber) {
            visitorNumber = 1;
        } else {
            visitorNumber = parseInt(visitorNumber) + 1;
        }

        // Obtiene la dirección IPv4 pública del visitante utilizando ipify.org
        fetch('https://api.ipify.org?format=json')
            .then(response => response.json())
            .then(data => {
                visitorIPv4 = data.ip;
                // Muestra la dirección IPv4 en el HTML
                document.getElementById('visitorIPv4').textContent = visitorIPv4;
            })
            .catch(error => console.error(error));

        // Obtiene la hora actual
        var visitTime = new Date();
        var visitTimeString = visitTime.toLocaleString();

        // Almacena el número de visitante y la hora de la visita en el almacenamiento local
        localStorage.setItem('visitorNumber', visitorNumber);

        // Muestra el número de visitante y la hora de la visita en el HTML
        document.getElementById('visitorNumber').textContent = visitorNumber;
        document.getElementById('visitTime').textContent = visitTimeString;
    </script>
</body>
</html>

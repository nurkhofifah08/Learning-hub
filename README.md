<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Learning Hub</title>

    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background: transparent;
        }

        .card {
            padding: 25px;
            border-radius: 20px;
            text-align: center;
            background: linear-gradient(135deg, #eef2ff, #ffffff);
            box-shadow: 0 8px 25px rgba(0,0,0,0.08);
        }

        .greeting {
            font-size: 18px;
            margin-bottom: 10px;
        }

        .clock {
            font-size: 45px;
            font-weight: bold;
        }

        .date {
            margin-top: 8px;
            color: #666;
        }
    </style>
</head>

<body>

    <div class="card">

        <div class="greeting" id="greeting">
            Selamat belajar! 👋
        </div>

        <div class="clock" id="clock">
            00:00:00
        </div>

        <div class="date" id="date">
            -
        </div>

    </div>


    <script>

        function updateClock() {

            const now = new Date();

            const hour = now.getHours();

            let greeting;

            if (hour < 11) {
                greeting = "Selamat pagi! ☀️";
            } 
            else if (hour < 15) {
                greeting = "Selamat siang! 🌤️";
            } 
            else if (hour < 18) {
                greeting = "Selamat sore! 🌅";
            } 
            else {
                greeting = "Selamat malam! 🌙";
            }

            document.getElementById("greeting").textContent =
                greeting + " Selamat belajar!";

            document.getElementById("clock").textContent =
                now.toLocaleTimeString("id-ID");

            document.getElementById("date").textContent =
                now.toLocaleDateString("id-ID", {
                    weekday: "long",
                    day: "numeric",
                    month: "long",
                    year: "numeric"
                });
        }

        updateClock();

        setInterval(updateClock, 1000);

    </script>

</body>
</html>

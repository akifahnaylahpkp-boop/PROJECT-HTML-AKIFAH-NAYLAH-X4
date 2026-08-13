# PROJECT-HTML-AKIFAH-NAYLAH-X4
PROJECT HTML 1 
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Klasifikasi Segitiga</title>

    <style>
        body {
            font-family: Arial;
            background: #f3e8ff;
            text-align: center;
            padding: 40px;
        }

        .container {
            background: white;
            width: 380px;
            margin: auto;
            padding: 30px;
            border-radius: 18px;
            box-shadow: 0 5px 15px #d8b4fe;
        }

        h1 {
            color: #9333ea;
        }

        input {
            width: 85%;
            padding: 12px;
            margin: 6px;
            border: 2px solid #c084fc;
            border-radius: 8px;
        }

        button {
            margin-top: 15px;
            padding: 12px 30px;
            background: #9333ea;
            color: white;
            border: none;
            border-radius: 8px;
        }

        #hasil {
            margin-top: 20px;
            color: #7e22ce;
            font-weight: bold;
            font-size: 20px;
        }
    </style>
</head>

<body>

<div class="container">

    <h1>🟣 Klasifikasi Segitiga</h1>

    <input id="sisi1" type="number" placeholder="Sisi A">
    <input id="sisi2" type="number" placeholder="Sisi B">
    <input id="sisi3" type="number" placeholder="Sisi C">

    <button onclick="klasifikasi()">Klasifikasikan</button>

    <div id="hasil"></div>

</div>

<script>

function klasifikasi() {

    let a = Number(document.getElementById("sisi1").value);
    let b = Number(document.getElementById("sisi2").value);
    let c = Number(document.getElementById("sisi3").value);

    let hasil = document.getElementById("hasil");

    if (a <= 0 || b <= 0 || c <= 0) {
        hasil.innerHTML = "⚠️ Semua sisi harus diisi!";
        return;
    }

    if (a + b <= c || a + c <= b || b + c <= a) {
        hasil.innerHTML = "❌ Tidak dapat membentuk segitiga.";
        return;
    }

    if (
        a*a + b*b == c*c ||
        a*a + c*c == b*b ||
        b*b + c*c == a*a
    ) {

        hasil.innerHTML = "📐 Segitiga Siku-Siku";

    } else if (a == b || a == c || b == c) {

        hasil.innerHTML = "🔺 Segitiga Sama Kaki";

    } else {

        hasil.innerHTML = "🔻 Segitiga Sembarang";
    }
}

</script>

</body>
</html>
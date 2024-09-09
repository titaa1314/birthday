<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy 20th Birthday</title>
    <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap">
    <style>
        body {
            font-family: 'Poppins', sans-serif;
            background-color: #f9f9f9;
            margin: 0;
            padding: 0;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            color: #333;
            overflow-x: hidden;
        }
        h1 {
            font-size: 3rem;
            color: #4b6584;
            margin-bottom: 20px;
            text-align: center;
            letter-spacing: 2px;
        }
        p {
            font-size: 1.5rem;
            color: #333;
            width: 80%;
            max-width: 600px;
            line-height: 1.6;
            text-align: center;
            margin-bottom: 40px;
        }
        img {
            width: 300px;
            height: auto;
            margin: 10px;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease;
        }
        img:hover {
            transform: scale(1.05);
            box-shadow: 0 6px 12px rgba(0, 0, 0, 0.2);
        }
        button {
            padding: 15px 30px;
            font-size: 1.2rem;
            color: white;
            background-color: #82ccdd;
            border: none;
            border-radius: 50px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            cursor: pointer;
            transition: background-color 0.3s ease, box-shadow 0.3s ease;
        }
        button:hover {
            background-color: #60a3bc;
            box-shadow: 0 6px 10px rgba(0, 0, 0, 0.2);
        }
        /* Pesan progres */
        .progress {
            margin-top: 20px;
            font-size: 1.2rem;
            color: #4b6584;
        }
        /* Animasi Bunga Dandelion */
        .flower {
            position: absolute;
            width: 30px;
            height: 30px;
            background: url('https://i.ibb.co/5KGBTVp/dandelion.png') no-repeat center/contain;
            animation: fall 5s linear infinite;
        }
        @keyframes fall {
            to {
                transform: translateY(100vh);
            }
        }
    </style>
</head>
<body>

    <h1 id="frag1" onclick="findFragment(1)">Happy 20th Birthday, Farah!</h1>

    <p id="frag2" onclick="findFragment(2)">
        Hari ini, aku langitkan semua doa terbaik aku untuk kamu. Sesuai sama nama kamu 'Farah' yang artinya kebahagiaan. Semoga hari-hari berikutnya kamu diiringi kebahagiaan yang tidak ada habisnya. Semoga kebahagiaan kamu bersama orang tua yang selalu kamu impikan itu kini sudah terlaksana. Semoga kamu selalu dilindungi dari orang yang berniat jahat sama kamu atau apapun itu. Dan yang paling penting, semoga kamu selalu menjadi anak yang sholehah yang bukan di dunia saja. Sehat selalu ya, cantik.
    </p>

    <img id="frag11" src="https://storage.googleapis.com/prompt-model-images/file-MdAsWcmz48ARH0eYyXqVkNhJ" alt="Foto momen kebersamaan" onclick="findFragment(11)">
    <img id="frag13" src="https://storage.googleapis.com/prompt-model-images/file-YeYUCaAsfZnwrSQkZ5tWCNTO" alt="Kolase Farah" onclick="findFragment(13)">

    <!-- Progres pesan tersembunyi -->
    <div class="progress" id="progress">Tersisa 13/13 pesan tersembunyi</div>

    <script>
        let foundFragments = [];
        const totalFragments = 13;
        let scrollSpeed = 5;

        function findFragment(fragmentId) {
            if (!foundFragments.includes(fragmentId)) {
                foundFragments.push(fragmentId);
                alert(`Pinter kamu menemukan 1 dari 13 pesan tersembunyi!`);
                updateProgress();
            }
        }

        function updateProgress() {
            const remaining = totalFragments - foundFragments.length;
            document.getElementById('progress').textContent = `Tersisa ${remaining}/${totalFragments} pesan tersembunyi`;
        }

        // Animasi Bunga Dandelion
        function createFlower() {
            const flower = document.createElement('div');
            flower.classList.add('flower');
            flower.style.left = Math.random() * window.innerWidth + 'px';
            document.body.appendChild(flower);

            setTimeout(() => {
                flower.remove();
            }, 5000 / scrollSpeed);
        }

        // Bunga jatuh otomatis tanpa scroll
        setInterval(createFlower, 500);

        // Deteksi scrolling untuk meningkatkan kecepatan bunga jatuh
        window.addEventListener('scroll', () => {
            scrollSpeed = 10; // Tingkatkan kecepatan saat scroll
            setTimeout(() => scrollSpeed = 5, 1000); // Kembali normal setelah 1 detik tidak scroll
        });
    </script>

</body>
</html>

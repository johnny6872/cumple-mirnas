<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>Feliz Cumpleaños Moy</title>
<style>
    body {
        margin: 0;
        padding: 0;
        background: linear-gradient(135deg, #ff9a9e, #fad0c4);
        font-family: Arial, sans-serif;
        text-align: center;
        color: #fff;
        overflow: hidden;
    }

    .contenedor {
        height: 100vh;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }

    img {
        width: 260px;
        border-radius: 20px;
        box-shadow: 0px 10px 25px rgba(0,0,0,0.3);
        animation: zoom 3s infinite alternate;
    }

    @keyframes zoom {
        from { transform: scale(1); }
        to { transform: scale(1.05); }
    }

    h1 {
        margin-top: 20px;
        font-size: 28px;
        animation: fadeIn 2s ease-in-out;
    }

    @keyframes fadeIn {
        from { opacity: 0; transform: translateY(20px);} 
        to { opacity: 1; transform: translateY(0);} 
    }

    .subtitulos {
        position: absolute;
        bottom: 40px;
        width: 100%;
        font-size: 20px;
        font-weight: bold;
        text-shadow: 2px 2px 5px black;
    }

    .emoji {
        position: absolute;
        font-size: 30px;
        animation: flotar linear infinite;
    }

    @keyframes flotar {
        0% {
            transform: translateY(100vh) rotate(0deg);
            opacity: 1;
        }
        100% {
            transform: translateY(-10vh) rotate(360deg);
            opacity: 0;
        }
    }
</style>
</head>
<body>

<div class="contenedor">
    <img src="Imagen de WhatsApp 2023-07-19 a las 20.19.29.jpg" alt="Foto especial">

    <h1>
        Feliz cumpleaños, Moy. My bro, la quiero mucho y Dios me la bendiga 🎉
    </h1>
</div>

<div class="subtitulos" id="subtitulo"></div>

<script>
    const frases = [
        "Cosas por las que es la mejor persona y se merece ese carro 💫",
        "1- Me alegra los días con sus pendejadas 😄",
        "2- Medio rarita, pero se le quiere 😂",
        "3- Dios la puso en mi camino; por eso ya no soy tan ateo 🙏",
        "4- Me hizo ir a un retiro; a huevos, el mejor retiro al que he ido 🔥",
        "5- Trauma, pero se le quiere 🍻",
        "La mejor amiga ❤️",
        "Feliz cumpleaños, Moy 🎂"
    ];

    let i = 0;
    const subtitulo = document.getElementById("subtitulo");

    function cambiarSubtitulo() {
        subtitulo.style.opacity = 0;

        setTimeout(() => {
            subtitulo.textContent = frases[i];
            subtitulo.style.opacity = 1;
            i = (i + 1) % frases.length;
        }, 500);
    }

    setInterval(cambiarSubtitulo, 3500);
    cambiarSubtitulo();

    function crearEmoji() {
        const emoji = document.createElement("div");
        emoji.classList.add("emoji");

        const emojis = ["🎉","🎂","🎈","✨","💖"];
        emoji.innerText = emojis[Math.floor(Math.random() * emojis.length)];

        emoji.style.left = Math.random() * 100 + "vw";
        emoji.style.animationDuration = (3 + Math.random() * 3) + "s";

        document.body.appendChild(emoji);

        setTimeout(() => {
            emoji.remove();
        }, 6000);
    }

    setInterval(crearEmoji, 300);
</script>

</body>
</html>

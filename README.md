# soheib-Valentin
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For Douaa</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
        <div id="valentine-card">
            <img id="main-image" src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExM2ZicDhkbmZ6bmZ6bmZ6bmZ6bmZ6bmZ6bmZ6bmZ6bmZ6bmZ6bmZ6JmVwPXYxX2ludGVybmFsX2dpZl9ieV9pZCZjdD1z/07sL0GljrVZYyUjU0F/giphy.gif" alt="Cute gif">
            
            <h1 id="question">Will you be my Valentine, Douaa?</h1>
            
            <div class="buttons">
                <button id="yesBtn">Yes</button>
                <button id="noBtn">No</button>
            </div>
        </div>
    </div>
    <script src="script.js"></script>
</body>
</html>
body {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
    background-color: #ffdde1;
    font-family: 'Arial', sans-serif;
    overflow: hidden; /* Prevents scrollbars when button moves */
}

.container {
    text-align: center;
}

#valentine-card img {
    width: 200px;
    height: auto;
    margin-bottom: 20px;
}

h1 {
    color: #d63384;
    font-size: 2em;
}

.buttons {
    margin-top: 20px;
    position: relative;
    height: 60px; /* Space for the absolute positioned buttons */
}

button {
    padding: 12px 28px;
    font-size: 1.2em;
    border: none;
    border-radius: 10px;
    cursor: pointer;
    transition: transform 0.2s ease;
}

#yesBtn {
    background-color: #ff4d6d;
    color: white;
}

#noBtn {
    background-color: #888;
    color: white;
    position: absolute;
}
const yesBtn = document.querySelector('#yesBtn');
const noBtn = document.querySelector('#noBtn');
const question = document.querySelector('#question');
const mainImage = document.querySelector('#main-image');

// When Douaa clicks Yes
yesBtn.addEventListener('click', () => {
    question.innerHTML = "I love you, Douaa!! ❤️";
    // Happy GIF
    mainImage.src = "https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExM2ZicDhkbmZ6bmZ6bmZ6bmZ6bmZ6bmZ6bmZ6bmZ6bmZ6bmZ6bmZ6JmVwPXYxX2ludGVybmFsX2dpZl9ieV9pZCZjdD1z/5K7ngC8KC3hYE/giphy.gif";
    
    // Hide the No button and the Yes button after clicking
    noBtn.style.display = 'none';
    yesBtn.style.display = 'none';
});

// When Douaa tries to click No, it jumps away
noBtn.addEventListener('mouseover', () => {
    // Calculate random position within the window
    const x = Math.floor(Math.random() * (window.innerWidth - noBtn.offsetWidth));
    const y = Math.floor(Math.random() * (window.innerHeight - noBtn.offsetHeight));
    
    noBtn.style.left = `${x}px`;
    noBtn.style.top = `${y}px`;
});

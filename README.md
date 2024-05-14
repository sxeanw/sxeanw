<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Emotion-Based Song Recommender</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>How Are You Feeling?</h1>
        <input type="text" id="emotion-input" placeholder="Enter your emotion...">
        <button onclick="getSong()">Get Song</button>
        <div id="song-result"></div>
    </div>
    <script src="script.js"></script>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
    background-color: #f0f0f0;
}

.container {
    text-align: center;
    background: #fff;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 0 10px rgba(0,0,0,0.1);
}

input {
    padding: 10px;
    margin-bottom: 10px;
    width: 80%;
    border: 1px solid #ccc;
    border-radius: 4px;
}

button {
    padding: 10px 20px;
    border: none;
    background-color: #007BFF;
    color: #fff;
    border-radius: 4px;
    cursor: pointer;
}

button:hover {
    background-color: #0056b3;
}

#song-result {
    margin-top: 20px;
    font-size: 1.2em;
}
const songs = {
    happy: "Happy by Pharrell Williams",
    sad: "Someone Like You by Adele",
    angry: "Break Stuff by Limp Bizkit",
    relaxed: "Weightless by Marconi Union",
    excited: "Can't Stop the Feeling! by Justin Timberlake",
    nostalgic: "Summer of '69 by Bryan Adams",
    love: "Perfect by Ed Sheeran"
};

function getSong() {
    const emotion = document.getElementById('emotion-input').value.toLowerCase().trim();
    const song = songs[emotion];
    const resultDiv = document.getElementById('song-result');
    if (song) {
        resultDiv.textContent = `You should listen to: ${song}`;
    } else {
        resultDiv.textContent = "Sorry, we couldn't find a song for that emotion. Try another!";
    }
}


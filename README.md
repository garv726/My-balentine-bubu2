<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Be My Valentine?</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #fce4ec; /* Light pink background */
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            overflow: hidden;
            text-align: center;
        }

        h1 {
            color: #d81b60;
            font-size: 2.0rem; /* Perfect size for mobile */
            margin-bottom: 20px;
            padding: 0 10px;
        }

        img {
            max-width: 250px;
            border-radius: 15px;
            margin-bottom: 20px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
        }

        .buttons {
            display: flex;
            gap: 20px;
        }

        button {
            padding: 15px 30px;
            font-size: 1.2rem;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            z-index: 100; /* Keeps button on top */
        }

        #yesBtn {
            background-color: #e91e63; /* Darker pink */
            color: white;
            font-weight: bold;
            box-shadow: 0 4px 10px rgba(233, 30, 99, 0.4);
        }

        #noBtn {
            background-color: #ffffff;
            color: #333;
            box-shadow: 0 4px 10px rgba(0,0,0,0.1);
            position: relative; 
        }
    </style>
</head>
<body>

    <div id="container">
        <img id="mainImage" src="https://media.tenor.com/J33FvF7yDk8AAAAi/cute-waving.gif" alt="Cute Valentine Bear"> 
        
        <h1>Will you be my Valentine Bubu?</h1>
        
        <div class="buttons">
            <button id="yesBtn">Yes</button>
            <button id="noBtn">No</button>
        </div>
    </div>

    <script>
        const yesBtn = document.getElementById('yesBtn');
        const noBtn = document.getElementById('noBtn');
        const mainImage = document.getElementById('mainImage');
        const headerText = document.querySelector('h1');

        // Logic to make the "No" button run away randomly
        function moveButton() {
            const x = Math.random() * (window.innerWidth - noBtn.offsetWidth - 20);
            const y = Math.random() * (window.innerHeight - noBtn.offsetHeight - 20);
            
            noBtn.style.position = 'absolute';
            noBtn.style.left = `${x}px`;
            noBtn.style.top = `${y}px`;
        }

        // Move on hover (for computers)
        noBtn.addEventListener('mouseover', moveButton);
        
        // Move on touch (for phones)
        noBtn.addEventListener('touchstart', (e) => {
            e.preventDefault(); 
            moveButton();
        });

        // Logic for when they click "Yes"
        yesBtn.addEventListener('click', () => {
            // Updated text with the heart emoji!
            headerText.innerHTML = "YAY! I knew it! ❤️🎉";
            
            // I put a working internet link here for the Leo Cheers!
            mainImage.src = "https://media.giphy.com/media/g9582DNuQppxC/giphy.gif"; 
            
            // Hide the buttons
            yesBtn.style.display = 'none';
            noBtn.style.display = 'none';
            
            // Change background color slightly
            document.body.style.backgroundColor = "#ffc1e3";
        });
    </script>
</body>
</html>

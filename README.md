<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nexus AI Image Generator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        #container {
            background: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
            text-align: center;
        }
        #generateBtn {
            padding: 10px 20px;
            background-color: #28a745;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        #generateBtn:hover {
            background-color: #218838;
        }
        #image {
            margin-top: 20px;
            max-width: 100%;
            height: auto;
        }
    </style>
</head>
<body>
    <div id="container">
        <h1>Nexus AI Image Generator</h1>
        <button id="generateBtn">Generate Image</button>
        <img id="image" src="" alt="Generated Image">
    </div>
    <script>
        document.getElementById('generateBtn').addEventListener('click', function() {
            fetch('https://api.pollinations.ai/generate')
                .then(response => response.json())
                .then(data => {
                    document.getElementById('image').src = data.image_url;
                })
                .catch(error => console.error('Error fetching image:', error));
        });
    </script>
</body>
</html>
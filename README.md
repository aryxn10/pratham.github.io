# Enhancing Your Birthday Website with Images and Interactivity

I'll customize the birthday website with more images and interactive elements to make it even more special for Akanksha. Here's an enhanced version of the code:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday Akanksha!</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            background-color: #fce4ec;
            font-family: 'Arial', sans-serif;
            overflow-x: hidden;
            text-align: center;
            background-image: url('https://images.unsplash.com/photo-1527529482837-4698179dc6ce?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80');
            background-size: cover;
            background-attachment: fixed;
        }
        
        .container {
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
            background-color: rgba(255, 255, 255, 0.8);
            border-radius: 15px;
            box-shadow: 0 8px 32px rgba(31, 38, 135, 0.37);
            backdrop-filter: blur(4px);
            margin-top: 20px;
            margin-bottom: 20px;
        }
        
        h1 {
            font-size: 3.5rem;
            color: #e91e63;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.2);
            animation: bounce 2s infinite;
        }
        
        .birthday-message {
            font-size: 1.5rem;
            color: #6a1b9a;
            margin-bottom: 30px;
        }
        
        .cake {
            font-size: 100px;
            margin: 20px 0;
            animation: rotate 10s infinite linear;
            display: inline-block;
        }
        
        .balloons {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }
        
        .balloon {
            position: absolute;
            width: 40px;
            height: 50px;
            border-radius: 50%;
            animation: float 15s infinite ease-in-out;
        }
        
        .confetti-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }
        
        .confetti {
            position: absolute;
            width: 10px;
            height: 10px;
            animation: fall 8s infinite linear;
        }
        
        .btn {
            background-color: #e91e63;
            color: white;
            border: none;
            padding: 12px 24px;
            font-size: 1.2rem;
            border-radius: 50px;
            cursor: pointer;
            margin: 10px;
            transition: all 0.3s;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
        }
        
        .btn:hover {
            background-color: #c2185b;
            transform: scale(1.05);
        }
        
        .gift-box {
            width: 150px;
            height: 150px;
            background-color: #ff4081;
            position: relative;
            margin: 30px auto;
            animation: pulse 2s infinite;
            cursor: pointer;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
            border-radius: 10px;
        }
        
        .gift-box:before {
            content: '';
            position: absolute;
            width: 30px;
            height: 150px;
            background-color: #f50057;
            left: 50%;
            transform: translateX(-50%);
            border-radius: 5px;
            z-index: 1;
        }
        
        .gift-box:after {
            content: '';
            position: absolute;
            width: 150px;
            height: 30px;
            background-color: #f50057;
            top: 50%;
            transform: translateY(-50%);
            border-radius: 5px;
            z-index: 1;
        }
        
        .gift-message {
            display: none;
            font-size: 1.5rem;
            color: #e91e63;
            margin: 20px 0;
            padding: 15px;
            background-color: rgba(255, 255, 255, 0.8);
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
        }
        
        .photo-gallery {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 10px;
            margin: 20px 0;
        }
        
        .photo-frame {
            width: 150px;
            height: 150px;
            border: 5px solid white;
            box-shadow: 0 4px 8px rgba(0,0,0,0.2);
            overflow: hidden;
            border-radius: 10px;
            transition: transform 0.3s;
            cursor: pointer;
        }
        
        .photo-frame:hover {
            transform: scale(1.1);
        }
        
        .photo-frame img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .memory-container {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0,0,0,0.8);
            z-index: 100;
            display: flex;
            justify-content: center;
            align-items: center;
            opacity: 0;
            transition: opacity 0.3s;
            pointer-events: none;
        }
        
        .memory-container.active {
            opacity: 1;
            pointer-events: all;
        }
        
        .memory {
            background-color: white;
            padding: 20px;
            border-radius: 10px;
            max-width: 600px;
            width: 80%;
            position: relative;
        }
        
        .close-memory {
            position: absolute;
            top: 10px;
            right: 10px;
            background: none;
            border: none;
            font-size: 20px;
            cursor: pointer;
            color: #e91e63;
        }
        
        .memory-title {
            font-size: 1.5rem;
            color: #e91e63;
            margin-bottom: 10px;
        }
        
        .memory-text {
            font-size: 1rem;
            color: #333;
        }
        
        .cake-container {
            position: relative;
            width: 200px;
            height: 200px;
            margin: 0 auto;
        }
        
        .cake-img {
            width: 100%;
            cursor: pointer;
        }
        
        .candle {
            position: absolute;
            top: 30px;
            width: 20px;
            height: 40px;
            background: linear-gradient(to bottom, #ffeb3b, #ffc107);
            border-radius: 10px 10px 0 0;
            z-index: 2;
        }
        
        .flame {
            position: absolute;
            top: -20px;
            left: 5px;
            width: 10px;
            height: 20px;
            background: linear-gradient(to bottom, #ff5722, #ff9800);
            border-radius: 50% 50% 20% 20%;
            animation: flicker 1s infinite alternate;
        }
        
        #countdown {
            font-size: 2rem;
            color: #e91e63;
            margin: 20px 0;
            font-weight: bold;
        }
        
        .birthday-wish {
            max-width: 400px;
            height: 100px;
            margin: 20px auto;
            padding: 10px;
            font-size: 1rem;
            border: 2px solid #e91e63;
            border-radius: 10px;
            resize: none;
        }
        
        .wishes-container {
            max-height: 200px;
            overflow-y: auto;
            margin: 20px 0;
            padding: 10px;
            background-color: rgba(255, 255, 255, 0.7);
            border-radius: 10px;
        }
        
        .wish {
            padding: 10px;
            margin: 10px 0;
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            text-align: left;
        }
        
        .polaroid {
            background: white;
            padding: 10px 10px 30px 10px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
            transform: rotate(var(--rotation)); 
            transition: all 0.3s;
        }
        
        .polaroid:hover {
            transform: rotate(0deg) scale(1.05);
        }
        
        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }
        
        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }
        
        @keyframes float {
            0% { transform: translateY(100vh); opacity: 1; }
            100% { transform: translateY(-100px); opacity: 0; }
        }
        
        @keyframes fall {
            0% { transform: translateY(-100px) rotate(0deg); opacity: 1; }
            100% { transform: translateY(100vh) rotate(720deg); opacity: 0; }
        }
        
        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }
        
        @keyframes flicker {
            0%, 100% { transform: scaleY(1); }
            50% { transform: scaleY(1.2); }
        }
        
        .decoration {
            position: fixed;
            width: 100%;
            height: 50px;
            background-image: repeating-linear-gradient(45deg, #ff4081, #ff4081 10px, #f48fb1 10px, #f48fb1 20px);
            z-index: -1;
        }
        
        .decoration-top {
            top: 0;
        }
        
        .decoration-bottom {
            bottom: 0;
        }
    </style>
</head>
<body>
    <div class="decoration decoration-top"></div>
    <div class="decoration decoration-bottom"></div>
    <div class="balloons" id="balloons"></div>
    <div class="confetti-container" id="confetti"></div>
    
    <div class="container">
        <h1>Happy Birthday AKANKSHA!</h1>
        <div class="birthday-message">
            Wishing you an amazing day filled with joy, laughter, and wonderful memories!
        </div>
        
        <div id="countdown">Birthday Countdown: Loading...</div>
        
        <div class="cake-container">
            <img src="https://images.unsplash.com/photo-1563729784474-d77dbb933a9e?ixlib=rb-1.2.1&auto=format&fit=crop&w=1267&q=80" class="cake-img" alt="Birthday Cake">
            <div class="candle" style="left: 90px;">
                <div class="flame" id="flame"></div>
            </div>
        </div>
        
        <div class="photo-gallery">
            <div class="photo-frame polaroid" style="--rotation: -5deg;" onclick="showMemory(1)">
                <img src="https://images.unsplash.com/photo-1527529482837-4698179dc6ce?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Birthday Memory">
            </div>
            <div class="photo-frame polaroid" style="--rotation: 3deg;" onclick="showMemory(2)">
                <img src="https://images.unsplash.com/photo-1530103862676-de8c9debad1d?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Birthday Memory">
            </div>
            <div class="photo-frame polaroid" style="--rotation: -2deg;" onclick="showMemory(3)">
                <img src="https://images.unsplash.com/photo-1464349153735-7db50ed83c84?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Birthday Memory">
            </div>
            <div class="photo-frame polaroid" style="--rotation: 4deg;" onclick="showMemory(4)">
                <img src="https://images.unsplash.com/photo-1523301343968-6a6ebf63c672?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Birthday Memory">
            </div>
        </div>
        
        <div class="gift-box" id="giftBox"></div>
        <div class="gift-message" id="giftMessage">
            Dear Akanksha, may your birthday be as beautiful and special as you are! 
            Here's to another amazing year of your life! 🎉
        </div>
        
        <button class="btn" id="playBtn">Play Birthday Song</button>
        <button class="btn" id="moreBtn">More Confetti!</button>
        <button class="btn" id="wishBtn">Make a Wish</button>
        
        <div id="wishingWell" style="display: none;">
            <textarea class="birthday-wish" id="wishText" placeholder="Write your birthday wish for Akanksha here..."></textarea>
            <button class="btn" id="submitWish">Submit Wish</button>
            
            <div class="wishes-container" id="wishesContainer">
                <div class="wish">
                    <strong>Mom & Dad:</strong> Happy birthday to our amazing daughter! We love you so much!
                </div>
                <div class="wish">
                    <strong>Best Friend:</strong> Cheers to another year of our crazy adventures! Happy birthday!
                </div>
            </div>
        </div>
    </div>
    
    <div class="memory-container" id="memoryContainer">
        <div class="memory">
            <button class="close-memory" onclick="closeMemory()">×</button>
            <h3 class="memory-title" id="memoryTitle">Memory Title</h3>
            <p class="memory-text" id="memoryText">Memory description goes here.</p>
            <img id="memoryImage" src="" alt="

<html lang="te">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ugadi Subhakanshalu</title>
    <style>
        body, html {
            margin: 0;
            padding: 0;
            height: 100%;
            overflow: hidden;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #FFD700; /* Yellow Background */
        }

        /* Curtain Styling */
        .curtain-container {
            position: fixed;
            width: 100%;
            height: 100%;
            display: flex;
            z-index: 10;
        }

        .curtain {
            width: 50%;
            height: 100%;
            background-color: #B22222; /* Red Curtains */
            transition: transform 1.5s ease-in-out;
            display: flex;
            align-items: center;
            position: relative;
        }

        .left-curtain { 
            justify-content: flex-end; 
            border-right: 2px solid #8B0000;
        }
        .right-curtain { 
            justify-content: flex-start; 
            border-left: 2px solid #8B0000;
        }

        /* Gold Button */
        #goldButton {
            position: absolute;
            left: 50%;
            top: 50%;
            transform: translate(-50%, -50%);
            padding: 15px 30px;
            font-size: 24px;
            background: linear-gradient(45deg, #D4AF37, #F9A602);
            color: #fff;
            border: 2px solid #fff;
            border-radius: 50px;
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(0,0,0,0.3);
            z-index: 20;
            font-weight: bold;
        }

        /* Open State for Curtains */
        .open .left-curtain { transform: translateX(-100%); }
        .open .right-curtain { transform: translateX(100%); }
        .open #goldButton { display: none; }

        /* Content Sections */
        .content-layer {
            position: absolute;
            width: 100%;
            height: 100%;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            visibility: hidden;
        }

        /* Big Om Styling */
        .om-symbol {
            font-size: 150px;
            color: #FF4500;
            cursor: pointer;
            text-shadow: 0 0 20px rgba(255, 69, 0, 0.4);
            transition: transform 0.3s ease;
        }
        .om-symbol:hover { transform: scale(1.1); }

        /* Final Wishes Styling */
        .wishes {
            padding: 20px;
            color: #4B0082;
            background: rgba(255, 255, 255, 0.8);
            border-radius: 20px;
            box-shadow: 0 0 20px rgba(0,0,0,0.1);
            max-width: 80%;
        }

        h1 { font-size: 2.5rem; color: #8B0000; }
        p { font-size: 1.5rem; line-height: 1.6; }
    </style>
</head>
<body>

    <div class="curtain-container" id="curtainWrapper">
        <div class="curtain left-curtain"></div>
        <button id="goldButton" onclick="openCurtains()">శుభోదయం</button>
        <div class="curtain right-curtain"></div>
    </div>

    <div class="content-layer" id="omSection">
        <div class="om-symbol" onclick="showWishes()">ఓం</div>
        <p style="color: #8B0000;">(Press Om for Blessings)</p>
    </div>

    <div class="content-layer" id="wishSection">
        <div class="wishes">
            <h1>శ్రీ వేంకటేశ్వర స్వామి ఆశీస్సులు</h1>
            <p>మీకు, మీ కుటుంబ సభ్యులకు <strong>ఉగాది శుభాకాంక్షలు!</strong></p>
            <p>ఆ వేంకటేశ్వర స్వామి అనుగ్రహంతో ఈ సంవత్సరం మీకు ఆయురారోగ్యాలు, ఐశ్వర్యాలు కలగాలని కోరుకుంటున్నాను.</p>
        </div>
    </div>

    <script>
        function openCurtains() {
            document.getElementById('curtainWrapper').classList.add('open');
            // Show the Om section after curtains start moving
            setTimeout(() => {
                document.getElementById('omSection').style.visibility = 'visible';
            }, 500);
        }

        function showWishes() {
            document.getElementById('omSection').style.display = 'none';
            document.getElementById('wishSection').style.visibility = 'visible';
        }
    </script>

</body>
</html>

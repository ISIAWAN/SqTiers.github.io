<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SqTiers - Minecraft PvP Tier List</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 0;
        }
        header {
            background-color: #333;
            color: white;
            padding: 20px;
            text-align: center;
        }
        .container {
            display: flex;
            justify-content: center;
            padding: 20px;
        }
        .tier-column {
            width: 250px;
            margin: 0 20px;
            background-color: #fff;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
            padding: 10px;
        }
        .tier-column h2 {
            text-align: center;
            font-size: 22px;
            margin-bottom: 15px;
            color: #333;
        }
        .player {
            padding: 12px;
            margin: 8px 0;
            background-color: #f1f1f1;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
            color: #333;
        }
        .player:hover {
            background-color: #ddd;
        }
        .footer {
            background-color: #333;
            color: white;
            text-align: center;
            padding: 10px;
            position: absolute;
            bottom: 0;
            width: 100%;
        }
    </style>
</head>
<body>

<header>
    <h1>SqTiers - Minecraft PvP Tier List</h1>
    <p>Welcome to the Minecraft PvP Tier List! Rank your favorite players.</p>
</header>

<div class="container">
    <!-- S Tier -->
    <div class="tier-column" id="s-tier" ondrop="drop(event)" ondragover="allowDrop(event)">
        <h2>S Tier</h2>
        <div class="player" id="player1" draggable="true" ondragstart="drag(event)">Player1 - 5000 Elo</div>
        <div class="player" id="player2" draggable="true" ondragstart="drag(event)">Player2 - 4800 Elo</div>
    </div>
    
    <!-- A Tier -->
    <div class="tier-column" id="a-tier" ondrop="drop(event)" ondragover="allowDrop(event)">
        <h2>A Tier</h2>
        <div class="player" id="player3" draggable="true" ondragstart="drag(event)">Player3 - 4600 Elo</div>
        <div class="player" id="player4" draggable="true" ondragstart="drag(event)">Player4 - 4400 Elo</div>
    </div>

    <!-- B Tier -->
    <div class="tier-column" id="b-tier" ondrop="drop(event)" ondragover="allowDrop(event)">
        <h2>B Tier</h2>
        <div class="player" id="player5" draggable="true" ondragstart="drag(event)">Player5 - 4200 Elo</div>
        <div class="player" id="player6" draggable="true" ondragstart="drag(event)">Player6 - 4000 Elo</div>
    </div>
</div>

<div class="footer">
    <p>Created by [Your Name]</p>
</div>

<script>
    // Allow drop functionality
    function allowDrop(ev) {
        ev.preventDefault();
    }

    // Start dragging player
    function drag(ev) {
        ev.dataTransfer.setData("text", ev.target.id);
    }

    // Drop player into new tier
    function drop(ev) {
        ev.preventDefault();
        var data = ev.dataTransfer.getData("text");
        var draggedElement = document.getElementById(data);
        ev.target.appendChild(draggedElement);
    }
</script>

</body>
</html>

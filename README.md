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
            padding: 10px;
            text-align: center;
        }
        .container {
            display: flex;
            justify-content: center;
            padding: 20px;
        }
        .tier-column {
            width: 200px;
            margin: 0 10px;
            background-color: #fff;
            border-radius: 5px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
            padding: 10px;
        }
        .tier-column h2 {
            text-align: center;
            font-size: 20px;
            margin-bottom: 10px;
        }
        .player {
            padding: 10px;
            margin: 5px 0;
            background-color: #f1f1f1;
            border-radius: 5px;
            cursor: pointer;
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
</header>

<div class="container">
    <div class="tier-column" id="s-tier">
        <h2>S Tier</h2>
        <div class="player" draggable="true" ondragstart="drag(event)" id="player1">Player1 - 5000 Elo</div>
        <div class="player" draggable="true" ondragstart="drag(event)" id="player2">Player2 - 4800 Elo</div>
    </div>
    
    <div class="tier-column" id="a-tier">
        <h2>A Tier</h2>
        <div class="player" draggable="true" ondragstart="drag(event)" id="player3">Player3 - 4600 Elo</div>
        <div class="player" draggable="true" ondragstart="drag(event)" id="player4">Player4 - 4400 Elo</div>
    </div>

    <div class="tier-column" id="b-tier">
        <h2>B Tier</h2>
        <div class="player" draggable="true" ondragstart="drag(event)" id="player5">Player5 - 4200 Elo</div>
        <div class="player" draggable="true" ondragstart="drag(event)" id="player6">Player6 - 4000 Elo</div>
    </div>
</div>

<div class="footer">
    <p>Created by [Your Name]</p>
</div>

<script>
    function allowDrop(ev) {
        ev.preventDefault();
    }

    function drag(ev) {
        ev.dataTransfer.setData("text", ev.target.id);
    }

    function drop(ev) {
        ev.preventDefault();
        var data = ev.dataTransfer.getData("text");
        var draggedElement = document.getElementById(data);
        ev.target.appendChild(draggedElement);
    }

    // Enable the drag-and-drop functionality
    const columns = document.querySelectorAll('.tier-column');
    columns.forEach(column => {
        column.addEventListener('dragover', allowDrop);
        column.addEventListener('drop', drop);
    });
</script>

</body>
</html>

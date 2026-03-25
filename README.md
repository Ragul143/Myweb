<html>
<head>
    <title>Love Page</title>

    <style>
        body {
            margin: 0;
            font-family: Arial;
            background: #0f0f0f;
            color: white;
            text-align: center;
            transition: 1s;
        }

        .box {
            margin-top: 120px;
        }

        input {
            padding: 10px;
            margin: 10px;
            border-radius: 8px;
            border: none;
        }

        button {
            padding: 10px 20px;
            margin: 10px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-size: 16px;
        }

        #yes {
            background: #ff007f;
            color: white;
        }

        #no {
            background: gray;
            color: white;
            position: absolute;
        }

        .hidden {
            display: none;
        }
    </style>
</head>

<body>

<!-- LOGIN -->
<div class="box" id="loginPage">
    <h2>🔐 Login</h2>
    <input type="text" placeholder="Username" id="user"><br>
    <input type="password" placeholder="Password" id="pass"><br>
    <button onclick="login()">Login</button>
</div>

<!-- LOVE QUESTION -->
<div class="box hidden" id="lovePage">
    <h1>I Love You 💖</h1>
    <h2>Do you love me?</h2>

    <button id="yes" onclick="yesClick()">Yes ❤️</button>
    <button id="no" onmouseover="moveNo()">No 😜</button>
</div>

<!-- FINAL PAGE -->
<div class="box hidden" id="finalPage">
    <h1 id="msg"></h1>
</div>

<script>

function login() {
    var u = document.getElementById("user").value;
    var p = document.getElementById("pass").value;

    if(u !== "" && p !== "") {
        document.getElementById("loginPage").classList.add("hidden");
        document.getElementById("lovePage").classList.remove("hidden");
    } else {
        alert("Enter Username & Password");
    }
}

// NO button move
function moveNo() {
    var btn = document.getElementById("no");

    var x = Math.random() * window.innerWidth;
    var y = Math.random() * window.innerHeight;

    btn.style.left = x + "px";
    btn.style.top = y + "px";
}

// YES click
function yesClick() {
    document.body.style.background = "linear-gradient(to right, #ff99cc, #ff4da6)";

    document.getElementById("lovePage").classList.add("hidden");
    document.getElementById("finalPage").classList.remove("hidden");

    document.getElementById("msg").innerHTML = "I LOVE YOU 🌹 KAMINI 💖";
}

</script>

</body>
</html>

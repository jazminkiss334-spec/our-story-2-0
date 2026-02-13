<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>LOVE_PROTOCOL</title>

<style>
body{
    background:black;
    color:#00ff88;
    font-family:Courier New, monospace;
    text-align:center;
}
h1{
    margin-top:40px;
    text-shadow:0 0 15px #00ff88;
}
#terminal{
    margin-top:40px;
    min-height:150px;
    font-size:18px;
}
input{
    background:black;
    border:1px solid #00ff88;
    color:#00ff88;
    padding:10px;
    width:350px;
    margin-top:20px;
}
button{
    background:#001a0f;
    border:1px solid #00ff88;
    color:#00ff88;
    padding:10px 20px;
    cursor:pointer;
}
button:hover{
    background:#003322;
}
.glitch{
    animation:glitch 1s infinite;
}
@keyframes glitch{
    0%{text-shadow:2px 2px red;}
    25%{text-shadow:-2px -2px blue;}
    50%{text-shadow:2px -2px lime;}
    75%{text-shadow:-2px 2px magenta;}
    100%{text-shadow:2px 2px red;}
}
.heart{
    font-size:70px;
    animation:beat 1s infinite;
}
@keyframes beat{
    0%{transform:scale(1);}
    50%{transform:scale(1.3);}
    100%{transform:scale(1);}
}
.robot{
    font-size:80px;
    animation:float 2s infinite;
}
@keyframes float{
    0%{transform:translateY(0);}
    50%{transform:translateY(-20px);}
    100%{transform:translateY(0);}
}
</style>
</head>

<body>

<h1 class="glitch">OPERATION: LOVE_PROTOCOL</h1>

<div id="terminal">
Type <b>start</b> to initialize system...
</div>

<input id="answer" placeholder="ENTER COMMAND">
<br>
<button onclick="checkAnswer()">EXECUTE</button>

<script>

let level = 0;
const terminal = document.getElementById("terminal");

function normalize(text){
    return text.toLowerCase().trim();
}

function checkAnswer(){
    let input = normalize(document.getElementById("answer").value);

    if(level === 0){
        if(input === "start"){
            level = 1;
            terminal.innerHTML = "SYSTEM INITIALIZED ✔<br><br>LEVEL 1:<br>What was the first thing I asked you NOT to do at the beginning of our relationship?";
        } else {
            fail();
        }
    }

    else if(level === 1){
        if(input.includes("not put") && input.includes("floor")){
            level = 2;
            terminal.innerHTML = "LEVEL 1 COMPLETE ✔<br><br>LEVEL 2:<br>What was the first drink we had together and where?";
        } else fail();
    }

    else if(level === 2){
        if(input.includes("tea") && input.includes("billy")){
            level = 3;
            terminal.innerHTML = "LEVEL 2 COMPLETE ✔<br>'If you continue like this maybe today you can love me one hour more.'<br><br>LEVEL 3:<br>Correct the wrong location and day:<br><br>Our first kiss was in the city on Friday...";
        } else fail();
    }

    else if(level === 3){
        if(input.includes("danube") && input.includes("sunday")){
            level = 4;
            terminal.innerHTML = "LEVEL 3 COMPLETE ✔<br><br>LEVEL 4:<br>Answer ALL in one line:<br>1) What did we eat the first night?<br>2) What themed escape room?<br>3) What chocolate did you give me in the taxi?";
        } else fail();
    }

    else if(level === 4){
        if(input.includes("spaghetti") && input.includes("egyptian") && input.includes("ferrero")){
            level = 5;
            terminal.innerHTML = "LEVEL 4 COMPLETE ✔<br><br>LEVEL 5:<br>What was the first thing that caught you about me?";
        } else fail();
    }

    else if(level === 5){
        if(input.includes("face") || input.includes("eyes")){
            level = 6;
            terminal.innerHTML = "LEVEL 5 COMPLETE ✔<br><br>LEVEL 6:<br>Describe our relationship's strengths in 5 words.";
        } else fail();
    }

    else if(level === 6){
        if(input.split(" ").length >= 5){
            showFinal();
        } else fail();
    }

    document.getElementById("answer").value = "";
}

function fail(){
    terminal.innerHTML += "<br><br>ACCESS DENIED ❌ Try again...";
}

function showFinal(){
    document.body.innerHTML = `
        <h1 class="glitch">SYSTEM SUCCESSFUL</h1>
        <div class="robot">🤖</div>
        <div class="heart">❤️</div>
        <h2>
        A test successful :<br><br>
        I love you my Love<br>
        Happy Valentine's Day ❤️
        </h2>
    `;
}

</script>

</body>
</html>
**# our-story-2-0

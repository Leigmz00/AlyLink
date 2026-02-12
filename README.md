<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>will you be my valentine?</title>

<style>
body{
  margin:0;
  height:100vh;
  display:flex;
  align-items:center;
  justify-content:center;
  background:#fff0f3;
  font-family:-apple-system,BlinkMacSystemFont,Arial,sans-serif;
  overflow:hidden;
  padding:1rem
}
#box{
  background:#fff;
  padding:2rem 1.5rem;
  border-radius:24px;
  box-shadow:0 12px 30px rgba(255,77,109,.2);
  text-align:center;
  width:100%;
  max-width:360px;
  z-index:2
}
h1{color:#ff4d6d;font-size:1.7rem}
button{
  margin:10px;
  padding:14px 28px;
  font-size:1.1rem;
  border:0;
  border-radius:40px;
  font-weight:bold;
  cursor:pointer
}
#yes{background:#ff4d6d;color:#fff}
#no{background:#ffb3c1;color:#fff}
.heart{
  position:absolute;
  bottom:-40px;
  animation:up 4s linear forwards;
  pointer-events:none
}
@keyframes up{
  to{transform:translateY(-110vh);opacity:0}
}
</style>
</head>

<body>
<div id="box">
  <div style="font-size:3rem">🌹</div>
  <h1 id="q">Will you be my Valentine?</h1>
  <button id="yes">YES</button>
  <button id="no">NO</button>
</div>

<script>
const y=document.getElementById("yes"),
n=document.getElementById("no"),
b=document.getElementById("box");

const msgs=[
  "Baby, are you sure?",
  "Really baby? 🥺",
  "Come on baby",
  "Don’t break my heart 💔",
  "Please baby",
  "Okay… yes? 🤍"
];

let i=0,s=1.1;

function heart(){
  const h=document.createElement("div");
  h.className="heart";
  h.textContent="❤️";
  h.style.left=Math.random()*100+"vw";
  h.style.fontSize=12+Math.random()*18+"px";
  document.body.appendChild(h);
  setTimeout(()=>h.remove(),4000)
}
setInterval(heart,900);

n.onclick=()=>{
  n.textContent=msgs[Math.min(i++,msgs.length-1)];
  s+=.25;
  y.style.fontSize=s+"rem"
};

y.onclick=()=>{
  b.innerHTML=`
    <div style="font-size:4rem">💖✨</div>
    <h1>Baby… thank you</h1>
    <p style="color:#ff4d6d">
      I choose you, baby.  
      Today, tomorrow, and in all the little moments.
      You make my heart feel home 🤍
    </p>`;
  for(let j=0;j<40;j++)setTimeout(heart,j*40)
};
</script>
</body>
</html>

# valentine-page
A romantic Valentine website with falling hearts ❤️
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My Valentine ❤️</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

  <div class="card">
    <h1>💖 Happy Valentine’s Day 💖</h1>
    
    <p class="message">
      Every moment with you feels like magic.  
      Your smile lights up my world and your love fills my heart completely ❤️
    </p>

    <img src="https://i.imgur.com/TJitvOH.jpeg" class="photo">

    <p class="from">With Love 💌</p>
  </div>

  <div id="hearts"></div>

<script src="script.js"></script>
</body>
</html>body{
  margin:0;
  font-family: Arial, sans-serif;
  text-align:center;
  background: linear-gradient(135deg,#ff4d6d,#ff99aa);
  color:white;
  overflow:hidden;
}

.card{
  margin-top:60px;
  background:rgba(255,255,255,0.15);
  padding:30px;
  border-radius:20px;
  display:inline-block;
  box-shadow:0 0 25px rgba(0,0,0,0.3);
  position:relative;
  z-index:10;
}

h1{
  margin-bottom:15px;
}

.message{
  font-size:18px;
  margin-bottom:25px;
}

.photo{
  width:220px;
  height:220px;
  object-fit:cover;
  border-radius:50%;
  border:5px solid white;
  margin-bottom:20px;
}

.from{
  font-size:18px;
}

/* hearts */
#hearts{
  position:fixed;
  top:0;
  left:0;
  width:100%;
  height:100%;
  pointer-events:none;
  z-index:1;
}

.heart{
  position:absolute;
  animation:fall linear infinite;
}

@keyframes fall{
  0%{transform:translateY(-50px) rotate(0);opacity:1;}
  100%{transform:translateY(100vh) rotate(360deg);opacity:0;}
}
const container = document.getElementById("hearts");

function makeHeart(){
  const heart = document.createElement("div");
  heart.className="heart";
  heart.innerHTML="❤️";

  heart.style.left=Math.random()*100+"vw";
  heart.style.fontSize=(20+Math.random()*30)+"px";
  heart.style.animationDuration=(3+Math.random()*5)+"s";

  container.appendChild(heart);

  setTimeout(()=>heart.remove(),6000);
}

setInterval(makeHeart,300);

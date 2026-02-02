<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Valentine 💖</title>

<style>
body{
    margin:0;
    height:100vh;
    font-family:Arial, sans-serif;
    background:linear-gradient(135deg,#ff5f8a,#ff9fb5);
    display:flex;
    justify-content:center;
    align-items:center;
    text-align:center;
    overflow:hidden;
}

#card{
    background:white;
    padding:20px;
    border-radius:16px;
    width:90%;
    max-width:360px;
    position:relative;
}

button{
    padding:12px 20px;
    border:none;
    border-radius:12px;
    font-size:16px;
    cursor:pointer;
    margin:10px;
}

#yes{background:#ff3366;color:white;}
#no{background:#ddd;position:absolute;}

#msg{
    font-size:14px;
    color:#ff3366;
    margin-top:10px;
}

#gallery{display:none;}

img{
    width:100%;
    border-radius:12px;
    margin-top:10px;
}

.caption{
    margin-top:8px;
    font-size:15px;
    color:#ff3366;
}

#next{background:#ff3366;color:white}

/* Fireworks */
.firework{
    position:absolute;
    width:6px;
    height:6px;
    background:red;
    border-radius:50%;
    animation:explode 1s ease-out forwards;
}
@keyframes explode{
    to{
        transform:translate(var(--x),var(--y)) scale(0);
        opacity:0;
    }
}
</style>
</head>

<body>

<div id="card">
    <h2 id="title">Will you be my Valentine? 💘</h2>
    <button id="yes">YES 💖</button>
    <button id="no">NO 😜</button>
    <div id="msg"></div>

    <div id="gallery">
        <!-- Kesariya Song -->
        <iframe width="0" height="0"
        src="https://www.youtube.com/embed/BddP6PYo2gs?autoplay=1&loop=1&playlist=BddP6PYo2gs">
        </iframe>

        <img id="photo">
        <div class="caption" id="text"></div>
        <button id="next">Next 💕</button>
    </div>
</div>

<script>
const noBtn=document.getElementById("no");
const yesBtn=document.getElementById("yes");
const msg=document.getElementById("msg");
const gallery=document.getElementById("gallery");
const photo=document.getElementById("photo");
const text=document.getElementById("text");
const next=document.getElementById("next");

const noTexts=[
"🥹😻 Sach mai na kar ri ho",
"😁🥺 Dubara likh ke aae dekh lo cute hu mai ✨️💗",
"💞🎀 jawline bhi mst h meri radha raani ka bhakt hu",
"😄 funny bhi hu thoda",
"🤣 oh hooo manegi ni yes hi karna hoga ni toh khelegi ni"
];

let noCount=0;

const photos=[
{img:"https://i.postimg.cc/CLJqjJtX/image1.jpg",txt:"you are the most cutest person I have ever seen 🎀💞"},
{img:"https://i.postimg.cc/8z4j4vDw/image2.jpg",txt:"thank you so mujh mujhe jhelne ke lie 😁✨️💗"},
{img:"https://i.postimg.cc/SxHk9xZw/image3.jpg",txt:"I love jo bhi tumhari bacho baali harkate h sab kuch 💓😍😘"},
{img:"https://i.postimg.cc/9MzX1YhY/image4.jpg",txt:"hope humari dosti humesa bani rahe 🎀♥️🤌🏻"},
{img:"https://i.postimg.cc/0QF0z0kR/image5.jpg",txt:"Betuuuuuu I love you so muchhh 💞💞😘😘😘"}
];

let index=0;

noBtn.addEventListener("mouseover",()=>{
    msg.innerText=noTexts[Math.min(noCount,noTexts.length-1)];
    noCount++;
    noBtn.style.left=Math.random()*200+"px";
    noBtn.style.top=Math.random()*200+"px";
});

yesBtn.addEventListener("click",()=>{
    document.getElementById("title").style.display="none";
    yesBtn.style.display="none";
    noBtn.style.display="none";
    msg.style.display="none";
    gallery.style.display="block";
    showPhoto();
});

function showPhoto(){
    photo.src=photos[index].img;
    text.innerText=photos[index].txt;
}

next.addEventListener("click",()=>{
    index++;
    if(index<photos.length){
        showPhoto();
    }else{
        next.style.display="none";
        text.innerText="Forever Us 💖";
        fireworks();
    }
});

function fireworks(){
    for(let i=0;i<40;i++){
        const f=document.createElement("div");
        f.className="firework";
        f.style.left="50%";
        f.style.top="50%";
        f.style.setProperty("--x",(Math.random()*400-200)+"px");
        f.style.setProperty("--y",(Math.random()*400-200)+"px");
        f.style.background=`hsl(${Math.random()*360},100%,60%)`;
        document.body.appendChild(f);
        setTimeout(()=>f.remove(),1000);
    }
}
</script>

</body>
</html># Love-dairy

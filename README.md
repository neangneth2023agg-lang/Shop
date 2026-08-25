# Shop Gia Minh
Kim cương 
<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>Gia Minh • Effect Shop</title>

<style>
*{box-sizing:border-box}
body{
 margin:0;background:#050713;color:#fff;
 font-family:Arial,Helvetica,sans-serif
}
.app{
 max-width:500px;min-height:100vh;margin:auto;
 background:radial-gradient(circle at 50% -10%,#26365d,#080a13 48%);
 padding-bottom:90px
}
header{
 padding:14px;position:sticky;top:0;z-index:20;
 background:#080c17dd;backdrop-filter:blur(15px);
 border-bottom:1px solid #27334d
}
.brand{display:flex;gap:10px;align-items:center}
.logo{
 width:44px;height:44px;border-radius:14px;
 display:grid;place-items:center;font-size:24px;
 background:linear-gradient(135deg,#ffe15a,#ff4d9d);
 box-shadow:0 0 25px #ffd84d66
}
h1{font-size:17px;margin:0}
small{color:#8995ab}
.demo{
 margin:10px 13px;padding:8px;text-align:center;
 border:1px solid #ffd84d44;border-radius:10px;
 color:#ffe58a;background:#ffd84d0c;font-size:11px
}
main{padding:0 14px}
.page{display:none}.page.active{display:block}
.hero{padding:18px 2px 12px}
.hero h2{margin:0 0 5px;font-size:25px}
.hero p{margin:0;color:#8995ab;font-size:13px}

.cards,.shopgrid{
 display:grid;grid-template-columns:repeat(2,1fr);gap:10px
}
.card,.item,.order{
 background:linear-gradient(145deg,#141d31,#0d1422);
 border:1px solid #28344c;border-radius:16px;padding:14px
}
.card h3,.item strong{font-size:14px}
.icon{font-size:31px}
.muted{color:#8995ab;font-size:11px}
.btn{
 width:100%;border:0;border-radius:11px;
 padding:11px;font-weight:bold;cursor:pointer;
 background:#ffd84d;color:#101010
}
.btn.dark{background:#202b40;color:#fff}
.btn.green{background:#43e6a0}
.btn.pink{background:#ff4d8d;color:white}
.row{display:flex;gap:8px}.row>*{flex:1}

/* EFFECT SHOP */
.effect-shop{
 position:relative;overflow:hidden;margin:5px 0 18px;
 padding:22px 16px;border-radius:20px;
 border:1px solid #55dcff66;
 background:
 radial-gradient(circle at 10% 20%,#ff4d9d55,transparent 30%),
 radial-gradient(circle at 90% 80%,#35d6ff55,transparent 35%),
 #111a2b;
 box-shadow:0 0 35px #35d6ff22
}
.effect-shop:before{
 content:"";position:absolute;width:180px;height:180px;
 border-radius:50%;border:2px solid #ffffff22;
 top:-100px;right:-70px;
 box-shadow:0 0 0 20px #ffffff08,0 0 0 40px #ffffff05
}
.effect-title{
 font-size:21px;font-weight:1000;
 background:linear-gradient(90deg,#ffd84d,#ff4d9d,#35d6ff);
 -webkit-background-clip:text;color:transparent
}
.effect-sub{font-size:11px;color:#aeb9cb;margin:5px 0 15px}
.spark{
 display:inline-block;animation:spark 1.4s infinite alternate
}
@keyframes spark{
 from{transform:scale(.8) rotate(-8deg);filter:brightness(1)}
 to{transform:scale(1.2) rotate(8deg);filter:brightness(2)}
}

/* WHEEL */
.wheelbox{text-align:center;padding:8px 0 25px}
.pointer{
 width:0;height:0;margin:auto;
 border-left:14px solid transparent;
 border-right:14px solid transparent;
 border-top:28px solid white;
 filter:drop-shadow(0 0 8px #fff);
 position:relative;z-index:4
}
.wheelwrap{
 width:min(82vw,330px);height:min(82vw,330px);
 margin:-3px auto 20px;position:relative
}
.wheel{
 width:100%;height:100%;border-radius:50%;
 border:9px solid #ffd84d;
 background:conic-gradient(
 #ff526d 0 45deg,#28c9f5 45deg 90deg,
 #9b6cff 90deg 135deg,#43e6a0 135deg 180deg,
 #ffb83d 180deg 225deg,#ff579c 225deg 270deg,
 #4e8cff 270deg 315deg,#ffd84d 315deg 360deg);
 box-shadow:0 0 0 4px #654b12,0 0 45px #ffd84d88;
 transition:transform 4.8s cubic-bezier(.12,.8,.15,1)
}
.wheel:after{
 content:"💎";position:absolute;
 width:78px;height:78px;left:50%;top:50%;
 transform:translate(-50%,-50%);
 display:grid;place-items:center;border-radius:50%;
 background:#080d19;border:5px solid white;font-size:34px;
 box-shadow:0 0 30px #35d6ff99
}
.labels{position:absolute;inset:0;font-size:11px;font-weight:bold}
.labels span{
 position:absolute;left:50%;top:50%;
 width:70px;margin-left:-35px;text-align:center
}
.l1{transform:translateY(-125px)}
.l2{transform:rotate(45deg) translateY(-125px)}
.l3{transform:rotate(90deg) translateY(-125px)}
.l4{transform:rotate(135deg) translateY(-125px)}
.l5{transform:rotate(180deg) translateY(-125px)}
.l6{transform:rotate(225deg) translateY(-125px)}
.l7{transform:rotate(270deg) translateY(-125px)}
.l8{transform:rotate(315deg) translateY(-125px)}

.result{
 display:none;margin-top:15px;padding:16px;
 border-radius:17px;text-align:center;
 background:#0d1727;border:1px solid #35d6ff66;
 box-shadow:0 0 35px #35d6ff22
}
.result.show{display:block}
.result h2{color:#ffd84d;margin:0 0 8px}

/* WITHDRAW */
.withdraw{
 margin-top:15px;padding:16px;
 background:#111a2a;border:1px solid #29364e;
 border-radius:17px
}
input{
 width:100%;padding:12px;margin:6px 0 9px;
 border-radius:10px;border:1px solid #29364e;
 background:#080e1b;color:white;outline:none
}
input:focus{border-color:#35d6ff}
.success{
 display:none;text-align:center;margin-top:12px;
 padding:15px;border-radius:15px;
 background:#0b3028;border:1px solid #43e6a0;
 box-shadow:0 0 30px #43e6a055
}
.success.show{display:block}
.success .check{
 font-size:45px;animation:pop .6s ease
}
@keyframes pop{
 0%{transform:scale(.2);opacity:0}
 70%{transform:scale(1.2)}
 100%{transform:scale(1);opacity:1}
}

/* ADMIN */
.adminbox{
 padding:16px;border-radius:17px;
 background:#111a2a;border:1px solid #29364e
}
.admin-panel{display:none}
.admin-panel.show{display:block}
.stat{
 display:flex;justify-content:space-between;
 padding:11px 0;border-bottom:1px solid #253149;
 font-size:13px
}

/* NAV */
.bottom{
 position:fixed;bottom:0;left:50%;
 transform:translateX(-50%);
 width:min(500px,100%);
 display:grid;grid-template-columns:repeat(5,1fr);
 padding:8px 4px calc(8px + env(safe-area-inset-bottom));
 background:#080c15f5;backdrop-filter:blur(15px);
 border-top:1px solid #29354c;z-index:30
}
.nav{
 border:0;background:none;color:#758197;font-size:10px
}
.nav div{font-size:20px;margin-bottom:3px}
.nav.active{color:#fff}

/* MODAL */
.modal{
 display:none;position:fixed;inset:0;background:#000b;
 z-index:60;align-items:flex-end
}
.modal.show{display:flex}
.sheet{
 width:min(500px,100%);margin:auto 0 0;
 padding:20px;background:#111a2a;
 border:1px solid #2d3950;border-radius:20px 20px 0 0
}
.sheet h2{color:#ffd84d}
.sheet p{color:#aeb9cb;font-size:13px}

/* CONFETTI */
#confetti{
 position:fixed;inset:0;width:100%;height:100%;
 pointer-events:none;z-index:100
}
</style>
</head>

<body>

<canvas id="confetti"></canvas>

<div class="app">

<header>
 <div class="brand">
  <div class="logo">💎</div>
  <div>
   <h1>GIA MINU • FF SHOP</h1>
   <small>Effect Rewards Center</small>
  </div>
 </div>
</header>

<div class="demo">
 ⚠️ DEMO — không có giao dịch hoặc kim cương thật
</div>

<main>

<!-- HOME -->
<section id="home" class="page active">

<div class="effect-shop">
 <div class="effect-title">
  ✨ GIA MINH • EFFECT SHOP
 </div>
 <div class="effect-sub">
  Bộ sưu tập hiệu ứng • Skin • Emote • Quà tặng
 </div>
 <button class="btn pink" onclick="openPage('shop')">
  KHÁM PHÁ EFFECT SHOP ✨
 </button>
</div>

<div class="hero">
 <h2>Chào mừng 👋</h2>
 <p>Khám phá vòng quay phần thưởng demo.</p>
</div>

<div class="cards">

<div class="card">
 <div class="icon">🎡</div>
 <h3>Vòng quay kim cương</h3>
 <p class="muted">Quay phần thưởng demo.</p>
 <button class="btn" onclick="openPage('wheel')">
  QUAY NGAY
 </button>
</div>

<div class="card">
 <div class="icon">💎</div>
 <h3>Rút kim cương</h3>
 <p class="muted">Mô phỏng nhập ID.</p>
 <button class="btn dark" onclick="openPage('withdraw')">
  RÚT DEMO
 </button>
</div>

</div>

</section>


<!-- WHEEL -->
<section id="wheel" class="page">

<div class="hero">
 <h2>🎡 Vòng quay kim cương</h2>
 <p>Hiệu ứng quay và phần thưởng chỉ mang tính mô phỏng.</p>
</div>

<div class="wheelbox">

<div class="pointer"></div>

<div class="wheelwrap">
 <div id="wheel" class="wheel"></div>

 <div class="labels">
  <span class="l1">💎50</span>
  <span class="l2">💎100</span>
  <span class="l3">🎁Rương</span>
  <span class="l4">💎200</span>
  <span class="l5">🕺Emote</span>
  <span class="l6">💎500</span>
  <span class="l7">🎟️Vé</span>
  <span class="l8">💎999</span>
 </div>
</div>

<button id="spin" class="btn" onclick="spin()">
 🎡 QUAY VÒNG
</button>

<div id="result" class="result">
 <h2>🎉 CHÚC MỪNG!</h2>
 <p id="prize"></p>
 <p>Thông tin: <b>••••••••</b></p>

 <div class="row">
  <button class="btn green" onclick="claim()">
   NHẬN NGAY
  </button>
  <button class="btn dark" onclick="later()">
   ĐỢI MỘT CHÚT
  </button>
 </div>
</div>

</div>

</section>


<!-- WITHDRAW -->
<section id="withdraw" class="page">

<div class="hero">
 <h2>💎 Rút kim cương DEMO</h2>
 <p>Chỉ mô phỏng giao diện, không chuyển kim cương thật.</p>
</div>

<div class="withdraw">

<label>ID người chơi</label>

<input id="playerID"
       inputmode="numeric"
       placeholder="Nhập ID demo...">

<label>Số kim cương</label>

<input id="diamondAmount"
       inputmode="numeric"
       placeholder="Ví dụ: 500">

<button class="btn"
        onclick="withdraw()">
 💎 RÚT KIM CƯƠNG
</button>

<div id="success"
     class="success">

 <div class="check">✓</div>

 <h3>RÚT KIM CƯƠNG THÀNH CÔNG!</h3>

 <p id="successText"></p>

 <small>
  Đây là kết quả DEMO, không có giao dịch thật.
 </small>

</div>

</div>

</section>


<!-- SHOP -->
<section id="shop" class="page">

<div class="effect-shop">

 <div class="effect-title">
  ✨ GIA MINH • EFFECT SHOP
 </div>

 <div class="effect-sub">
  Hiệu ứng đặc biệt dành cho giao diện demo
 </div>

 <button class="btn pink"
         onclick="effectDemo()">
  ✨ XEM HIỆU ỨNG
 </button>

</div>

<div class="shopgrid">

<div class="item">
 <div class="icon">🔫</div>
 <strong>Skin súng</strong>
 <p class="price">DEMO</p>
 <button class="btn" onclick="itemDemo()">XEM</button>
</div>

<div class="item">
 <div class="icon">👕</div>
 <strong>Trang phục</strong>
 <p class="price">DEMO</p>
 <button class="btn" onclick="itemDemo()">XEM</button>
</div>

<div class="item">
 <div class="icon">🕺</div>
 <strong>Emote</strong>
 <p class="price">DEMO</p>
 <button class="btn" onclick="itemDemo()">XEM</button>
</div>

<div class="item">
 <div class="icon">🎒</div>
 <strong>Ba lô</strong>
 <p class="price">DEMO</p>
 <button class="btn" onclick="itemDemo()">XEM</button>
</div>

</div>

</section>


<!-- ORDERS -->
<section id="orders" class="page">

<div class="hero">
 <h2>📦 Đơn hàng</h2>
 <p>Lịch sử nhận thưởng demo.</p>
</div>

<div id="ordersList">

<div class="order">
 <b>Chưa có phần thưởng</b>
 <small>Lịch sử sẽ xuất hiện ở đây.</small>
</div>

</div>

</section>


<!-- ACCOUNT -->
<section id="account" class="page">

<div class="hero">
 <h2>👤 Tài khoản</h2>
</div>

<div class="card">
 <div class="icon">💎</div>
 <h3>Gia Minu</h3>
 <p class="muted">Tài khoản demo</p>
 <hr style="border-color:#29354c">
 <p>Kim cương demo: <b style="color:#ffd84d">9,999</b></p>
 <p>Phần thưởng đã nhận: <b id="claimed">0</b></p>
</div>

<div class="hero">
 <h2>👑 Admin</h2>
</div>

<div class="adminbox">

<p class="muted">
Đăng nhập khu vực quản trị DEMO.
</p>

<input id="adminName"
       placeholder="Tên Admin">

<input id="adminPass"
       type="password"
       placeholder="Mật khẩu demo">

<button class="btn"
        onclick="adminLogin()">
 👑 ĐĂNG NHẬP ADMIN
</button>

<div id="adminPanel"
     class="admin-panel">

 <br>

 <div class="stat">
  <span>Người dùng</span>
  <b>1</b>
 </div>

 <div class="stat">
  <span>Vòng quay</span>
  <b>Đang hoạt động</b>
 </div>

 <div class="stat">
  <span>Phần thưởng</span>
  <b id="adminClaimed">0</b>
 </div>

 <br>

 <button class="btn dark"
         onclick="adminLogout()">
  ĐĂNG XUẤT
 </button>

</div>

</div>

</section>

</main>


<!-- NAV -->
<nav class="bottom">

<button class="nav active"
 onclick="openPage('home')">
 <div>⌂</div>
 Trang chủ
</button>

<button class="nav"
 onclick="openPage('wheel')">
 <div>🎡</div>
 Vòng quay
</button>

<button class="nav"
 onclick="openPage('shop')">
 <div>✨</div>
 Shop
</button>

<button class="nav"
 onclick="openPage('orders')">
 <div>📦</div>
 Đơn hàng
</button>

<button class="nav"
 onclick="openPage('account')">
 <div>👤</div>
 Tài khoản
</button>

</nav>

</div>


<!-- MODAL -->
<div id="modal" class="modal">

<div class="sheet">

<h2 id="modalTitle">
 🎉 CHÚC MỪNG!
</h2>

<p id="modalText"></p>

<button class="btn dark"
 onclick="closeModal()">
 Đóng
</button>

</div>

</div>


<script>

let spinning=false;
let rotation=0;
let selectedPrize="";
let claimed=0;

const prizes=[
 "💎 50 Kim cương ",
 "💎 100 Kim cương ",
 "🎁 Rương ",
 "💎 200 Kim cương ",
 "🕺 Emote ",
 "💎 500 Kim cương ",
 "🎟️ Vé ",
 "💎 999 Kim cương "
];


function openPage(id){

 document
 .querySelectorAll(".page")
 .forEach(x=>x.classList.remove("active"));

 document
 .getElementById(id)
 .classList.add("active");

 document
 .querySelectorAll(".nav")
 .forEach(x=>x.classList.remove("active"));

 const map={
  home:0,
  wheel:1,
  shop:2,
  orders:3,
  account:4
 };

 if(map[id]!==undefined)
 document
 .querySelectorAll(".nav")[map[id]]
 .classList.add("active");

 window.scrollTo(0,0);
}


function spin(){

 if(spinning)return;

 spinning=true;

 document.getElementById("spin").disabled=true;

 document
 .getElementById("result")
 .classList.remove("show");

 const index=
 Math.floor(Math.random()*prizes.length);

 selectedPrize=prizes[index];

 const extra=
 360*7+(360-(index*45+22.5));

 rotation+=extra;

 document
 .getElementById("wheel")
 .style.transform=
 `rotate(${rotation}deg)`;

 setTimeout(()=>{

  document
  .getElementById("prize")
  .textContent=selectedPrize;

  document
  .getElementById("result")
  .classList.add("show");

  fireworks();

  spinning=false;

  document.getElementById("spin").disabled=false;

 },4900);

}


function claim(){

 claimed++;

 document
 .getElementById("claimed")
 .textContent=claimed;

 document
 .getElementById("adminClaimed")
 .textContent=claimed;

 const order=document.createElement("div");

 order.className="order";

 order.innerHTML=
 `<b>${selectedPrize}</b>
 <small>Vừa nhận • DEMO</small>`;

 document
 .getElementById("ordersList")
 .prepend(order);

 showModal(
 "🎉 CHÚC MỪNG!",
 "Bạn đã nhận "+selectedPrize+
 " — đây chỉ là phần thưởng demo."
 );

}


function later(){

 showModal(
 "⏳ Đợi một chút",
 "Phần thưởng đang được giữ trong giao diện demo."
 );

}


function withdraw(){

 const id=
 document.getElementById("playerID").value.trim();

 const amount=
 document.getElementById("diamondAmount").value.trim();

 if(!/^[0-9]{5,15}$/.test(id)){

  showModal(
   "⚠️ ID chưa hợp lệ",
   "Hãy nhập một ID demo gồm 5–15 chữ số."
  );

  return;
 }

 if(!/^[0-9]+$/.test(amount) || Number(amount)<=0){

  showModal(
   "⚠️ Số lượng chưa hợp lệ",
   "Hãy nhập số kim cương demo hợp lệ."
  );

  return;
 }

 document
 .getElementById("successText")
 .textContent=
 `ID: ${id} • ${Number(amount).toLocaleString()} 💎`;

 document
 .getElementById("success")
 .classList.add("show");

 fireworks();

}


function adminLogin(){

 const name=
 document.getElementById("adminName").value;

 const pass=
 document.getElementById("adminPass").value;

 /*
   Tài khoản chỉ dành cho DEMO cục bộ.
   Không dùng mật khẩu thật.
 */
 if(name==="Admin" && pass==="999k"){

  document
  .getElementById("adminPanel")
  .classList.add("show");

  showModal(
   "👑 Admin Demo",
   "Đăng nhập khu quản trị demo thành công."
  );

 }else{

  showModal(
   "❌ Không thể đăng nhập",
   "Thông tin Admin demo không chính xác."
  );

 }

}


function adminLogout(){

 document
 .getElementById("adminPanel")
 .classList.remove("show");

 document
 .getElementById("adminPass")
 .value="";

}


function itemDemo(){

 showModal(
  "✨ Vật phẩm ",
  "Đây là vật phẩm trong Gia Minh Effect Shop."
 );

}


function effectDemo(){

 fireworks();

 showModal(
  "✨ GIA MINH EFFECT",
  "Hiệu ứng ánh sáng đã được kích hoạt!"
 );

}


function showModal(title,text){

 document
 .getElementById("modalTitle")
 .textContent=title;

 document
 .getElementById("modalText")
 .textContent=text;

 document
 .getElementById("modal")
 .classList.add("show");

}


function closeModal(){

 document
 .getElementById("modal")
 .classList.remove("show");

}


/* HIỆU ỨNG PHÁO GIẤY + ÁNH SÁNG */

function fireworks(){

 const canvas=
 document.getElementById("confetti");

 const ctx=
 canvas.getContext("2d");

 canvas.width=innerWidth;
 canvas.height=innerHeight;

 const colors=[
 "#ffd84d",
 "#35d6ff",
 "#ff4d9d",
 "#43e6a0",
 "#ffffff"
 ];

 let particles=[];

 for(let i=0;i<220;i++){

  const angle=
  Math.random()*Math.PI*2;

  const speed=
  Math.random()*10+4;

  particles.push({

   x:innerWidth/2,
   y:innerHeight*.38,

   vx:Math.cos(angle)*speed,
   vy:Math.sin(angle)*speed,

   gravity:.22,

   size:Math.random()*7+3,

   life:1,

   color:
   colors[
    Math.floor(Math.random()*colors.length)
   ],

   rot:Math.random()*6

  });

 }

 let start=performance.now();

 function draw(t){

  ctx.clearRect(
   0,0,
   canvas.width,
   canvas.height
  );

  particles.forEach(p=>{

   p.x+=p.vx;
   p.vy+=p.gravity;
   p.y+=p.vy;
   p.rot+=.12;
   p.life-=.007;

   ctx.save();

   ctx.globalAlpha=
   Math.max(0,p.life);

   ctx.translate(p.x,p.y);

   ctx.rotate(p.rot);

   ctx.fillStyle=p.color;

   ctx.shadowBlur=12;
   ctx.shadowColor=p.color;

   ctx.fillRect(
    -p.size/2,
    -p.size/2,
    p.size,
    p.size*1.8
   );

   ctx.restore();

  });

  if(t-start<3200){

   requestAnimationFrame(draw);

  }else{

   ctx.clearRect(
    0,0,
    canvas.width,
    canvas.height
   );

  }

 }

 requestAnimationFrame(draw);

}

</script>

</body>
</html>

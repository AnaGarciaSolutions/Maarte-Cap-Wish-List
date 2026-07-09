<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
<title>MAARTE Caps — Wish List</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,500;0,600;1,400&family=Barlow+Condensed:wght@500;600;700&family=Barlow:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  :root{
    --espresso:#2C1810; --espresso-mid:#3D2318; --espresso-light:#5C3527;
    --peony:#E8A0A8; --peony-deep:#D98996; --peony-light:#F2C4C9; --cream:#FAF6F0; --warm-white:#FFFDF9;
    --text-dark:#1A0F0A; --text-mid:#4A2E22; --border:rgba(44,24,16,0.16);
  }
  *{margin:0;padding:0;box-sizing:border-box;}
  body{background:var(--cream);font-family:'Barlow',sans-serif;color:var(--text-dark);font-size:18px;line-height:1.5;-webkit-text-size-adjust:100%;}

  .header{background:var(--espresso);padding:34px 22px 28px;text-align:center;position:relative;}
  .header::after{content:'';position:absolute;bottom:0;left:0;right:0;height:4px;background:linear-gradient(90deg,var(--peony),var(--espresso-light),var(--peony));}
  .brand{font-family:'Cormorant Garamond',serif;font-size:46px;font-weight:600;letter-spacing:0.16em;color:var(--warm-white);line-height:1;}
  .brand-rule{width:54px;height:2px;background:var(--peony);margin:15px auto 17px;opacity:0.85;}
  .h-label{font-family:'Barlow Condensed',sans-serif;font-size:15px;font-weight:600;letter-spacing:0.18em;text-transform:uppercase;color:var(--peony-light);margin-bottom:10px;}
  .h-title{font-family:'Cormorant Garamond',serif;font-size:42px;font-weight:500;color:var(--warm-white);line-height:1.05;letter-spacing:0.02em;}
  .h-title span{font-style:italic;color:var(--peony-light);}
  .h-sub{margin-top:12px;font-size:17px;color:rgba(250,246,240,0.75);}

  .intro{background:var(--warm-white);border-bottom:1px solid var(--border);padding:18px 22px;text-align:center;font-size:17px;color:var(--text-mid);line-height:1.55;}

  .wrap{max-width:560px;margin:0 auto;padding:26px 20px 120px;}

  .sec-title{font-family:'Barlow Condensed',sans-serif;font-size:22px;font-weight:700;letter-spacing:0.04em;color:var(--espresso);text-transform:uppercase;margin:30px 0 16px;display:flex;align-items:center;gap:12px;}
  .sec-title .num{background:var(--espresso);color:var(--peony-light);width:34px;height:34px;border-radius:50%;display:inline-flex;align-items:center;justify-content:center;font-size:18px;flex-shrink:0;}
  .sec-title:first-of-type{margin-top:8px;}

  .field{margin-bottom:18px;}
  .row2{display:flex;gap:13px;}
  .row2 .field{flex:1;}
  label.fl{display:block;font-size:16px;font-weight:600;color:var(--espresso-light);margin-bottom:7px;}
  input,select{width:100%;background:var(--warm-white);border:1.5px solid var(--border);border-radius:5px;padding:15px;font-family:'Barlow',sans-serif;font-size:18px;color:var(--text-dark);}
  input::placeholder{color:rgba(74,46,34,0.45);}
  input:focus,select:focus{outline:none;border-color:var(--peony-deep);box-shadow:0 0 0 3px rgba(232,160,168,0.25);}

  .prod{background:var(--warm-white);border:1.5px solid var(--border);border-radius:6px;padding:18px;margin-bottom:14px;display:flex;justify-content:space-between;align-items:center;gap:14px;}
  .prod-info{flex:1;}
  .prod-name{font-size:20px;font-weight:600;color:var(--espresso);}
  .prod-desc{font-size:16px;color:var(--text-mid);margin-top:4px;}
  .stepper{display:flex;gap:0;}
  .sbtn{width:52px;height:52px;background:var(--cream);border:1.5px solid var(--border);color:var(--espresso);font-size:28px;cursor:pointer;border-radius:6px;display:flex;align-items:center;justify-content:center;}
  .qv{width:54px;text-align:center;font-family:'Barlow Condensed',sans-serif;font-size:26px;font-weight:700;color:var(--espresso);}

  .dnote{font-size:16px;color:var(--text-mid);margin-bottom:14px;background:rgba(44,24,16,0.04);border-radius:5px;padding:12px 14px;}
  .pills{display:flex;flex-direction:column;gap:11px;}
  .pill{background:var(--warm-white);border:1.5px solid var(--border);border-radius:6px;padding:18px;cursor:pointer;display:flex;justify-content:space-between;align-items:center;}
  .pill.active{border-color:var(--peony-deep);background:rgba(232,160,168,0.1);}
  .p-t{font-size:18px;font-weight:600;color:var(--espresso);}
  .p-s{font-size:16px;color:var(--text-mid);margin-top:3px;}
  .p-mark{width:26px;height:26px;border-radius:50%;border:2px solid var(--border);}
  .pill.active .p-mark{border-color:var(--peony-deep);}

  .summary{background:var(--warm-white);border:1.5px solid var(--border);border-radius:6px;overflow:hidden;margin-top:26px;}
  .summary-head{background:var(--espresso);padding:14px 18px;color:var(--peony-light);font-family:'Barlow Condensed',sans-serif;font-size:16px;font-weight:700;text-transform:uppercase;}
  .summary-body{padding:18px;}
  .sum-row{display:flex;justify-content:space-between;padding:6px 0;font-size:17px;}
  .sum-row.total{border-top:2px solid var(--border);margin-top:10px;padding-top:14px;}
  .sum-row.total .lbl{font-family:'Barlow Condensed',sans-serif;font-size:20px;font-weight:700;text-transform:uppercase;color:var(--espresso);}
  .sum-row.total .amt{font-family:'Cormorant Garamond',serif;font-size:34px;font-weight:600;font-style:italic;color:var(--espresso);}

  .success{display:none;background:rgba(139,195,74,0.15);border:1px solid rgba(139,195,74,0.5);color:#558B2F;padding:16px;border-radius:6px;margin-bottom:20px;font-size:16px;font-weight:600;text-align:center;}
  .success.show{display:block;}

  .footer{text-align:center;padding:8px 20px;font-family:'Cormorant Garamond',serif;font-size:18px;font-style:italic;color:var(--espresso-light);}

  .bar{position:fixed;bottom:0;left:0;right:0;background:var(--espresso);border-top:3px solid var(--peony);padding:15px 20px calc(15px + env(safe-area-inset-bottom));}
  .bar-btn{width:100%;background:var(--peony);color:var(--espresso);border:none;border-radius:6px;padding:18px;font-family:'Barlow Condensed',sans-serif;font-size:18px;font-weight:700;text-transform:uppercase;cursor:pointer;}
  .bar-btn:disabled{opacity:0.4;}

  @media (max-width:430px){
    .h-title{font-size:36px;} .row2{flex-direction:column;}
  }
</style>
</head>
<body>

<div class="header">
  <div class="brand">MAARTE</div>
  <div class="brand-rule"></div>
  <div class="h-label">Caps Wish List · Vintage brown wash</div>
  <div class="h-title">Join the <span>wish list</span></div>
  <div class="h-sub">One colorway only. Fill this in to reserve your slot.</div>
</div>

<div class="intro">Choose your quantity below. Your total updates as you go.</div>

<div class="wrap">
  <div class="success" id="success">✓ Thank you! Your wish list entry saved.</div>

  <div class="sec-title"><span class="num">1</span> Your details</div>
  <div class="row2">
    <div class="field"><label class="fl">First name</label><input type="text" id="fFirst" placeholder="Juana"></div>
    <div class="field"><label class="fl">Surname</label><input type="text" id="fLast" placeholder="dela Cruz"></div>
  </div>
  <div class="field"><label class="fl">Mobile number</label><input type="tel" id="fMobile" placeholder="0917 123 4567"></div>
  <div class="field"><label class="fl">Instagram username</label><input type="text" id="fInsta" placeholder="@yourhandle"></div>

  <div class="sec-title"><span class="num">2</span> Delivery address</div>
  <div class="field"><label class="fl">House number / unit</label><input type="text" id="aHouse" placeholder="12B"></div>
  <div class="field"><label class="fl">Street</label><input type="text" id="aStreet" placeholder="Mabini Street"></div>
  <div class="field"><label class="fl">Barangay</label><input type="text" id="aBrgy" placeholder="Barangay San Antonio"></div>
  <div class="field"><label class="fl">City</label><input type="text" id="aCity" placeholder="Pasig City"></div>
  <div class="field"><label class="fl">Province</label><select id="aProv" onchange="updateUI()"><option value="">Select province</option></select></div>
  <div class="field"><label class="fl">ZIP code</label><input type="tel" id="aZip" placeholder="1600"></div>

  <div class="sec-title"><span class="num">3</span> How many caps?</div>
  <div class="prod">
    <div class="prod-info">
      <div class="prod-name">🧢 MAARTE Cap</div>
      <div class="prod-desc">Vintage brown wash, light pink embroidery, free size 52–58cm</div>
    </div>
    <div class="stepper">
      <button class="sbtn" onclick="bump(-1)">–</button>
      <span class="qv" id="capQty">0</span>
      <button class="sbtn" onclick="bump(1)">+</button>
    </div>
  </div>

  <div class="sec-title"><span class="num">4</span> Delivery method</div>
  <div class="dnote">Shipping fee calculated from your province selection.</div>
  <div class="pills" id="pills"></div>

  <div class="summary">
    <div class="summary-head">Order Summary</div>
    <div class="summary-body" id="summaryBody"></div>
  </div>
</div>

<div class="footer">For all of the ways you are maarte.</div>

<div class="bar">
  <button class="bar-btn" id="barBtn" onclick="submit()" disabled>Submit Wish List</button>
</div>

<script>
const CAP_PRICE=799, COURIER_MM=300, COURIER_PROV=350;
const PROVINCES={
  "Metro Manila (NCR)":["Metro Manila"],
  "Luzon":["Abra","Albay","Apayao","Aurora","Bataan","Batanes","Batangas","Benguet","Bulacan","Cagayan","Camarines Norte","Camarines Sur","Catanduanes","Cavite","Ifugao","Ilocos Norte","Ilocos Sur","Isabela","Kalinga","La Union","Laguna","Marinduque","Masbate","Mountain Province","Nueva Ecija","Nueva Vizcaya","Occidental Mindoro","Oriental Mindoro","Palawan","Pampanga","Pangasinan","Quezon","Quirino","Rizal","Romblon","Sorsogon","Tarlac","Zambales"],
  "Visayas":["Aklan","Antique","Biliran","Bohol","Capiz","Cebu","Eastern Samar","Guimaras","Iloilo","Leyte","Negros Occidental","Negros Oriental","Northern Samar","Samar","Siquijor","Southern Leyte"],
  "Mindanao":["Agusan del Norte","Agusan del Sur","Basilan","Bukidnon","Camiguin","Cotabato","Davao de Oro","Davao del Norte","Davao del Sur","Davao Occidental","Davao Oriental","Dinagat Islands","Lanao del Norte","Lanao del Sur","Maguindanao del Norte","Maguindanao del Sur","Misamis Occidental","Misamis Oriental","Sarangani","South Cotabato","Sultan Kudarat","Sulu","Surigao del Norte","Surigao del Sur","Tawi-Tawi","Zamboanga del Norte","Zamboanga del Sur","Zamboanga Sibugay"]
};
const DELIVERY=[{id:"courier",title:"Courier delivery",pickup:false},{id:"pickup",title:"Pick-up in Kamias, QC",sub:"No shipping fee",pickup:true}];

let capQty=0, delivery="courier";

(function(){
  const sel=document.getElementById("aProv");
  Object.keys(PROVINCES).forEach(g=>{
    const og=document.createElement("optgroup");
    og.label=g;
    PROVINCES[g].forEach(p=>{const o=document.createElement("option");o.value=p;o.textContent=p;og.appendChild(o)});
    sel.appendChild(og);
  });
  document.getElementById("pills").innerHTML=DELIVERY.map(d=>`<button class="pill ${d.id===delivery?'active':''}" onclick="setDelivery('${d.id}')"><div><div class="p-t">${d.title}</div><div class="p-s">${d.sub||''}</div></div><div class="p-mark"></div></button>`).join("");
})();

function bump(n){capQty=Math.max(0,capQty+n);document.getElementById("capQty").textContent=capQty;updateUI();}
function setDelivery(id){delivery=id;DELIVERY.forEach(d=>document.querySelector(`[onclick="setDelivery('${d.id}')"]`).classList.toggle("active",d.id===id));updateUI();}
function val(id){return document.getElementById(id).value.trim();}
function peso(x){return"₱"+x.toLocaleString();}

function updateUI(){
  const capPrice=capQty>=10?CAP_PRICE*0.9:CAP_PRICE;
  const subtotal=capQty*capPrice;
  const prov=val("aProv"), isMetro=prov==="Metro Manila", rate=isMetro?COURIER_MM:COURIER_PROV;
  const boxes=capQty>0?Math.ceil(capQty/5):0, shipping=DELIVERY.find(d=>d.id===delivery).pickup?0:boxes*rate;
  const total=subtotal+shipping;

  const body=document.getElementById("summaryBody");
  if(capQty===0){body.innerHTML="<div style='text-align:center;color:#4A2E22;'>Add caps above to see total.</div>";
  } else {
    let html=`<div class="sum-row"><span>🧢 MAARTE Cap · ${capQty} × ${peso(capPrice)}</span><span>${peso(subtotal)}</span></div>`;
    if(capQty>=10){const disc=CAP_PRICE*0.1*capQty;html+=`<div class="sum-row" style="color:#D98996;"><span>✨ 10% off</span><span>−${peso(disc)}</span></div>`;}
    html+=DELIVERY.find(d=>d.id===delivery).pickup?`<div class="sum-row"><span>Pick-up Kamias, QC</span><span>No fee</span></div>`:`<div class="sum-row"><span>Courier shipping</span><span>${peso(shipping)}</span></div>`;
    html+=`<div class="sum-row total"><span class="lbl">Total</span><span class="amt">${peso(total)}</span></div>`;
    body.innerHTML=html;
  }
  document.getElementById("barBtn").disabled=capQty===0;
}

function submit(){
  const name=[val("fFirst"),val("fLast")].filter(Boolean).join(" ");
  if(!name||!val("fInsta")&&!val("fMobile")||capQty===0||!val("aProv")){alert("Fill all required fields.");return;}
  
  const data={
    id:Date.now().toString(),
    date:new Date().toLocaleString("en-PH",{dateStyle:"medium",timeStyle:"short"}),
    name,contact:val("fInsta")||val("fMobile"),address:[val("aHouse"),val("aStreet"),val("aBrgy"),val("aCity")].filter(Boolean).join(", "),
    province:val("aProv"),qty:capQty,delivery:DELIVERY.find(d=>d.id===delivery).title,
    capPrice:capQty>=10?CAP_PRICE*0.9:CAP_PRICE,total:(capQty*(capQty>=10?CAP_PRICE*0.9:CAP_PRICE))+(DELIVERY.find(d=>d.id===delivery).pickup?0:Math.ceil(capQty/5)*(val("aProv")==="Metro Manila"?COURIER_MM:COURIER_PROV))
  };
  
  let entries=JSON.parse(localStorage.getItem("maarte_wishlist")||"[]");
  entries.push(data);
  localStorage.setItem("maarte_wishlist",JSON.stringify(entries));
  
  document.getElementById("success").classList.add("show");
  setTimeout(()=>{["fFirst","fLast","fMobile","fInsta","aHouse","aStreet","aBrgy","aCity","aProv","aZip"].forEach(id=>document.getElementById(id).value="");capQty=0;document.getElementById("capQty").textContent="0";updateUI();document.getElementById("success").classList.remove("show");},3000);
}

updateUI();
</script>
</body>
</html>

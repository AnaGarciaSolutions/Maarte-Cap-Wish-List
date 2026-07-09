<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MAARTE Caps Tracker</title>
<style>
  body{font-family:Arial,sans-serif;background:#f5f5f5;margin:0;padding:20px;}
  .container{max-width:1200px;margin:0 auto;}
  h1{background:#2C1810;color:white;padding:20px;text-align:center;margin:0;}
  .toolbar{margin:20px 0;display:flex;gap:10px;flex-wrap:wrap;}
  input{padding:10px;border:1px solid #ccc;border-radius:4px;flex:1;min-width:250px;}
  button{padding:10px 20px;background:#2C1810;color:white;border:none;border-radius:4px;cursor:pointer;}
  button:hover{background:#1a0f0a;}
  table{width:100%;border-collapse:collapse;background:white;box-shadow:0 2px 4px rgba(0,0,0,0.1);}
  th{background:#2C1810;color:white;padding:12px;text-align:left;font-weight:bold;}
  td{padding:12px;border-bottom:1px solid #ddd;}
  tr:hover{background:#f9f9f9;}
  .delete-btn{background:#c0392b;color:white;padding:6px 12px;border:none;border-radius:3px;cursor:pointer;font-size:12px;}
  .delete-btn:hover{background:#a93226;}
  .empty{text-align:center;padding:40px;color:#666;}
</style>
</head>
<body>

<div class="container">
  <h1>MAARTE Caps Wish List Tracker</h1>
  
  <div class="toolbar">
    <input type="text" id="search" placeholder="Search name, contact, address..." oninput="filter()">
    <button onclick="refresh()">Refresh</button>
    <button onclick="download()">Download CSV</button>
  </div>
  
  <table>
    <thead>
      <tr>
        <th>Date</th>
        <th>Name</th>
        <th>Contact</th>
        <th>Address</th>
        <th>Province</th>
        <th>Qty</th>
        <th>Delivery</th>
        <th>Cap Price</th>
        <th>Total</th>
        <th>Action</th>
      </tr>
    </thead>
    <tbody id="tbody"></tbody>
  </table>
  <div id="empty" class="empty" style="display:none;">No entries yet.</div>
</div>

<script>
let allData = [];

function load(){
  allData = JSON.parse(localStorage.getItem("maarte_wishlist") || "[]");
  filter();
}

function filter(){
  const search = (document.getElementById("search").value || "").toLowerCase();
  const filtered = allData.filter(e => (e.name + e.contact + e.address).toLowerCase().includes(search));
  
  const tbody = document.getElementById("tbody");
  if(filtered.length === 0){
    tbody.innerHTML = "";
    document.getElementById("empty").style.display = "block";
  } else {
    document.getElementById("empty").style.display = "none";
    tbody.innerHTML = filtered.map((e,i) => `
      <tr>
        <td>${e.date}</td>
        <td>${e.name}</td>
        <td>${e.contact}</td>
        <td>${e.address}</td>
        <td>${e.province}</td>
        <td>${e.qty}</td>
        <td>${e.delivery}</td>
        <td>₱${e.capPrice.toLocaleString()}</td>
        <td><strong>₱${e.total.toLocaleString()}</strong></td>
        <td><button class="delete-btn" onclick="deleteEntry('${e.id}')">Delete</button></td>
      </tr>
    `).join("");
  }
}

function deleteEntry(id){
  if(!confirm("Delete this entry?")) return;
  allData = allData.filter(e => e.id !== id);
  localStorage.setItem("maarte_wishlist", JSON.stringify(allData));
  load();
}

function refresh(){
  load();
}

function download(){
  if(allData.length === 0){
    alert("No data to download.");
    return;
  }
  const headers = ["Date","Name","Contact","Address","Province","Qty","Delivery","Cap Price","Total"];
  const rows = allData.map(e => [e.date,e.name,e.contact,e.address,e.province,e.qty,e.delivery,e.capPrice,e.total]);
  let csv = headers.join(",") + "\n";
  rows.forEach(r => csv += r.map(v => `"${String(v).replace(/"/g,'""')}"`).join(",") + "\n");
  const blob = new Blob([csv], {type:"text/csv"});
  const url = URL.createObjectURL(blob);
  const a = document.createElement("a");
  a.href = url;
  a.download = `MAARTE_Tracker_${new Date().toISOString().slice(0,10)}.csv`;
  a.click();
  URL.revokeObjectURL(url);
}

load();
</script>
</body>
</html>

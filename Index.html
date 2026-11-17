<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Mobile Card Studio (QR + Web NFC)</title>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
  <style>
    body {
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
      background: #0f172a;
      color: #f8fafc;
      padding: 16px;
      margin: 0;
    }
    .box {
      max-width: 420px;
      margin: 0 auto 20px;
      background: #1e293b;
      padding: 18px;
      border-radius: 16px;
      border: 1px solid #334155;
    }
    h2 { font-size: 18px; margin: 0 0 12px; color: #f59e0b; }
    label { font-size: 12px; color: #94a3b8; display: block; margin-bottom: 4px; }
    input, select {
      width: 100%;
      padding: 12px;
      margin-bottom: 12px;
      border-radius: 10px;
      border: 1px solid #475569;
      background: #0f172a;
      color: #fff;
      font-size: 14px;
      box-sizing: border-box;
    }
    button {
      width: 100%;
      padding: 14px;
      border: none;
      border-radius: 12px;
      font-size: 15px;
      font-weight: 700;
      cursor: pointer;
      margin-bottom: 10px;
    }
    .btn-qr { background: #f59e0b; color: #0f172a; }
    .btn-nfc { background: #10b981; color: #ffffff; }
    .btn-print { background: #3b82f6; color: #ffffff; }
    #status {
      font-size: 13px;
      padding: 10px;
      border-radius: 8px;
      background: rgba(255,255,255,0.05);
      margin-top: 8px;
      word-break: break-all;
    }

    /* Printable 4.2cm x 4.2cm Sticker Preview */
    .sticker-wrap {
      background: #ffffff;
      color: #000000;
      width: 160px;
      height: 175px;
      margin: 16px auto;
      padding: 10px;
      border-radius: 10px;
      text-align: center;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: space-between;
      border: 2px dashed #94a3b8;
    }
    .st-title { font-size: 11px; font-weight: 800; text-transform: uppercase; line-height: 1.1; }
    .st-sub { font-size: 9px; font-weight: 700; color: #333; }
    #qrcode img { margin: 0 auto; }

    @media print {
      body { background: #fff; }
      .no-print { display: none !important; }
      .sticker-wrap { border: 1px solid #ccc; margin: 10px; page-break-inside: avoid; }
    }
  </style>
</head>
<body>

  <div class="box no-print">
    <h2>⚡ 1. Build Link & QR Sticker</h2>
    <label>Shop Name</label>
    <input type="text" id="shopName" value="Apex Fitness Studio" oninput="updateAll()">

    <label>Category</label>
    <select id="shopCat" onchange="updateAll()">
      <option value="gym">Gym / Fitness</option>
      <option value="salon">Salon / Makeover</option>
      <option value="cafe">Cafe / Restaurant</option>
      <option value="clinic">Clinic / Doctor</option>
      <option value="general">General Store</option>
    </select>

    <label>Direct Google Review URL (Optional override)</label>
    <input type="text" id="gLink" placeholder="https://g.page/r/..." oninput="updateAll()">

    <button class="btn-qr" onclick="updateAll()">🔄 Generate QR Sticker</button>
    <button class="btn-nfc" onclick="writeViaWebNFC()">📲 Write to NFC Card (Chrome Android - No App!)</button>
    <button class="btn-print" onclick="window.print()">🖨️ Save as PDF / Print Sticker</button>

    <div id="status">Ready. Target URL will appear here.</div>
  </div>

  <!-- Exact 4.2cm x 4.5cm Back-of-Card Sticker -->
  <div class="sticker-wrap" id="stickerCard">
    <div class="st-title" id="stName">APEX FITNESS STUDIO</div>
    <div id="qrcode"></div>
    <div class="st-sub">📱 SCAN CAMERA TO REVIEW</div>
  </div>

  <script>
    let finalUrl = "";
    const qrContainer = document.getElementById("qrcode");
    let qrObj = new QRCode(qrContainer, { width: 115, height: 115, correctLevel: QRCode.CorrectLevel.H });

    function updateAll() {
      const base = window.location.origin + window.location.pathname.replace("admin.html", "");
      const name = document.getElementById("shopName").value.trim() || "Our Store";
      const cat = document.getElementById("shopCat").value;
      const glink = document.getElementById("gLink").value.trim();

      const params = new URLSearchParams();
      params.set("name", name);
      params.set("cat", cat);
      if (glink) params.set("glink", glink);

      finalUrl = `${base}?${params.toString()}`;
      document.getElementById("stName").textContent = name.toUpperCase();
      document.getElementById("status").innerHTML = `<strong>Live Link:</strong><br>${finalUrl}`;

      qrObj.clear();
      qrObj.makeCode(finalUrl);
    }

    // App-Free Web NFC Writer (Works inside Chrome on any NFC Android phone!)
    async function writeViaWebNFC() {
      const statusEl = document.getElementById("status");
      if (!("NDEFReader" in window)) {
        statusEl.innerHTML = "❌ This phone/browser doesn't have Web NFC hardware. Open this exact webpage in Chrome on any NFC Android phone and tap here!";
        return;
      }
      try {
        const ndef = new NDEFReader();
        statusEl.innerHTML = "⏳ <strong>HOLD NFC CARD TO BACK OF PHONE NOW...</strong>";
        await ndef.write({ records: [{ recordType: "url", data: finalUrl }] });
        statusEl.innerHTML = "✅ <strong>SUCCESS! Link written to NFC card!</strong>";
      } catch (err) {
        statusEl.innerHTML = "⚠️ Error: " + err.message + " (Make sure NFC is turned ON in phone settings)";
      }
    }

    updateAll();
  </script>
</body>
</html>

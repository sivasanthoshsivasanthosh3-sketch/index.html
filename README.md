<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Public DWG Drawings</title>
  <style>
    body { font-family: Arial; background:#f4f6f8; margin:0; }
    header { background:#0f4c81; color:white; padding:35px; text-align:center; }
    main { max-width:900px; margin:30px auto; padding:0 15px; }
    .item { background:white; padding:18px; margin-bottom:12px; border-radius:10px;
            display:flex; justify-content:space-between; align-items:center; }
    a { text-decoration:none; padding:10px 14px; border-radius:8px; font-weight:bold; }
    .view { background:#0f4c81; color:white; margin-right:8px; }
    .dwg { background:#e8eef4; color:#0f4c81; border:1px solid #c8d6e3; }
  </style>
</head>
<body>

<header>
  <h1>Public DWG Drawings</h1>
</header>

<main id="list"></main>

<script>
const files = [
  "C:\Users\siva\Pictures\moviebox\OneDrive\Documents\AUTO CAD"
];

document.getElementById("list").innerHTML = files.map(f => `
  <div class="item">
    <strong>${f}</strong>
    <div>
      <a class="view" href="drawings/${f}.pdf" target="_blank">View PDF</a>
      <a class="dwg" href="drawings/${f}.dwg" download>Download DWG</a>
    </div>
  </div>
`).join("");
</script>

</body>
</html>

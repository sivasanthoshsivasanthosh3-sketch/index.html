
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Public DWG Drawings</title>

<style>
* {
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    background: #f1f5f9;
    margin: 0;
    color: #1e293b;
}

header {
    background: linear-gradient(135deg, #0f4c81, #1677b8);
    color: white;
    text-align: center;
    padding: 55px 15px;
}

header h1 {
    font-size: 34px;
    margin: 0 0 12px;
}

header p {
    margin: 0;
    color: #dbeafe;
}

main {
    max-width: 950px;
    margin: 35px auto;
    padding: 0 18px;
}

.search {
    width: 100%;
    padding: 15px;
    border: 1px solid #cbd5e1;
    border-radius: 10px;
    font-size: 16px;
    margin-bottom: 22px;
}

.item {
    background: white;
    padding: 20px;
    margin-bottom: 14px;
    border-radius: 12px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 15px;
    box-shadow: 0 3px 12px #00000008;
}

.item strong {
    font-size: 16px;
}

.download {
    background: #0f4c81;
    color: white;
    text-decoration: none;
    padding: 12px 17px;
    border-radius: 8px;
    font-weight: bold;
    white-space: nowrap;
}

.download:hover {
    background: #1677b8;
}

footer {
    text-align: center;
    padding: 25px;
    color: #64748b;
}

@media(max-width:600px) {
    .item {
        flex-direction: column;
        align-items: flex-start;
    }

    header h1 {
        font-size: 27px;
    }
}
</style>
</head>

<body>

<header>
    <h1>Public DWG Drawings</h1>
    <p>Free Civil Engineering & AutoCAD Drawing Downloads</p>
</header>

<main>

    <input
        type="text"
        id="search"
        class="search"
        placeholder="Search your drawings..."
    >

    <div id="list"></div>

</main>

<footer>
    © 2026 Public DWG Drawings
</footer>

<script>

// ADD YOUR DRAWING FILES HERE

const files = [
    {
        name: "EX.16 KEST",
        path: "drawings/EX.16%20KEST.zip"
    }
];

// DISPLAY DRAWINGS

function displayFiles(data) {

    const list = document.getElementById("list");

    if (data.length === 0) {
        list.innerHTML = "<p>No drawings found.</p>";
        return;
    }

    list.innerHTML = data.map(file => `
        <div class="item">
            <strong>📐 ${file.name}</strong>

            <a class="download"
               href="${file.path}"
               download>
               Download File
            </a>
        </div>
    `).join("");
}

displayFiles(files);

// SEARCH FUNCTION

document.getElementById("search").addEventListener("input", function() {

    const keyword = this.value.toLowerCase();

    const filtered = files.filter(file =>
        file.name.toLowerCase().includes(keyword)
    );

    displayFiles(filtered);

});

</script>

</body>
</html>

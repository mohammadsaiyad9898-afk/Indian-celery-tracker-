echo "# Indian-celery-tracker-" >> README.md
2
git init
3
git add README.md
4
git commit -m "first commit"
5
git branch -M main
6
git remote add origin https://github.com/mohammadsaiyad9898-afk/Indian-celery-tracker-.git
7
git push -u origin main
<!DOCTYPE html>
<html lang="hi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Desi Calorie Tracker</title>
    <style>
        :root { --main: #e67e22; --dark: #2c3e50; }
        body { font-family: sans-serif; background: #fdf2e9; margin: 0; padding: 15px; color: var(--dark); }
        .card { background: white; max-width: 400px; margin: auto; padding: 20px; border-radius: 20px; box-shadow: 0 8px 20px rgba(0,0,0,0.1); }
        .total-display { background: var(--dark); color: white; padding: 20px; border-radius: 15px; margin-bottom: 20px; }
        #total-val { font-size: 40px; margin: 0; color: #f1c40f; }
        input, select, button { width: 100%; padding: 12px; margin-bottom: 12px; border-radius: 10px; border: 1px solid #ddd; font-size: 16px; box-sizing: border-box; }
        button { background: var(--main); color: white; border: none; font-weight: bold; cursor: pointer; }
        .list-box { text-align: left; max-height: 200px; overflow-y: auto; border-top: 1px solid #eee; padding-top: 10px; }
        .item { font-size: 14px; padding: 5px 0; border-bottom: 1px dotted #ccc; }
    </style>
</head>
<body>

<div class="card">
    <h2>🥘 Desi Calorie Tracker</h2>
    <div class="total-display">
        <p style="margin:0;">Total Calories</p>
        <h1 id="total-val">0</h1>
    </div>

    <input type="text" id="search" placeholder="Search (e.g. Roti, Poha)..." onkeyup="filterFood()">
    
    <select id="food-select" size="5">
        <option value="70">Roti (1 piece) - 70 kcal</option>
        <option value="110">Butter Roti - 110 kcal</option>
        <option value="250">Aloo Paratha - 250 kcal</option>
        <option value="300">Paneer Paratha - 300 kcal</option>
        <option value="150">Dal (1 bowl) - 150 kcal</option>
        <option value="210">Chawal / Rice (1 cup) - 210 kcal</option>
        <option value="250">Paneer Sabzi - 250 kcal</option>
        <option value="180">Dal Tadka - 180 kcal</option>
        <option value="150">Poha (1 bowl) - 150 kcal</option>
        <option value="180">Idli (2 pieces) - 180 kcal</option>
        <option value="300">Masala Dosa - 300 kcal</option>
        <option value="120">Dahi (1 cup) - 120 kcal</option>
        <option value="45">Chai (sugar) - 45 kcal</option>
        <option value="350">Biryani (1 plate) - 350 kcal</option>
        <option value="400">Chole Bhature - 400 kcal</option>
        <option value="150">Samosa (1 pc) - 150 kcal</option>
        <option value="280">Chicken Curry - 280 kcal</option>
        <option value="90">Boiled Egg - 90 kcal</option>
        <option value="150">Omelette (2 eggs) - 150 kcal</option>
        <option value="50">Apple - 50 kcal</option>
        <option value="100">Banana - 100 kcal</option>
        <option value="60">Upma - 140 kcal</option>
        <option value="200">Pav Bhaji - 400 kcal</option>
        <option value="150">Gulab Jamun (1 pc) - 150 kcal</option>
        <option value="320">Rajma Chawal - 320 kcal</option>
        <option value="290">Kadahi Paneer - 290 kcal</option>
        <option value="80">Idli Sambar - 160 kcal</option>
        <option value="50">Buttermilk (Chaas) - 50 kcal</option>
        </select>

    <button onclick="addFood()">+ Add to My List</button>

    <div class="list-box" id="log">
        <strong>Aaj kya khaya:</strong>
    </div>
</div>

<script>
    let total = 0;
    function addFood() {
        let select = document.getElementById('food-select');
        let cal = parseInt(select.value);
        let name = select.options[select.selectedIndex].text.split('-')[0];
        
        total += cal;
        document.getElementById('total-val').innerText = total;

        let log = document.getElementById('log');
        let item = document.createElement('div');
        item.className = 'item';
        item.innerHTML = `✅ ${name} <b>${cal} kcal</b>`;
        log.appendChild(item);
    }

    function filterFood() {
        let input = document.getElementById('search').value.toLowerCase();
        let opts = document.getElementById('food-select').options;
        for (let opt of opts) {
            opt.style.display = opt.text.toLowerCase().includes(input) ? "" : "none";
        }
    }
</script>

</body>
</html>

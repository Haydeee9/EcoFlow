# EcoFlow
mkdir flood-alarm-system && cd flood-alarm-system
flood-alarm-system/
├── index.html
├── style.css
├── script.js
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Flood Alarm System</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <header>
    <h1>Flood Alarm System</h1>
    <p>Real-Time Monitoring and Education</p>
  </header>

  <nav>
    <a href="#monitoring">Monitoring</a>
    <a href="#education">Education</a>
    <a href="#history">History</a>
    <a href="#contact">Contact</a>
  </nav>

  <!-- Real-Time Monitoring Section -->
  <section id="monitoring">
    <h2>Real-Time Monitoring</h2>
    <p id="status">Loading water level data...</p>
  </section>

  <!-- Educational Content -->
  <section id="education">
    <h2>Flood Education</h2>
    <p>Floods are caused by heavy rain, poor drainage, and rising sea levels.</p>
    <ul>
      <li>Build flood barriers</li>
      <li>Clear drainage systems</li>
      <li>Stay informed through weather alerts</li>
    </ul>
  </section>

  <!-- Historical Data Section -->
  <section id="history">
    <h2>Historical Data</h2>
    <canvas id="waterChart"></canvas>
  </section>

  <!-- Contact Section -->
  <section id="contact">
    <h2>Contact</h2>
    <p>Emergency Hotline: 911</p>
    <p>Email: support@floodsystem.com</p>
  </section>

  <script src="script.js"></script>
</body>
</html>
✅ 4. Write the CSS Code
➡️ style.css
Example simple CSS styling:

css
Copy
Edit
body {
  font-family: Arial, sans-serif;
  background-color: #f9f9f9;
  margin: 0;
  padding: 0;
  color: #333;
}

header {
  background-color: #4CAF50;
  color: white;
  padding: 1em;
  text-align: center;
}

nav {
  background-color: #eee;
  padding: 0.5em;
  text-align: center;
}

nav a {
  color: #333;
  margin: 0 1em;
  text-decoration: none;
  font-weight: bold;
}

section {
  padding: 2em;
  border-bottom: 1px solid #ccc;
}

h2 {
  color: #4CAF50;
}

canvas {
  max-width: 100%;
}

// Simulate real-time water level data
let waterLevel = Math.random() * 100;

function updateWaterLevel() {
  waterLevel = Math.random() * 100; // Simulate new data
  document.getElementById('status').innerText = `Water Level: ${waterLevel.toFixed(2)} cm`;

  // Update chart if available
  if (chart) {
    const now = new Date().toLocaleTimeString();
    chart.data.labels.push(now);
    chart.data.datasets[0].data.push(waterLevel);

    if (chart.data.labels.length > 10) {
      chart.data.labels.shift();
      chart.data.datasets[0].data.shift();
    }

    chart.update();
  }
}

setInterval(updateWaterLevel, 3000); // Update every 3 seconds

// Chart.js for historical data
const ctx = document.getElementById('waterChart').getContext('2d');
const chart = new Chart(ctx, {
  type: 'line',
  data: {
    labels: [],
    datasets: [{
      label: 'Water Level (cm)',
      data: [],
      borderColor: '#4CAF50',
      backgroundColor: 'rgba(76, 175, 80, 0.2)',
      borderWidth: 2
    }]
  }
});

updateWaterLevel(); // Initial call

git init  
git add .  
git commit -m "Initial commit for flood alarm system"  
git branch -M main  
git remote add origin https://github.com/USERNAME/flood-alarm-system.git  
git push -u origin main  

https://USERNAME.github.io/flood-alarm-system

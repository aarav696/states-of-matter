# states-of-matter
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>States of Matter</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      margin: 0;
      padding: 20px;
      background: #f0f9ff;
      color: #0f172a;
    }

    h1 {
      text-align: center;
      font-size: 28px;
      margin-bottom: 10px;
    }

    .button-list {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 10px;
      margin-bottom: 20px;
    }

    .button-list button {
      padding: 12px 18px;
      font-size: 16px;
      background-color: #38bdf8;
      color: white;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      transition: background 0.3s;
    }

    .button-list button:hover {
      background-color: #0ea5e9;
    }

    #info-panel {
      background: #e0f2fe;
      padding: 20px;
      border-radius: 12px;
      text-align: center;
    }

    #description {
      font-size: 18px;
      margin-bottom: 10px;
    }

    #state-image {
      max-width: 100%;
      border-radius: 8px;
      display: none;
    }

    #video-container iframe {
      width: 100%;
      max-height: 240px;
      margin-top: 15px;
      border: none;
      border-radius: 8px;
    }

    @media (max-width: 600px) {
      .button-list button {
        width: 100%;
        font-size: 18px;
      }

      #video-container iframe {
        height: 200px;
      }
    }
  </style>
</head>
<body>
  <h1>🄠 States of Matter Changes</h1>

  <div class="button-list">
    <button onclick="showChange('melting')">Melting</button>
    <button onclick="showChange('freezing')">Freezing</button>
    <button onclick="showChange('vaporization')">Vaporization</button>
    <button onclick="showChange('condensation')">Condensation</button>
    <button onclick="showChange('sublimation')">Sublimation</button>
    <button onclick="showChange('deposition')">Deposition</button>
  </div>

  <div id="info-panel">
    <h2>Click a process above to learn more!</h2>
    <div id="description"></div>
    <img id="state-image" src="" alt="" />
    <div id="video-container"></div>
  </div>

  <script>
    function showChange(type) {
      const data = {
        melting: {
          text: "🔥 <b>Melting:</b> Solid → Liquid. Example: Ice melting into water at 0°C.",
          image: "https://upload.wikimedia.org/wikipedia/commons/8/87/Ice_melting.jpg",
          video: "https://www.youtube.com/embed/44eJAG6jZF8"
        },
        freezing: {
          text: "❄️ <b>Freezing:</b> Liquid → Solid. Example: Water freezing into ice.",
          image: "https://upload.wikimedia.org/wikipedia/commons/a/a0/Ice_cubes.jpg",
          video: "https://www.youtube.com/embed/DV2ONItWYqM"
        },
        vaporization: {
          text: "💨 <b>Vaporization:</b> Liquid → Gas. Example: Water boiling into steam.",
          image: "https://upload.wikimedia.org/wikipedia/commons/f/f3/Steam_from_kettle.jpg",
          video: "https://www.youtube.com/embed/nxU2Txk_Y5g"
        },
        condensation: {
          text: "🌧️ <b>Condensation:</b> Gas → Liquid. Example: Steam condensing on a cold surface.",
          image: "https://upload.wikimedia.org/wikipedia/commons/1/19/Water_condensation.jpg",
          video: "https://www.youtube.com/embed/lA3S1-2XQDM"
        },
        sublimation: {
          text: "💨 <b>Sublimation:</b> Solid → Gas. Example: Dry ice turning into carbon dioxide gas.",
          image: "https://upload.wikimedia.org/wikipedia/commons/5/5e/Sublimation_of_CO2.jpg",
          video: "https://www.youtube.com/embed/w7djYd_cKX8"
        },
        deposition: {
          text: "❄️ <b>Deposition:</b> Gas → Solid. Example: Frost forming on a window.",
          image: "https://upload.wikimedia.org/wikipedia/commons/f/f4/Frost_patterns.jpg",
          video: "https://www.youtube.com/embed/q2l_Mg1V3Xk"
        }
      };

      const panel = data[type];
      document.getElementById("description").innerHTML = panel.text;
      document.getElementById("state-image").src = panel.image;
      document.getElementById("state-image").style.display = 'block';
      document.getElementById("video-container").innerHTML = `<iframe src="${panel.video}" allowfullscreen></iframe>`;
    }
  </script>
</body>
</html>

<!DOCTYPE html>
<html lang="sk">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Tvoje ciele – Minikurz</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      background: #f6f9fc;
      margin: 0;
      padding: 0;
      color: #333;
    }
    .container {
      max-width: 800px;
      margin: 30px auto;
      background: white;
      padding: 25px 30px;
      border-radius: 12px;
      box-shadow: 0 4px 20px rgba(0,0,0,0.08);
    }
    h1, h2 {
      text-align: center;
      color: #2c3e50;
    }
    .task {
      display: none;
      margin-top: 20px;
    }
    .task.active {
      display: block;
    }
    label {
      display: block;
      margin-bottom: 8px;
      font-weight: 600;
    }
    input[type="text"], textarea, select {
      width: 100%;
      padding: 10px;
      margin-bottom: 15px;
      border: 1px solid #ccc;
      border-radius: 5px;
      font-size: 16px;
    }
    .option-group label {
      display: block;
      margin: 5px 0;
    }
    button {
      background: #3498db;
      color: white;
      border: none;
      padding: 12px 20px;
      border-radius: 5px;
      cursor: pointer;
      font-size: 16px;
    }
    button:hover {
      background: #2980b9;
    }
    .slider-value {
      font-weight: bold;
      margin-left: 10px;
    }
    .summary {
      white-space: pre-wrap;
      background: #f0f8ff;
      padding: 15px;
      border-radius: 5px;
      margin-top: 20px;
    }
    .highlight {
      background: #dff0d8;
      padding: 10px;
      border-left: 5px solid #3c763d;
      margin: 15px 0;
      border-radius: 4px;
    }
    .scale {
      display: flex;
      justify-content: space-between;
    }
    .image-choice img {
      width: 100px;
      height: auto;
      cursor: pointer;
      border: 2px solid transparent;
      margin: 5px;
    }
    .image-choice img.selected {
      border-color: #3498db;
    }
  </style>
</head>
<body>
  <div class="container">
    <div id="intro" class="task active">
      <h1>Tvoje ciele</h1>
      <div class="highlight">
        <p>Vitaj! Tento minikurz je pre teba, ak túžiš ujasniť si, kam kráčaš a prečo. Zaberie ti približne 1 hodinu. Verím, že ti pomôže nastaviť si jasný smer a urobiť prvý krok.</p>
      </div>
      <button onclick="nextTask()">Začať kurz</button>
    </div>

    <!-- ÚLOHY 1–20 -->
    <div class="task" id="task1">
      <h2>Úloha 1</h2>
      <label for="q1">Napíš 3 veci, ktoré ťa motivujú.</label>
      <textarea id="q1" rows="4"></textarea>
      <button onclick="nextTask()">Ďalej</button>
    </div>

    <div class="task" id="task2">
      <h2>Úloha 2</h2>
      <label>Vyber, čo ťa najviac vystihuje:</label>
      <div class="option-group">
        <label><input type="radio" name="q2" value="Vizionár"> Vizionár</label>
        <label><input type="radio" name="q2" value="Plánovač"> Plánovač</label>
        <label><input type="radio" name="q2" value="Chaotik"> Chaotik</label>
      </div>
      <button onclick="nextTask()">Ďalej</button>
    </div>

    <div class="task" id="task3">
      <h2>Úloha 3</h2>
      <label for="q3">Aký cieľ si chceš splniť do 3 mesiacov?</label>
      <textarea id="q3" rows="4"></textarea>
      <button onclick="nextTask()">Ďalej</button>
    </div>

    <div class="task" id="task4">
      <h2>Úloha 4</h2>
      <label for="q4">Ako veľmi ti na tom záleží? (0–10)</label>
      <input type="range" id="q4" min="0" max="10" value="5" oninput="document.getElementById('val4').innerText = this.value">
      <span class="slider-value" id="val4">5</span>
      <button onclick="nextTask()">Ďalej</button>
    </div>

    <div class="task" id="task5">
      <h2>Úloha 5</h2>
      <label for="q5">Prečo je tento cieľ pre teba dôležitý?</label>
      <textarea id="q5" rows="4"></textarea>
      <button onclick="nextTask()">Ďalej</button>
    </div>

    <div class="task" id="task6">
      <h2>Úloha 6</h2>
      <label>Vyber si preferovaný spôsob plánovania:</label>
      <select id="q6">
        <option value="Digitálny kalendár">Digitálny kalendár</option>
        <option value="Papierový diár">Papierový diár</option>
        <option value="To-do appka">To-do appka</option>
      </select>
      <button onclick="nextTask()">Ďalej</button>
    </div>

    <div class="task" id="task7">
      <h2>Úloha 7</h2>
      <label for="q7">Rozdeľ svoj cieľ na 3 malé kroky.</label>
      <textarea id="q7" rows="4"></textarea>
      <button onclick="nextTask()">Ďalej</button>
    </div>

    <div class="task" id="task8">
      <h2>Úloha 8</h2>
      <label>Ako hodnotíš svoju pripravenosť? (1–5)</label>
      <div class="scale">
        <label><input type="radio" name="q8" value="1">1</label>
        <label><input type="radio" name="q8" value="2">2</label>
        <label><input type="radio" name="q8" value="3">3</label>
        <label><input type="radio" name="q8" value="4">4</label>
        <label><input type="radio" name="q8" value="5">5</label>
      </div>
      <button onclick="nextTask()">Ďalej</button>
    </div>

    <div class="task" id="task9">
      <h2>Úloha 9</h2>
      <label for="q9">Čo spravíš ako prvé?</label>
      <textarea id="q9" rows="4"></textarea>
      <button onclick="nextTask()">Ďalej</button>
    </div>

    <div class="task" id="task10">
      <h2>Úloha 10</h2>
      <label for="q10">Ako sa odmeníš za splnenie cieľa?</label>
      <textarea id="q10" rows="3"></textarea>
      <button onclick="nextTask()">Ďalej</button>
    </div>

    <div class="task" id="task11">
      <h2>Úloha 11</h2>
      <label>Vyber si vizuál, ktorý vystihuje tvoje tempo:</label>
      <div class="image-choice" id="q11">
        <img src="https://via.placeholder.com/100?text=Raketa" onclick="selectImage(this)">
        <img src="https://via.placeholder.com/100?text=Bicykel" onclick="selectImage(this)">
        <img src="https://via.placeholder.com/100?text=Šnek" onclick="selectImage(this)">
      </div>
      <button onclick="nextTask()">Ďalej</button>
    </div>

    <div class="task" id="task12">
      <h2>Úloha 12</h2>
      <label for="q12">Ako si budeš merať pokrok?</label>
      <textarea id="q12" rows="3"></textarea>
      <button onclick="nextTask()">Ďalej</button>
    </div>

    <div class="task" id="task13">
      <h2>Úloha 13</h2>
      <label for="q13">Kto ťa môže podporiť a ako?</label>
      <textarea id="q13" rows="3"></textarea>
      <button onclick="nextTask()">Ďalej</button>
    </div>

    <div class="task" id="task14">
      <h2>Úloha 14</h2>
      <label for="q14">Napíš si pozitívnu vetu, ktorú si budeš opakovať.</label>
      <input type="text" id="q14" />
      <button onclick="nextTask()">Ďalej</button>
    </div>

    <div class="task" id="task15">
      <h2>Úloha 15</h2>
      <label for="q15">Spomeň si na úspech, ktorý si dosiahol v minulosti.</label>
      <textarea id="q15" rows="4"></textarea>
      <button onclick="nextTask()">Ďalej</button>
    </div>

    <div class="task" id="task16">
      <h2>Úloha 16</h2>
      <label>Čo najviac potrebuješ, aby si neuskol?</label>
      <select id="q16">
        <option>Motiváciu</option>
        <option>Podporu</option>
        <option>Struktúru</option>
        <option>Pripomienky</option>
      </select>
      <button onclick="nextTask()">Ďalej</button>
    </div>

    <div class="task" id="task17">
      <h2>Úloha 17</h2>
      <label for="q17">Ako bude vyzerať tvoj ideálny deň, keď dosiahneš cieľ?</label>
      <textarea id="q17" rows="4"></textarea>
      <button onclick="nextTask()">Ďalej</button>
    </div>

    <div class="task" id="task18">
      <h2>Úloha 18</h2>
      <label for="q18">Napíš si 3 slová, ktoré ti budú pripomínať tvoj smer.</label>
      <input type="text" id="q18" />
      <button onclick="nextTask()">Ďalej</button>
    </div>

    <div class="task" id="task19">
      <h2>Úloha 19</h2>
      <label for="q19">Čo budeš robiť, keď sa ti nebude chcieť?</label>
      <textarea id="q19" rows="3"></textarea>
      <button onclick="nextTask()">Ďalej</button>
    </div>

    <div class="task" id="task20">
      <h2>Úloha 20</h2>
      <label for="q20">Zhrnutie: Aký je tvoj plán na najbližší týždeň?</label>
      <textarea id="q20" rows="4"></textarea>
      <button onclick="showSummary()">Dokončiť kurz</button>
    </div>

    <div class="task" id="summary">
      <h1>Gratulujem!</h1>
      <p>Dokončil si kurz. Tu je tvoje zhrnutie:</p>
      <div class="summary" id="answers"></div>
    </div>
  </div>

  <script>
    let currentTask = 0;

    function nextTask() {
      document.querySelectorAll(".task")[currentTask].classList.remove("active");
      currentTask++;
      document.querySelectorAll(".task")[currentTask].classList.add("active");
    }

    function showSummary() {
      document.querySelectorAll(".task")[currentTask].classList.remove("active");
      document.getElementById("summary").classList.add("active");

      let summary = "";
      for (let i = 1; i <= 20; i++) {
        let answer;
        if (document.getElementById("q" + i)) {
          answer = document.getElementById("q" + i).value || "";
        } else {
          let radios = document.querySelectorAll("input[name=q" + i + "]:checked");
          answer = radios.length > 0 ? radios[0].value : "";
        }
        summary += `Úloha ${i}:\n${answer}\n\n`;
      }

      document.getElementById("answers").textContent = summary;
    }

    function selectImage(img) {
      document.querySelectorAll("#q11 img").forEach(el => el.classList.remove("selected"));
      img.classList.add("selected");
    }
  </script>
</body>
</html>

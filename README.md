# robert1098.github.io
<!DOCTYPE html>
<html lang="bs">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Dan Maternjeg Jezika - Bosna</title>
  <style>
    body { 
      font-family: Arial, sans-serif; 
      margin: 0; 
      padding: 0; 
      background: linear-gradient(to right, #ffcc00, #ff6600); 
      text-align: center; 
    }
    .landing { 
      background: url('https://example.com/bosnia-landscape.jpg') center/cover no-repeat; 
      height: 100vh; 
      display: flex; 
      flex-direction: column; 
      justify-content: center; 
      align-items: center; 
      color: white; 
      text-align: center;
      animation: fadeIn 2s ease-in-out;
    }
    .landing h1 { 
      font-size: 3.5em; 
      text-shadow: 3px 3px 6px black; 
      color: white;
      opacity: 0;
      animation: fadeInText 2s ease-in-out forwards;
    }
    .landing p { 
      font-size: 1.7em; 
      max-width: 700px; 
      opacity: 0;
      animation: fadeInText 2s ease-in-out 0.5s forwards;
    }
    .start-btn { 
      padding: 12px 25px; 
      font-size: 1.3em; 
      background: white; 
      color: #ff6600; 
      border: none; 
      border-radius: 8px; 
      cursor: pointer; 
      margin-top: 20px; 
      transition: all 0.3s ease;
      opacity: 0;
      animation: fadeInText 2s ease-in-out 1s forwards;
    }
    .start-btn:hover { background: #ffcc00; transform: scale(1.1); }
    .container { 
      max-width: 600px; 
      margin: 20px auto; 
      background: white; 
      padding: 20px; 
      border-radius: 8px; 
      box-shadow: 0px 0px 10px #ccc; 
      opacity: 0; 
      animation: fadeIn 2s ease-in-out 1.5s forwards; 
    }
    h1, h2 { color: #4a4a4a; }
    form { text-align: left; }
    label, input, select, textarea { 
      display: block; 
      width: 100%; 
      margin-bottom: 10px; 
    }
    input, select, textarea { 
      padding: 8px; 
      border: 1px solid #ccc; 
      border-radius: 4px; 
    }
    button { 
      background-color: #28a745; 
      color: white; 
      padding: 10px; 
      border: none; 
      border-radius: 4px; 
      cursor: pointer; 
    }
    button:hover { background-color: #218838; }
    .header-img { 
      width: 100%; 
      max-height: 300px; 
      object-fit: cover; 
      border-radius: 8px; 
    }
    .word-list { 
      margin-top: 20px; 
      text-align: left; 
    }
    .word-item { 
      background: #eef; 
      padding: 10px; 
      margin: 5px 0; 
      border-radius: 5px; 
      position: relative;
    }
    .delete-btn {
      background-color: #d9534f; 
      color: white; 
      padding: 5px 10px; 
      border: none; 
      border-radius: 4px; 
      cursor: pointer; 
      position: absolute; 
      top: 10px; 
      right: 10px;
    }
    .delete-btn:hover { background-color: #c9302c; }

    /* Quiz Modal Styles */
    .overlay {
      display: none;
      position: fixed;
      top: 0; left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0,0,0,0.5);
      z-index: 999;
    }
    .quiz-modal {
      display: none;
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      background: white;
      padding: 20px;
      border-radius: 8px;
      box-shadow: 0px 0px 10px #000;
      z-index: 1000;
      width: 90%;
      max-width: 400px;
      text-align: left;
    }
    .quiz-modal h3 { margin-top: 0; }
    .quiz-modal p { margin: 10px 0 5px; }
    .quiz-modal label { display: block; margin-bottom: 5px; }
    .quiz-modal button { margin-top: 10px; }

    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }
    @keyframes fadeInText {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }
  </style>
</head>
<body>
  <div class="landing">
    <h1>Dobrodošli na Dan Maternjeg Jezika</h1>
    <p>Sačuvajmo jezičko bogatstvo Bosne i Hercegovine prijavljujući riječi iz naših lokalnih dijalekata.</p>
    <button class="start-btn" onclick="document.getElementById('mainContent').scrollIntoView({behavior: 'smooth'})">Počnimo</button>
  </div>

  <div class="container" id="mainContent">
    <img src="https://example.com/mother-language-day.jpg" alt="Dan Maternjeg Jezika" class="header-img">
    <h1>Dan Maternjeg Jezika u Bosni</h1>
    <p>Pridružite se očuvanju jezičke raznolikosti Bosne i Hercegovine prijavljivanjem riječi iz vašeg dijalekta.</p>
    
    <h2>Prijavite Riječ</h2>
    <form id="wordForm">
      <label for="word">Riječ (Obavezno):</label>
      <input type="text" id="word" name="word" required>
      
      <label for="meaning">Značenje/Definicija (Obavezno):</label>
      <textarea id="meaning" name="meaning" required></textarea>
      
      <label for="example">Primjer Upotrebe (Opcionalno):</label>
      <textarea id="example" name="example"></textarea>
      
      <label for="region">Regija/Dijalekat:</label>
      <select id="region" name="region">
        <option value="Sarajevo">Sarajevo</option>
        <option value="Tuzla">Tuzla</option>
        <option value="Banja Luka">Banja Luka</option>
        <option value="Mostar">Mostar</option>
      </select>
      
      <label for="contributor">Ime Prijavioca (Opcionalno):</label>
      <input type="text" id="contributor" name="contributor">
      
      <button type="submit">Pošalji Riječ</button>
    </form>
    
    <h2>Prijavljene Riječi</h2>
    <div id="wordList" class="word-list"></div>
  </div>

  <!-- Quiz Modal and Overlay -->
  <div class="overlay" id="overlay"></div>
  <div class="quiz-modal" id="quizModal">
    <h3>Odgovori na kviz da obrišeš riječ</h3>
    <div id="quizQuestions"></div>
    <button onclick="checkQuiz()">Potvrdi</button>
  </div>

  <script>
    // Load words from localStorage and display them
    function loadWords() {
      const storedWords = JSON.parse(localStorage.getItem('words')) || [];
      const wordListContainer = document.getElementById('wordList');
      wordListContainer.innerHTML = ''; // Clear current list

      storedWords.forEach((word, index) => {
        const wordItem = document.createElement('div');
        wordItem.classList.add('word-item');
        wordItem.innerHTML = `
          <strong>Riječ:</strong> ${word.word}<br>
          <strong>Značenje:</strong> ${word.meaning}<br>
          ${ word.example ? `<strong>Primjer:</strong> ${word.example}<br>` : '' }
          <strong>Regija:</strong> ${word.region}<br>
          ${ word.contributor ? `<strong>Prijavitelj:</strong> ${word.contributor}` : '' }
          <button class="delete-btn" onclick="openQuiz(${index})">Obriši</button>
        `;
        wordListContainer.appendChild(wordItem);
      });
    }

    // Save a new word to localStorage
    document.getElementById('wordForm').addEventListener('submit', function(e) {
      e.preventDefault();
      const word = document.getElementById('word').value;
      const meaning = document.getElementById('meaning').value;
      const example = document.getElementById('example').value;
      const region = document.getElementById('region').value;
      const contributor = document.getElementById('contributor').value;
      
      const storedWords = JSON.parse(localStorage.getItem('words')) || [];
      storedWords.push({ word, meaning, example, region, contributor });
      localStorage.setItem('words', JSON.stringify(storedWords));

      loadWords();
      this.reset();
    });

    // Global variable to hold the index of the word being deleted
    let currentDeleteIndex = null;

    // When user clicks delete button, open the quiz modal
    function openQuiz(index) {
      currentDeleteIndex = index;
      generateQuiz();
      document.getElementById('overlay').style.display = "block";
      document.getElementById('quizModal').style.display = "block";
    }

    // Quiz questions array (example questions about word meanings)
    const quizQuestionsPool = [
      { q: "Šta znači 'pendžer'?", a: "A. Prozor", b: "B. Stol", c: "C. Vrata", correct: "A" },
      { q: "Šta znači 'sehara'?", a: "A. Sanduk", b: "B. Krevet", c: "C. Torba", correct: "A" },
      { q: "Šta znači 'ćeif'?", a: "A. Zadovoljstvo", b: "B. Strah", c: "C. Ljutnja", correct: "A" },
      { q: "Šta znači 'mahala'?", a: "A. Kvart", b: "B. Ulica", c: "C. Trg", correct: "A" },
      { q: "Šta znači 'sikter'?", a: "A. Odlazi", b: "B. Dođi", c: "C. Sjedi", correct: "A" },
      { q: "Šta znači 'hale'?", a: "A. Briga", b: "B. Ljubav", c: "C. Ljubomora", correct: "A" }
    ];

    // Generate a quiz with 3 random questions
    function generateQuiz() {
      const selectedQuestions = quizQuestionsPool.sort(() => 0.5 - Math.random()).slice(0, 3);
      let quizHTML = "";
      selectedQuestions.forEach(question => {
        quizHTML += `
          <p>${question.q}</p>
          <label><input type="radio" name="${question.q}" value="A"> ${question.a}</label>
          <label><input type="radio" name="${question.q}" value="B"> ${question.b}</label>
          <label><input type="radio" name="${question.q}" value="C"> ${question.c}</label>
        `;
      });
      document.getElementById('quizQuestions').innerHTML = quizHTML;
      // Save selected quiz questions for checking answers later
      localStorage.setItem("currentQuiz", JSON.stringify(selectedQuestions));
    }

    // Check the quiz answers when user clicks "Potvrdi"
    function checkQuiz() {
      const selectedQuestions = JSON.parse(localStorage.getItem("currentQuiz")) || [];
      const answers = document.querySelectorAll("#quizQuestions input:checked");

      if (answers.length < 3) {
        alert("Morate odgovoriti na sva pitanja!");
        return;
      }

      let correctCount = 0;
      // For each question in the quiz, check if the selected answer is correct
      selectedQuestions.forEach(q => {
        const answer = document.querySelector(`input[name="${q.q}"]:checked`);
        if (answer && answer.value === q.correct) {
          correctCount++;
        }
      });

      if (correctCount === 3) {
        // Remove the word from storage if quiz passed
        let storedWords = JSON.parse(localStorage.getItem('words')) || [];
        storedWords.splice(currentDeleteIndex, 1);
        localStorage.setItem('words', JSON.stringify(storedWords));
        loadWords();
        closeQuiz();
      } else {
        alert("Netačno! Pokušajte ponovo.");
      }
    }

    // Close the quiz modal
    function closeQuiz() {
      document.getElementById('quizModal').style.display = "none";
      document.getElementById('overlay').style.display = "none";
      localStorage.removeItem("currentQuiz");
    }

    // Load words when the page loads
    window.onload = loadWords;
  </script>
</body>
</html>


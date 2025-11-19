# vbellou.github.io
Breathe Free
<!doctype html>
<html lang="el">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Ανάσα Καθαρή — Breathe Free</title>
  <link rel="stylesheet" href="styles.css" />
</head>
<body>
  <header class="hero">
    <div class="hero-inner">
      <h1>Ανάσα Καθαρή — Breathe Free</h1>
      <p class="lead">Πρόληψη & Διακοπή Καπνίσματος — Νεανικός και διαδραστικός οδηγός.</p>
      <div class="buttons">
        <a class="btn" href="#teenzone">Για Εφήβους</a>
        <a class="btn" href="#adultguide">Για Ενήλικες</a>
        <a class="btn pulse" href="#quit">Ξεκίνα τη Διακοπή</a>
      </div>
    </div>
  </header>

  <main>
    <section id="teenzone" class="section">
      <h2>Teen Zone — Μύθοι vs Αλήθειες</h2>
      <p>Σύντομα, έντονα facts ειδικά για εφήβους. Μην αφήνεις τα social να αποφασίζουν για σένα.</p>
      <div class="grid-3">
        <div class="card white">
          <h3>Μύθοι & Αλήθειες</h3>
          <ul>
            <li>Το αερόλυμα δεν είναι απλός υδρατμός — περιέχει χημικά.</li>
            <li>Η νικοτίνη αλλάζει τον αναπτυσσόμενο εγκέφαλο.</li>
            <li>Οι εταιρείες στοχεύουν νέους με γεύσεις & marketing.</li>
          </ul>
        </div>

        <div class="card white">
          <h3>Πώς σε επηρεάζει;</h3>
          <select id="impactSel" class="input">
            <option value="0">Διάλεξε...</option>
            <option value="1">Λίγο</option>
            <option value="2">Μέτρια</option>
            <option value="3">Πολύ</option>
          </select>
          <button class="btn small" onclick="calcImpact()">Δες</button>
        </div>

        <div class="card white">
          <h3>Υλικό για Εκπαιδευτικούς</h3>
          <a class="link" href="Πλήρης Οδηγός για τη Διακοπή του Καπνίσματος.docx">Λήψη οδηγού (docx)</a><br>
          <a class="link" href="Nicotine & Tobacco Products teen version.pptx">Λήψη παρουσίασης (pptx)</a>
        </div>
      </div>
    </section>

    <section id="adultguide" class="section">
      <h2>Οδηγός Διακοπής</h2>
      <div class="card dark">
        <p>Βασισμένος στον πλήρη οδηγό: STAR μέθοδος, ΘΥΝ, φάρμακα, στρατηγικές & υποστήριξη.</p>
      </div>
    </section>

    <section id="quit" class="section">
      <h2>Υπολογιστής Εξοικονομήσεων</h2>
      <div class="card dark">
        <input id="cigsPerDay" class="input" placeholder="Τσιγάρα / ημέρα" type="number" />
        <input id="pricePack" class="input" placeholder="Κόστος πακέτου (€)" type="number" />
        <button class="btn small" onclick="calcSavings()">Υπολόγισε</button>
        <div id="savingsResult" class="result"></div>
      </div>
    </section>
  </main>

  <footer>
    Demo static site — χωρίς προώθηση προϊόντων καπνού.
  </footer>

  <script src="script.js"></script>
</body>
</html>


/* Stylesheet for Breathe Free static site */

body{
  margin:0;
  font-family:Inter,system-ui,-apple-system,Segoe UI,Roboto,Helvetica,Arial;
  background:#f5f6fa;
  color:#222;
}

.hero{
  background:linear-gradient(135deg,#1b9fff,#6a4cff);
  padding:90px 20px;
  color:#fff;
  text-align:center;
}

.hero-inner{
  max-width:800px;
  margin:0 auto;
}

.lead{
  margin-top:10px;
  opacity:0.95;
}

.buttons{
  margin-top:20px;
  display:flex;
  gap:12px;
  justify-content:center;
  flex-wrap:wrap;
}

.btn{
  padding:10px 20px;
  border-radius:999px;
  background:rgba(255,255,255,0.1);
  border:2px solid rgba(255,255,255,0.2);
  text-decoration:none;
  color:#fff;
  font-weight:600;
  transition:all .2s;
}

.btn:hover{
  transform:translateY(-4px);
  box-shadow:0 8px 20px rgba(0,0,0,0.3);
}

.pulse{
  animation:pulse 2s infinite;
}
@keyframes pulse{
  0%{transform:scale(1)}
  50%{transform:scale(1.05)}
  100%{transform:scale(1)}
}

.section{
  padding:50px 20px;
  max-width:1100px;
  margin:0 auto;
}

.grid-3{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:20px;
}

.card{
  background:#fff;
  border-radius:12px;
  padding:20px;
  box-shadow:0 4px 18px rgba(0,0,0,0.08);
}

.card.white{
  background:#fff;
  color:#000;
}

.card.dark{
  background:#0f1724;
  color:#fff;
}

.input{
  width:100%;
  margin-top:10px;
  padding:10px;
  border-radius:8px;
  border:1px solid #ccc;
}

.btn.small{
  padding:8px 14px;
  margin-top:10px;
}

footer{
  text-align:center;
  padding:20px;
  color:#555;
  font-size:14px;
}
// script.js — Breathe Free static site

// Teen zone impact quizunction calcImpact(){
  const v = parseInt(document.getElementById('impactSel').value);
  if(!v){ alert('Διάλεξε μια απάντηση πρώτα.'); return; }
  const msgs=[
    'Μικρή επίδραση — κράτα τις υγιείς συνήθειες!',
    'Μέτρια επίδραση — δοκίμασε στρατηγικές αντιμετώπισης.',
    'Μεγάλη επίδραση — ζήτα υποστήριξη και κάνε μικρά βήματα.'
  ];
  alert(msgs[v-1]);
}

// Savings calculator
function calcSavings(){
  const cigs = parseFloat(document.getElementById('cigsPerDay').value) || 0;
  const price = parseFloat(document.getElementById('pricePack').value) || 0;

  if(!cigs || !price){
    document.getElementById('savingsResult').innerText = 'Συμπλήρωσε και τα δύο πεδία.';
    return;
  }

  const costPerCig = price / 20;
  const yearly = costPerCig * cigs * 365;

  document.getElementById('savingsResult').innerText = `Θα εξοικονομούσες περίπου €${yearly.toFixed(0)} τον χρόνο.`;
}

// Optional enhancements
// Smooth scroll for section links
document.querySelectorAll('a[href^="#"]').forEach(a => {
  a.addEventListener('click', function(e){
    const target = document.querySelector(this.getAttribute('href'));
    if(target){
      e.preventDefault();
      target.scrollIntoView({ behavior:'smooth' });
    }
  });
});

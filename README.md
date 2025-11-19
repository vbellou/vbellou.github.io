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

## Personal Study Blog 



<div style="font-family: sans-serif; text-align: center; margin-top: 20px;">
  <h2>📚 Countdown to AP CSP Test 📅</h2>
  <h1 id="countdown" style="font-size: 2rem; color: #4f46e5;"></h1>
</div>

<script>
  const testDate = new Date("May 15, 2025 08:00:00").getTime();

  const countdownFunc = setInterval(() => {
    const now = new Date().getTime();
    const distance = testDate - now;

    if (distance < 0) {
      clearInterval(countdownFunc);
      document.getElementById("countdown").innerHTML = "🚀 It's test day!";
      return;
    }

    const days = Math.floor(distance / (1000 * 60 * 60 * 24));
    const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
    const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
    const seconds = Math.floor((distance % (1000 * 60)) / 1000);

    document.getElementById("countdown").innerHTML =
      `${days}d ${hours}h ${minutes}m ${seconds}s`;
  }, 1000);
</script>





| Date       | Topic                               |
|------------|--------------------------------------------|
| Apr 21     | [Big Idea 1: Creative Development](https://apclassroom.collegeboard.org/103/home?unit=1) |
| Apr 22     | [Big Idea 2: Data](https://apclassroom.collegeboard.org/103/home?unit=2) |
| Apr 23     | [Big Idea 3: Algorithms & Programming](https://apclassroom.collegeboard.org/103/home?unit=3) |
| Apr 24     | [Big Idea 4: Computer Systems & Networks](https://apclassroom.collegeboard.org/103/home?unit=4) |
| Apr 25     | [Big Idea 5: Impact of Computing](https://apclassroom.collegeboard.org/103/home?unit=5) |
| Apr 26     | Review: Binary + Number Systems            |
| Apr 27     | Practice FRQs: Abstraction                 |
| Apr 28     | Practice FRQs: Data & Algorithms           |
| Apr 29     | Practice FRQs: Simulations + Events        |
| Apr 30     | Review: Vocabulary & Concepts              |
| May 1      | Practice MCQs: Units 1–3                   |
| May 2      | Practice MCQs: Units 4–5                   |
| May 3      | FRQ Practice Set 1 (Timed)                 |
| May 4      | Debugging & Logic Flow Practice            |
| May 5      | Internet + Cybersecurity Focus             |
| May 6      | Function Writing + Parameters Practice     |
| May 7      | FRQ Practice Set 2 (Timed)                 |
| May 8      | Algorithm Tracing + Flowcharts             |
| May 9      | Practice MCQs: Full Mixed Set              |
| May 10     | FRQ Practice Set 3 (Untimed + Feedback)    |
| May 11     | Concept Review: Weakest Areas              |
| May 12     | Full-Length Mock Test (Timed)              |
| May 13     | Review Mistakes from Practice MCs          |
| May 14     | Light Review + Rest + Confidence           |
| **May 15** | **✅ Test Day**            |



<div style="margin: 20px 0;">
  <h2>🧠 Practice with Flashcards!</h2>
  <iframe 
    src="https://quizlet.com/593721377/match/embed?i=4v4pqu&x=1jj1" 
    height="500" 
    width="100%" 
    style="border:0"
    allowfullscreen
    loading="lazy">
  </iframe>
</div>


<div style="margin-top: 2rem;">
  <h2>Study Videos: AP CSP Crash Courses</h2>

  <!-- Unit 1 -->
  <h3 style="color:#4f46e5;">Big Idea 1: Creative Development</h3>
  <iframe width="100%" height="315" src="https://www.youtube.com/embed/CjKUtZHkJ9M" frameborder="0" allowfullscreen></iframe>

  <!-- Unit 2 -->
  <h3 style="color:#4f46e5;">Big Idea 2: Data</h3>
  <iframe width="100%" height="315" src="https://www.youtube.com/embed/nKIu9yen5nc" frameborder="0" allowfullscreen></iframe>

  <!-- Unit 3 -->
  <h3 style="color:#4f46e5;">Big Idea 3: Algorithms & Programming</h3>
  <iframe width="100%" height="315" src="https://www.youtube.com/embed/IqtpV9x42qY" frameborder="0" allowfullscreen></iframe>

  <!-- Unit 4 -->
  <h3 style="color:#4f46e5;">Big Idea 4: Computer Systems & Networks</h3>
  <iframe width="100%" height="315" src="https://www.youtube.com/embed/qMO-LTOrJaE" frameborder="0" allowfullscreen></iframe>

  <!-- Unit 5 -->
  <h3 style="color:#4f46e5;">Big Idea 5: Impact of Computing</h3>
  <iframe width="100%" height="315" src="https://www.youtube.com/embed/4Q0gYjAVonI" frameborder="0" allowfullscreen></iframe>
</div>

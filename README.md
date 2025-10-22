<section class="quiz-container">
  <h2>AI & Data Career Fit Quiz</h2>
  <p>Discover which AI or Data role fits your strengths and interests.</p>

  <form id="careerQuiz">
    <div class="question">
      <p><strong>1. What type of problems excite you the most?</strong></p>
      <label><input type="radio" name="q1" value="Insight"> Finding patterns in numbers</label><br>
      <label><input type="radio" name="q1" value="Engineering"> Building or improving systems</label><br>
      <label><input type="radio" name="q1" value="Business"> Understanding people and impact</label><br>
      <label><input type="radio" name="q1" value="Design"> Designing creative AI solutions</label>
    </div>

    <div class="question">
      <p><strong>2. Which tool sounds most interesting to you?</strong></p>
      <label><input type="radio" name="q2" value="Insight"> Excel or Power BI</label><br>
      <label><input type="radio" name="q2" value="Engineering"> Databases or Cloud</label><br>
      <label><input type="radio" name="q2" value="Design"> AI Design Tools</label><br>
      <label><input type="radio" name="q2" value="AIResearch"> Statistical Tools</label>
    </div>

    <button type="button" onclick="calculateResult()">See My Career Fit</button>
  </form>

  <div id="result" class="result-box"></div>
</section>

<script>
function calculateResult() {
  const form = document.forms['careerQuiz'];
  const categories = {Insight:0, Engineering:0, Business:0, Design:0, AIResearch:0};
  for (let q of ['q1','q2']) {
    const answer = form[q].value;
    if (answer) categories[answer]++;
  }

  const bestFit = Object.keys(categories).reduce((a,b)=>categories[a]>categories[b]?a:b);
  const messages = {
    Insight: "You are analytical and logical — great fit for Data Analyst, BI, or Statistician roles.",
    Engineering: "You like structure and systems — Data Engineer or Cloud Engineer could be perfect.",
    Business: "You connect data and decisions — ideal for Business Analyst or Product Manager roles.",
    Design: "You’re creative and innovative — explore Generative AI Design or Product roles.",
    AIResearch: "You love exploring deep questions — consider AI Research or Machine Learning."
  };
  document.getElementById('result').innerHTML = `<h3>Your Best Fit:</h3><p>${messages[bestFit]}</p>`;
}
</script>

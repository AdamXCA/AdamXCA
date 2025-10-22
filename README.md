# 🎯 AI & Data Career Fit Quiz

This is a beginner-friendly, educational quiz designed to help students and professionals discover which career in the AI and Data field best suits their interests.

It's a self-contained HTML file with no external dependencies (besides Google Fonts), making it easy to deploy on GitHub Pages, a personal website, or even use offline.

## ✨ Features

* **20 Guided Questions:** The quiz is split into 5 sections covering real-world scenarios, AI impact, technical skills, learning style, and future aspirations.
* **Modern "High-Tech" UI:** A sleek, dark-mode interface built to look professional and engaging.
* **Educational Hints:** Each question includes a hint with a "Learn More" link to explain key technical terms (e.g., "Large Language Models," "Data Engineering").
* **Dynamic Progress Bar:** A visual bar at the top shows the user's completion progress.
* **Standardized Answers:** All questions use a 5-point interest scale, making the quiz fast to take and easy to score.
* **Save & Print Results:** Users can save their submission as a `.txt` file or print a clean, formatted report (to PDF).
* **Zero Dependencies:** Built with pure HTML, CSS, and vanilla JavaScript.

## 🚀 How to Use

1.  **Clone or Download:**
    * Clone this repository: `git clone https://github.com/YOUR_USERNAME/YOUR_REPONAME.git`
    * OR, simply download the `tech_quiz.html` file.
2.  **Open:** Open the `tech_quiz.html` file in any modern web browser (like Chrome, Firefox, or Edge).
3.  **Take the Quiz:** Complete the 20 questions.
4.  **Save:** Once you submit, you'll see options to "Print Results (as PDF)" or "Download Answers (.txt)".

## 🛠️ How It Works (For Developers)

The quiz is built on three core components within the single HTML file:

* **HTML:** The structure of the quiz, using `<fieldset>` and `<legend>` for sections and custom-styled radio buttons for options.
* **CSS:** All styling is contained within the `<style>` tag. It handles the dark mode, "button-like" options, and the dynamic progress bar. It also includes `@media print` rules to create a clean, printable report that hides the quiz and UI elements.
* **JavaScript:** The `<script>` tag at the bottom handles all logic:
    * **Progress Bar:** An event listener on the form updates the progress bar's width on any `change` event.
    * **Submission:** The `submit` listener prevents the default form action and displays the results section.
    * **Result Saving:**
        * **Print:** The "Print" button simply calls `window.print()`. The CSS print styles do the rest.
        * **Download:** The "Download" button dynamically gathers all question text and the selected answers, formats them into a string, creates a `Blob` (a file in memory), and triggers a browser download for the user.

## 🤝 How to Contribute

This quiz is a great starting point, but the most important piece is ready for you to build!

**The #1 area for contribution is the `SCORING LOGIC`.**

Currently, the JavaScript `submit` listener *only* shows the results section. It doesn't actually calculate a score.

### Your Mission:

Inside the `form.addEventListener('submit', ...)` function, add your own scoring logic. Here's a suggested path:

1.  **Define Career Profiles:** Create a `scores` object (e.g., `scores = { dataAnalyst: 0, mlEngineer: 0, dataEngineer: 0, aiStrategist: 0 }`).
2.  **Get Form Data:** Use `const formData = new FormData(form);` to get all the answers.
3.  **Map Questions to Profiles:** Loop through each question and add points to the appropriate profile based on the answer. For example:
    * **Q20 ("...translating complex data into simple stories")** should add a lot of points to `scores.dataAnalyst`.
    * **Q19 ("...designing the massive systems")** should add a lot of points to `scores.dataEngineer`.
    * **Q18 ("...building and training the complex AI models")** should add a lot of points to `scores.mlEngineer`.
    * **Q14 ("...more interested in the 'big picture' strategy")** should add points to `scores.aiStrategist`.
4.  **Calculate & Display Results:** Sort the `scores` object to find the user's top 3 matching careers.
5.  **Update the Results Div:** Instead of the placeholder, populate the `#results` div with the user's personalized report.

## 📄 License

This project is open-sourced under the [MIT License](LICENSE).

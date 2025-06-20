<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MCQ Test Paper</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 40px;
            line-height: 1.6;
        }
        .quiz-container {
            max-width: 800px;
            margin: auto;
            padding: 20px;
            border: 1px solid #ccc;
            border-radius: 10px;
        }
        .question {
            margin-bottom: 20px;
        }
        .question h3 {
            margin-bottom: 10px;
            color: #333;
        }
        .options label {
            display: block;
            margin: 5px 0;
        }
        .submit-btn {
            background-color: #4CAF50;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        .submit-btn:hover {
            background-color: #45a049;
        }
        #result {
            margin-top: 20px;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <div class="quiz-container">
        <h1>MCQ Test Paper</h1>
        <form id="quiz-form">
            <div class="question">
                <h3>1. What is the capital of France?</h3>
                <div class="options">
                    <label><input type="radio" name="q1" value="a"> a) Paris</label>
                    <label><input type="radio" name="q1" value="b"> b) London</label>
                    <label><input type="radio" name="q1" value="c"> c) Berlin</label>
                    <label><input type="radio" name="q1" value="d"> d) Madrid</label>
                </div>
            </div>
            <div class="question">
                <h3>2. Which planet is known as the Red Planet?</h3>
                <div class="options">
                    <label><input type="radio" name="q2" value="a"> a) Jupiter</label>
                    <label><input type="radio" name="q2" value="b"> b) Mars</label>
                    <label><input type="radio" name="q2" value="c"> c) Venus</label>
                    <label><input type="radio" name="q2" value="d"> d) Mercury</label>
                </div>
            </div>
            <div class="question">
                <h3>3. What is 2 + 2?</h3>
                <div class="options">
                    <label><input type="radio" name="q3" value="a"> a) 3</label>
                    <label><input type="radio" name="q3" value="b"> b) 4</label>
                    <label><input type="radio" name="q3" value="c"> c) 5</label>
                    <label><input type="radio" name="q3" value="d"> d) 6</label>
                </div>
            </div>
            <button type="submit" class="submit-btn">Submit Answers</button>
        </form>
        <div id="result"></div>
    </div>

    <script>
        document.getElementById('quiz-form').addEventListener('submit', function(event) {
            event.preventDefault();
            let score = 0;
            const answers = {
                q1: 'a',
                q2: 'b',
                q3: 'b'
            };

            for (let i = 1; i <= 3; i++) {
                const selected = document.querySelector(`input[name="q${i}"]:checked`);
                if (selected && selected.value === answers[`q${i}`]) {
                    score++;
                }
            }

            const resultDiv = document.getElementById('result');
            resultDiv.innerHTML = `You scored ${score} out of 3!`;
        });
    </script>
</body>
</html>

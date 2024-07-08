<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BMI Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 50px;
            background-color: #f4f4f4;
        }

        #bmi-container {
            max-width: 400px;
            margin: 0 auto;
            background-color: #ffffff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }

        h1 {
            color:#333333
          ;
        }

        label {
            display: block;
            margin-top: 10px;
            font-weight: bold;
            color: #333333;
        }

        input {
            width: 100%;
            padding: 8px;
            margin-top: 6px;
            margin-bottom: 10px;
            box-sizing: border-box;
            border: 1px solid #ccc;
            border-radius: 4px;
        }

        button {
            background-color: #4caf50;
            color: #ffffff;
            padding: 10px 15px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }

        #result {
            font-weight: bold;
            margin-top: 20px;
            color: #333333;
        }
    </style>
</head>
<body>
    <div id="bmi-container">
        <h1>BMI Calculator</h1>

        <label for="weight">Weight (kg):</label>
        <input type="text" id="weight" placeholder="Enter Weight" required>

        <label for="height">Height (cm):</label>
        <input type="text" id="height" placeholder="Enter Height" required>

        <button onclick="calculateBMI()">Calculate BMI</button>

        <div id="result"></div>
    </div>

    <script>
        function calculateBMI() {
            var weight = parseFloat(document.getElementById('weight').value);
            var height = parseFloat(document.getElementById('height').value);

            if (isNaN(weight) || isNaN(height) || weight <= 0 || height <= 0) {
                document.getElementById('result').innerHTML = "Please enter valid weight and height.";
                return;
            }

            var bmi = weight / Math.pow(height / 100, 2);
            document.getElementById('result').innerHTML = "Your BMI is: " + bmi.toFixed(2);
        }
    </script>
</body>
</html>

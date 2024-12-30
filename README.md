# T-W-Calculator
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tuition Fee Calculator</title>
</head>
<body>
    <h1>Tuition Fee Calculator</h1>
    <p>Total Cost for Spring 2025: 84,267 tk.</p>
    <p>Registration Time Payment: 33,867 tk.</p>

    <label for="waiver">Enter your waiver percentage (e.g., 50): </label>
    <input type="number" id="waiver" placeholder="0"><br><br>

    <label for="paid">Enter how much you paid at registration (e.g., 33867): </label>
    <input type="number" id="paid" placeholder="0"><br><br>

    <button onclick="calculate()">Calculate</button>

    <h2 id="result"></h2>

    <script>
        function calculate() {
            const totalTuition = 69600;
            const semesterFee = 14667;
            const regTimePayable = 33867;

            // Get user inputs
            const waiverPercent = parseFloat(document.getElementById("waiver").value) || 0;
            const paid = parseFloat(document.getElementById("paid").value) || 0;

            // Calculate waiver amount
            const waveAmount = totalTuition * (waiverPercent / 100);

            // Calculate payable amounts
            const afterWaiver = totalTuition - waveAmount;
            const totalPayable = afterWaiver + semesterFee;
            const beforeFinal = totalPayable - paid;

            // Display the results
            document.getElementById("result").innerText =
                `Total Payable: ${totalPayable} tk\nRemaining Before Final: ${beforeFinal} tk`;
        }
    </script>
</body>
</html>

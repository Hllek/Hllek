<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Random Name Picker with Demon</title>
</head>
<body>
    <h1>Random Name Picker</h1>
    <p id="randomName">Click the demon to pick a random name!</p>
    
    <!-- ปุ่มรูปปีศาจ -->
    <img src="https://drive.google.com/uc?export=view&id=1_GSH_yEm9J7E_zbiolN0Zy5zp-t1hwBm" alt="Random Demon" style="width:300px;height:300px;cursor:pointer;" onclick="pickRandomName()">

    <script>
        // รายชื่อ 30 คน
        const names = [
            "Person 1", "Person 2", "Person 3", "Person 4", "Person 5",
            "Person 6", "Person 7", "Person 8", "Person 9", "Person 10",
            "Person 11", "Person 12", "Person 13", "Person 14", "Person 15",
            "Person 16", "Person 17", "Person 18", "Person 19", "Person 20",
            "Person 21", "Person 22", "Person 23", "Person 24", "Person 25",
            "Person 26", "Person 27", "Person 28", "Person 29", "Person 30"
        ];

        // รายชื่อคนที่ไม่ต้องการให้ถูกเลือก
        const excludedNames = ["Person 5", "Person 10", "Person 15"];

        // ฟังก์ชันสุ่มชื่อ 1 คนโดยไม่เลือกคนที่อยู่ใน excludedNames
        function pickRandomName() {
            let availableNames = names.filter(name => !excludedNames.includes(name));
            if (availableNames.length === 0) {
                document.getElementById("randomName").innerText = `No names left to choose from.`;
                return;
            }
            const randomIndex = Math.floor(Math.random() * availableNames.length);
            const chosenName = availableNames[randomIndex];
            document.getElementById("randomName").innerText = `The chosen person is: ${chosenName}`;
        }
    </script>
</body>
</html>

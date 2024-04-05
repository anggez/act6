<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Name and Age Remarks</title>
<style>
    body {
        font-family: Arial, sans-serif;
        margin: 0;
        padding: 0;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        background-color: #f0f0f0;
        font-size: xx-large;
        background-image: url(https://i.pinimg.com/736x/3a/e0/1f/3ae01f8bdec9c5acfdd07bdd40c22c86.jpg);
        background-repeat: no-repeat;
        background-size: 100%;
    }

    #form-container {
        text-align: center;
        padding: 20px;
        border: 1px solid #323dda;
        border-radius: 5px;
        background-color: rgb(214, 164, 195);
        box-shadow: 5PX 5PX  lightcoral;
    }
</style>
</head>
<body>
<div id="form-container">
    <h2>ACTIVITY 6</h2>
    <form>
        <label for="name">Name:</label>
        <input type="text" id="name" required><br><br>
        <label for="age">Age:</label>
        <input type="number" id="age" required><br><br>
       
        <button type="button" onclick="generateRemarks()"> Remarks</button>
    </form>
    <div id="remarks"></div>
</div>

<script>
    function generateRemarks() {
        var name = document.getElementById('name').value;
        var age = parseInt(document.getElementById('age').value);

        var remarks = document.getElementById('remarks');
        remarks.innerHTML = '';

        if (isNaN(age)) {
            remarks.innerHTML = 'Please enter a valid age.';
            return;
        }

        if (age < 0) {
            remarks.innerHTML = 'Age cannot be negative.';
            return;
        }

        var remarkText = '';

        if (age <= 12) {
            remarkText = 'Hello, ' + name + '! You are still young.';
        } else if (age <= 18) {
            remarkText = 'Hello, ' + name + '! You are a teenager.';
        } else if (age <= 30) {
            remarkText = 'Hello, ' + name + '! You are a young adult.';
        } else if (age <= 60) {
            remarkText = 'Hello, ' + name + '! You are an adult.';
        } else {
            remarkText = 'Hello, ' + name + '! You are a senior citizen.';
        }

        remarks.innerHTML = remarkText;
    }
</script>
</body>
</html>

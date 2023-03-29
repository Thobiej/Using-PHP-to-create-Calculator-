# Using-PHP-to-create-Calculator-


<?php
    // Check if the form has been submitted
    if(isset($_POST['submit'])){
        // Retrieve the values from the form
        $num1 = $_POST['num1'];
        $num2 = $_POST['num2'];
        $operator = $_POST['operator'];

        // Check which operation to perform
        switch($operator){
            case "+":
                $result = $num1 + $num2;
                break;
            case "-":
                $result = $num1 - $num2;
                break;
            case "*":
                $result = $num1 * $num2;
                break;
            case "/":
                $result = $num1 / $num2;
                break;
            default:
                $result = "Invalid operator";
        }
    }
?>

<!DOCTYPE html>
<html>
<head>
    <title>Calculator</title>
</head>
<body>
    <form method="post" action="">
        <label>Number 1:</label>
        <input type="text" name="num1"><br>

        <label>Number 2:</label>
        <input type="text" name="num2"><br>

        <label>Operator:</label>
        <select name="operator">
            <option value="+">+</option>
            <option value="-">-</option>
            <option value="*">*</option>
            <option value="/">/</option>
        </select><br>

        <input type="submit" name="submit" value="Calculate">
    </form>

    <?php
        // Output the result
        if(isset($result)){
            echo "Result: " . $result;
        }
    ?>
</body>
</html>

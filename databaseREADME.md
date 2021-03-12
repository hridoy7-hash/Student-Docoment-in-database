# Student-Docoment-in-database
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PHP LEARNING</title>
</head>
<?php

if(isset($_POST['submit'])){
    $firstname=$_POST['firstname'];
    $lastname=$_POST['lastname'];
    $department=$_POST['department'];
    $session=$_POST['session'];
    $contact=$_POST['contactnumber'];

    $connection = mysqli_connect('localhost','root','','student_docoment');

    if(!$connection){
        die ("Not connected ".mysqli_error($connection));
    }
     //INSERT INTO `student_docoment` (`Id`, `First name`, `Last name`, `Department`, `Session`, `Contact number`) VALUES (NULL, 'Sagor', 'Rahman', 'CSE', '2017', '01745934072');
    $query = "INSERT INTO `student_docoment` (`First name`, `Last name`, `Department`, `Session`, `Contact number`)";
    $query.= "VALUES ('$firstname','$lastname',' $department','$session','$contact')";

    $result = mysqli_query($connection,$query);
    if(!$result){
        die ("data insert unsuccessfull".mysqli_error($connection)) ;
    }

}
?>
<body>

        <form action="index.php" method="post">
        <input type="text" name="firstname" placeholder="USER NAME">
        <input type="text" name="lastname" placeholder="LAST NAME">
        <input type="text" name="department" placeholder="DEPARTMENT">
        <input type="text" name="session" placeholder="SESSION">
        <input type="text" name="contactnumber" placeholder="CONTACTNUMBER">
        <input type="submit" name="submit" value="submit">

</form>

</body>
</html>

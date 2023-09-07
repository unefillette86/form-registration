<?php
header('Content-Type: text/html; charset=utf-8');
$mysqli = mysqli_connect("localhost", "rzczxmuv_users", "12345678", "rzczxmuv_users");
if ($mysqli == false){
    print("error");
}else {
 $email = $_POST["email"];
 $password = $_POST["password"];

 $result = $mysqli->query("SELECT * FROM `users` WHERE `email` = '$email'");

if ($result->num_rows != 0){
print("exist");
} else {
$mysqli->query("INSERT INTO `users`(`email`, `password`) VALUES ('$email', '$password')");
print("Ok");
	 }

}


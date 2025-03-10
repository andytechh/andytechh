- 👋 Hi, I’m Andy G. Lazarte 2nd year BSIT Student
- 👀 I’m interested in backend development
- 🌱 I’m currently learning c++ and java
- 💞️ I’m looking to collaborate on any projects in c++
- 📫 How to reach me? dm me on my fb account https://www.facebook.com/profile.php?id=100031935578704
- Portfolio -[ https://main--whimsical-cassata-73e697.netlify.app/](https://myportfolio-andy.netlify.app/)

<!---
andytechh/andytechh is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
https://www.figma.com/design/lGuqUQJdSZvV0tNcmmfya4/Untitled?node-id=1-2&t=UjovqP2ujPcfGQUB-1
--->
<?php
$servername = "localhost";
$username = "root"; // Change this if you have a different MySQL user
$password = ""; // Change this if you have set a password for MySQL
$database = "user_database";

// Create connection
$conn = new mysqli($servername, $username, $password, $database);

// Check connection
if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}
?>
<?php
session_start();
include 'connection.php';

if ($_SERVER["REQUEST_METHOD"] == "POST") {
    $username = $_POST['username'];
    $password = $_POST['password'];

    $sql = "SELECT * FROM user WHERE username='$username'";
    $result = $conn->query($sql);

    if ($result->num_rows > 0) {
        $row = $result->fetch_assoc();
        if (password_verify($password, $row['password'])) {
            $_SESSION['username'] = $username;
            header("Location: welcome.php");
            exit();
        } else {
            echo "Invalid password.";
        }
    } else {
        echo "User not found.";
    }
}

$conn->close();
?>

<form method="post">
    Username: <input type="text" name="username" required><br>
    Password: <input type="password" name="password" required><br>
    <input type="submit" value="Login">
</form>





<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sign Up - GreenTech Solutions</title>

    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f9;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        .container {
            background-color: white;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            padding: 40px;
            width: 350px;
        }

        h2 {
            text-align: center;
            color: #2a9d8f;
            margin-bottom: 20px;
        }

        label {
            display: block;
            font-weight: bold;
            margin-top: 10px;
            color: #333;
        }

        input[type="text"],
        input[type="email"],
        input[type="password"],
        input[type="date"],
        input[type="tel"],
        textarea {
            width: 100%;
            padding: 10px;
            margin: 8px 0;
            border: 1px solid #ddd;
            border-radius: 4px;
            box-sizing: border-box;
        }

        textarea {
            resize: vertical;
            height: 80px;
        }

        input[type="submit"] {
            background-color: #2a9d8f;
            color: white;
            padding: 12px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            width: 100%;
            margin-top: 15px;
        }

        input[type="submit"]:hover {
            background-color: #21867a;
        }

        .error {
            color: red;
            font-size: 12px;
        }
    </style>

    <script>
        function validateForm() {
            var firstName = document.getElementById("firstName").value;
            var lastName = document.getElementById("lastName").value;
            var email = document.getElementById("email").value;
            var password = document.getElementById("password").value;
            var confirmPassword = document.getElementById("confirmPassword").value;
            var phone = document.getElementById("phone").value;
            var address = document.getElementById("address").value;
            var dob = document.getElementById("dob").value;

            var valid = true;

            // Clear previous errors
            var errorMessages = document.querySelectorAll('.error');
            errorMessages.forEach(function(msg) {
                msg.textContent = '';
            });

            // Validate First Name
            if (firstName == "") {
                document.getElementById("firstNameError").textContent = "First Name is required.";
                valid = false;
            }

            // Validate Last Name
            if (lastName == "") {
                document.getElementById("lastNameError").textContent = "Last Name is required.";
                valid = false;
            }

            // Validate Email
            var emailPattern = /^[a-zA-Z0-9._-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,4}$/;
            if (email == "") {
                document.getElementById("emailError").textContent = "Email is required.";
                valid = false;
            } else if (!emailPattern.test(email)) {
                document.getElementById("emailError").textContent = "Please enter a valid email address.";
                valid = false;
            }

            // Validate Password
            if (password == "") {
                document.getElementById("passwordError").textContent = "Password is required.";
                valid = false;
            }

            // Validate Confirm Password
            if (confirmPassword == "") {
                document.getElementById("confirmPasswordError").textContent = "Please confirm your password.";
                valid = false;
            } else if (password != confirmPassword) {
                document.getElementById("confirmPasswordError").textContent = "Passwords do not match.";
                valid = false;
            }

            // Validate Phone Number
            var phonePattern = /^\d{10}$/;
            if (phone == "") {
                document.getElementById("phoneError").textContent = "Phone Number is required.";
                valid = false;
            } else if (!phonePattern.test(phone)) {
                document.getElementById("phoneError").textContent = "Please enter a valid 10-digit phone number.";
                valid = false;
            }

            // Validate Address
            if (address == "") {
                document.getElementById("addressError").textContent = "Address is required.";
                valid = false;
            }

            // Validate Date of Birth
            if (dob == "") {
                document.getElementById("dobError").textContent = "Date of Birth is required.";
                valid = false;
            }

            return valid;
        }
    </script>
</head>
<body>
    <div class="container">
        <h2>Sign Up - GreenTech Solutions</h2>
        <form onsubmit="return validateForm()">
            <label for="firstName">First Name:</label>
            <input type="text" id="firstName" name="firstName">
            <div class="error" id="firstNameError"></div>

            <label for="lastName">Last Name:</label>
            <input type="text" id="lastName" name="lastName">
            <div class="error" id="lastNameError"></div>

            <label for="email">Email:</label>
            <input type="email" id="email" name="email">
            <div class="error" id="emailError"></div>

            <label for="password">Password:</label>
            <input type="password" id="password" name="password">
            <div class="error" id="passwordError"></div>

            <label for="confirmPassword">Confirm Password:</label>
            <input type="password" id="confirmPassword" name="confirmPassword">
            <div class="error" id="confirmPasswordError"></div>

            <label for="phone">Phone Number:</label>
            <input type="tel" id="phone" name="phone">
            <div class="error" id="phoneError"></div>

            <label for="address">Address:</label>
            <textarea id="address" name="address"></textarea>
            <div class="error" id="addressError"></div>

            <label for="dob">Date of Birth:</label>
            <input type="date" id="dob" name="dob">
            <div class="error" id="dobError"></div>

            <input type="submit" value="Sign Up">
        </form>
    </div>
</body>
</html>



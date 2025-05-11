<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login Form</title>
    <link href="https://cdn.jsdelivr.net/npm/remixicon@4.5.0/fonts/remixicon.css" rel="stylesheet" />
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        .su {
            color: white;
            transition: 0.5s ease;
        }

        .su:hover {
            color: rgb(186, 186, 186);
        }

        .fp {
            color: white;
            transition: 0.5s ease;
        }

        .fp:hover {
             color: rgb(186, 186, 186);
        }

    </style>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.5/dist/css/bootstrap.min.css" rel="stylesheet"
        integrity="sha384-SgOJa3DmI69IUzQ2PVdRZhwQ+dy64/BUtbMJw1MZ8t5HZApcHrRKUc4W0kG879m7" crossorigin="anonymous" />
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.5/dist/js/bootstrap.bundle.min.js"
        integrity="sha384-k6d4wzSIapyDyv1kpU366/PK5hCdSbCRGRCMv+eplOQJWyd1fbcAu9OCUj5zNLiq"
        crossorigin="anonymous"></script>
</head>

<body class="d-flex justify-content-center align-items-center bg-dark-subtle" style="height: 100vh;">
    <div class="bg-dark p-3 rounded">
        <form action="#">

            <h3 class="text-center text-white">Please Login Here</h3>
            <div class="justify-content-center align-items-center m-auto mt-3">
                <input class="form-control border border-1 border-dark" type="email" id="emailInput"
                    placeholder="Enter your Email*" required autocomplete="username">
                    <div id="emailError" class="text-danger fw-bold text-capitalize" style="font-size: 12px;"></div><br>

                <input class="form-control border border-1 border-dark" type="password" id="passwordInput"
                    placeholder="Enter your password*" autocomplete="current-password" required>
                <div id="passwordError" class="text-danger fw-bold text-capitalize" style="font-size: 12px;"></div>

                <div class="ms-2 d-flex mt-1" style="gap: 43%;">
                    <a href="Sign_up.html" class="su text-decoration-none" style="font-size: 11px;">Sign UP</a>
                    <a href="#" class="fp text-decoration-none" style="font-size: 11px;">Forgot Password</a>
                </div>
                <br>

                <button onclick="loginDetail(event)"
                    class="form-control btn btn-dark border border-2 border-white">Login</button>
            </div>
        </form>
    </div>

</body>
<script src="Login.js"></script>

</html>

function loginDetail(event) {
    event.preventDefault();

    const email = document.getElementById('emailInput').value.trim();
    const password = document.getElementById('passwordInput').value.trim();

    const emailError = document.getElementById('emailError');
    const passwordError = document.getElementById('passwordError');

    emailError.textContent = "";
    passwordError.textContent = "";

    let isValid = true;

    if (email === "") {
        emailError.textContent = "Email is Required";
        isValid = false;
    }

    else if (!email.includes("@") || !email.includes('.')) {
        emailError.textContent = "Please Enter Valid Email!";
        isValid = false;
    }


    if (password === "") {
        passwordError.textContent = "Password is Required!"
        isValid = false;
    }

    else if (password.length < 6) {
        passwordError.textContent = "Password must be at least 6 characters!";
        isValid = false;
    }

    document.getElementById('emailInput').addEventListener('input', function () {
        document.getElementById('emailError').textContent = "";
    });


    document.getElementById('passwordInput').addEventListener('input', function () {
        document.getElementById('passwordError').textContent = "";
    });

    if (isValid) {
        alert("Login Successfull")
    }
}


/*Upper login form*/

/*Down login form*/

<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Sign Up Form</title>
  <link href="https://cdn.jsdelivr.net/npm/remixicon@4.5.0/fonts/remixicon.css" rel="stylesheet" />
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.5/dist/css/bootstrap.min.css" rel="stylesheet"
    crossorigin="anonymous" />
  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.5/dist/js/bootstrap.bundle.min.js"
    crossorigin="anonymous"></script>

  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    .li {
      color: white;
      transition: 0.5s ease;
    }

    .li:hover {
      color: rgb(186, 186, 186);
    }

    .fp {
      color: white;
      transition: 0.5s ease;
    }

    .fp:hover {
      color: rgb(186, 186, 186);
    }
  </style>
</head>

<body class="d-flex justify-content-center align-items-center bg-dark-subtle" style="height: 100vh;">
  <div class="bg-dark p-3 rounded">
    <form>

      <h3 class="text-center text-white">Please Login Here</h3>
      <div class="justify-content-center align-items-center m-auto mt-3">

        <input class="form-control border border-1 border-dark" type="email" id="emailInput"
          placeholder="Enter your Email*" required autocomplete="username" />
        <div id="emailError" class="text-danger fw-bold text-capitalize" style="font-size: 11px;"></div><br />

        <input class="form-control border border-1 border-dark" type="password" id="passwordInput"
          placeholder="Enter your password*" autocomplete="current-password" required />
        <div id="passwordError" class="text-danger fw-bold text-capitalize" style="font-size: 11px;"></div><br />

        <input type="password" id="confirmPassInput" class="form-control border border-1 border-dark"
          placeholder="Confirm your password*" autocomplete="current-password" required />
        <div id="confirmPassError" class="text-danger fw-bold text-capitalize" style="font-size: 11px;"></div>

        <div class="ms-2 d-flex mt-2" style="gap: 48%;">
          <a href="Login.html" class="li text-decoration-none" style="font-size: 11px;">Login</a>
          <a href="#" class="fp text-decoration-none" style="font-size: 11px;">Forgot Password</a>
        </div>
        <br />

        <button onclick="loginDetail(event)" class="form-control btn btn-dark border border-2 border-white">
          Login
        </button>
      </div>
    </form>
  </div>

  <script src="Sign_up.js"></script>
</body>

</html>


// Error clear on input
document.getElementById('emailInput').addEventListener('input', function () {
    document.getElementById('emailError').textContent = "";
});

document.getElementById('passwordInput').addEventListener('input', function () {
    document.getElementById('passwordError').textContent = "";
});

document.getElementById('confirmPassInput').addEventListener('input', function () {
    document.getElementById('confirmPassError').textContent = "";
});

// Validation
function loginDetail(event) {
    event.preventDefault();

    const email = document.getElementById('emailInput').value.trim();
    const password = document.getElementById('passwordInput').value.trim();
    const confirm = document.getElementById('confirmPassInput').value.trim();

    const emailError = document.getElementById('emailError');
    const passwordError = document.getElementById('passwordError');
    const confirmPassError = document.getElementById('confirmPassError');

    emailError.textContent = "";
    passwordError.textContent = "";
    confirmPassError.textContent = "";

    let isValid = true;

    if (email === "") {
        emailError.textContent = "Email is required";
        isValid = false;
    }

    else if (!email.includes("@") || !email.includes(".")) {
        emailError.textContent = "Please enter a valid email!";
        isValid = false;
    }

    if (password === "") {
        passwordError.textContent = "Password is required!";
        isValid = false;
    }

    else if (password.length < 6) {
        passwordError.textContent = "Password must be at least 6 characters!";
        isValid = false;
    }

    if (confirm === "") {
        confirmPassError.textContent = "Enter confirm password!";
        isValid = false;
    }

    else if (confirm.length < 6) {
        confirmPassError.textContent = "Confirm password must be at least 6 characters!";
        isValid = false;
    }

    else if (confirm !== password) {
        confirmPassError.textContent = "Passwords do not match!";
        confirmPassError.classList.remove("text-danger");
        confirmPassError.style.color = "yellow";
        isValid = false;
    }

    if (isValid) {
        alert("Login Successful");
    }
}

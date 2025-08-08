<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <mete name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>login</title>
  <style>
    body {
        font-family:Times New Roman, Sans-Serif;
        background-color:#7FFFD4;
        display: flex;
        align-items: center;
        justify-content: center;
        height: 100vh;
        margin: 0;
    }
    .login-container {
        background: #fff;
        padding: 20px;
        border-radius: 8px;
        text-align: center;
        width: 280px;
    }
    input,button {
        width:  100%;
        padding:  10px;
        margin: 10px 0;
        border: 1px solid #ccc;
        border-radius: 5px;
    }

    button {
        background: #4CAF50;
        color:	white;
        border: none;
        cursor:	pointer;
    }
    .hidden {
      display: none;
    }
    
    .error {
      color: red;
      font-size: 14px;
      margin-top: -5px;
    }
  </style>
</head>
<body>  
<div class="login-container" id="loginbox">
     <h2>login</h2>
      <input type="text" id="Username" placeholder="Username"/>
      <input type="password" id="password" placeholder="password"/>
      <div id="errorMsg" class="error hidden"></div>
      <button onclick="login()">Login</button>
</div>

<dis class="login-container hidden" id="welcomeBox">
      <h2>selamat datang</h2>
      <p id="welcomeUser"></p>
      <button onclick="logout()">logout</button>
</div>
     
<script>
    const user = "nabila";
    const pass = "1818";
    
if(localStorage.getltem("loginUser")) {
    showWelome(localStorage.getltem("loginUser"));
}

function login(){
    cost uname = document.getElemenByld("username")value.trim();
    cost pwd = documentgetElemenByld("password")value.trim();
    cost errorMsg= documentgetElemenByld("errorMsg"); 

if(!uname|| !pwd) {
 errorMsg.textContent = "username  dan password  wajib diisi.";
 errorMsg.classL.List.remove("hidden");
 return;
}
 if(uname === user&& pwd === pass) {
     localStroge.setitem("loginUser",uname);
     showWelome(uname);
 } else {
     errorMsg.textContent = "Username atau password salah."; 
     errorMsg.classList.remove("hidden");
 }
}

function logout() {
  localStorage.removeltem("loginUser"); 
  document.getElementById("loginBox").classList.remove("hidden"); 
  document.getElementById("welcomeBox").classList.add("hidden"); 
  document.getElementById("errorMsg").classList.add("hidden"); 
  document.getElementById("username").value = "";
  document.getElementById("password").value = "";
}
function showWelcome(name) {
  document.getElementById("loginBox").classList.add("hidden"); 
  document.getElementById("welcomeBox").classList.remove("hidden");
  document.getElementById("welcomeUser").textContent = 'Halo, ${name}';
  
  
  
} 
</script>

</body>
</html>

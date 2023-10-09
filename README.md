This is js project
<!DOCTYPE HTML>
<html>
    <head>
        <meta name="viewport" content="width=device-width,initial-scale=1.0">
        <title>Password Strength Indicator</title>
    </head>
    <body>
        <div class="container">
         <div class="input-box">
            <input type="password" id="password" placeholder="Password">
            <button type="submit">Submit</button>
            <p id="message">Password is <span id="strength"></span></p>
         </div>
        </div>


        <style>
            *{
                margin: 0;
                padding: 0;
                font-family: 'poppins',sans-serif;
                box-sizing: border-box;
            }
            .container{
                height: 100vh;
                width: 100%;
                background: #201f21;
                display: flex;
                align-items: center;
                justify-content: center;
            }
            .input-box{
                width: 400px;
                max-width: 90%;
                position: relative;
            }
            .input-box input{
                width: 100%;
                height: 60px;
                padding: 0 20px;
                border: 1px solid #ccc;
                outline: none;
                color: #fff;
                background: transparent;
            }
            button{
                background: transparent;
                border: 0;
                outline: none;
                border-radius: 50%;
                cursor: pointer;
                position: absolute;
                top: 50%;
                transform: translateY(-50%);
                right: 15px;
            }
            #message{
                position: absolute;
                bottom: -30px;
                color: #fff;
                font-size: 15px;
                display: none;
            }
            ::placeholder{
                font-size: 15px;
            }
        </style>
        <script>
            var pass = document.getElementById("password");
            var msg = document.getElementById("message");
            var str = document.getElementById("strength");

            pass.addEventListener('input',()=>{
                if(pass.value.length > 0){
                    msg.style.display = "block";
                }
                else{
                    msg.style.display = "none";
                }
                if(pass.value.length < 4){
                    str.innerHTML = "weak";
                    pass.style.borderColor = "#ff5925";
                    msg.style.color = "#ff5925";
                }
                else if(pass.value.length >= 4 && pass.value.length < 8){
                    str.innerHTML = "medium";
                    pass.style.borderColor = "yellow";
                    msg.style.color = "yellow";
                }
                else if (pass.value.length >= 8){
                    str.innerHTML ="strong";
                    pass.style.borderColor = "#26d730";
                    msg.style.color = "#26d730";
                }
            })
        </script>
    </body>
</html>

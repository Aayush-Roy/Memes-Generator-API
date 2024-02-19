//Gnerate random memes using API
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<style>
    *{
        margin: 0;
        padding: 0;
    }
    .container{
        height: 510px;
        padding:15px 17px;
        width:450px;
        background-color: #7F27FF;
        border: 2px solid black;
    }
    #btn{
        width: 100%;
        padding:18px 25px;
        border: 0;
        font-weight: 600;
        font-size: 17px;
        background-color: #EBF400;
        border-bottom:5px solid #F57D1F;
border-radius: 4px;
        margin-top:10px;
    }
    body{
        min-height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        
    }
    #img-container{
        width: 100%;
        background-color:#F72798;
        height:445px;
        border:2px solid black;

    }
</style>
<body>
    <div class="container">
        <div id="img-container">

        </div>
        <button id="btn">GET</button>
    </div>
    
    <script>
       const url = "https://meme-api.com/gimme/wholesomememes";
       const btn = document.querySelector("#btn");
       const imgContainer = document.querySelector("#img-container");

       const getMeme = async ()=>{
        let response = await fetch(url);
        let data = await response.json();
        let imgElement = document.createElement("img");
        imgElement.src = data.url;
        imgElement.style.width = "100%";
        imgElement.style.height = "100%";
        imgContainer.innerHTML = "";
        imgContainer.appendChild(imgElement);
       }

       btn.addEventListener("click",getMeme);
     
    </script>
</body>
</html>

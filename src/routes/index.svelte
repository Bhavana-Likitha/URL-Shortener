<script>
    import Logo from "$lib/components/logo.svelte";
    import axios from 'axios';
    let url=''
    let shorturl='http://trim-url.vercel.app/'
    async function sendReq () {
        const response = await axios.post('https://url-shortener-manitej66.azurewebsites.net/api/shorten?code=USDsXCIeE0UKKJTi9pMWHTyQOFWIu2zAOmWmzcAW7PorrkqDeOcnHQ==',
        {
        "url": url
        }
        )
    shorturl = shorturl + response.data.shortUrl
    }
    </script>
    <Logo/>
    <body>
        <link rel="preconnect" href="https://fonts.gstatic.com">
        <link rel="preconnect" href="https://fonts.gstatic.com">
        <link href="https://fonts.googleapis.com/css2?family=Lato&display=swap" rel="stylesheet">
        <div class="img-cont">
    <img src="https://image.freepik.com/free-vector/www-concept-illustration_114360-2143.jpg" alt=""/>
        </div>
        <div>
            <h1>Shorten Any Links</h1>
            <p>Build and protect your brand using powerful <br> and recognizable short links. </p>
        </div>
    <div class="ib">
        <input bind:value={url} type="text" placeholder="Type or Paste your link">
        <button class ="button" on:click={sendReq}>SHORTEN</button>
    </div>
    <h3>{shorturl}</h3>
</body>
    <style>
        p{
            font-family: 'Lato', sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 18px;
        }
        h1{
            display: flex;
            justify-content: center;
            align-items: center;
            font-family: 'Lato', sans-serif;
            font-size: 35px;
        }
        .img-cont{
    display: flex;
    justify-content: center;
    }
    img{
        max-width: 100%;
        width: 300px;
        height: 300px;
    }
        .ib{
            display: flex;
            justify-content: center;
            align-items: center;
        }
        h3{
            display: flex;
            justify-content: center;
            align-items: center;
            font-family: 'Roboto', sans-serif;
        }
        input{
            width: 250px;
            height: 40px;
            border-radius: 10px;
            border: none;
            margin: 10px 0;
            padding:0 15px;
            outline: none;
            font-size: 0.9rem;  
            background: #ffff; 
            box-shadow: -10px -10px 15px rgb(236, 234, 234),
            10px 10px 10px rgb(241, 234, 234); 
            font-family: 'Lato', sans-serif;
                 }
            button{
                width: 150px;
                height: 40px;
                border: none;
                border-radius: 10px;
                outline: none;
                box-shadow: -10px -10px 15px rgb(236, 234, 234),
            10px 10px 10px rgb(241, 234, 234); 
                margin-left: 10px;
                font-family: 'Lato', sans-serif;
                font-weight: bold;
                transition: all 0.3s ease 0s;
                cursor: pointer;
                background-image: linear-gradient(315deg, #02aab0  0%,  #00cdac 74%);
    color: #fff;
            }
            .button:hover {
                background-image: linear-gradient(315deg, #02aab0  0%,  #00cdac 74%);
                color: #fff;
            
  transform: translateY(-7px);
}
@media(max-width:500px){
    img{
        max-width: 100%;
        width: 300px;
        height: 300px;
    }
    h3{
           font-size: 15px;
        }
}

    </style>
<script>
    import emailjs from '@emailjs/browser'
    (function(){
      emailjs.init("DZ-dLiRVZHpqsCR1B");
   })();
   let _name;
   let _email;
   let _body;
   const service_id='service_m4cg6he'
   const templateID='template_r0co7am'
   let sendEmail=()=>{
       var params={
           name:_name,
           email:_email,
           body:_body
        }
        emailjs.send(service_id,templateID,params)
        alert('Email sent')

   }

</script>

<body>
    <div class="main">
        <form class="form">
            <a href="/home" class="back">Go back</a>
            <br>
            <h2>Contact me</h2>
            <label for="name">Name:</label>
            <input type="text" placeholder="Enter your name" id="name" required bind:value={_name}>
            <label for="email">Email:</label>
            <input type="email" placeholder="Enter your email id" id="email" required bind:value={_email}>
            <label for="message">Message:</label>
            <textarea id="message" rows="10" cols="40"placeholder='How can I help you?' bind:value={_body}></textarea>
            <a href="/"><button type="submit" on:click={sendEmail}>Send message</button></a>
        </form>
    </div>
</body>
<style>
    a{
        text-decoration: none;
        align-items: center;
        justify-content: center;
        display: flex;
        cursor: default;
    }
    input,textarea{
        color: black;
    }
    h2{
        text-align: center;
        font-weight: 400;
    }
    .back:hover{
        transform: scale(115%);
    }
    .back{
        text-align: center;
        background-image:radial-gradient(#a881bd,rgb(117, 105, 151));
        padding: 10px;
        margin: 2px;
        font-weight: 400;
        border-radius: 3px;
        text-decoration: none;
        display: inline;
        width: fit-content;
        margin: 0 auto;
        transition: transform 200ms;
    }
    label{
        padding: 10px;
        padding-left: 2px;
        font-size: 1.2rem;
        color: rgb(159, 148, 178);
    }
    input{
        padding: 10px;
        font-size: 1.1rem;
        border: 1px solid rgb(208, 208, 208);
        border-radius: 30px;
        max-width: 300px;
        color: white;
        background-color: rgba(52, 42, 60, 0.505);
    }

    .form{
        display: flex;
        justify-content: center;
        flex-direction: column;
        padding: 30px;
        min-width: 50vw;
    }
    .main{
        max-width: 900px;
        flex-direction: column;
        display: flex;
        justify-content: center;
        align-items: center;

    }
    textarea{
        resize: none;
        padding: 15px;
        font-size: 1.1rem;
        border: 1px solid rgb(208, 208, 208);
        border-radius: 30px;
        width: 90%;
        color: white;
        background-color: rgba(52, 42, 60, 0.505);
    }
    button{
        margin: 20px auto;
        display: inline;
        padding: 10px 25px;
        border-radius: 20px;
        background-image: linear-gradient(#1A1A40,#460C68);
        font-size: 1.2rem;
        cursor: pointer;
        border: 2px solid rgb(132, 118, 175);
        transition: padding 300ms;
    }

    button:hover{
        background-image: linear-gradient(#12122d,#240636);
        padding: 10px 30px;
    }
    .form{
        margin: 20px;
        border: 1px solid rgb(93, 76, 111);
        border-radius: 5px;
        color:white;
        background-color: rgba(52, 42, 60, 0.505);
    }
    *{
        scrollbar-color: black;
        font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        color: white;
    }
    body{
        background-image: linear-gradient(#1A1A40,#460C68);
        /* background-color: #0d1117; */
        margin: 0;
        height: 100vh;
        width: 100vw;
        display: flex;
        justify-content: center;
        align-items: center;
        overflow-x: hidden;

    }
</style>
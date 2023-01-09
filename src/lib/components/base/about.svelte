<script>
    import repo from '$lib/assets/repo.png'
    import cpp from '$lib/assets/tools/cpp.png'
    import blender from '$lib/assets/tools/blender.png'
    import dart from '$lib/assets/tools/dart.png'
    import django from '$lib/assets/tools/django.png'
    import flutter from '$lib/assets/tools/flutter.png'
    import js from '$lib/assets/tools/js.png'
    import py from '$lib/assets/tools/py.png'
    import sk from '$lib/assets/tools/sklearn.png'
    import svelte from '$lib/assets/tools/svelte.png'
    import fast from '$lib/assets/tools/fast.png'
    import { fade,fly,slide } from 'svelte/transition';
    let Userdata=[{repo:'loading',description:'loading',language:'loading',languageColor:'dimgrey'}]
    async function getdata(){
        await fetch('https://gh-pinned-repos.egoist.dev/?username=ommahale')
        .then((response) => response.json())
        .then((data) => Userdata=data);
    }
    getdata()

</script>


<style>

    h1,h2{
        font-weight: 500;
        text-align: center;
        padding-bottom: 10px;
        border-bottom: 1px solid #30363d;
    }
    h3{
        text-align: center;

    }
    .main{
        padding: 20px;
        margin: 5px;
        border: 1px solid #30363d;
        border-radius: 5px;
        color: rgb(209, 209, 209);
        font-size: 20px;
        max-width: 900px;
    }
    .repo_li{
        justify-content: center;
        font-size: 1rem;
        display: flex;
        /* display: grid;
        grid-template-columns: 1fr 1fr; */
        list-style: none;
        margin: 0%;
        padding: 3px;
        flex-wrap: wrap;
    }
    .repo_li li{
        width: 340px;
        margin: 10px 10px;
        padding: 9px;
        border: 1px solid #30363d;
        border-radius: 5px;
        color: dimgray;
        transition: border-color 500ms;
    }
    .repo_li li:hover{
        border-color: #525b66;
    }
    a:hover{
        text-decoration: underline;
    }
    a{
        text-decoration: none;
        color: #1e8fff;
        font-weight: 200;

    }
    .lang{
        border: 1px solid;
        margin: 10px;
        border-radius: 5px;
        display: inline-block;
    }
    .tools{
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
    
    }
    .tools img:hover{
        transform: scale(120%);
    }
    .tools img{
        max-height: 70px;
        margin: 5px;
        transition: transform 300ms;
    }
    img{
        margin-right: 10px;
    }
    li{
        padding-bottom: 10px;
    }
</style>
<div in:fly="{{ x: 200, duration: 1000 }}" class="main">
    <h1>Hi I'm Om Mahale 👋</h1>
    <h3>A Mobile application developer, Web Developer and ML/AI enthusiast</h3>
        <ul>
            <li>🤖 I am looking foward to learn more in the field of ML and AI</li>
            <li>😃 I have larned and implemented various front end development tools for web as well as native application </li>
            <li>🔭 Also experienced in using various 3D animation and Game Development tools such as Blender and Unreal Engine</li>
            <li>🌱 Visit all of my projects at <a href="https://github.com/ommahale">my GitHub</a></li>
        </ul>
        <h3>Here are some of the tools that am am familiar with:</h3>
        <div class="tools" in:fly="{{delay:1000}}">
            <img src={cpp} alt="">
            <img src={js} alt="">
            <img src={dart} alt="">
            <img src={flutter} alt="">
            <img src={django} alt="">
            <img src={blender} alt="">
            <img src={py} alt="">
            <img src={sk} alt="">
            <img src={svelte} alt="">
            <img src={fast} alt="">
        </div>
    <div class="flex"></div>
    <br>
    <br>
</div>
<h2>Here are some projects that I have worked / am currently working on:</h2>
<ul class="repo_li">
    {#each Userdata as item}
        <!-- svelte-ignore security-anchor-rel-noreferrer -->
        <li in:fade><img src={repo} alt="repo">
            <a href="{item['link']}" target="_blank">
                <strong>{item['repo']}:</strong>
            </a>
            <br>
            <br> 
            {item['description']} 
            <div>
                <div class="lang" style="color: {item['languageColor']};border-color:{item['languageColor']}">
                    Lang: {item['language']}</div>
                </div>
            </li>
    {/each}
</ul>
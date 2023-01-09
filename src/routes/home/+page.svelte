<script>
    import About from '$lib/components/base/about.svelte'
    import Profile from '$lib/components/base/profile.svelte'
    import Edu from '$lib/components/base/Edu.svelte'
    import Skills from '$lib/components/base/skills.svelte'
    import Tab from '$lib/components/shared/tab.svelte'
    import MediaQuery from "$lib/components/shared/MediaQuery.svelte";
    import { fade,fly } from 'svelte/transition';

    let current='Overview'
    import logo from '$lib/assets/logo.png';
    let items=['Overview','About Me','Skills']
    let tabchange=(e)=>{
        console.log(e)
        current=e.detail;
    }
</script>
<body>
    <nav>
        <img src={logo} alt="logo">
        <div>Welcome To My Portfolio</div>
    </nav>
    <MediaQuery query="(min-width: 701px)" let:matches>
        {#if matches}
            
        <div class="main_content_pc">
            <div class="p1">
                <Profile/>
            </div>
            <div class="contents">
                <Tab {current} {items} on:itemActive={tabchange}></Tab>
                {#if current==='Overview'}
                    <About/>
                {/if}
                {#if current==='About Me'}
                    <p in:fly="{{ x: 200, duration: 1000 }}"><Edu/></p>
                {/if}
                {#if current==='Skills'}
                    <p in:fly="{{ x: 200, duration: 1000 }}"><Skills/></p>
                {/if}
            </div>
        </div>
        {/if}

    </MediaQuery>
    <MediaQuery query="(max-width: 700px)" let:matches>
        {#if matches}
        <div class="main_content_mobile">
            <div class="p1">
                <Profile/>
            </div>
            <div class="contents">
                <Tab {current} {items} on:itemActive={tabchange}></Tab>
                {#if current==='Overview'}
                    <About/>
                {/if}
                {#if current==='About Me'}
                    <p in:fly="{{ x: 200, duration: 1000 }}"><Edu/></p>
                {/if}
                {#if current==='Skills'}
                    <p in:fly="{{ x: 200, duration: 1000 }}"><Skills/></p>
                {/if}
            </div>
        </div>
        {/if}
    </MediaQuery>
</body>
<style>
    .p1{
        margin: 30px 0;
        grid-area: a1;
    }
    .contents{
        overflow-x: hidden;
        grid-area: a2;
    }
    .main_content_pc{
        display: grid;
        grid-template-areas: 'a1 a2 a2 a2 a2 a2';
        max-width: 1200px;
        margin: 0 auto;
    }
    
    .main_content_mobile{
        overflow-x: hidden;
        display: grid;
        grid-template-areas: 
        'a1 a1 a1''a2 a2 a2';
        max-width: 1300px;
        margin: 0 auto;
    }
    nav{
        display: flex;
        align-items: center;
        padding: 10px;
        margin-bottom: 6px;
        background-color: #161b22;
        justify-content: center;
    }
    nav img{
        background-blend-mode: screen;
        border-radius: 100px;
        height: 40px;
        width: 40px;
    }
    nav div{
        background-color: #161b22;
        position: relative;
        font-size: 1.3rem;
        margin: 0 auto;
        display: inline;
    }

    *{
        scrollbar-color: black;
        font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        color: white;
        background-color: #0d1117;
        font-size: 1.2rem;
    }
    body{
        margin: 0;
        height: 100%;
        width: 100%;
    }
    
</style>
<script>
    import pic from '$lib/assets/IMG_2313.png'
    import MediaQuery from "$lib/components/shared/MediaQuery.svelte";
    import { fade,fly } from 'svelte/transition';
    import book from '$lib/assets/book.png'
</script>

<div class="main">
    <MediaQuery query="(max-width: 480px)" let:matches >
        {#if matches}
        <img src={pic} alt="profile pic" class="mobile" loading='lazy' in:fly="{{ x: 200, duration: 1000}}">
        {/if}
    </MediaQuery>
    <MediaQuery query="(min-width: 481px)" let:matches>
        {#if matches}
        <img src={pic} alt="profile pic" class="pc">
        {/if}
    </MediaQuery>
    <span class="content" in:fly="{{ x: 200, duration: 1000 }}">
        <div class="title">
            OM MAHALE
        </div>
        <div class="sub">
            ommahale
        </div>
        <div class="space"></div>
        <span class="about">
            Flutter developer and a Machine Learning and Artificial Intelligence enthusiast. Experienced in SvelteJS.
            <div class="contact"><a href="/contact">Contact me</a></div>
        </span>
        <div class="img"><img src={book} alt="book"><span class="vbutton">Bachlore of Engineering (Persuing)</span></div>
    </span>

</div>
<style>
    .contact{
        margin: 0;
        padding: 0;
        display: flex;
        align-items: center;
        justify-content: center;
    }
    a:hover{
        padding: 7px 12px;
    }
    a{
        transition: padding 500ms;
        text-decoration: none;
        background-color: #556270;
        color: white;
        padding: 7px;
        margin-top: 15px;
        border-radius: 15px;
    }
    .img img{
        border: none;
    }
    .vbutton{
        cursor: default;
        color:blueviolet ;
        border: 1px solid blueviolet;
        border-radius: 10px;
        margin: 3px 5px;
        padding: 0 3px;
    }
    .space{
        height: 10px;
    }
    .sub{
        color: dimgray;
        font-size: 1.3em;
        font-weight: 100;
    }
    .main{
        margin: 10px;
        max-width: 400px;
    }
    .content{
        margin-left: 15px;
        max-width: 300px;
        font-size: 16px;
    }
    .title{
        font-size: 1.5rem;
        font-weight: 500;

    }
    img{
        border: 2px solid dimgray;
        margin-bottom: 10px;
    }
    .pc{
        border-radius: 500px;
        max-height: 300px;
        max-width: 300px;
    }
    .mobile{
        border-radius: 500px;
        max-height: 50px;
    }
    div{
        display: flex;
        flex-wrap: wrap;
    }
    .about{
        display: inline-block;
        padding-bottom: 10px;
        margin-bottom: 30px;
        border-bottom: 1px solid #30363d;
        font-size: 1.2rem;
    }
</style>
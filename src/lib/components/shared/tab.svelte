<script>
    export let items;
    export let current;
    import {createEventDispatcher} from 'svelte'
    let dispatch = createEventDispatcher();

</script>

<div class="tabs">
    <ul>
        {#each items as item}
            <!-- svelte-ignore a11y-click-events-have-key-events -->
            <li on:click={()=>dispatch('itemActive', item)} >
                <div class:active={item===current}>{item}</div>
            </li>
        {/each}
    </ul>
</div>

<style>
    .tabs{
        background-color: #0d1117;
        margin-bottom: 20px;
    }
    li{
        list-style: none;
        padding: 10px;
        cursor: pointer;
        margin: 20px;
        font-size: 1rem;
        color: rgb(206, 206, 206);
    }
    li:hover{
        color: rgb(187, 187, 187);
    }
    .active{
        color: rgb(255, 255, 255);
        border-bottom: 3px solid #f78166;
    }
    ul{
        margin: auto auto;
        padding: 0;
        display: flex;
        justify-content: flex-start;
        max-width: 100%;
        height: 100%;
        border-bottom: 1px solid #30363d;
    }
    li div{
        text-align: center;
        padding: 4px;
    }
</style>
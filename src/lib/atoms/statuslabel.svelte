<script>
    export let data;
    import { onMount } from 'svelte';
    onMount(() => { 

        let commentBar = document.querySelectorAll('.comment-hidden');
        let commentviewer = document.querySelectorAll('.comment-viewer');

        // Voeg submit event listener toe voor het tonen van resultaten bij het indienen van het formulier
        for(let i = 0; i < commentviewer.length; i++){
            commentviewer[i].addEventListener('click', ()=>{
            commentBar[i].classList.toggle("comment-viewable");
            commentBar[i].classList.toggle("comment-hidden")
        });
        }



    });
    </script>
    
    <section>

    {#each data.statusupdates as statusupdate}
    
    <p class="status-update">{statusupdate.comment.text}</p>
    <div class="comment-viewer"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><!--!Font Awesome Free 6.5.1 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free Copyright 2024 Fonticons, Inc.-->
        <path d="M512 240c0 114.9-114.6 208-256 208c-37.1 0-72.3-6.4-104.1-17.9c-11.9 8.7-31.3 20.6-54.3 30.6C73.6 471.1 44.7 480 16 480c-6.5 0-12.3-3.9-14.8-9.9c-2.5-6-1.1-12.8 3.4-17.4l0 0 0 0 0 0 0 0 .3-.3c.3-.3 .7-.7 1.3-1.4c1.1-1.2 2.8-3.1 4.9-5.7c4.1-5 9.6-12.4 15.2-21.6c10-16.6 19.5-38.4 21.4-62.9C17.7 326.8 0 285.1 0 240C0 125.1 114.6 32 256 32s256 93.1 256 208z"/>
    </svg>{statusupdate.reaction.length}</div>
    <div class="comment-hidden comment-style">{#each statusupdate.reaction as reaction}
        <div class="user-container">
            <div class="img-container"><img src={data.personens[0].image.url}></div>
            <p class="user-name">{data.personens[0].name}</p>
        </div>
        <p class="reaction-text">{reaction.text}</p>{/each}</div>
            {/each}
        </section>
    <style>
    .status-update{
        border: 2px solid rgba(13, 158, 255, 0.5);
        padding: 1em;
        font-size: 14px;
        width: 20em;
        margin-top: 1em;
        background-color: rgb(247, 247, 247);
    }
    .status-update:nth-of-type(2){
        border-color: rgb(8, 196, 8);
    }
    .status-update:nth-of-type(4){
        border-color: rgb(165, 13, 13);
    }
    div{
        font-size: 14px;
    }
    .comment-viewer{
        display: flex;
        flex-flow: row wrap;
        justify-content: flex-end;
        border: 2px solid rgba(13, 158, 255, 0.5);
        border-top: none;
        padding: 2px;
    }
    .comment-style{
        border: 2px solid rgba(7, 7, 7, 0.5);
        margin-top: 1em;
        padding: 1em;
        display: flex;
        flex-flow: row wrap;
        width: 20em;

    }
    svg{
        width: 20px;
        fill: rgb(128, 128, 128);
        margin-right: 4px;
        margin-top: -1.5px;
    }

    .comment-hidden{
        display: none;
    }
    .comment-viewable{
        display: flex;
    }

    .reaction-text{
        border: 2px solid rgba(13, 158, 255, 0.5);
        padding: 1em;
        font-size: 14px;
        width: 20em;
        margin-top: 1em;
        background-color: rgb(247, 247, 247);
    }

    .reaction-text:nth-child(even){
        margin-left: 20px;
    }
    .reaction-text:nth-child(odd){
        margin-right: 20px;
    }

    .user-name{
        font-weight: bold;
        margin-left: 0.5em;
        margin-top: 0.8em;
    }
    .img-container{
        border: 1px solid black;
        border-radius: 100%;
        overflow: hidden;
        height: 3em;
        width: 3em;
    }

    .user-container{
        display:flex;
        flex-flow: row nowrap;
        margin-top: 1em;
    }
    img{
        width: 3em;
    }
    </style>
    
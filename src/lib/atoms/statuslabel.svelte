<script>
    export let data;
    import { onMount } from 'svelte';
    onMount(() => { 

        let commentBar = document.querySelectorAll('.comment-hidden');
        let commentviewer = document.querySelectorAll('.comment-viewer');

        // Voeg submit event listener toe voor het tonen van resultaten bij het indienen van het formulier
        for(let i = 0; i < commentviewer.length; i++){
            commentviewer[i].addEventListener('click', ()=>{
            setTimeout(() =>{commentBar[i].classList.toggle("comment-viewable")}, 1);
            commentBar[i].classList.toggle("comment-hidden")
        });
        }



    });
    </script>
    
    <section>

    {#each data.statusupdates as statusupdate}
    
    <p class="status-update">{statusupdate.comment.text}</p>
    <div class="comment-viewer">{statusupdate.reaction.length} Reacties...</div>
    <div class="comment-hidden comment-style">{#each statusupdate.reaction as reaction}
        <div class="user-container">
            {#each data.personens as persoon}
            <div class="img-container"><img src={persoon.image.url}></div>
            <svg xmlns="http://www.w3.org/2000/svg" width="800" height="800" viewBox="-1 0 26 26"><path fill="#000" fill-rule="evenodd" d="M19 24a3 3 0 1 1 0-6 3 3 0 0 1 0 6ZM5 16a3 3 0 1 1 0-6 3 3 0 0 1 0 6ZM19 2a3 3 0 1 1 0 6 3 3 0 0 1 0-6Zm0 14c-1.77 0-3.315.925-4.204 2.312l-5.355-3.06c.346-.68.559-1.438.559-2.252 0-.503-.097-.979-.235-1.437l5.571-3.183A4.97 4.97 0 0 0 19 10a5 5 0 0 0 5-5 5 5 0 0 0-5-5 5 5 0 0 0-5 5c0 .503.097.979.235 1.438L8.664 9.62A4.973 4.973 0 0 0 5 8a5 5 0 0 0-5 5 5 5 0 0 0 5 5c1.14 0 2.179-.396 3.02-1.038L8 17l6.055 3.46c-.02.18-.055.354-.055.54a5 5 0 0 0 5 5 5 5 0 0 0 5-5 5 5 0 0 0-5-5Z"/></svg>
            <p class="user-name">{persoon.name}</p>
            {/each}
        </div>
        <p class="reaction-text">{reaction.text}</p>
            
        {/each}       
        <form>
            <input type="text" name="comment" id="comment">
            <div id="radio-sorter">
            <input type="radio" id="option-trekker">
            <label for="option-trekker"><svg xmlns="http://www.w3.org/2000/svg" xml:space="preserve" width="800" height="800" viewBox="0 0 512 512"><path d="M143.891 239.572c53.747 0 97.473-43.725 97.473-97.472s-43.725-97.472-97.473-97.472c-53.747 0-97.472 43.725-97.472 97.472s43.725 97.472 97.472 97.472zm0-158.825c33.83 0 61.352 27.522 61.352 61.351s-27.522 61.351-61.352 61.351-61.351-27.522-61.351-61.351c0-33.828 27.521-61.351 61.351-61.351zM368.109 239.572c53.747 0 97.472-43.725 97.472-97.472s-43.725-97.472-97.472-97.472-97.473 43.725-97.473 97.472c.001 53.746 43.727 97.472 97.473 97.472zm0-158.825c33.83 0 61.351 27.522 61.351 61.351s-27.522 61.351-61.351 61.351-61.352-27.522-61.352-61.351c.001-33.828 27.523-61.351 61.352-61.351z"/><path d="M255.995 310.254C171.658 205.199 0 264.747 0 400.513v48.799c0 9.974 8.086 18.06 18.06 18.06h475.88c9.974 0 18.06-8.086 18.06-18.06v-48.799c0-135.808-171.777-195.224-256.005-90.259zm-4.341 120.997H36.121v-30.739c0-59.42 48.346-107.76 107.772-107.76 59.988 0 107.76 48.534 107.76 107.76v30.739zm224.225 0H287.774c0-33.754 2.149-55.077-11.501-87.179 19.558-31.862 54.011-51.32 91.833-51.32 59.426 0 107.772 48.34 107.772 107.76v30.739z"/></svg>
            Trekker</label>
            
            <input type="radio" id="option-helper">
            <label for="option-helper"><svg xmlns="http://www.w3.org/2000/svg" xml:space="preserve" width="800" height="800" viewBox="0 0 422.491 422.491"><path d="M338.594 289.207c-36.805 0-66.641 29.836-66.641 66.641 0 36.808 29.836 66.644 66.641 66.644 36.807 0 66.643-29.836 66.643-66.644-.002-36.805-29.838-66.641-66.643-66.641zm43.295 98.914-10.424 10.423a2.198 2.198 0 0 1-3.108 0l-20.532-20.533-.779.777a2.198 2.198 0 0 1-3.108 0l-4.979-4.979a2.203 2.203 0 0 1 0-3.109l5.104-5.104-4.543-4.544-11.429 11.432c2.123 6.051.771 13.062-4.059 17.892a17.088 17.088 0 0 1-12.24 5.04 1.469 1.469 0 0 1-1.037-.435 1.472 1.472 0 0 1 0-2.086l4.799-4.802-2.866-10.707-10.706-2.868-4.803 4.802a1.476 1.476 0 0 1-2.519-1.038 17.086 17.086 0 0 1 5.037-12.239c4.832-4.829 11.842-6.183 17.895-4.058l11.429-11.431-15.086-15.084-10.685-6.877-4.766-8.412 5.041-5.039 8.409 4.767 6.879 10.684 15.084 15.084 10.229-10.229c-2.123-6.052-.771-13.063 4.06-17.894a17.089 17.089 0 0 1 12.239-5.039 1.476 1.476 0 0 1 1.037 2.521l-4.801 4.801 2.869 10.708 10.707 2.868 4.803-4.801a1.467 1.467 0 0 1 1.604-.321c.551.228.91.763.914 1.357a17.091 17.091 0 0 1-5.036 12.24c-4.832 4.829-11.843 6.184-17.896 4.06l-10.229 10.229 4.541 4.544 5.104-5.104a2.2 2.2 0 0 1 3.111 0l4.977 4.977a2.2 2.2 0 0 1 0 3.111l-.776.776 20.532 20.532c.863.856.863 2.249.003 3.108z"/><path d="M303.637 280.498 262.66 264.16l-19.881-16.748c-5.25-4.438-13.004-4.109-17.873.731l-27.639 27.48-27.717-27.492a13.239 13.239 0 0 0-17.863-.722l-19.879 16.748-84.894 33.854C19.578 308.897 19.6 405.704 17.254 414.59h261.183c-15.414-14.857-25.032-35.692-25.032-58.745-.002-33.889 20.762-63.016 50.232-75.347zM100.042 160.169l15.943-.04c9.848 51.453 44.795 80.728 81.27 80.728 36.475 0 57.666-17.339 71.719-49.293-10.729 8.416-26.324 16.114-48.135 17.704a11.155 11.155 0 0 1-9.277 4.951h-10.188c-6.168 0-11.166-4.999-11.166-11.167s4.998-11.167 11.166-11.167h10.188c3.613 0 6.814 1.723 8.855 4.383 35.068-2.815 51.559-24.083 58.135-36.091l15.916-.006c9.746 0 17.646-7.903 17.646-17.646v-39.996c0-6.246-3.254-11.723-8.152-14.859C298.067 38.434 252.464 0 197.255 0S96.444 38.434 90.55 87.668c-4.898 3.137-8.152 8.613-8.152 14.859v39.996c-.002 9.742 7.897 17.646 17.644 17.646zm97.212-140.17c43.453 0 79.592 28.656 86.254 66.041a17.617 17.617 0 0 0-5.59 3.429c-10.406-32.855-40.471-52.385-80.664-52.385-40.193 0-70.275 19.519-80.695 52.357A17.599 17.599 0 0 0 111 86.04c6.663-37.385 42.801-66.041 86.254-66.041z"/></svg>
            Helper</label>

            <input type="radio" id="option-deler">
            <label for="option-deler"><svg xmlns="http://www.w3.org/2000/svg" width="800" height="800" viewBox="-1 0 26 26"><path fill="#000" fill-rule="evenodd" d="M19 24a3 3 0 1 1 0-6 3 3 0 0 1 0 6ZM5 16a3 3 0 1 1 0-6 3 3 0 0 1 0 6ZM19 2a3 3 0 1 1 0 6 3 3 0 0 1 0-6Zm0 14c-1.77 0-3.315.925-4.204 2.312l-5.355-3.06c.346-.68.559-1.438.559-2.252 0-.503-.097-.979-.235-1.437l5.571-3.183A4.97 4.97 0 0 0 19 10a5 5 0 0 0 5-5 5 5 0 0 0-5-5 5 5 0 0 0-5 5c0 .503.097.979.235 1.438L8.664 9.62A4.973 4.973 0 0 0 5 8a5 5 0 0 0-5 5 5 5 0 0 0 5 5c1.14 0 2.179-.396 3.02-1.038L8 17l6.055 3.46c-.02.18-.055.354-.055.54a5 5 0 0 0 5 5 5 5 0 0 0 5-5 5 5 0 0 0-5-5Z"/></svg>
            Deler</label>
        </div>
            <input type="file" id="myfile" name="myfile">
            <input type="submit" value="Reageer!" id="submit-confirm">

        </form>
    </div>
            {/each}
        </section>
        <div class="comment-viewable"></div>
    <style>
    .status-update{
        border: 1px solid rgba(13, 158, 255, 0.5);
        border-radius: 20px;
        box-shadow: 2px 4px 4px -2px rgba(135, 135, 135, 0.12);
        padding: 1em;
        font-size: 14px;
        width: 40ch;
        margin-top: 1em;
        background-color: rgb(255, 255, 255);
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

        padding: 2px;
        font-weight: bold;
        font-size: 12px;
    }
    .comment-viewer:hover{
        cursor: pointer;
    }
    .comment-style{
        border: 2px solid rgba(7, 7, 7, 0.5);
        margin-top: 1em;
        padding: 1em;
        display: flex;
        flex-flow: row wrap;
        width: 20em;
        opacity: 0;
        transition: all 0.2s linear;
    }
    svg{
        width: 20px;
        height: 20px;
        fill: rgb(128, 128, 128);

    }

    .comment-hidden{
        display: none;
        transition: all 0.2s linear;


    }
    .comment-viewable{
        display: flex;
        opacity: 1;
        transition: all 0.2s linear;

    }

    .reaction-text{
        border: 2px solid rgba(13, 158, 255, 0.5);
        padding: 1em;
        font-size: 14px;
        width: min(100%, 75ch);
        margin-top: 1em;
        background-color: rgb(247, 247, 247);
        box-shadow: 6px 6px 6px -2px rgba(135, 135, 135, 0.12);
        border-radius: 5px;
        text-wrap: balance;
        
    }

    .reaction-text:nth-of-type(even){
        margin-left: 3em;
    }
    .reaction-text:nth-of-type(odd){
        margin-right: 3em;
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
    .user-container:nth-of-type(even){
        margin-left: auto;
    }
    .user-container:nth-of-type(odd){
        margin-right: auto;
    }

    .user-container:nth-of-type(even) div:nth-of-type(even), .user-container:nth-of-type(even) p:nth-of-type(even), .user-container:nth-of-type(even) svg:nth-of-type(even){
        display: none;
    }
    .user-container:nth-of-type(odd) div:nth-of-type(odd), .user-container:nth-of-type(odd) p:nth-of-type(odd), .user-container:nth-of-type(odd) svg:nth-of-type(odd){
        display: none;
    }
    img{
        width: 3em;
    }
    form{
        width: 20em;
        border-top: 1px solid black;
        padding: 1em;
        margin: 1.5em -1em -1em -1em;
    }

    #comment{
        padding: 3em;
    }

    input{
        margin-bottom: 1em;
    }

    input[type="radio"]{
        margin-bottom: 0;
    }

    input[type="file"]{
        margin-top: 1em;
    }
    #submit-confirm{
        padding: 0.7em;
        border-radius: 10px;
        background-color: rgba(13, 158, 255, 0.5);
        box-shadow: 5px 5px 5px -2px rgba(135, 135, 135, 0.12);
        border-width: 1px;
        font-weight: bold;
    }

    #comment{
        border-radius: 15px;
        box-shadow: 6px 6px 6px -2px rgba(135, 135, 135, 0.12);
        border-width: 1px;
    }

    #radio-sorter{
        display: flex;
        flex-flow: row wrap;
        width: 5em;
    }
    </style>
    
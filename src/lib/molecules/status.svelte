<script>
	import Statusdatum from '$lib/atoms/statusdatum.svelte';
    import Statuslabel from '$lib/atoms/statuslabel.svelte';
    import Risico from '$lib/atoms/risico.svelte'
    import { onMount } from 'svelte';
	export let data;
//     onMount(() => { 

//     let lineDetect = document.querySelector('#line');
//     let boxDetect = document.querySelector('.test-container');
//     const style = getComputedStyle(boxDetect);
//     function detectChange(){
//         if(parseInt(style.height) > 750){
//             lineDetect.style.top = "45%";
//         }
//         else{
//             lineDetect.style.top = "50%";
//         }
//         console.log(parseInt(style.height))

//     }
//     boxDetect.addEventListener("click", detectChange);


// });
</script>
<h2>Status wens</h2>
<Risico />
<section>

    <Statusdatum {data}/>
    <div class="test-container">
    <div title="status line container">


        </div>
    <Statuslabel {data}/>
</div>

</section>

<style>
    h2{
        padding: 1em;
    }
    section{
        display: flex;
        flex-flow: row wrap;
        padding: 1em;
        width: 100%;
        justify-content: space-between;
        align-items: center;
    }
    #circle{
        width: 2em;
        height: 2em;
        background-color: rgba(13, 158, 255, 0.5);
        display: inline-block;
        border-radius: 50%;
        margin-top: 3.3em
    }
    #line {
        position: absolute;
        top: 50%; 
        transform: translate(-550%, -42%);
        width: .4em;
        height: 95%;
        background-color: skyblue;
}
    div{
        position: relative;
        display: flex;
        flex-flow: column nowrap;
        margin-bottom: 2.8em;
        height: auto;
    }

    .test-container{
        flex-flow: row wrap;
    }
</style>
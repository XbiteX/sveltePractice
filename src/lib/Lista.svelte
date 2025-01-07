<script>
    import Carta from "./Card.svelte"
    import ListaMoto from "./listaMoto.json"
    import Sort from "$lib/Sort.svelte"
    let listaMotoModificabile = [...ListaMoto]
    function aggiornaLista(event){
        listaMotoModificabile = [...event.detail]
    }
</script>

<style>
    .contenitore{
        width: 100%;
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: space-evenly;
        gap: 20px;
        background-color: bisque;
    }
</style>
<Sort {listaMotoModificabile} on:aggiorna={aggiornaLista}></Sort>
<div class="contenitore">
    {#each listaMotoModificabile as moto}
        <Carta {...moto}></Carta>
    {/each}
</div>
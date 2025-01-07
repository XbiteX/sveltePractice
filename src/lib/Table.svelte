<script>
    import listaMoto from "./listaMoto.json"
    import Sort from "./Sort.svelte"
    let listaMotoModificabile = [...listaMoto]

    function aggiornaLista(event){
        listaMotoModificabile = [...event.detail]
    }
</script>

<Sort {listaMotoModificabile} on:aggiorna={aggiornaLista}></Sort>
<table>
    <thead>
        <tr>
            <th>nome</th>
            <th>cilindrata</th>
            <th>prezzo</th>
            <th>trasmissione</th>
        </tr>
    </thead>
    <tbody id="body">
        {#each listaMotoModificabile as moto}
            <tr>
                <td>{moto.name}</td>
                <td>{moto.cc}</td>
                <td>{moto.price}</td>
                <td>{moto.transmission}</td>
            </tr>
        {/each}
    </tbody>
</table>
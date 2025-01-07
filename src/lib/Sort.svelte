<script>
    import { Select, Label } from 'flowbite-svelte';
    import { GradientButton } from 'flowbite-svelte';
    export let listaMotoModificabile
    import { createEventDispatcher } from 'svelte';
    const dispatch = createEventDispatcher();

    let selectedType = '';
    let types = [
      { value: 'name', name: 'alphabetically' },
      { value: 'price', name: 'pricely' },
      { value: 'cc', name: 'capacity' }
    ];

    let selectedOrder = '';
    let orders = [
      { value: 'inc', name: 'increasing' },
      { value: 'dec', name: 'decreasing' }
    ];

    function sorteggia(){
        if(selectedType=='' || selectedOrder==''){
            alert('seleziona ambe le opzioni');
            return
        }else if(selectedType=='name'){
            if(selectedOrder=='inc'){
                listaMotoModificabile = listaMotoModificabile.sort((a, b) => a.name.localeCompare(b.name));
            }else{
                listaMotoModificabile = listaMotoModificabile.sort((a, b) => b.name.localeCompare(a.name));
            }
        }else if(selectedType=='price'){
            if(selectedOrder=='inc'){
                listaMotoModificabile = listaMotoModificabile.sort((a, b) => a.price - b.price);
            }else{
                listaMotoModificabile = listaMotoModificabile.sort((a, b) => b.price - a.price);
            }
        }else if(selectedType=='cc'){
            if(selectedOrder=='inc'){
                listaMotoModificabile = listaMotoModificabile.sort((a, b) => a.cc - b.cc);
            }else{
                listaMotoModificabile = listaMotoModificabile.sort((a, b) => b.cc - a.cc);
            }
        }
        
        dispatch('aggiorna', listaMotoModificabile);
    }
</script>

<style>
    #contenitore{
        display: flex;
    }
</style>

<div id="contenitore">
    <Label>
        sort...
        <Select class="mt-2" items={types} bind:value={selectedType} />
    </Label>
    <Label>
        sort...
        <Select class="mt-2" items={orders} bind:value={selectedOrder} />
    </Label>
    <div class="flex items-end">
        <GradientButton on:click={sorteggia} outline color="purpleToPink">sort</GradientButton>
    </div>
</div>

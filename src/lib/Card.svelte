<script>
    export let id;
    export let name;
    export let cc;
    export let price;
    export let transmission;
    export let img;

</script>



<a href="#" class="block max-w-sm p-6 bg-white border border-gray-200 rounded-lg shadow hover:bg-gray-100 dark:bg-gray-800 dark:border-gray-700 dark:hover:bg-gray-700">

    <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">{name}</h5>
    <div class="font-normal text-gray-700 dark:text-gray-400">
        <h6>id{id}</h6>
        <h6>cilindrata: {cc}</h6><br>
        <h6>{price}$</h6><br>
        <h6>trasmissione: {transmission}</h6><br>
        <h6>cilindrata: {cc}</h6><br>
        <img src={img} alt="immagine">
    </div>
</a>

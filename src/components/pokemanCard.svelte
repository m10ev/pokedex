<script>
    export let pokeman;
</script>
<a class="p-6 bg-gray-100 text-gray-800 text-center rounded-md shadow-sm hover:shadow-md flex flex-col items-center" href={`/pokemon/${pokeman.id}`}>
    <img class="h-40 w-40" src={pokeman.image} alt={pokeman.name}>
    <h2 class="uppercase text-2xl">{pokeman.id}. {pokeman.name}</h2>
</a>
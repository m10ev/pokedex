<script>
    import { pokemon } from "../stores/pokemart.js";
    import PokemanCard from "../components/pokemanCard.svelte"
    console.log($pokemon)

    let searchTerm = "";
    let filteredPokemon = [];

    $: {
        console.log(searchTerm);
        if(searchTerm){
            //Catch Pokemon
            filteredPokemon = $pokemon.filter(pokeman => pokeman.name.toLowerCase().includes(searchTerm.toLowerCase()));
        }else{
            filteredPokemon = [... $pokemon]
        }
    }
</script>
<svelte:head>
    <title>Svelte Kit Pokedex</title>
</svelte:head>
<h1 class="text-4xl text-center my-8">Svelte Kit Pokedex</h1>
<input class="w-full rounded-md text-lg p-4 border-2 border-gray-200" type="text" bind:value={searchTerm} placeholder="Search Pokemon">
<div class=" py-4 grid gap-4 md:grid-cols-2 grid-cols-1">
    {#each  filteredPokemon as pokeman }
    <PokemanCard pokeman={pokeman}/>
{/each}
</div>
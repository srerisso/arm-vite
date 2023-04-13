<h1>Proyectos</h1>

<script>
    import { onMount } from 'svelte';
    import { each } from 'svelte/internal';
	let projects = [];

    onMount(async () => {
        const response = await fetch('http://localhost:3000/proyectos');
        projects = await response.json();
    })

    // console.log(projects);
</script>

<main>

<!-- List of Projects -->
<h2>Últimos Proyectos</h2>
<ul>
    <li>Código * Cliente * Referencia</li>
	{#each projects as project}
        <li>{project.Codigo_Alg} - {project.cliente_id} - {project.Referencia}</li>
    {/each}

</ul>


</main>

<script>
import {onMount} from 'svelte';
import lozad from 'lozad';
export let data;
let loaded='dcnpm';
let observe;
onMount(() => {observe=lozad();observe.observe();});

const checkLoad = () => {

}


</script>

<div>
{#if loaded !==undefined}
{data.name}
<img class="lozad" src='21.gif' data-src={data.displayImage} id="image" alt="profile" loading="lazy"/>
{/if}
</div>

<style>
img{
    height: 200px;
    width:200px;
}
</style>
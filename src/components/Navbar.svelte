<script>
import { createEventDispatcher } from "svelte";
const dispatch = createEventDispatcher();
export let activePage;
export let items;
</script>

<div class="navbar">
    <div class="nav-left">
        <span class="nav-logo">Logo</span>
    </div>

    <div class="nav-right">
        {#each items as item}
        <div class="nav-item">
            <span class="nav-link" class:active={item === activePage} on:click={() => dispatch('pageChange', item)}>{item}</span>
        </div>
        {/each}
        <div class="nav-item">
            <input class="nav-search" type="text" name="search" id="search" placeholder="Search" />
            <i class="fa-solid fa-magnifying-glass icon"></i>
        </div>
    </div>
</div>

<style>
.navbar {
    display: flex;
    justify-content: space-between;
    padding-left:30px;
    padding-right: 20px;
    height: 70px;
    background-color: crimson;
    /* --->  choose right color and style better  <--- */
}

.nav-logo {
    font-weight: 800;
    font-size: 3rem;
}

.nav-link {
    margin: auto;
    color:black;
    cursor: pointer;
}

.active {
    border-bottom: 2px solid lightskyblue;
}

.nav-right {
    display: flex;
    justify-content: center;
    align-items: center;
}

.nav-item {
    text-align: center;
    margin: 0 10px;
}

.nav-search {
    border: 0.5px solid lightgray;
    border-radius: 2px;
    padding: 5px;
}

.icon {
    font-size: 20px;
}
</style>
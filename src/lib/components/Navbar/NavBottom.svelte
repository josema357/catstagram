<script>
  import house from '$lib/assets/svg/house.svg';
  import searchFill from '$lib/assets/svg/search-fill.svg';
  import heart from '$lib/assets/svg/heart.svg';
  import create from '$lib/assets/svg/plus-square.svg';
	import ItemNav from './ItemNav.svelte';
</script>

<div class="nav-bottom">
  <ItemNav logo={house} text="Inicio"/>
  <ItemNav logo={searchFill} text="Buscar"/>
  <ItemNav logo={heart} text="Notificaciones"/>
  <ItemNav logo={create} text="Crear"/>
</div>

<style>
  .nav-bottom {
    position: fixed;
    bottom: 0;
    width: 100%;
    display: flex;
    justify-content: center;
    background-color: white;
  }
  @media(min-width: 750px){
    .nav-bottom{
      display: none;
    }
  }
</style>
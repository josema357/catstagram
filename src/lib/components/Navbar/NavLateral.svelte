<script>
  import logo from '$lib/assets/img/logo-cat.jpg';
  import house from '$lib/assets/svg/house.svg';
  import searchFill from '$lib/assets/svg/search-fill.svg';
  import heart from '$lib/assets/svg/heart.svg';
  import create from '$lib/assets/svg/plus-square.svg';
  import list from '$lib/assets/svg/list.svg';
	import ItemNav from './ItemNav.svelte';
</script>

<div class="navLateral">
  <div class="box-logo">
    <p>Catstagram</p>
    <img class="logo" src={logo} alt="logo">
  </div>
  <div class="box-items">
    <ItemNav logo={house} text="Inicio"/>
    <ItemNav logo={searchFill} text="Buscar"/>
    <ItemNav logo={heart} text="Notificaciones"/>
    <ItemNav logo={create} text="Crear"/>
  </div>
  <div class="box-plus">
    <ItemNav logo={list} text="Mas"/>
  </div>
</div>

<style>
.navLateral {
  display: flex;
  position: fixed;
  flex-direction: column;
  width: 240px;
  height: 100dvh;
  border: 1px solid rgb(197, 197, 197);
  padding: 12px;
  box-sizing: border-box;
  background-color: white;
}
.box-logo{
  display: flex;
  justify-content: center;
  padding: 20px 0px 50px;
}
.box-logo p{
  width: 100%;
  margin: 0;
  font-size: 20px;
  font-weight: 800;
  padding-left: 12px;
  font-family: "Pacifico", cursive;
  font-style: normal;
  font-weight: 400;
}
.box-items {
  flex: 1;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  gap: 15px;
}
.logo{
  display: none;
  width: 30px;
  height: 30px;
}
.box-plus{
  display: flex;
  align-items: center;
}
@media(max-width:1200px){
  .navLateral{
    width: 70px;
  }
  .box-items {
    align-items: center;
    
  }
  .box-logo p {
    display: none;
  }
  .logo{
    display: block;
  }
  .box-plus{
    display: flex;
    justify-content: center;
  }
}
@media(max-width:750px){
  .navLateral {
    display: none;
  }
}
</style>
<script>
  import heart from '$lib/assets/svg/heart.svg';
  import search from '$lib/assets/svg/search.svg';
  import logo from '$lib/assets/img/logo-cat.jpg';
  import NavLateral from '$lib/components/NavLateral.svelte';
	import NavBottom from '../../lib/components/NavBottom.svelte';
</script>

<nav>
  <div>
    <p>Catstagram</p>
    <img class="logo" src={logo} alt="logo">
  </div>
  <div class="left-side">
    <div class="search">
      <img src={search} alt="search-logo">
      <input type="text" placeholder="Search">
    </div>
    <img src={heart} alt="notification-logo">
  </div>
</nav>
<div class="layout">
  <NavLateral/>
  <slot></slot>
  <NavBottom/>
</div>

<style>
  nav{
    display: none;
    justify-content: space-between;
    align-items: center;
    padding: 12px;
    border-bottom: 1px solid rgb(209, 209, 209);
  }
  nav p{
    margin: 0;
    font-size: 20px;
    font-weight: 800;
  }
  .logo{
    display: none;
    width: 35px;
    height: 35px;
  }
  .left-side{
    display: flex;
    gap: 15px;
  }
  .left-side > img{
    cursor: pointer;
  }
  .search{
    background-color: #efefef;
    padding: 8px 10px;
    border-radius: 5px;
    display: flex;
    align-items: center;
    gap: 8px;
  }
  input{
    border: none;
    outline: none;
    background-color: transparent;
  }
  .layout{
    display: flex;
  }
  @media(max-width:750px){
    nav {
      display: flex;
    }
  }
  @media(max-width:380px){
    nav p{
      display: none;
    }
    .logo{
      display: block;
    }
  }
  @media(max-width: 300px){
    .logo{
      display: none;
    }
  }
</style>
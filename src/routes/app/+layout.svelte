<script>
  import heart from '$lib/assets/heart.svg';
  import search from '$lib/assets/search.svg';
</script>

<nav>
  <div>
    <p>Catstagram</p>
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
  <div>Navbar Lateral</div>
  <slot></slot>
</div>

<style>
  nav{
    display: flex;
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
  @media(max-width:400px){
    nav p{
      display: none;
    }
  }
</style>
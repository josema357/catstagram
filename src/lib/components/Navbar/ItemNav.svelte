<script>
  export let logo;
  export let text;
</script>

<a href={`/app/${text.toLowerCase()}`}>
  <div class="item">
    <img src={logo} alt={text}>
    <span>{text}</span>
  </div>
</a>

<style>
  a{
    width: 100%;
    text-decoration: none;
    color: black;
  }
  a:hover{
    background-color: rgb(240, 240, 240);
  }
  .item {
    width: 100%;
    display: flex;
    align-items: flex-start;
    gap: 15px;
    padding: 12px;
    box-sizing: border-box;
    border-radius: 8px;
    cursor: pointer;
  }
  .item img {
    width: 25px;
    height: 25px;
  }
  .item span{
    display: block;
    height: 25px;
    font-size: 16px;
    display: flex;
    align-items: center;
  }
  @media(max-width:1200px){
    .item {
      justify-content: center;
    }
    .item span {
      display: none;
    }
  }
  @media(max-width:280px){
    .item {
      padding: 10px;
    }
  }
</style>
<script>
  export let logo;
  export let text;
</script>

<div class="item">
  <img src={logo} alt={text}>
  <span>{text}</span>
</div>

<style>
  .item {
    width: 100%;
    display: flex;
    align-items: flex-start;
    gap: 15px;
    padding: 12px;
    box-sizing: border-box;
    border-radius: 12px;
  }
  .item:hover{
    background-color: rgb(240, 240, 240);
  }
  .item img {
    width: 25px;
    height: 25px;
  }
  .item span{
    font-size: 16px;
  }
  @media(max-width:1200px){
    .item {
      justify-content: center;
    }
    .item span {
      display: none;
    }
}
</style>
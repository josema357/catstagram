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
    display: flex;
    align-items: flex-start;
    gap: 15px;
  }
  .item img {
    width: 25px;
    height: 25px;
  }
  .item span{
    font-size: 16px;
    font-weight: bold;
  }
  @media(max-width:1050px){
    .item span {
      display: none;
    }
}
</style>
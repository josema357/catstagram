
<script>
  import UserImage from "$lib/assets/svg/user-circle.svg"
  export let count;
</script>
<div class="principal-user">
  <div class="card-user">
    <img src={UserImage} alt="user-logo"/>
    <div class="card-name-user">
      <p class="name-user">unknown#000{count}</p>
      <p>User unknown</p>
    </div>
  </div>
  <div class="card-settings">
    <p class="ver">See</p>
  </div>
</div>
<style>
  .principal-user{
    display: flex;
    justify-content: space-between;
  }
  .ver{
    font-size: 12px;
    cursor: pointer;
  }
  .card-user{
    display: flex;
    gap: 8px;
  }
  .card-user img{
    width: 32px;
    height: 32px;
    border-radius: 50%;
    object-fit: cover;
  }
  .name-user{
    margin: 0;
    text-wrap: nowrap;
    font-size: 16px;
    font-weight: 800;
  }
  .card-name-user p:nth-of-type(2){
    margin: 0;
    font-size: 12px;
    text-wrap: nowrap;
  }

</style>
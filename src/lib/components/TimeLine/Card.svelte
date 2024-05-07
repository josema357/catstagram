<script>
  import user from "$lib/assets/svg/user-circle.svg"
  import settings from "$lib/assets/svg/three-dots.svg"
  import cat from "$lib/assets/img/cat.webp"
  import heart from "$lib/assets/svg/heart.svg"
  import share from "$lib/assets/svg/share.svg"
  import bookmark from "$lib/assets/svg/bookmark.svg"
  import Comments from "$lib/components/Timeline/Comments.svelte"
</script>

<div class="card">
  <div class="card-container">
    <div class="card-header">
      <div class="card-user">
        <img src={user} alt="user-logo"/>
        <h2>User.cat</h2>
        <span>Lima, Peru</span>
      </div>
      <div class="card-settings">
        <img src={settings} alt="settings-logo"/>
      </div>
    </div>
    <div class="card-photo">
      <figure>
        <img src={cat} alt=""/>
      </figure>
    </div>
    <div class="card-icons">
      <div class="icons-left">
        <img src={heart} alt=""/>
        <img src={share} alt=""/>
      </div>
      <div class="icons-right">
        <img src={bookmark} alt=""/>
      </div>
    </div>
    <div class="card-description">
      <h3>user.cat</h3>
      <span>Hola!</span>
    </div>
    <Comments/>
  </div>
</div>

<style>
  .card-container{
    border-bottom: 1px solid gray;
    padding: 30px 0;
    max-width: 500px;
    width: 100%;
  }
  .card-photo{

  }
  figure{
    margin: 0;
  }
  figure > img{
    width: 100%;
  }
</style>
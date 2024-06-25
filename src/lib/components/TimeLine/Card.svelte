<script>
  import settings from "$lib/assets/svg/three-dots.svg"
  import heart from "$lib/assets/svg/heart.svg"
  import share from "$lib/assets/svg/share.svg"
  import bookmark from "$lib/assets/svg/bookmark.svg"
  import Comments from "$lib/components/Timeline/Comments.svelte"

  export let id;
  export let url;
  export let width;
  export let height;
  export let breeds;

  const API = "https://api.thecatapi.com/v1/";
	const API_KEY = import.meta.env.VITE_API_KEY;

  const dataPost = {
    "image_id": id
  }

  async function handlerFavourite(){
    await fetch(`${API}favourites`, {
      method: "POST",
      body: JSON.stringify(dataPost),
      headers: {
        "Content-Type": "application/json",
        "x-api-key": API_KEY
      }
    })
    .catch((error) => console.error("Error:", error))
  }

</script>
  <div class="card-container">
    <div class="card-header">
      <div class="card-user">
        <img src={url} alt="user-logo"/>
        <div class="card-name-user">
          <p class="name-user">{breeds[0].name}.{id.toLowerCase()}</p>
          <p>Origin, {breeds[0].origin}</p>
        </div>
      </div>
      <div class="card-settings">
        <img src={settings} alt="settings-logo"/>
      </div>
    </div>
    <div class="card-photo">
      <figure class="card-photo-figure">
        <img src={url} alt=""/>
      </figure>
    </div>
    <div class="card-icons">
      <div class="icons-left">
        <figure on:click={handlerFavourite}>
          <img src={heart} alt=""/>
        </figure>
        <a href="https://www.facebook.com/sharer/sharer.php?u=https://catstagram.com" target="_blank">
          <img src={share} alt=""/>
        </a>
      </div>
      <div class="icons-right">
        <a href={breeds[0].wikipedia_url} target="_blank">
          <img src={bookmark} alt=""/>
        </a>
      </div>
    </div>
    <div class="card-description">
      <p><span>{breeds[0].name}.{id.toLowerCase()}</span> {breeds[0].description}</p>
    </div>
    <Comments id={id}/>
  </div>

<style>
  .card-container{
    border-bottom: 1px solid rgb(218, 218, 218);
    padding: 30px 0;
    max-width: 500px;
    width: 100%;
    display: flex;
    flex-direction: column;
    gap: 10px;
  }
  .card-header{
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 8px;
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
  figure{
    margin: 0;
  }
  .name-user{
    margin: 0;
    text-wrap: nowrap;
    font-size: 16px;
    font-weight: 800;
  }
  .card-name-user p:nth-of-type(2){
    margin: 0;
    font-size: 10px;
    text-wrap: nowrap;
  }
  .card-photo-figure{
    margin: 0;
    width: 100%;
  }
  .card-photo-figure > img{
    width: 100%;
    object-fit: contain;
    border-radius: 4px;
  }
  .card-icons{
    width: 100%;
    display: flex;
    justify-content: space-between;
  }
  .icons-left{
    display: flex;
    gap: 10px;
  }
  .icons-left figure{
    cursor: pointer;
  }
  .icons-left a img{
    width: 20px;
  }
  .icons-right img{
    width: 18px;
    cursor: pointer;
  }
  .card-description{
    display: flex;
    align-items: start;
    gap: 4px;
    font-size: 12px;
  }
  .card-description p{
    margin: 0;
  }
  .card-description span{
    font-weight: 800;
  }
</style>
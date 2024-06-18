<script>
  import settings from "$lib/assets/svg/three-dots.svg"
  import heart from "$lib/assets/svg/heart.svg"
  import share from "$lib/assets/svg/share.svg"
  import bookmark from "$lib/assets/svg/bookmark.svg"
  import Comments from "$lib/components/Timeline/Comments.svelte"
  import Modal from "../Modal/Modal.svelte"
  import { blur } from "svelte/transition"
	import Share from "../Modal/Share.svelte";

  export let id;
  export let url;

  let isModal = false;

  function handleModal(){
    isModal = !isModal;
  }
</script>
  <div class="card-container">
    {#if isModal}
      <div transition:blur>
        <Modal>
          <Share on:clik={handleModal}/>
        </Modal>
      </div>
    {/if}
    <div class="card-header">
      <div class="card-user">
        <img src={url} alt="user-logo"/>
        <div class="card-name-user">
          <p class="name-user">{id.toLowerCase()}.cat</p>
          <p>Lima, Peru</p>
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
        <img src={heart} alt=""/>
        <img src={share} alt="" on:click={handleModal}/>
      </div>
      <div class="icons-right">
        <img src={bookmark} alt=""/>
      </div>
    </div>
    <div class="card-description">
      <p>{id.toLowerCase()}.cat</p>
      <span>Hello cat!</span>
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
    gap: 8px;
  }
  .icons-left img{
    cursor: pointer;
  }
  .icons-left img:nth-of-type(2){
    width: 20px;
  }
  .icons-right img{
    width: 18px;
  }
  .card-description{
    display: flex;
    align-items: start;
    gap: 4px;
  }
  .card-description p{
    margin: 0;
    font-weight: 800;
  }
</style>
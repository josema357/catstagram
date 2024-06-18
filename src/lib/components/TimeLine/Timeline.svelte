<script>
  import Card from "./Card.svelte";
	import Skeleton from "./Skeleton.svelte";
	import UserUnknow from "./UserUnknow.svelte";
  export let data = [];
</script>

<div class="timeline">
  <div class="timeline-container">
    { #each data as cat }
      <Card {...cat}/>
    {:else}
      <div class="container-skeleton">
        <Skeleton/>
        <Skeleton/>
        <Skeleton/>
      </div>
    {/each}
    
  </div>
  <div class="timeline-side">
    <UserUnknow count={21}/>
    <hr>
    <UserUnknow count={22}/>
    <UserUnknow count={34}/>
    <UserUnknow count={25}/>
    <UserUnknow count={56}/>
    <UserUnknow count={89}/>
    <footer>
      <span>Information</span>
      <span>Blog</span>
      <span>Jobs</span>
      <span>API</span>
      <span>Conditions</span>
      <span>Contacts</span>
    </footer>
    <p class="year">© 2024 JOSE MANUEL</p>
  </div>
</div>

<style>
  .timeline{
    display: flex;
    margin-left: 240px;
    scroll-behavior: auto;
    padding: 20px 40px 20px 0;
    box-sizing: border-box;
    justify-content: space-around;
  }
  .container-skeleton{
    display: flex;
    width: 100%;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  hr{
    width: 100%;
  }
  .timeline-container{
    flex: 2;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .timeline-side{
    padding-top: 16px;
    flex: 1;
    display: flex;
    flex-direction: column;
    gap: 8px;
  }
  footer{
    display: flex;
    flex-wrap: wrap;
    padding-top: 8px;
    gap: 10px;
    font-size: 12px;
    font-weight: 400;
    color: rgb(145, 145, 145);
  }
  footer > span{
    cursor: pointer;
  }
  .year{
    margin: 0;
    font-size: 12px;
    font-weight: 400;
    color: rgb(145, 145, 145);
  }
  @media(max-width:1200px){
    .timeline{
      margin-left: 70px;
    }
  }
  @media(max-width:1050px){
    .timeline-side{
      display: none;
    }
    .timeline{
      padding: 20px 40px;
    }
  }
  @media(max-width: 750px){
    .timeline{
      margin-left: 0;
      margin-top: 60px;
      margin-bottom: 50px;
      padding: 10px;
    }
  }
</style>
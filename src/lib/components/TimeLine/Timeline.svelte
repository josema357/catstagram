<script>
  import Card from "./Card.svelte";
  export let data = [];

  console.log(data);
</script>

<div class="timeline">
  <div class="timeline-container">
    { #each data as cat }
      <Card {...cat}/>
    {:else}
      <p>Loading...</p>
    {/each}
    
  </div>
  <div class="timeline-side">
     --ererererere --ererererere --ererererere --ererererere --ererererere --ererererere --ererererere
  </div>
</div>

<style>
  .timeline{
    display: flex;
    margin-left: 240px;
    scroll-behavior: auto;
    padding: 20px 40px;
    box-sizing: border-box;
    justify-content: space-around;
  }
  .timeline-container{
    flex: 2;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .timeline-side{
    flex: 1;
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
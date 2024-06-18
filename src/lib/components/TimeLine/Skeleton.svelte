<div class="card-container">
  <div class="card-header">
    <div class="image placeholder"></div>
    <div class="text">
      <p class="name placeholder"></p>
      <span class="place placeholder"></span>
    </div>
  </div>
  <div class="card-content">
    <div class="card-image placeholder"></div>
    <div class="card-text">
      <div class="icons-left">
        <div class="placeholder"></div>
        <div class="placeholder"></div>
      </div>
      <div class="icons-right placeholder"></div>
    </div>
  </div>
</div>

<style>
  .card-container{
    max-width: 500px;
    width: 100%;
    padding-bottom: 32px;
  }
  .card-header{
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .card-header .text{
    width: 100%;
    display: flex;
    height: 100%;
    flex-direction: column;
    gap: 4px;
  }
  .name{
    margin: 0;
    width: 100%;
    max-width: 150px;
    height: 12px;
    border-radius: 4px;
  }
  .place{
    width: 100%;
    max-width: 90px;
    height: 12px;
    border-radius: 4px;
  }
  .card-header .image{
    width: 40px;
    height: 36px;
    border-radius: 50%;
  }
  .placeholder{
    background-color: rgb(237, 237, 237);
    animation-name: placeholder;
    animation-duration: 2s;
    animation-iteration-count: infinite;
  }
  /*------------------------------------*/
  .card-content{
    padding-top: 16px;
    display: flex;
    flex-direction: column;
    gap: 16px;
  }
  .card-image{
    width: 100%;
    height: 250px;
    border-radius: 4px;
  }
  .card-text{
    width: 100%;
    display: flex;
    justify-content: space-between;
  }
  .icons-left{
    display: flex;
    gap: 4px;
  }
  .icons-left div{
    width: 30px;
    height: 30px;
    border-radius: 50%;
  }
  .icons-right{
    width: 30px;
    height: 30px;
    border-radius: 50%;
  }
  @keyframes placeholder{
    0%{
      background-color: rgb(237, 237, 237);
    }
    50%{
      background-color: rgb(224, 224, 224);
    }
    100%{
      background-color: rgb(237, 237, 237);
    }
  }
</style>
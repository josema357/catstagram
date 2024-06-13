<script>
  export let id;
</script>

<div class="comments">
  <div class="comments-content">
    <div class="comments-users">
      <p>{id.toLowerCase()}</p>
      <span>hi cat - hi cat - hi cat</span>
    </div>
    <div class="comments-add">
      <form class="comments-form">
        <input type="text" class="comments-input" placeholder="Add comment..." id="text">
        <button type="submit">Post</button>
      </form>
    </div>
  </div>
</div>

<style>
  .comments-content{
    display: flex;
    flex-direction: column;
    gap: 12px;
  }
  .comments-users{
    display: flex;
    align-items: start;
    gap: 4px;
  }
  .comments-users p{
    margin: 0;
    font-weight: bold;
    font-size: 14px;
  }
  .comments-users span{
    font-size: 14px;
  }
  .comments-form{
    display: flex;
  }
  .comments-input{
    width: 100%;
    border: none;
    outline: none;
  }
  .comments-input::placeholder{
    font-weight: 600;
  }
  .comments-form button{
    border: none;
    background: none;
    cursor: pointer;
    font-weight: 600;
    width: 50px;
  }
</style>
<svelte:head>
	<title>Catstagram</title>
</svelte:head>
<script>
  function redirect(){
    window.location.href="/app/inicio";
  }
</script>
<div class="main">
  <div class="box">
    <h1 class="box-title">Catstagram</h1>
    <section>
      <div class="box-input">
        <input type="text" placeholder="Phone number, username or email"/>
        <input type="password" placeholder="Password"/>
        <button on:click={redirect}>Click here</button>
      </div>
      <p class="separator">or</p>
      <div class="box-recovery">
        <p>Sign in with Facebook</p>
        <p><a href="/">Did you forget your password?</a></p>
      </div>
    </section>
  </div>
  <div id="box-signup" class="box">
    <p>Don't have an account? <a href="/">Sign up</a></p>
  </div>
  <footer>
    <span>Information</span>
    <span>Blog</span>
    <span>Jobs</span>
    <span>API</span>
    <span>Conditions</span>
    <span>Contacts</span>
  </footer>
</div>

<style>
  .main{
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100dvh;
    position: relative;
    margin: 0 8px;
    box-sizing: border-box;
  }
  .box{
    border: 1px solid rgb(197, 197, 197);
    border-radius: 3px;
    width: 100%;
    max-width: 350px;
    padding: 40px 40px 10px;
    box-sizing: border-box;
    margin-bottom: 10px;
  }
  .box-title{
    font-size: 30px;
    text-align: center;
    margin-bottom: 30px;
    font-family: "Pacifico", cursive;
    font-style: normal;
    font-weight: 400;
  }
  .box-input{
    display: flex;
    flex-direction: column;
  }
  input{
    padding: 10px;
    font-size: 12px;
    border: 1px solid rgb(197, 197, 197);
    outline: none;
    border-radius: 3px;
    margin-bottom: 10px;
    background-color: rgb(248, 248, 248);
  }
  button{
    padding: 10px;
    background-color: rgb(66, 183, 42);
    border: none;
    border-radius: 5px;
    color: white;
    font-weight: 600;
    cursor: pointer;
  }
  .separator{
    text-align: center;
    color: rgb(174, 174, 174);
  }
  .box-recovery{
    text-align: center;
    font-size: 12px;
    font-weight: 600;
    color: rgb(56, 81, 133);
  }
  .box-recovery > p{
    cursor: pointer;
  }
  .box-recovery a{
    text-decoration: none;
    color: rgb(65, 62, 101);
    font-weight: 400;
  }
  #box-signup{
    padding: 0 40px;
    text-align: center;
  }
  #box-signup > p{
    font-size: 12px;
  }
  #box-signup a{
    text-decoration: none;
    font-weight: 600;
    color: rgb(66, 183, 42)
  }
  footer{
    position: absolute;
    bottom: 0;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 10px;
    font-size: 14px;
    font-weight: 400;
    color: rgb(174, 174, 174);
    margin-bottom: 8px;
  }
  footer > span{
    cursor: pointer;
  }
  @media(max-width:260px){
    .box{
      padding: 40px 0px 10px;
    }
  }
</style>


<script>

</script>

<div class="loader"></div>

<style>
  .loader {
    margin-top: 20px;
  border: 10px solid #f3f3f3; /* Light grey */
  border-top: 10px solid black; /* Blue */
  border-radius: 50%;
  width: 40px;
  height: 40px;
  animation: spin 2s linear infinite;
}

@keyframes spin {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}
</style>
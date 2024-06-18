<div class="modal">
  <div class="modal-overlay"/>
  <slot></slot>
</div>

<style>
  .modal{
    position: relative;
  }
  .modal-overlay{
    background-color: rgba(0, 0, 0, 0.7);
    position: fixed;
    width: 100%;
    height: 100%;
    inset: 0;
    z-index: 8;
    cursor: pointer;
  }
</style>
<script>
    export let titre;
    export let description;
    export let priorite
    function minus()
    {
        priorite -= 1;
    };
    function plus()
    {
        priorite += 1;
    };
</script>

<div class="card">
    <header class="card-header">
      <p class="card-header-title">{titre}</p>
      <button class="card-header-icon" aria-label="more options">
        <span class="icon">
          <i class="fas fa-angle-down" aria-hidden="true"></i>
        </span>
      </button>
    </header>
    <div class="card-content">
      <div class="content">
{description}
      </div>
    </div>
    <footer class="card-footer">
      <button class="card-footer-item" on:click={minus}>-</button>
      <p class="card-footer-item">{priorite}</p>
      <button class="card-footer-item" on:click={plus}>+</button>
    </footer>
  </div>
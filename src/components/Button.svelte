<script>
  export let count;
  export let label;
</script>

<button on:click>{label} {count || ''}</button>

<style>
</style>

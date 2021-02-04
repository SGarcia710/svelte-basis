<script>
  import { count } from '../store/store';

  const handleClick = () => {
    count.update((actualValue) => actualValue + 1);
  };
</script>

<button on:click={handleClick}>
  Click {$count || ''}
</button>

<style>
  button {
    background-color: #f76027;
    color: white;
    border: none;
    border-radius: 4px;
    padding: 0.5rem;
    text-transform: uppercase;
    cursor: pointer;
  }
</style>

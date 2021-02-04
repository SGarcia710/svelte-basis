<script>
  import Button from './Button.svelte';

  let someText = `Frontend Developer at Overactive`;
  let count = 0;
  let styles = {
    darkMode: false,
  };

  const handleClick = () => {
    count += 1;
  };

  const toggleTheme = () => {
    styles.darkMode = !styles.darkMode;
    window.document.body.classList.toggle('dark-mode');
  };
</script>

<div class="About">
  {#if !styles.darkMode}
    <p>
      {someText}
    </p>
  {:else}
    <p>Hello dark mode</p>
  {/if}

  <Button on:click={handleClick} {count} label="Click" />
  <Button
    on:click={toggleTheme}
    label={` ${styles.darkMode ? 'Light mode' : 'Dark mode'}`}
  />
</div>

<style>
  p {
    color: var(--theme-color);
  }
</style>

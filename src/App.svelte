<script>
  import About from './components/About.svelte';
  import Text from './components/Text.svelte';
  import Person from './components/Person.svelte';
  import Skills from './components/Skills.svelte';
  import Input from './components/Input.svelte';
  import Photos from './components/Photos.svelte';
  import ButtonCount from './components/ButtonCount.svelte';

  export let name; // Para que sea posible ponerle las props
  export let lastName; // desde afuera, se necesita el export
  let svelteLogo = 'https://arepa.s3.amazonaws.com/svelte-logo.png';
  let inputValue;

  const data = {
    name: 'Sebastian',
    lastName: 'Garcia Ospina',
    age: 24,
  };
</script>

<main>
  <h1>Hello {name} {lastName}!</h1>
  <About />
  <Text anotherText="Hola" />
  <Text />
  <Person {...data} />
  <Skills />
  <Photos />
  <ButtonCount />
  <Input value={inputValue} />
  <img src={svelteLogo} alt="Svelte logo" />
</main>

<style>
  /* Estilos globales:  */
  :global(body) {
    background-color: #f2eee2;
    color: #0084f6;
  }

  /* Variables globales */
  :global(:root) {
    --theme-color: purple;
  }
  :global(body.dark-mode) {
    background-color: #1d3040;
    color: #bfc2c7;
  }

  /* Estilos del componente */
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  main img {
    width: 30%;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
    padding: 0;
    margin: 0;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

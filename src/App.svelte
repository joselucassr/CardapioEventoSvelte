<script>
  import { cardapio } from './assets/cardapio';
  import Produto from './lib/Produto.svelte';

  const { tapiocas, diversos, cuscuz, bebidas } = cardapio;
  const colors = ['#FF7C00', '#0264B9', '#B20093', '#3B9B1B'];

  const capitalize = (string) => {
    return string.charAt(0).toUpperCase() + string.substring(1).toLowerCase();
  };
</script>

<!-- <h1>Cardápio</h1> -->
<main>
  {#each Object.keys(cardapio) as tipo, i}
    <section class={tipo}>
      <h2 style="color: {colors[i]}">{capitalize(tipo)}</h2>
      <div class="cards">
        {#each cardapio[tipo] as { nome, preco } (nome)}
          <Produto {nome} {preco} color={colors[i]} />
        {/each}
      </div>
    </section>
  {/each}
</main>

<style>
  :root {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen,
      Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  }

  h1 {
    margin-bottom: 0;
    margin-left: 2.5vw;

    font-weight: 400;
    color: #333333;
  }

  h2 {
    /* margin-bottom: 0; */
  }

  main {
    display: flex;
    flex-direction: column;
    gap: 2rem;
    align-items: center;

    margin-bottom: 6rem;
  }

  section {
    width: 90vw;
    max-width: 900px;
  }

  .cards {
    display: flex;
    flex-direction: column;
    gap: 2rem;
  }
</style>

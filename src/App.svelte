<script>
  import { cardapio } from './assets/cardapio';
  import Produto from './lib/Produto.svelte';

  const { tapiocas, diversos, cuscuz, bebidas } = cardapio;
  const colors = ['#FF7C00', '#0264B9', '#B20093', '#3B9B1B'];

  const capitalize = (string) => {
    return string.charAt(0).toUpperCase() + string.substring(1).toLowerCase();
  };
</script>

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

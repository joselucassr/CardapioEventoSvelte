<script>
  export let nome;
  export let preco;
  export let color;
</script>

<div class="produto" style="border-color: {color}; color: {color}; ">
  <!-- box-shadow: 10px 10px 10px {color}20; -->
  <div class="nome">{nome}</div>
  <div class="preco">R$ {preco.toFixed(2).replace('.', ',')}</div>
</div>

<style>
  .produto {
    display: flex;
    flex-direction: column;
    gap: 1rem;
    padding: 20px;
    justify-content: space-between;

    border: 2px solid black;
    border-radius: 0.5rem;
    border-style: dashed;
  }

  .nome {
    font-weight: bold;
    font-size: 1.4rem;
  }

  .preco {
    font-size: 1.25rem;
  }
</style>

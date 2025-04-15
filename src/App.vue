<script setup>

</script>

<template>
  <header>
    <div class="titulo">
      <p class="um">
        IFbooks
      </p>
      <p class="dois">
        a preço a<br>leitura
      </p>
    </div>
    <div class="barra-pesquisa">
    <i class="fas fa-search icone-pesquisa"></i>
    <input type="text" placeholder="Pesquisar...">
  </div>
    <div>
      <ul class="page">
        <li>
          Termos
        </li>
        <li>
          Equipe
        </li>
        <li>
          Envio
        </li>
        <li>
          Devoluções
        </li>
      </ul>
    </div>
    <div>
      <ul class="icon">
        <li>
          <i class="fa-solid fa-cart-shopping"></i>
        </li>
        <li class="icone">
          <i class="fa-solid fa-heart"></i>
        </li>
        <li>
          <i class="fa-solid fa-user"></i>
        </li>
        <li></li>
      </ul>
    </div>
  </header>

  <main>

  </main>
</template>

<style scoped>
/*                   GERAL                      */
li {
  list-style-type: none;
}



/*                     HEADER                   */
header {
  display: flex;
  justify-content: center;

}

/*tituluzinho*/
div.titulo {
  display: flex;
  margin: 1vw 3vw 0 0;
}

div.titulo p.um {
  margin: 1vw 1vw 0 0;
  font-size: 1.5rem;
}

div.titulo p.dois {
  word-break: normal;
  border-left: 2px solid #27AE60;
  padding-left: 1vw;
  color: #27AE60;
}

/*barra de pesquisa*/
.barra-pesquisa {
      position: relative;
      width: 300px;
    }

    .barra-pesquisa input {
      width: 100%;
      padding: 10px 10px 10px 35px; /* espaço para o ícone */
      font-size: 16px;
      border: 1px solid gre;
      border-radius: 4px;
      margin: 1.5vw 0 0 0;
      background-color: #747474;
    }

    .icone-pesquisa {
      position: absolute;
      top: 50%;
      left: 17vw;
      margin: 6px 0 0 0;
      transform: translateY(-50%);
      color: #888;
      font-size: 16px;
      pointer-events: none;
    }

/*paginazinhas*/
div ul.page {
  display: flex;
  margin-left: 1vw;
}

div ul.page li {
  margin: 1vw 2vw 0 3vw;
}

/*iconezinhos*/
div ul.icon {
  display: flex;
  justify-content: space-between
}

div ul.icon li {
  margin: 1vw 1vw 0 1vw;
}

div ul.icon li.icone {
  border-right: 1px solid;
  border-left: 1px solid;
  padding: 0 1vw 0 1vw;
}
</style>

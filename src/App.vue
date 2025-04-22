<script setup>
const produtos = [
    {
        id: 1,
        titulo: 'Chain of Iron: Volume 2',
        resenha: 'Cassandra Clare',
        preco: 23.24,
        capa: 'https://cdn.kobo.com/book-images/6db37b19-2d7d-4e5b-a1d8-b006188c9db4/1200/1200/False/the-last-hours-chain-of-iron.jpg',
    },
    {
        id: 2,
        titulo: 'Chain of Thorns',
        resenha: 'Cassandra Clare',
        preco: 23.24,
        capa: 'https://cdn.kobo.com/book-images/4aa958d8-c1ed-4bf2-90ce-fef019f92a15/353/569/90/False/the-last-hours-chain-of-thorns.jpg',
    },
    {
        id: 3,
        titulo: 'City of Fallen Angels',
        resenha: 'Cassandra Clare',
        preco: 13.94,
        capa: 'https://m.media-amazon.com/images/I/815MzJpG6iL._AC_UF1000,1000_QL80_.jpg',
    },
    {
        id: 4,
        titulo: 'Nona the Ninth',
        resenha: 'Cassandra Clare',
        preco: 16.84,
        capa: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcThSjYxA73VNaIFSItXwUsuMHkRQo7f8PXGBg&s',
    },
    {
        id: 5,
        titulo: 'Harlem Shuffle',
        resenha: 'Colson Whitehead',
        preco: 26.92,
        capa: 'https://m.media-amazon.com/images/I/81ZPFCh0xML.jpg',
    },
    {
        id: 6,
        titulo: 'Two Old Women',
        resenha: 'Velma Wallis',
        preco: 13.95,
        capa: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQBXEMa4hM454G7Whh7PrDN8R_oYebpPdFl_Q&s',
    },
    {
        id: 7,
        titulo: 'Carrie Soto Is Back',
        resenha: 'Taylor Jenkins Reid',
        preco: 26.04,
        capa: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQGJROWBwFV4AHVxK1H0NNVTiEBBlVbmnf2gg&s',
    },
    {
        id: 8,
        titulo: 'Book Lovers',
        resenha: 'Emily Henry',
        preco: 15.81,
        capa: 'https://m.media-amazon.com/images/I/71Xy4AL7jKL.jpg',
    }
];
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
  <body>
    <section class="listalivros">
    <h1>Lista de Livros</h1>
    <div v-for="produto in produtos" :key="produto.id" class="livro">
      <img :src="produto.capa" alt="" width="100%" height="100%" />
      <h2>{{ produto.titulo }}</h2>
      <p class="res">{{ produto.resenha }}</p>
        <strong>R$ {{ produto.preco.toFixed(2) }}</strong>
        <br>
      <button class="compra">
            <i class="fa-solid fa-cart-shopping"></i>
            <p>comprar</p>
      </button>      
    </div>
  </section>

  </body>
  
</template>

<style scoped>
/*                   GERAL                      */
li {
  list-style-type: none;
}
* {
  font-family: 'SuaFonte', sans-serif; /* Substitua 'SuaFonte' pela fonte que você quer */
}

/* Garantindo que os ícones Font Awesome usem sua própria fonte */
i, .fa {
  font-family: 'Font Awesome 5 Free', 'Font Awesome 5 Free Solid', 'FontAwesome', sans-serif !important;
}

/*                     HEADER                   */
header {
  display: flex;
  justify-content: center;
  border-bottom: 2px solid #27AE60;
  
}

/*tituluzinho*/
div.titulo {
  display: flex;
  margin: 1vw 3vw 4px 0;

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
      border: none;
      border-radius: 4px;
      margin: 1.5vw 0 0 0;
      background-color: #F1F1F1;
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
  color: #7B7881;
}

/*iconezinhos*/
div ul.icon {
  display: flex;
  justify-content: space-between;
  color: #27AE60;
}

div ul.icon li {
  margin: 1vw 1vw 0 1vw;
}

div ul.icon li.icone {
  border-right: 1px solid;
  border-left: 1px solid;
  padding: 0 1vw 0 1vw;
}
/* SECTION LIVROSSSSSSSSSSSSSSSSSSSSSSSS*/
section.listalivros {
  margin: 5vw;
}

section.listalivros h1 {
  font-size: 2rem;
  color: #231F2D;
}


section.listalivros .livro {
  display: inline-block;
  width: 20%;
  margin: 1.5vw 1.5vw; 
}

section.listalivros .livro img {
  border-radius: 5px;
}

section.listalivros .livro h2 {
  font-size: 1.7rem;
  color: #231F2D;
}

section.listalivros .livro p.res {
  color: #7B7881;
}

section.listalivros .livro strong {
  
}
section.listalivros .livro .compra {
  background-color: #27AE60;
  width: 100%;
  height: 40px;
  color: white;
  padding: 10px;
  border: none;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.5rem;
  font-size: 1.1rem;
  margin-top: 1vw;
}

</style>

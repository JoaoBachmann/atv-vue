<script setup>
import { ref, reactive, computed } from "vue";
const produtos = reactive([
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
]);

const carrinho = reactive({
  items: [
  ]
});

function remover(a, id) {
  let posicaoItem = a.findIndex(objeto => objeto.id == id)
  a.splice(posicaoItem, 1)
}
function decrementar(item) {
  if (item.quantidade > 1) {
    item.quantidade--
  } else {
    remover(carrinho.items, item.id)
  }
}

function incrementar(item) {
  item.quantidade++
}
function adicionar(item) {
  carrinho.items.push({ ...item, quantidade: 1 })
}

function totalCarrinho() {
  let total = 0;
  for (let item of carrinho.items) {
    total += item.preco * item.quantidade;
  }
  return total.toFixed(2).replace(".", ",");
}

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


    <section class="autorL">
      <div class="sobreA">
        <p class="autor">Autor de Abril</p>
        <h2 class="negrito">Eric-Emanuel Schmitt</h2>
        <p class="texto">
          Eric-Emmanuel Schmitt has been awarded more than 20 literary prizes and distinctions, and
          in 2001 he received the title of Chevalier des Arts et des Lettres. His books have been
          translated into over 40 languages.
        </p>
        <button>
          <a href="#"></a>
          Acessar página do livro</button>
      </div>

      <div class="fotoLivro">
        <img src="/public/Imagens/book.png" alt="livro" />
        <p>*within the stock limit</p>
      </div>
    </section>

    <section class="opcoes">
      <div class="linha">
        <i class="fa-solid fa-truck"></i>
        <p>Frete grátis para SC</p>
      </div>
      <div class="linha">
        <i class="fa-solid fa-star"></i>
        <p>Livros recomendados</p>
      </div>
      <div>
        <i class="fa-solid fa-book-open"></i>
        <p>Mais vendidos</p>
      </div>
    </section>
    <section class="listalivros">
      <h1>Lista de Livros</h1>
      <div v-for="produto in produtos" :key="produto.id" class="livro">
        <img :src="produto.capa" alt="" width="100%" height="100%" />
        <h2>{{ produto.titulo }}</h2>
        <p class="res">{{ produto.resenha }}</p>
        <strong>R$ {{ produto.preco.toFixed(2).replace(".", ",") }}</strong>
        <br>
        <button class="compra" @click="adicionar(produto)">
          <i class="fa-solid fa-cart-shopping"></i>
          <p>comprar</p>
        </button>
        
      </div>
    </section>
    <section class="carrinho">
      <h1>Carrinho</h1>
      <div class="titulos">
        <h2>
          Titulos
        </h2>
        <h2 class="qnt">
          Quantidade
        </h2>
        <h2>
          subtotal
        </h2>
      </div>
      <div v-for="item in carrinho.items" :key="item.id" class="  itensCarrinhos">
        <div class="maior">
          <img class="imgCarrinho" :src="item.capa" alt="">
          <div>
            <h2>{{ item.titulo }}</h2>
            <p>{{ item.resenha }}</p>
            <strong>R${{ item.preco.toFixed(2).replace(".", ",") }}</strong>
          </div>
        </div>
        <div class="contador">
          <button @click="decrementar(item)">-</button>
          <strong>{{ item.quantidade }}</strong>
          <button @click="incrementar(item)">+</button>
        </div>
        <strong class="preco">R${{ (item.preco * item.quantidade).toFixed(2).replace(".", ",") }}</strong>
      </div>
      <button class="butao">Voltar para loja</button>
      <ul class="principal">
        <li class="cupom">
          <input type="text" placeholder="Código do Cupom" name="search">
          <button type="submit">Inserir Cupom</button>
        </li>
        <li class="totalC">
          <h2>Total da Compra</h2>
          <div class="maiorFinal">
            <div>
              <p>Produtos:</p>
              <strong>{{ carrinho.items.length }}</strong>
            </div>
            <div class="border">
              <p>Frete:</p>
              <strong>Gratis</strong>
            </div>
            <div>
              <p>Total:</p>
              <strong>R$ {{ totalCarrinho() }}</strong>
            </div>
          </div>
          <button>Ir Para o Pagamento</button>
        </li>
      </ul>
    </section>
  </body>
  <footer>
    <div class="pe">
      <div class="unha">
        <p>IFbooks</p>
        <i class="fa-brands fa-square-facebook"></i>
        <i class="fa-brands fa-square-instagram"></i>
        <i class="fa-brands fa-square-x-twitter"></i>
      </div>
      <div class="ifbook">
        <p>Contato</p>
        <div class="redes">
          <i class="fa-solid fa-phone"> </i>
          <p>+55 47 40045263</p>
        </div>
        <div class="redes">
          <i class="fa-solid fa-clock"> </i>
          <p>8h às 23h - Seg a Sex</p>
        </div>
        <div class="redes">
          <i class="fa-solid fa-envelope"></i>
          <p>contato@ifbooks.com</p>
        </div>
        <div class="img">
          <img src="../public/Imagens/paipal 1.png" alt="paypal">
          <img src="../public/Imagens/MasterCard-Logo-1979 1.png" alt="Master Card">
          <img src="../public/Imagens/VISA-card-logo- 1.png" alt="Visa">
        </div>
      </div>
    </div>
    <div class="theLast">
      <P>© Alguns direitos reservados. IFbooks 2025. </P>
    </div>
  </footer>

</template>
<style scoped>
/*                   GERAL                      */
li {
  list-style-type: none;
}

* {
  font-family: 'SuaFonte', sans-serif;
  /* Substitua 'SuaFonte' pela fonte que você quer */
}

/* Garantindo que os ícones Font Awesome usem sua própria fonte */
i,
.fa {
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
  border-left: 2px solid;
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
  padding: 10px 10px 10px 35px;
  /* espaço para o ícone */
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

section.listalivros .livro strong {}

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

/* SECTION CARRINHOSSSSSSSSSSSSSSSSSSS*/
section.carrinho h1 {
  color: #27AE60;
  font-size: 3.5rem;
  margin: 0 0 0 7vw;
}

section.carrinho div.titulos {
  display: flex;
  justify-content: space-between;
  margin: 6vw 8vw 0 8vw;
  border-bottom: 2px solid #27AE60;

}

.itensCarrinhos {
  display: flex;
  justify-content: space-between;
  margin: 4vw 8vw 4vw 8vw;
  border-bottom: 1px solid grey;
}
section.carrinho .maior {
  max-width: 30%;
  display: flex;
  margin-bottom: 3vw;
}
section.carrinho .maior div {
  margin: 2vw;
}
.imgCarrinho {
  width: 8vw;
  height: 12vw;
  border-radius: 4px;
}
section.carrinho .maior div h2 {
  font-size: 2rem;
  margin-top: 0;
}
section.carrinho .maior div p {
  color: gray;
}
section.carrinho .maior div strong {
  font-size: 2rem;
  margin-top: 2px;
}
.carrinho div.contador {
border: 1px solid;
margin: 1vw 18vw 0 0;
padding: 1vw 2vw;
font-size: 1.4rem;
border-radius: 4px;
max-height: 1.5vw;
}
.carrinho div.contador button {
border: none;
background-color: white;
font-size: 1.4rem;
}
.carrinho strong.preco {
font-size: 2rem;
margin: 3vw 0 0 0;
}
.carrinho div.contador button {
border: none;
background-color: white;
font-size: 1.4rem;
}
.carrinho strong.preco {
font-size: 2rem;
margin: 3vw 0 0 0;
}
.carrinho button.butao {
  background-color: white;
  border: 1px solid grey;
  border-radius: 4px;
  padding: 1vw 2.5vw;
  font-size: 1.2rem;
  margin-left: 9vw;
}
.carrinho ul.principal {
  display: flex;
  justify-content: space-between;
  margin: 3vw 0 10vw 0;
}
.carrinho ul li.cupom {
  margin: 2vw 0 0 6.8vw;
}
.carrinho ul li.cupom input {
  padding: 1vw 3vw;
  font-size: 1.2rem;
  border: 1px solid black;
  border-radius: 4px;
}
.carrinho ul li.cupom button {
  background-color: #27AE60;
  border: none;
  padding: 1vw 3vw;
  border-radius: 4px;
  margin-left: 2vw;
  color: white;
  font-size: 1.3rem;
}
.carrinho ul li.totalC {
border: 1px solid;
border-radius: 4px;
margin: 2vw 8vw 0 0;
padding: 1vw 1vw 0 1vw;
font-size: 1.1rem;
padding: 0vw 2vw;
}
.carrinho div.maiorFinal div {
display: flex;
align-items: center;
justify-content: space-between;
padding: 0vw ;

}
.carrinho ul li.totalC button {
background-color: #27AE60;
color: white;
font-size: 1.2rem;
border: none;
padding: 1vw 3vw;
margin: 2vw;
border-radius: 4px;
}
.carrinho .border {
border-bottom: 1px solid grey;
border-top: 1px solid grey;
}
/*SECTION AUTOR*/

.autorL {
  display: flex;
  align-items: center;
  padding: 0 10vw;
}

.texto {
  font-size: 1.1vw;
}

.sobreA {
  color: grey;
  font-size: 1.01vw;
  padding: 0 15vw 0 0;
}

.sobreA .autor {
  background-color: white;
  color: #27ae60;
  border: 1px solid;
  width: 20%;
  padding: 0.5vw;
}

.sobreA .negrito {
  color: black;
  font-size: 3vw;
}

.sobreA button {
  font-size: 1.1vw;
  background-color: #27ae60;
  color: white;
  border-color: #27ae60;
  padding: 20px;
}

/*DIV FOTO LIVRO*/

.fotoLivro p {
  padding: 0 0 0 15vw;

}

/*Section OPCOES*/
.opcoes {
  padding: 3vw 0;
  display: flex;
  justify-content: space-between;
  border-top: 2px solid #27ae60;
  border-bottom: 2px solid #27ae60;
}

.opcoes div {
  padding: 0 10vw 0;
  display: flex;
  align-items: center;
  /* Alinha verticalmente */
  gap: 1vw;
  /* Espaço entre o ícone e o texto */
  font-size: 1.2vw;
  font-weight: bolder;
}

.linha {
  border-right: 1px solid grey;
}

/*FOOTER*/
footer {
  background-color: #27ae60;
}

.pe {
  display: flex;
  justify-content: space-between;
}

.pe {
  padding: 1.5vw 5vw;
  border-bottom: 1px solid white;
}

/*lado esquerdo*/
.pe .unha {
  color: white;
  font-size: 1.2vw;
}

.pe .unha i {
  padding: 0 7px 0 0;
}

/*lado direito*/
.ifbook p {
  color: white;
  font-size: 1.1vw;
}

.ifbook i {
  color: white;
  font-size: 1.1vw;
}

.ifbook .redes {
  display: flex;
  align-items: center;
  /* Alinha verticalmente */
}

.redes i {
  padding: 0 10px 0 0;
}

/*cartoes*/
.img {
  padding: 2vw 0;
}

.img img {
  padding: 0 0.5vw;
}

/*theLast*/


.theLast {
  color: #FFFFFF;
  font-size: 1.2vw;
  display: flex;
  justify-content: center;
  padding: 2vw;
}
</style>

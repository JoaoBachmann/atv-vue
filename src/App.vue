<script setup></script>

<template>
  <header></header>

  <main>
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
        <span class="fa-solid fa-truck"></span>
        <p>Frete grátis para SC</p>
      </div>
      <div class="linha">
        <span class="fa-solid fa-star"></span>
        <p>Livros recomendados</p>
      </div>
      <div>
        <span class="fa-solid fa-book-open"></span>
        <p>Mais vendidos</p>
      </div>
    </section>

    <section class="livros">
      <h1>Lançamentos</h1>
    </section>
  </main>
</template>
<style scoped>
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
.opcoes{
  padding: 3vw 0 ;
  display: flex;
  justify-content: space-between;
  border-top: 2px solid #27ae60;
  border-bottom: 2px solid #27ae60;
}

.opcoes div{
  padding: 0 10vw 0 ;
  display: flex;
  align-items: center; /* Alinha verticalmente */
  gap: 1vw; /* Espaço entre o ícone e o texto */
  font-size: 1.2vw;
  font-weight: bolder;
}

.linha{
  border-right: 1px solid grey;
}
</style>

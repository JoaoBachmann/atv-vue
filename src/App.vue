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
  </main>
  <footer>
    <div class="pe">
      <div class="unha">
        <p>IFbooks</p>
        <span class="fa-brands fa-square-facebook"></span>
        <span class="fa-brands fa-square-instagram"></span>
        <span class="fa-brands fa-square-x-twitter"></span>
      </div>
      <div class="ifbook">
        <p>Contato</p>
        <div class="redes">
          <span class="fa-solid fa-phone"></span>
          <p>+55 47 40045263</p>
        </div>
        <div class="redes">
          <span class="fa-solid fa-clock"></span>
          <p>8h às 23h - Seg a Sex</p>
        </div>
        <div class="redes">
          <span class="fa-solid fa-envelope"></span>
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

.pe .unha span {
  padding: 0 7px 0 0;
}

/*lado direito*/
.ifbook p {
  color: white;
  font-size: 1.1vw;
}

.ifbook span {
  color: white;
  font-size: 1.1vw;
}

.ifbook .redes {
  display: flex;
  align-items: center;
  /* Alinha verticalmente */
}

.redes span {
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

.theLast{
  color: #FFFFFF;
  font-size: 1.2vw;
  display: flex;
  justify-content: center;
  padding: 2vw;
}
</style>

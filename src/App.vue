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
  font-size: 1.05vw;
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
  display: flex;
  justify-content: left;
}
</style>

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
  },
]

/*const carrinho = {
    items: [
        {
            id: 1,
            nome: 'Livro 1',
            preco: 49.9,
            quantidade: 1,
            valorTotal: 49.9,
            },
        {
            id: 2,
            nome: 'Livro 2',
            preco: 99.9,
            quantidade: 2,
            valorTotal: 199.8,
        },
    ],
    frete: 0,
    desconto: 0,
    total: 288.3,
};*/
</script>

<template>
  <body>
    <header>
      <div class="header-esquerda">
        <p class="logo">IFbooks</p>
        <p class="dividir">|</p>
        <p class="slogan">
          Apreço <br />
          a leitura
        </p>
      </div>

      <input type="text" placeholder="Pesquisar" class="pesquisa" />

      <nav>
        <ul class="nav-menu">
          <li>Termos</li>
          <li>Equipe</li>
          <li>Envio</li>
          <li>Devoluções</li>

          <li>
            <a href="#"><img src="/public/imagens/Download.png" alt="carrinho de compras" /></a>
          </li>

          <li class="dividir">|</li>

          <li>
            <a href="#"><img src="/public/imagens/heartactive.png" alt="coração" /></a>
          </li>

          <li class="dividir">|</li>

          <li>
            <a href="#"><img src="/public/imagens/User.png" alt="usuário" /></a>
          </li>
        </ul>
      </nav>
    </header>

    <main>
      <section class="eric">
        <div class="texto">
          <span class="autor">Autor de abril</span>
          <h2>Eric-Emanuel Schmitt</h2>
          <p>
            Eric-Emmanuel Schmitt has been awarded more than 20 literary prizes and distinctions,
            and in 2001 he received the title of Chevalier des Arts et des Lettres. His books have
            been translated into over 40 languages.
          </p>
          <span class="livro">Acessar página do livro</span>
        </div>
        <div class="imagem">
          <img src="/public/imagens/image.png" alt="livro do eric emmanuel schmitt" />
        </div>
      </section>

      <section class="lista">
        <ul>
          <li class="borda">
            <img src="/public/imagens/Icon.png" alt="caminhão" />
            <p>Frete grátis para SC</p>
          </li>

          <li class="borda">
            <img src="/public/imagens/Star.png" alt="icone de estrela" />
            <p>Livros recomendados</p>
          </li>

          <li>
            <img src="/public/imagens/Bookopen.png" alt="livro" />
            <p>Mais vendidos</p>
          </li>
        </ul>
      </section>

      <section class="lançamentos">
        <h2>Lançamentos</h2>
        <div v-for="produto in produtos" :key="produto.id" class="livro">
          <img :src="produto.capa" alt="" width="100%" height="100%" />
          <h2>{{ produto.titulo }}</h2>
          <p class="res">{{ produto.resenha }}</p>
          <strong>R$ {{ produto.preco.toFixed(2) }}</strong>
          <br />
          <button class="compra">
            <p>comprar</p>
          </button>
        </div>
      </section>

      <footer>
        <div>
          <div >
            <h3>IFbooks</h3>
            <ul class="icones">
              <li>
                facebook <a href="#"><img src="" alt="" /></a>
              </li>
              <li>instagram</li>
              <li>twitter</li>
            </ul>
          </div>
          <div class="contato">
            <ul>
              <li><h4>Contato</h4></li>
              <li>+55 47 40045263</li>
              <li>8h às 23h - Seg a Sex</li>
              <li>contato@ifbooks.com</li>
            </ul>
            <ul class="cartoes">
              <li>cartao</li>
              <li>cartao</li>
              <li>cartao</li>
            </ul>
          </div>
        </div>
        <p>© Alguns direitos reservados. IFbooks 2025.</p>
      </footer>
    </main>
  </body>
</template>

<style scoped>
header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 12px 30px;
  border-bottom: 2px solid #27ae60;
  background-color: white;
  flex-wrap: wrap;
  gap: 20px;
}

.header-esquerda {
  display: flex;
  align-items: center;
  gap: 10px;
}

.logo {
  font-weight: bold;
  font-size: 16px;
  margin: 0;
}

.slogan {
  font-size: 12px;
  color: #27ae60;
  margin: 0;
}

.dividir {
  color: #27ae60;
}

.pesquisa {
  padding: 8px 12px;
  border: 1px solid #ccc;
  border-radius: 6px;
  width: 300px;
  flex: 1;
  max-width: 400px;
}

.nav-menu {
  display: flex;
  align-items: center;
  gap: 16px;
  list-style: none;
  margin: 0;
  padding: 0;
}

.nav-menu li {
  font-size: 14px;
  display: flex;
  align-items: center;
}

.nav-menu li img {
  width: 20px;
  height: 20px;
}
.eric {
  margin: 2vw 12vw;
  display: flex;
  align-items: center;
}
.eric span.autor {
  border: solid 1.5px #27ae60;
  padding: 8px;
  border-radius: 4px;
  color: #27ae60;
}
.eric h2 {
  margin: 2vw 0 0 0;
  font-size: 2.8rem;
  font-weight: bolder;
  color: black;
}
.eric div.texto {
  width: 60%;
  margin: 3vw 0;
}
.eric div.texto p {
  margin: 0 0 3.5vw 0;
  width: 42%;
}
.eric div.texto span.livro {
  background-color: #27ae60;
  padding: 15px;
  color: white;
}
.lista {
  border-top: 2px solid #27ae60;
  border-bottom: 2px solid #27ae60;
  padding: 3.7vw 0;
}
.lista ul {
  display: flex;
  justify-content: center;
  align-items: center;
}
.lista ul li {
  margin: 0 5vw;
  font-size: 1.5rem;
  color: black;
  font-weight: bolder;
  display: flex;
}
.lista ul li img {
  padding: 0 1.5vw 0 0;
}
.lista ul li.borda {
  border-right: 1px solid #937dc2;
  padding: 0 7vw 0 0;
}
.lançamentos {
  margin: 5vw;
}

.lançamentos h2 {
  font-size: 2rem;
  color: #231f2d;
  font-weight: bold;
}
.lançamentos .livro {
  display: inline-block;
  width: 20%;
  margin: 1.5vw 1.5vw;
}

.lançamentos .livro img {
  border-radius: 5px;
}

.lançamentos .livro h2 {
  font-size: 1.7rem;
  color: #231f2d;
}

.lançamentos .livro p.res {
  color: #7b7881;
}

.lançamentos .livro .compra {
  background-color: #27ae60;
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
footer {
  background-color: #27ae60;
  color: white;
  padding: 4vw 8vw;
}

footer > div {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 2vw;
}

footer ul {
  list-style: none;
  padding: 0;
}

footer h3 {
  font-size: 1.5rem;
  margin-bottom: 1vw;
}

footer .contato li {
  font-size: 1rem;
  margin-bottom: 0.3vw;
  color: lightgrey;
}

footer p {
  text-align: center;
  font-weight: lighter;
  margin-top: 3vw;
  width: 100%;
}

footer h4 {
  font-size: 1.2rem;
  margin-bottom: 0.5vw;
  color: white;
}
footer div ul.icones {
  display: flex;
}
footer div ul.cartoes{
  display: flex;
}
footer div ul.cartoes li {
  margin: 3vw 1vw 0 0;
}
</style>

<script setup>

import { ref } from 'vue';

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

const mostrarCarrinho = ref(false);
const produtoSelecionado = ref(null);

function abrirCarrinho(produto) {
  produtoSelecionado.value = produto;
  mostrarCarrinho.value = true;
}

function voltarParaLoja() {
  mostrarCarrinho.value = false;
}
const carrinho = [
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
    quantidade: 1,
  }
];

function diminuir(qnt) {

}
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
        </ul>
      </nav>

      <div class="elements">
      <button class="barra" @click="abrirCarrinho(produto)"><img src="/public/imagens/Download.png" alt=""></button>
      <button class="barra"><img src="/public/imagens/heartactive.png" alt=""></button>
      <button><img src="/public/imagens/User.png" alt=""></button>
    </div>

    </header>

    <main>
      <section class="eric"  v-if="!mostrarCarrinho">
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

      <section class="lista"  v-if="!mostrarCarrinho">
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

      <section class="lançamentos"  v-if="!mostrarCarrinho">
        <h2>Lançamentos</h2>
        <div v-for="produto in produtos" :key="produto.id" class="livro">
          <img :src="produto.capa" alt="" width="100%" height="100%" />
          <h2>{{ produto.titulo }}</h2>
          <p class="res">{{ produto.resenha }}</p>
          <strong class="preco-lancamento">R$ {{ produto.preco.toFixed(2) }}</strong>
          <br />
          <button class="compra">
            <p>comprar</p>
          </button>
        </div>
      </section>

    
    <section class="carrinho" v-if="mostrarCarrinho">
      <h2>Carrinho</h2>
      <div class="classes">
        <h3>Título</h3>
        <h3 class="q">Quantidade</h3>
        <h3>Subtotal</h3>
      </div>

      <div class="compras" v-for="produto in carrinho" :key="produto.id">
        <div>
          <img :src="produto.capa" alt="" width="8%">
          <div>
            <h3>{{ produto.titulo }}</h3>
            <p>{{ produto.resenha }}</p>
            <p class="preco">R${{ produto.preco }}</p>
          </div>
        </div>

        <div>
          <button @click="">-</button>
          <strong>{{ produto.quantidade }}</strong>
          <button>+</button>
        </div>


      </div>
      
      <button class="Vloja" @click="voltarParaLoja">Voltar para a loja</button>
      <div class="compra">
        <div>
          <input class="cupom" type="text" placeholder="código do cupom"> <input class="inserircpm" type="button"
            value="Inserir Cupom">
        </div>

        <div class="final">
          <h3>Total da Compra</h3>
          <p class="linha">Produtos:</p>
          <p class="linha">Frete:Grátis</p>
          <p>Total: </p>
          <input type="button" value="Ir para o pagamento">
        </div>
      </div>
      </section>
      <footer>
        <div>
          <div>
            <h3>IFbooks</h3>
            <ul class="icones">
              <li><a href="#"><img src="/public/imagens/face.png" alt="" /></a>
              </li>
              <li><a href="#"><img src="/public/imagens/insta.png" alt=""></a>
              </li>
              <li><a href="#"><img src="/public/imagens/tt.png" alt=""></a></li>
            </ul>
          </div>
          <div class="contato">
            <ul>
              <li><h4>Contato</h4></li>
              <li><img src="/public/imagens/Icon (1).png" alt="telefone">+55 47 40045263</li>
              <li><img src="/public/imagens/Icon (2).png" alt="relogio">8h às 23h - Seg a Sex</li>
              <li><img src="/public/imagens/Icon (4).png" alt="email">contato@ifbooks.com</li>
            </ul>
            <ul class="cartoes">
              <li><img src="/public/imagens/paipal 1.png" alt="paipal"></li>
              <li><img src="/public/imagens/MasterCard-Logo-1979 1.png" alt="mastercard"></li>
              <li><img src="/public/imagens/VISA-card-logo- 1.png" alt="visa"></li>
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
body {
  background-color: white;
}
.logo {
  font-weight: bold;
  font-size: 16px;
  margin: 0;
  color: #231f2d;
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
  color: #7B7881;
}

.nav-menu li img {
  width: 20px;
  height: 20px;
}
.eric {
  margin: 2vw 12vw;
  display: flex;
  align-items: center;
  color: black;
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
.preco-lancamento {
  color: #000000; 
  font-size: 1.2rem;
  font-weight: bold;
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
.carrinho {
  padding: 8vw;

}

.carrinho h2 {
  color: #27AE60;
  font-size: 2rem;
  margin: 1vw;
  
}

.carrinho .classes {
  display: flex;
  justify-content: space-between;
  border-bottom: 1px solid #27AE60;
}

.carrinho .classes h3 {
  margin: 0 3vw 1vw;
  font-size: 2rem;
}

.carrinho .classes .q {
  margin-left: 16vw;
}

.carrinho .Vloja {
  margin-top: 6vw;
  border: 2px solid #aaaaaa;
  background-color: white;
  padding: 20px 60px;
  border-radius: 5px;
  font-weight: bold;
  font-size: 1.2rem;
}

.carrinho .cupom {
  margin-top: 6vw;
  border: 2px solid #000000;
  background-color: white;
  padding: 20px 60px;
  border-radius: 5px;
  font-weight: bold;
  font-size: 1.2rem;
}

.carrinho .inserircpm {
  margin-top: 6vw;
  border: none;
  background-color: #27AE60;
  padding: 20px 60px;
  border-radius: 5px;
  font-weight: bold;
  font-size: 1.2rem;
  color: white;
  margin-left: 1vw;
}

.carrinho .compra {
  display: flex;
}

.carrinho .final {
  border: 2px solid black;
  margin-left: 28vw;
  margin-top: 6vw;
  padding: 1vw;
  border-radius: 5px;
}

.carrinho .final h3 {
  font-size: 1.6rem;
}

.carrinho .final .linha {
  border-bottom: 1px solid #000000;
  padding-right: 17vw;
  padding-bottom: 1vw;
}

.carrinho .final input {
  background-color: #27AE60;
  color: white;
  border: none;
  padding: 20px 40px;
  border-radius: 5px;
  font-size: 1.2rem;
  margin-left: 3vw;
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
footer div ul.cartoes {
  display: flex;
}
footer div ul.cartoes li {
  margin: 3vw 1vw 0 0;
}
footer ul.icones li {
  margin: 0 0.5vw ;
}

</style>

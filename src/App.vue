<script setup>
import { ref, reactive, computed } from 'vue'
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

const mostrarCarrinho = ref(false)

function abrirCarrinho() {
  mostrarCarrinho.value = true
}

function voltarParaLoja() {
  mostrarCarrinho.value = false
}

const carrinho = reactive([])

function adicionarAoCarrinho(produto) {
  const item = carrinho.find((p) => p.id === produto.id)
  if (item) {
    item.quantidade++
  } else {
    carrinho.push({ ...produto, quantidade: 1 })
  }
}

function diminuir(produto) {
  if (produto.quantidade > 0) {
    produto.quantidade--
  }
}

function aumentar(produto) {
  produto.quantidade++
}

const totalProdutos = computed(() =>
  carrinho.reduce((soma, produto) => soma + produto.preco * produto.quantidade, 0),
)
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

      <div class="elementos">
        <button class="dividir" @click="mostrarCarrinho = true">
          <img src="/public/imagens/Download.png" alt="" />
        </button>
        <button class="dividir"><img src="/public/imagens/heartactive.png" alt="" /></button>
        <button><img src="/public/imagens/User.png" alt="" /></button>
      </div>
    </header>

    <main>
      <section class="eric" v-if="!mostrarCarrinho">
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

      <section class="lista" v-if="!mostrarCarrinho">
        <ul>
          <li class="borda">
            <img src="/public/imagens/caminhao.png" alt="caminhão" />
            <p>Frete grátis para SC</p>
          </li>

          <li class="borda">
            <img src="/public/imagens/Star.png" alt="icone de estrela" />
            <p>Livros recomendados</p>
          </li>

          <li>
            <img src="/public/imagens/Bookopen.png" alt="livro" />
            <p class="vendidos">Mais vendidos</p>
          </li>
        </ul>
      </section>

      <section class="lançamentos" v-if="!mostrarCarrinho">
        <h2>Lançamentos</h2>
        <div v-for="produto in produtos" :key="produto.id" class="livro">
          <img :src="produto.capa" alt="" width="100%" height="100%" />
          <h2>{{ produto.titulo }}</h2>
          <p class="resenha">{{ produto.resenha }}</p>
          <strong class="preco-lancamento">R$ {{ produto.preco.toFixed(2) }}</strong>
          <br />
          <button class="compra" @click="adicionarAoCarrinho(produto)">
            <p>comprar</p>
          </button>
        </div>
      </section>

      <section class="carrinho" v-if="mostrarCarrinho">
        <h2>Carrinho</h2>
        <div class="titulos">
          <h3>Título</h3>
          <h3 class="quantidade">Quantidade</h3>
          <h3>Subtotal</h3>
        </div>

        <div v-if="carrinho.filter((p) => p.quantidade > 0).length === 0">
          <p>Seu carrinho está vazio.</p>
        </div>

        <div
          class="comprar"
          v-for="produto in carrinho.filter((p) => p.quantidade > 0)"
          :key="produto.id"
        >
          <div class="infoProduto">
            <img :src="produto.capa" alt="" width="8%" class="imagemProduto" />
            <div>
              <h3>{{ produto.titulo }}</h3>
              <p>{{ produto.resenha }}</p>
              <p class="preco">R${{ produto.preco }}</p>
            </div>
          </div>

          <div class="contador">
            <button @click="diminuir(produto)">-</button>
            <strong>{{ produto.quantidade }}</strong>
            <button @click="aumentar(produto)">+</button>
          </div>

          <div class="subtotal">
            <p>R$ {{ (produto.preco * produto.quantidade).toFixed(2) }}</p>
          </div>
        </div>

        <button class="voltarLoja" @click="voltarParaLoja">Voltar para a loja</button>

        <div class="resumoFinal">
          <div class="cupom">
            <input class="codCupom" type="text" placeholder="código do cupom" />
            <input class="inserirCupom" type="button" value="Inserir Cupom" />
          </div>

          <div class="final">
            <h3>Total da Compra</h3>
            <p class="linha">
              <span>Produtos:</span>
              <span class="valor">R$ {{ totalProdutos.toFixed(2) }}</span>
            </p>
            <p class="linha">
              <span>Frete:</span>
              <span class="valor">Grátis</span>
            </p>
            <p>
              <span>Total:</span>
              <span class="valor">R$ {{ totalProdutos.toFixed(2) }}</span>
            </p>
            <input type="button" class="botaoFinal" value="Ir para o pagamento" />
          </div>
        </div>
      </section>

      <footer>
        <div>
          <div>
            <h3>IFbooks</h3>
            <ul class="icones">
              <li>
                <a href="#"><img src="/public/imagens/facebook.png" alt="facebook" /></a>
              </li>
              <li>
                <a href="#"><img src="/public/imagens/instagram.png" alt="instagram" /></a>
              </li>
              <li>
                <a href="#"><img src="/public/imagens/twitter.png" alt="twitter" /></a>
              </li>
            </ul>
          </div>

          <div class="contato">
            <ul>
              <li><h4>Contato</h4></li>
              <li><img src="/public/imagens/telefone.png" alt="telefone" />+55 47 40045263</li>
              <li><img src="/public/imagens/relogio.png" alt="relogio" />8h às 23h - Seg a Sex</li>
              <li><img src="/public/imagens/email.png" alt="email" />contato@ifbooks.com</li>
            </ul>
            <ul class="cartoes">
              <li><img src="/public/imagens/paipal 1.png" alt="paipal" /></li>
              <li><img src="/public/imagens/MasterCard-Logo-1979 1.png" alt="mastercard" /></li>
              <li><img src="/public/imagens/VISA-card-logo- 1.png" alt="visa" /></li>
            </ul>
          </div>
        </div>
        <p>© Alguns direitos reservados. IFbooks 2025.</p>
      </footer>
    </main>
  </body>
</template>

<style scoped>
body {
  background-color: white;
}
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
  color: #7b7881;
}
.nav-menu li img {
  width: 20px;
  height: 20px;
}

.elementos {
  display: flex;
  padding-right: 70px;
}
.elementos button {
  border: none;
  background-color: white;
  margin-left: 15px;
}
.elementos .dividir {
  border-right: 1px solid #4caf50;
  padding-right: 20px;
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
.lista ul li p.vendidos {
  border-bottom: solid 1.5px #937dc2;
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

.lançamentos .livro p.resenha {
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
  transition: background-color 0.3s ease, transform 0.2s ease;
}
.compra:hover {
  background-color: #219653;
  transform: scale(1.03); 
}

.carrinho {
  padding: 4vw 8vw;
  background-color: #f9f9f9;
}
.carrinho h2 {
  color: #27ae60;
  font-size: 2.5rem;
  margin-bottom: 2vw;
}
.carrinho .titulos {
  display: flex;
  justify-content: space-between;
  border-bottom: 2px solid #27ae60;
  padding-bottom: 10px;
  margin-bottom: 2vw;
}
.carrinho .titulos h3 {
  font-size: 1.2rem;
  flex: 1;
  text-align: center;
}
.carrinho .comprar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 3vw 2vw;
  margin-bottom: 2vw;
  border-radius: 2px;
}
.carrinho .comprar img {
  width: 80px;
  height: auto;
  margin: 0 2vw 0 0;
  border-radius: 6px;
}
.infoProduto {
  display: flex;
  align-items: center;
  gap: 2vw;
  flex: 2;
}
.imagemProduto {
  width: 80px;
  height: auto;
  border-radius: 6px;
}
.carrinho .comprar h3 {
  font-size: 1.1rem;
  margin: 0;
}
.carrinho .comprar p.preco {
  color: #666;
  font-size: 0.9rem;
}
.contador {
  display: flex;
  align-items: center;
  gap: 1vw;
  background-color: #f0f0f0;
  padding: 6px 12px;
  border-radius: 20px;
}
.contador button {
  background-color: #27ae60;
  color: white;
  border: none;
  padding: 6px 12px;
  font-size: 1rem;
  border-radius: 50%;
  cursor: pointer;
  font-weight: bold;
}
.subtotal {
  font-weight: bold;
  color: #333;
  font-size: 1rem;
  flex: 1;
  text-align: right;
}
.voltarLoja {
  margin: 6vw 0;
  background-color: transparent;
  border: 2px solid #27ae60;
  color: #27ae60;
  padding: 1vw 2vw;
  font-weight: bold;
  cursor: pointer;
  transition: 0.3s;
}
.voltarLoja:hover {
  background-color: #27ae60;
  color: white;
}
.cupom .codCupom{
  color: #666;
  padding: 1vw 2vw;
  font-size: 1rem ;
}
.cupom .inserirCupom {
  background-color: #27ae60;
  color: white;
  border: none;
  padding: 1vw 2vw;
  font-size: 1rem;
  cursor: pointer;
  transition: background-color 0.3s ease, transform 0.2s ease;
}
.cupom .inserirCupom:hover {
  background-color: #219653;
  transform: scale(1.05);
}
  
.final {
  border: 2px solid #27ae60;
  padding: 4vw;
  margin-top: 6vw;
  border-radius: 10px;
  background-color: white;
  max-width: 400px;
  margin-left: auto;
}
.final h3 {
  margin-bottom: 2vw;
  font-size: 1.4rem;
  color: #27ae60;
}
.final .linha {
  display: flex;
  justify-content: space-between;
  border-bottom: 1px solid #ccc;
  padding: 1vw 0;
}
.botaoFinal {
  background-color: #27ae60;
  color: white;
  border: none;
  padding: 1.4vw 2vw;
  border-radius: 0.8vw;
  font-size: 1vw;
  cursor: pointer;
  margin-top: 1.5vw;
  width: 100%;
  transition: background-color 0.3s ease;
}
.botaoFinal:hover {
  background-color: #219653;
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
  margin: 0 0.5vw;
}
</style>

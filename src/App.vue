<script setup>
/*const produtos = [
    {
        id: 1,
        titulo: 'Livro 1',
        resenha: 'Descrição breve 1'
        preco: 49.9,
        capa: 'https://placehold.co/600x400.png',
    },
    {
        id: 2,
        titulo: 'Livro 2',
        resenha: 'Descrição breve 2'
        preco: 99.9,
        capa: 'https://placehold.co/600x400.png',
    },
    {
        id: 3,
        titulo: 'Livro 3',
        resenha: 'Descrição breve 3'
        preco: 9.9,
        capa: 'https://placehold.co/600x400.png',
    },
    {
        id: 4,
        titulo: 'Livro 4',
        resenha: 'Descrição breve 4'
        preco: 199.9,
        capa: 'https://placehold.co/600x400.png',
    },
    {
        id: 5,
        titulo: 'Livro 5',
        resenha: 'Descrição breve 5'
        preco: 29.9,
        capa: 'https://placehold.co/600x400.png',
    }
];
const carrinho = {
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
    <p class="slogan">Apreço <br> a leitura</p>
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
          Eric-Emmanuel Schmitt has been awarded more than 20 literary prizes and distinctions, and
          in 2001 he received the title of Chevalier des Arts et des Lettres. His books have been
          translated into over 40 languages.
        </p>
        <span class="livro">Acessar página do livro</span>
      </div class="imagem">
      <div>
        <img src="/public/imagens/image.png" alt="" />
      </div>
    </section>

    <section class="lista">
        <ul>
          <li>
            <img src="" alt="" />
            <p>Frete grátis para SC</p>
          </li>
          <li>
            <img src="" alt="" />
            <p>Livros recomendados</p>
          </li>
          <li>
            <img src="" alt="" />
            <p>Mais vendidos</p>
          </li>
        </ul>
      </section>

    <section class="lançamentos">
      <h2>Lançamentos</h2>
      
      <ul>
        <div>
        <li>
          <img src="/public/imagens/chainofIron.png" alt="Chain of Iron: Volume 2" />
          <h3>Chain of Iron: Volume 2</h3>
          <p>Cassandra Clare</p>
          <p>R$23.24</p>
          <button>Comprar</button>
        </li>
        <li>
          <img src="/public/imagens/chainofThorns.png" alt="Chain of Thorns" />
          <h3>Chain of Thorns</h3>
          <p>Cassandra Clare</p>
          <p>R$23.24</p>
          <button>Comprar</button>
        </li>
        <li>
          <img src="/public/imagens/cityoufallenalgels.png" alt="City of Fallen Angels" />
          <h3>City of Fallen Angels</h3>
          <p>Cassandra Clare</p>
          <p>R$13.94</p>
          <button>Comprar</button>
        </li>
        <li>
          <img src="/public/imagens/nonathenith.png" alt="Nona the Ninth" />
          <h3>Nona the Ninth</h3>
          <p>Cassandra Clare</p>
          <p>R$16.84</p>
          <button>Comprar</button>
        </li>
      </div>
      <div>
        <li>
          <img src="/public/imagens/harlemshuffle.png" alt="Harlem Shuffle<" />
          <h3>Harlem Shuffle</h3>
          <p>Colson Whitehead</p>
          <p>R$26.92</p>
          <button>Comprar</button>
        </li>
        <li>
          <img src="/public/imagens/twooldwoman.png" alt="Two Old Women" />
          <h3>Two Old Women</h3>
          <p>Velma Wallis</p>
          <p>R$13.95</p>
          <button>Comprar</button>
        </li>
        <li>
          <img src="/public/imagens/carriesoto.png" alt="Carrie Soto Is Back" />
          <h3>Carrie Soto Is Back</h3>
          <p>Taylor Jenkins Reid</p>
          <p>R$26.04</p>
          <button>Comprar</button>
        </li>
        <li>
          <img src="/public/imagens/booklovers.png" alt="Book Lovers" />
          <h3>Book Lovers</h3>
          <p>Emily Henry</p>
          <p>R$15.81</p>
          <button>Comprar</button>
        </li>
      </div>
      </ul>
    </section>
    <footer>
      <div>
        <ul>
          <li>
            IFbooks
          </li>
          <li>
            facebook
          </li>
          <li>
            instagram
          </li>
          <li>
            twitter
          </li>
        </ul>
      </div>
      <div>
        <h4>Contato</h4>
        <ul>
          <li>
            +55 47 40045263
          </li>
          <li>
            8h às 23h - Seg a Sex
          </li>
          contato@ifbooks.com
        </ul>
        <p>
          © Alguns direitos reservados. IFbooks 2025. 
        </p>
      </div>
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
  border-bottom: 2px solid #27AE60;
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
  color: #27AE60;
  margin: 0;
}

.dividir {
  color: #27AE60;
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
  margin: 2vw 12vw ;
  display: flex;
  align-items:center ;
}
.eric span.autor {
  border: solid 1.5px #27AE60;
  padding: 8px ;
  border-radius: 4px ;
  color: #27AE60;
}
.eric h2 {
  margin: 2vw 0 0 0;
  font-size: 2.8rem;
  font-weight: bolder;
  color: black;
}
.eric div.texto {
  width: 60% ;
  margin: 3vw 0;
}
.eric div.texto p {
  margin: 0 0 3.5vw 0;
  width: 42%;
}
.eric div.texto span.livro {
  background-color: #27AE60;
  padding: 15px;
  color: white;
}
.lista{
  border-top: 2px solid #27AE60;
  border-bottom: 2px solid #27AE60;
  padding: 3.7vw 0;
}
.lista ul{
  display: flex;
  justify-content: center;
   align-items: center;
}
.lista ul li{
  margin: 0 5vw;
  font-size: 1.5rem;
  color: black;
  font-weight: bolder;
  
}
.lançamentos {
  display: flex;
}
.lançamentos ul div{
display: flex;
}
.lançamentos ul li {
  margin: 0 3vw 0 0 ;
}
</style>

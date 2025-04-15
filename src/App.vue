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
    <p>IFbooks</p>
    <p>Apreço a leitura</p>
    <input type="text" placeholder="Pesquisar" />
    <nav>
      <ul>
        <li>Termos</li>
        <li>Equipe</li>
        <li>Envio</li>
        <li>Devoluções</li>
      
        <li>
          <a href=""><img src="/public/imagens/Download.png" alt="carrinho de compras" /></a>
        </li>
        <li>
          <a href=""><img src="/public/imagens/heartactive.png" alt="coração" /></a>
        </li>
        <li>
          <a href=""><img src="/public/imagens/User.png" alt="" /></a>
        </li>
      </ul>
    </nav>
  </header>
  <main>
    <section class="eric">
      <div class="texto">
        <p class="autor">Autor de Abril</p>
        <h2>Eric-Emanuel Schmitt</h2>
        <p>
          Eric-Emmanuel Schmitt has been awarded more than 20 literary prizes and distinctions, and
          in 2001 he received the title of Chevalier des Arts et des Lettres. His books have been
          translated into over 40 languages.
        </p>
        <a href="#">Acessar página do livro</a>
      </div class="imagem">
      <div>
        <img src="/public/imagens/image.png" alt="" />
      </div>
      <div>
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
      </div>
    </section>
    <section>
      <h2>Lançamentos</h2>
      <ul>
        <li>
          <img src="" alt="" />
          <h3>Chain of Iron: Volume 2</h3>
          <p>Cassandra Clare</p>
          <p>R$23.24</p>
          <button>Comprar</button>
        </li>
        <li>
          <img src="" alt="" />
          <h3>Chain of Thorns</h3>
          <p>Cassandra Clare</p>
          <p>R$23.24</p>
          <button>Comprar</button>
        </li>
        <li>
          <img src="" alt="" />
          <h3>City of Fallen Angels</h3>
          <p>Cassandra Clare</p>
          <p>R$13.94</p>
          <button>Comprar</button>
        </li>
        <li>
          <img src="" alt="" />
          <h3>Nona the Ninth</h3>
          <p>Cassandra Clare</p>
          <p>R$16.84</p>
          <button>Comprar</button>
        </li>
        <li>
          <img src="" alt="" />
          <h3>Harlem Shuffle</h3>
          <p>Colson Whitehead</p>
          <p>R$26.92</p>
          <button>Comprar</button>
        </li>
        <li>
          <img src="" alt="" />
          <h3>Two Old Women</h3>
          <p>Velma Wallis</p>
          <p>R$13.95</p>
          <button>Comprar</button>
        </li>
        <li>
          <img src="" alt="" />
          <h3>Carrie Soto Is Back</h3>
          <p>Taylor Jenkins Reid</p>
          <p>R$26.04</p>
          <button>Comprar</button>
        </li>
        <li>
          <img src="" alt="" />
          <h3>Book Lovers</h3>
          <p>Emily Henry</p>
          <p>R$15.81</p>
          <button>Comprar</button>
        </li>
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
main{
  background-color: white;
}
header{
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 12px 30px;
  border-bottom: 2px solid #27AE60;
}
header ul{
  display: flex;
  align-items: center;
  justify-content: space-between;
  
}
section.eric{
  margin: 8vw 0 0 0;
  display: flex;
}
section.eric div.texto {
  width: 60%;
}
section.eric p.autor{
  color: #27AE60;
  border: 1.5px solid #27AE60;
  width: 7vw;
  padding: 10px;
  border-radius: 5px;
}
.eric div.texto{
  margin: ;
}
</style>

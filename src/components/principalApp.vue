<template>
  <div class="hello">
    <div class="retangulo"></div>

    <div class="container">
      <!-- Botões -->
      <button type="button" class="btn btn-outline-primary btn-topo">Home</button>
      <button type="button" class="btn btn-outline-primary btn-topo">Veículos</button>
      <!-- Fim dos Botões -->

      <h1 class="titulo">Veículos Encontrados</h1>
      <div class="barra-subtitulo"></div>

      <!-- Número de veículos encontrados e filtros de pesquisa -->
      <div id="contagem-carros">
        <div class="col-md-12">
          <div class="row">
            <div class="col-md-8"><p class="texto-menor"> {{ listacarros.length }} carros encontrados</p></div>

            <div id="btn-filtro" class="col-md-4 col-xs-12">

              <div id="button-align-list" class="button-align">
                <img src="../assets/icon-align-list.png" alt="">
              </div>

              <div id="button-align-cube" class="button-align">
                <img src="../assets/icon-align-cube.png" alt="">
              </div>

              <div id="button-relevantes" class="button-align">
                <img src="../assets/icon-arrows.png" alt="">
                <span>Mais relevantes</span>
              </div>
              
            </div>
          </div>
        </div>
      </div>
      <!-- Fim do Número de veículos encontrados e filtros de pesquisa -->

      <br><br>

      <!-- Card que exibe o ítem Carro -->
      <div id="listagem-carros" >
        <div class="row">
          <div class="col-md-3 col-xs-3 col-lg-3" v-for="(listacarro, index) in listacarros" :key="index">
            <div class="card">
              <!-- Imagem do carro -->
              <div class="card-image" v-bind:style="{ 'background-image': 'url(' + listacarro.vco_veiculos_foto.url_medium + ')' }">
                <div class="card-image-cidade" >
                  <img src="../assets/icon-place.png" alt="">
                  <span>{{ listacarro.loja_cidade }}</span>
                </div>
              </div>
              <!-- Fim da Imagem do carro -->

              <!-- Corpo do card do carro -->
              <div class="card-body">
                <h5 class="card-title">{{ listacarro.marca_titulo }}</h5>
                <p class="card-text">{{ listacarro.int_versao }}</p>
                <div class="caracteristicas">
                  <span><img src="../assets/calendar.png" class="icon" alt="ícone calendário"> {{ listacarro.int_anomodelofabricacao }}</span>
                  <span><img src="../assets/quilometragem.png" class="icon" alt="ícone quilometragem"> {{ listacarro.int_quilometragem }}km</span>
                  <span><img src="../assets/cambio.png" class="icon" alt="ícone câmbio"> {{ listacarro.vco_cambio.titulo }}</span>
                </div>
                <div class="col-md-12">
                  <div class="row">
                    <div class="col-md-12">
                      <h2 class="valor"><b>R$ {{ listacarro.int_preco_cliente }}</b> <img src="../assets/heart.png" class="icon-heart float-end" alt="like"></h2>
                    </div>
                  </div>
                </div>
              </div>
              <!-- Fim Corpo do card do carro -->

            </div>
          </div>

          <div class="col-md-3 col-xs-3 col-lg-3">
            <div id="propaganda"><img src="../assets/propaganda.png" alt=""></div>
            <div id="propaganda-mobile"><img src="../assets/propaganda-mobile.png" alt=""></div>
          </div>
        </div>
      </div>
      <!-- Fim do ítem que exibe o carro -->

    </div>

    <p id="text-final" class="text-center">
      Você já viu 20 de 106.553 veículos. <br><br>
      <a href="#" id="link-mais">Carregar mais <img src="../assets/icon-arrow-down.png" alt=""></a> 
    </p>
    
    <!-- Footer -->
    <footer class="footer">
      <div class="container">
        <div class="col-md-12">
          <div class="row">
            <div class="col-2 menu-footer">
              <h5>Encontre seu veículo</h5>
              <ul class="nav flex-column">
                <li class="nav-item mb-2"><a href="#" class="nav-link p-0 text-menu">Encontre seu Veículo</a></li>
                <li class="nav-item mb-2"><a href="#" class="nav-link p-0 text-menu">Lojas</a></li>
                <li class="nav-item mb-2"><a href="#" class="nav-link p-0 text-menu">Promoções</a></li>
                <li class="nav-item mb-2"><a href="#" class="nav-link p-0 text-menu">Vantagens</a></li>
                <li class="nav-item mb-2"><a href="#" class="nav-link p-0 text-menu">Garantia Mais</a></li>
              </ul>
            </div>

            <div class="col-2 menu-footer">
              <h5>A Empresa</h5>
              <ul class="nav flex-column">
                <li class="nav-item mb-2"><a href="#" class="nav-link p-0 text-menu">Sobre</a></li>
                <li class="nav-item mb-2"><a href="#" class="nav-link p-0 text-menu">Delivery</a></li>
                <li class="nav-item mb-2"><a href="#" class="nav-link p-0 text-menu">Aviso de Privacidade</a></li>
                <li class="nav-item mb-2"><a href="#" class="nav-link p-0 text-menu">Blog Seminovos</a></li>
              </ul>
            </div>

            <div class="col-2 menu-footer">
              <h5>Atendimento</h5>
              <ul class="nav flex-column">
                <li class="nav-item mb-2"><a href="#" class="nav-link p-0 text-menu">Perguntas Frequentes</a></li>
                <li class="nav-item mb-2"><a href="#" class="nav-link p-0 text-menu">Fale Conosco</a></li>
                <li class="nav-item mb-2"><a href="#" class="nav-link p-0 text-menu">Pós-vendas</a></li>
              </ul>
            </div>

            <div class="col-2 menu-footer">
              <h5>Lojistas</h5>
              <ul class="nav flex-column">
                <li class="nav-item mb-2"><a href="#" class="nav-link p-0 text-menu">Acesse Seminovos Atacado</a></li>
              </ul>
            </div>

            <div id="menu-social" class="col-md-2 col-xs-12 menu-mobile">
              <h5>Siga a gente</h5>
              <div id="facebook" class="icon-social"><img src="../assets/icon-facebook.png" alt=""></div>
              <div id="instagram" class="icon-social"><img src="../assets/icon-instagram.png" alt=""></div>
              <div id="twitter" class="icon-social"><img src="../assets/icon-twitter.png" alt=""></div>
              <div id="linkedin" class="icon-social"><img src="../assets/icon-linkedin.png" alt=""></div>
            </div>

            <div id="menu-atendimento atendimento" class="col-md-2 col-xs-12 menu-mobile">
              <h5>Atendimento ao Cliente</h5>
              <div id="whatsapp">
                <span>(00) 0.0000-0000</span>
              </div>
              <div id="icon-whatsapp">
                <img src="../assets/icon-whatsapp.png" alt="">
              </div>
            </div>
            
          </div>

        </div>
      </div>
    </footer>
    <!-- Fim do Footer -->

  </div>
</template>

<script>
/* Importando a API que será consumida */
import api from '@/services/api.js';

export default {
  name: 'principalApp',
  data(){
    return{
      listacarros: []
    }
  },
  mounted(){
    api.get('/data.json').then(response => {
      this.listacarros = response.data.resultados.data
    });
  }
}

</script>
 
<!-- Adicionando o atributo "scoped" para limitar estes estilos apenas a este componente -->
<style scoped>

.retangulo{
  background-color: #f88804;
  padding: 0;
  margin: 0;
  padding: 15px;
  text-align: center;
}

.container{
  padding: 15px;
  margin-top: 50px;
}

.btn-topo{
  margin: 5px;
  background-color: #fff;
  border-color: #f88804;
  color: #000;
}

.btn-topo:hover{
  background-color: #f88804;
}

.titulo{
  margin-top: 25px;
  font-family: 'Roboto';
  font-style: normal;
  font-weight: 700;
  font-size: 32px;
  line-height: 38px;
  display: flex;
  align-items: center;
  color: #444444;
}

.barra-subtitulo{
  width: 55px;
  height: 3px;
  left: 38px;
  top: 191px;

  background: #f88804;
  border-radius: 22px;
}

#contagem-carros{
  padding-top: 15px;
}

.card{
  margin: 8px;
  border-radius: 15px;
  height: 450px;
  box-shadow: 2px 2px 10px 2px rgba(0, 0, 0, 0.2);
}

.card-text{
  height: 50px;
}

.texto-menor{
  font-family: 'Roboto';
  font-style: normal;
  font-weight: 400;
  font-size: 18px;
  line-height: 21px;
  display: flex;
  align-items: center;
  color: #444444;
}

.caracteristicas{
  display: inline;
}

.caracteristicas span{
  padding-right: 3px;
  font-size: 10px;
}

.valor{
  font-size: 20px;
  padding-top: 20px;
}

.icon{
  width: 15px;
  height: auto;
  display: inline;
  margin-left: 10px;
}

.icon-heart{
  width: 20px;
  height: auto;
  padding-top: 5px;
}

.footer{
  background-color: #343A40CC;
  color: #fff;
}

.text-menu{
  color: #fff;
  font-size: 14px;
}

h5{
  font-size: 15px;
  padding-bottom: 10px;
}

#whatsapp{
  background: #f88804;
  border-radius: 4px; 
  padding: 5px;
  width: 120px;
  height: 40px;
  font-size: 12px;
  display: inline;
  align-items: center;
  text-align: center;
  margin: 5px;
}

#icon-whatsapp{
  background-color: #4AC959;
  border-radius: 4px; 
  padding: 5px;
  width: 60px;
  height: 60px;
  font-size: 12px;
  display: inline;
  align-items: center;
  text-align: center;
  margin: 5px;
}

#icon-whatsapp img{
  width: 15px;
  height: auto;
  margin: 0;
  padding: 0;
}

.icon-social{
  background-color: #f88804;
  align-items: center;
  text-align: center;
  display: inline;
  margin: 5px;
  padding: 5px;
  border-radius: 4px;
}

.icon-social img{
  width: 15px;
  height: auto;
}

#text-final{
  font-size: 14px;
  line-height: 16px;
  padding-top: 50px;
}

#link-mais{
  text-decoration: none;
  font-size: 14px;
  line-height: 16px;
  color: #f88804;
}

#link-mais img{
  width: 10px;
}

.button-align{
  background-color: #fff;
  border-radius: 4px;
  padding: 5px;
  margin: 5px;
  float: right;
}

.card-image{
  background-color: #dfdfdf;
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center center;
  width: 100%;
  height: 250px;
  border-radius: 15px 15px 0 0;
}

.imagem-carro{
  width: 100%;
  height: auto;
}

.card-image-cidade{
  background-color: #fff;
  width: 200px;
  height: 35px;
  border-radius: 0 20px 20px 0;
  z-index: 99;
  padding-left: 20px;
  margin-top: 180px;
}

.card-image-cidade img{
  width: 18px;
  height: auto;
  display: inline;
  margin-top: 2px;
}

.card-image-cidade span{
  font-size: 15px;
  margin: 0;
  padding: 0;
  margin-left: 5px;
  vertical-align: middle;
  color: #000;
}

#button-relevantes img, #button-align-cube img, #button-align-list img{
  width: 20px;
  display: inline;
}

#propaganda{
  height: 520px;
  margin: 8px;
}

#propaganda img, #propaganda-mobile img{
  width: 100%;
  height: auto;
  border-radius: 15px;
}

#propaganda-mobile{
  display: none;
  border-radius: 15px;
  padding-top: 15px;
}

.footer{
  padding-bottom: 50px;
}

/* Estilos mobile */
@media (max-width: 900px) {
  .menu-footer{
    display: none;
  }

  .menu-mobile{
    text-align: center;
  }

  #menu-social, #menu-atendimento{
    padding: 10px;
  }

  .button-align{
    float: left;
  }

  #propaganda{
    display: none;
  }

  #propaganda-mobile{
    display: flex;
  }

  #button-align-list{
    display: none;
  }

  #text-final{
    display: none;
  }
}

</style>

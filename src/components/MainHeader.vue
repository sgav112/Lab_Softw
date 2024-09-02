<template>
  <header>
    <!-- Barra superior negra -->
    <div class="top-bar">
      <div class="top-bar-content">
        <!-- Elementos de la barra superior -->
        <a href="#" class="top-bar-item">
          <img src="../assets/icono-camion.png" alt="Icono envío" class="icon">
          <div class="text-group">
            <span class="green-text">Envío gratis en cada pedido</span>
            <span class="subtext">Oferta exclusiva</span>
          </div>
        </a>

        <a href="#" class="top-bar-item">
          <img src="../assets/icono-ajuste-precios.png" alt="Icono ajuste de precios" class="icon">
          <div class="text-group">
            <span class="yellow-text">Ajuste de precios</span>
            <span class="subtext">En un plazo de 30 días</span>
          </div>
        </a>

        <a href="#" class="top-bar-item">
          <img src="../assets/icono-descargar-app.png" alt="Icono app" class="icon">
          <span class="yellow-text">Descarga la app de Temu</span>
        </a>
      </div>
    </div>

    <!-- Barra inferior rosada -->
    <div class="bottom-bar">
      <div class="bottom-bar-content">
        <!-- Logo -->
        <img src="../assets/logo-temu.png" alt="Temu logo" class="logo">

        <!-- Navegación -->
        <nav class="nav-links">
          <div class="masvendidos">
            <a href="#"> 
              <img src="../assets/icono-mas-vendidos.png" alt="Más vendidos" class="icon-small">
              <div class="text-wrapper">
                <span class="hot">HOT</span>
                Más vendidos
              </div>
            </a>
          </div>

          <a href="#">
            <img src="../assets/icono-estrella.png" alt="Icono estrella" class="icon-small"> 5 estrellas
          </a>
          <a href="#">
            <img src="../assets/icono-corazon.png" alt="Icono corazón" class="icon-small"> Amor y Amistad
          </a>
          <a href="#">Recién llegados</a>
          <a href="#">Categorías <span>&#9660;</span></a>
        </nav>

        <!-- Barra de búsqueda -->
        <div class="search-bar">
          <input type="text" placeholder="ropa para mujer">
          <button>
            <img src="../assets/icono-buscar.png" alt="Icono buscar" class="icon-small">
          </button>
        </div>

        <!-- Iconos de usuario, ayuda, idioma y carrito -->
        <a href="#" id="Iniciar_sesion" class="user-icon" @click="showModal = true">
          <img src="../assets/icono-usuario.png" alt="Icono usuario" class="icon">
          <span>Pedidos y cuenta</span>
        </a>

        <a href="#" class="help-icon">
          <img src="../assets/icono-ayuda.png" alt="Icono ayuda" class="icon">
          <span>Ayuda</span>
        </a>
        
        <a href="#" class="language-icon">
          <img src="../assets/icono-colombia.png" alt="Bandera Colombia" class="icon">
          <span>ES</span> 
        </a>

        <a href="#" class="cart-icon">
          <img src="../assets/icono-carro-compras.png" alt="Icono carrito" class="icon">
        </a> 
      </div>
    </div>
  </header>


  <div>
        <div v-if="showModal" class="modal" @click.self="showModal = false">
            <div class="modal-content">
                <button class="close-button" @click="showModal = false">x</button>
                <form class="form" @submit.prevent="login">
                    <div class="Arriba">
                        <div class="texto">
                            <h1>Iniciar sesión/Registrarse</h1>
                            <div class="columnas">
                                <div class="izquierda">
                                    <img alt="Seguridad" src="@/assets/Candado.png" width="15" height="15" />
                                </div>
                                <div class="derecha">
                                    <p>Todos los datos se cifrarán</p>
                                </div>
                            </div>
                        </div>
                        <div class="columnas_2">
                            <div class="zona1">
                                <div class="imagen"><img alt="Entregas" src="@/assets/camion-de-reparto.png" width="30"
                                        height="30" /></div>
                                <div class="texto1">Envío gratis</div>
                                <div class="texto2">En todos los pedidos</div>
                            </div>
                            <div class="zona2">
                                <div class="imagen"><img alt="Devoluciones" src="@/assets/devoluciones-faciles.png"
                                        width="30" height="30" /></div>
                                <div class="texto1">Devoluciones gratis </div>
                                <div class="texto2">Hasta 90 días*</div>
                            </div>
                        </div>


                    </div>
                    <div class="formulario">
                        <div class="Inputcito">
                            <span for="Email">Email o número de teléfono</span>
                            <input type="text" v-model="Email" id="Email" placeholder=" ">
                        </div>
                        <div class="Inputcito">
                            <span for="Clave">Contraseña</span>
                            <input type="password" v-model="Clave" placeholder=" ">
                        </div>


                        <div class="texto_abajo">
                            <a href="">¿Tienes problemas para iniciar sesion?</a>
                            <p>O continúa de otras maneras</p>
                        </div>
                    </div>

                    <div class="abajo">
                        <div class="Redes_sociales">
                            <div class="circulo">
                                <img src="@/assets/Google.png" alt="" height="100%" width="100%" />
                            </div>
                            <div class="circulo">
                                <img src="@/assets/Facebook.png" alt="" height="100%" width="100%" />
                            </div>
                        </div>
                        <div class="terminos">
                            <span>Al continuar,aceptas nuestros</span><a href="">Términos de uso</a>  <span>y</span>  <br>  <a href="">Política de privacidad.</a>
                        </div>
                    </div>
                    <button type="submit">Continuar</button>
                </form>
            </div>
        </div>
    </div>




</template>

<script>
export default {
name: 'algo',
    data() {
        return {
            showModal: false,
            username: '',
            password: ''
        };
    },
    methods: {
        login() {
            // Aquí puedes agregar la lógica para autenticar al usuario
            console.log('Usuario:', this.username);
            console.log('Clave:', this.password);

            // Cerrar el modal después de iniciar sesión
            this.showModal = false;
        }
    }}
</script>


<style scoped>
header {
  display: flex;
  flex-direction: column;
}

.top-bar {
  background-color: #0a0a0a;
  color: #fff;
  display: flex;
  justify-content: center;
  padding: 10px 0; 
  font-size: 0.9em; 
  width: 100%;
  
  
}

.top-bar-content, .bottom-bar-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
  
}

.top-bar-item {
  display: flex;
  align-items: center;
  text-decoration: none;
  color: #fff;
  margin-right: 20px;
  margin-left: 10px;
  
}

.text-group {
  display: flex;
  flex-direction: column;
}

.icon {
  height: 30px;
  margin-right: 10px;
  
}

.green-text, .yellow-text {
  font-weight: bold;
  line-height: 1.2;
}

.green-text { color: #A9F8A7; }
.yellow-text { color: #E8E478; }

.subtext { 
  color: #999; 
  font-size: 0.9em;
  line-height: 1.2; 
}

.bottom-bar {
  background-color: #F5657F;
  width: 100%;
  display: flex;
  justify-content: center;
  padding: 10px 0;
  font-size: 0.9em; 
}

.logo { 
  height: 50px;
  margin-right: 3px;
}

.nav-links {
  display: flex;
  gap: 15px;
  align-items: center;
  flex-grow: 1;
}

.nav-links a {
  display: flex;
  align-items: center;
  color: #fff;
  text-decoration: none;
  font-size: 0.9em;
  white-space: nowrap;
}

.masvendidos a {
  position: relative;
}

.text-wrapper {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.hot {
  position: absolute;
  top: -15px;
  left: 50%;
  transform: translateX(80%);
  background-color: #f57d05;
  color: #ffffff;
  font-weight: bold;
  font-size: 0.8em;
  padding: 2px 4px;
  border-radius: 3px;
  white-space: nowrap;
}

.icon-small {
  height: 18px;
  margin-right: 5px;
  
}

.search-bar {
  display: flex;
  align-items: center;
  background-color: #fff;
  border-radius: 20px;
  overflow: hidden;
  flex-grow: 1; 
  margin: 5px; 
}

.search-bar input {
  border: none;
  padding: 10px 15px;
  font-size: 0.9em;
  width: 100%;
  outline: none;
}

.search-bar button {
  background-color: #000;
  border: none;
  padding: 10px;
  cursor: pointer;
}

.user-icon, .help-icon, .language-icon, .cart-icon {
  display: flex;
  align-items: center;
  text-decoration: none;
  color: #fff;
  margin-left: 8px;
  margin-right: 0;
  font-size: 0.9em;
  
  
}

.user-icon span, .help-icon span, .language-icon span {
  margin-left:0px;
 
}

.form {
    padding: 40px 30px;
    background: #fefefe;
    display: flex;
    flex-direction: column;
    padding-bottom: 20px;

}

.form h4 {
    margin-bottom: 20px;
    color: rgba(0, 0, 0, 0.5);
}

.form h4 span {
    color: black;
    font-weight: 500;
}

.form p {
    line-height: 155%;
    font-size: 14px;
    color: #000;
    opacity: 0.65;
    font-weight: 400;

}


h1 {
    text-align: center;
}

.texto {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
}

.columnas {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    margin-bottom: 10px;
}

.izquierda {
    display: flex;
    justify-content: flex-end;
    align-items: center;

}

.derecha {
    display: flex;
    justify-content: flex-start;
    align-items: center;
}

.derecha p {
    color: #1AC64F;
}


.columnas_2 {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    gap: 20%;
    margin-bottom: 10px;
}

.imagen {
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #ffd5ab;
    border-radius: 100%;
    width: 60px;
    height: 60px;
}

.zona1,
.zona2 {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
}

.texto1 {
    font-size: 15px;
    font-weight: bold;
}

.texto2 {
    font-size: 10px;

}

.texto_abajo {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin-left: 10px;
    margin-right: 10px;
}

.texto_abajo a {
    text-decoration: none;
    color: gray;
    font-size: 12px;
    font-weight: bold;
    margin: 20px;
}

.texto_abajo a:hover {
    color: rgb(192, 192, 192);
}

.texto_abajo p {
    text-decoration: none;
    color: rgb(0, 0, 0);
    font-size: 12px;
    font-weight: bold;
}



input {
    font-size: 16px;
    height: 10%;
    border: solid grey 0.2px;
    background: #fff;
    width: 280px;
    box-sizing: border-box;
    transition: all 0.3s linear;
    color: #000;
    font-weight: 1000;
}

.form button {
    -webkit-appearance: none;
    appearance: none;
    width: 100%;
    border-radius: 24px;
    text-align: center;
    padding: 15px 40px;
    margin-top: 5px;
    background-color: #ff8110;
    color: white;
    font-size: 14px;
    margin-left: 5px;
    font-weight: 500;
    box-shadow: 0px 2px 6px -1px rgba(0, 0, 0, 0.13);
    border: none;
    transition: all 0.3s ease;
    outline: 0;
    font-weight: bold;
    cursor: pointer;
}

.form button:hover {
    transform: translateY(-3px);
    box-shadow: 0 2px 6px -1px rgba(251, 129, 20, 0.65);
}

.formulario button:hover:active {
    transform: scale(0.99);
}

.filas {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    gap: 5px;
}


.formulario {
    position: relative;
    margin-bottom: 10px;
    width: 100%;
}

.formulario label {
    position: absolute;
    top: calc(50% - 7px);
    left: 0;
    opacity: 0;
    transition: all 0.3s ease;
    padding-left: 44px;
}

.formulario input {
    width: 100%;
    padding: 15px;
    margin-left: auto;
    display: flex;
}

.formulario input:not(:placeholder-shown) {
    padding: 6%;
}

.formulario input:not(:placeholder-shown)+label {
    transform: translateY(-10px);
    opacity: 0.7;
}

.formulario input:not(:valid):not(:focus)+label+.icon {
    animation-name: shake-shake;
    animation-duration: 0.3s;
}

.formulario span {
    color: black;
    font-weight: 1000;
    font-size: 0.8em;
}

a.discrete {
    color: rgba(0, 0, 0, 0.4);
    font-size: 14px;
    border-bottom: solid 1px rgba(0, 0, 0, 0);
    padding-bottom: 4px;
    margin-left: auto;
    font-weight: 300;
    transition: all 0.3s ease;
    margin-top: 40px;
}

a.discrete:hover {
    border-bottom: solid 1px rgba(0, 0, 0, 0.2);
}

.Redes_sociales {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    width: 100%;
    margin: 0px;
}

.circulo {
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #fefefe;
    width: 25px;
    height: 25px;
    border-radius: 30px;
    margin: 10px;
    box-shadow: 0px 2px 6px -1px rgba(0, 0, 0, 0.12);
}

.terminos {
    display: flex;
    justify-content: center;
    align-items: center;

}
.terminos a {
    text-decoration: none;
    color: #4c58f7;
    cursor: pointer;
}
.terminos a:hover {
    color: #0415ff;
    font-weight: 350;
    text-decoration: underline;
}
.modal {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5);
    display: flex;
    justify-content: center;
    align-items: center;
}

.modal-content {
    background-color: white;
    padding: 20px;
    border-radius: 5px;
    position: relative;
}

h2 {
    margin-bottom: 20px;
    color: blue;
}

.close-button {
    position: absolute;
    top: 10px;
    right: 10px;
    background: none;
    border: none;
    font-size: 20px;
    cursor: pointer;
}
</style>
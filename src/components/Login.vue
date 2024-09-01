<template>
    <div>
        <button @click="showModal = true">Abrir modal</button>
        <!--v-if="showModal" class="modal" @click.self="showModal = false"-->
        <div>
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
                                <div class="imagen"><img alt="Entregas"  src="@/assets/camion-de-reparto.png"  width="30" height="30"/></div>
                                <div class="texto1">Envío gratis</div>
                                <div class="texto2">En todos los pedidos</div>
                            </div>
                            <div class="zona2">
                                <div class="imagen"><img alt="Devoluciones" src="@/assets/devoluciones-faciles.png" width="30" height="30"/></div>
                                <div class="texto1">Devoluciones gratis </div>
                                <div class="texto2">Hasta 90 días*</div>
                            </div>
                        </div>


                    </div>
                    <div class="formulario">
                        <div class="columnas">
                            <div class="Inputcito"><input type="text" v-model="username" placeholder="Username"></div>
                            <div class="Inputcito"><input type="password" v-model="password" placeholder="Password"></div>
                            
                            
                        </div>
                        
                        <button type="submit">Submit</button>
                    </div>

                    <div class="abajo">

                    </div>
                </form>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Login',
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
    }
};
</script>

<style>
* {
    color: black;
}
.form {
    display: flex;
    flex-direction: column;
    gap: 20px;
    padding: 20px;
    border-radius: 5px;
    background-color: white;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    
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
    height:60px;
}

.zona1, .zona2 {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
}

.texto1{
    font-size: 12px;
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
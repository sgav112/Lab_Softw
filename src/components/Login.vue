<template>
    <div>
        <button @click="showModal = true">Abrir modal</button>
        <div v-if="showModal" class="modal" @click.self="showModal = false">
            <div class="modal-content">
                <button class="close-button" @click="showModal = false">x</button>
                <h2>Iniciar sesión</h2>
                <form @submit.prevent="login">
                    <div class="Arriba">
                        
                    </div>
                    <div class="formulario"></div>
                    <img alt="Vue logo" class="logo" src="@/assets/Candado.png" width="125" height="125" />
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
    position: relative;}
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
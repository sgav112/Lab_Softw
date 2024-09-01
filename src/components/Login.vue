<template>
    <div>
        <button @click="showModal = true">Abrir modal</button>

        <div v-if="showModal" class="modal">
            <div class="modal-content">
                <h2>Iniciar sesión</h2>
                <form @submit.prevent="login">
                    <label for="username">Usuario:</label>
                    <input type="text" id="username" v-model="username" required>

                    <label for="password">Clave:</label>
                    <input type="password" id="password" v-model="password" required>

                    <button type="submit">Iniciar sesión</button>
                </form>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name:'Login',
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
}
</style>
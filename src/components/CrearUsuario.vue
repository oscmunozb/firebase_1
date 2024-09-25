<template>
    <div>
        <!-- Formulario para agregar nuevos usuarios -->
        <form @submit.prevent="addUsuario">
            <h2 class="text-center my-3">Agregar nuevo usuario</h2>
                <div class="my-2">
                    <label class="form-label" for="nombre">Nombre del usuario</label>
                    <input id="nombre" class="form-control" v-model="nuevoNombre" placeholder="Nombre del usuario" required>
                </div>
                <div class="my-2">
                    <label class="form-label" for="correo">Correo electrónico</label>
                    <input id="correo" class="form-control" v-model="nuevoCorreo" placeholder="Correo electrónico" type="email" required>
                </div>
            <div class="text-center my-2">
                <button class="btn btn-primary" type="submit">Agregar</button>
            </div>
        </form>
    </div>
</template>

<script>
import { getFirestore, collection, addDoc } from 'firebase/firestore';
import firebaseApp from '../firebaseconfig';

export default {
    data() {
        return {
            nuevoNombre: '', // Para almacenar el nombre del nuevo usuario
            nuevoCorreo: '',  // Para almacenar el correo del nuevo usuario
            db: null // Para almacenar la instancia de Firestore
        };
    },
    mounted() {
        this.db = getFirestore(firebaseApp); // Inicializar Firestore solo una vez al montar el componente
    },
    methods: {
        // Método para agregar un nuevo usuario a la base de datos
        async addUsuario() {
            if (this.nuevoNombre.trim() === '' || this.nuevoCorreo.trim() === '') return;
            const usuariosRef = collection(this.db, 'usuarios');
            await addDoc(usuariosRef, { nombre: this.nuevoNombre, correo: this.nuevoCorreo });
            // Limpiar los campos después de agregar el usuario
            this.nuevoNombre = '';
            this.nuevoCorreo = '';
        }
    }
};
</script>
<template>
    <div class="my-3">
        <!-- Mostrar todos los usuarios registrados -->
        <ul class="list-group">
            <li class="list-group-item" v-for="usuario in usuarios" :key="usuario.id">
                <div class="text-center">
                    <h4>Nombre: {{ usuario.nombre}} - Correo: {{ usuario.correo }}</h4>
                    <p>ID: {{ usuario.id }}</p>
                </div>
                <div class="text-center">
                    <button class="btn btn-danger mb-2" @click="deleteUsuario(usuario.id)">Eliminar</button>
                </div>
                
            </li>
        </ul>
    </div>
</template>

<script>
import { getFirestore, collection, onSnapshot, doc, deleteDoc } from 'firebase/firestore';
import firebaseApp from '../firebaseConfig';

export default {
    data() {
        return {
            usuarios: [], // Para almacenar los usuarios obtenidos de Firestore
            db: null // Para almacenar la instancia de Firestore
        };
    },
    mounted() {
        this.db = getFirestore(firebaseApp); // Inicializar Firestore solo una vez al montar el componente
        const usuariosRef = collection(this.db, 'usuarios');
        // Cargar usuarios existentes
        onSnapshot(usuariosRef, (snapshot) => {
            this.usuarios = snapshot.docs.map((doc) => ({
                id: doc.id,
                ...doc.data()
            }));
        });
    },
    methods: {
        // Método para eliminar usuarios de la base de datos
        async deleteUsuario(usuarioId) {
            const usuarioRef = doc(this.db, 'usuarios', usuarioId);
            await deleteDoc(usuarioRef);
        }
    }
};
</script>
# &#128187; Desafío - Firebase (I) &#128511;
En este desafío validaremos nuestros conocimientos de Firebase.

- Enlace a la aplicación desplegada en Vercel: [Firebase (I)](https://firebase-1.vercel.app/)

## &#128640; Tabla de contenidos
- [Descripción](#-descripción)
- [Tecnologías utilizadas](#-tecnologías-utilizadas)
- [DevOps](#-devops)
- [Cómo clonar el proyecto](#-cómo-clonar-el-proyecto)
- [Configuración del proyecto](#-configuración-del-proyecto)

## &#127755;  Descripción 
Se debe crear un CRUD, es decir, un sistema que pueda crear un usuario, editar usuarios, eliminar usuarios y listar los usuarios. Este debe ser hecho con dos componentes: uno con un formulario para el envío de datos y el otro debe listar los usuarios con un botón en cada una de las filas de usuarios, ya sean listas o no, para eliminar dicho usuario. Deberás utilizar Firestore para la persistencia de datos de forma remota y con la ayuda de Vuex alojar la información en una estado global. Los usuarios de este sistema deben tener por lo menos nombre y correo electrónico.

Nota: Enfocar el desarrollo de este CRUD en únicamente las operaciones Create (Crear), Read (Leer), Delete (Borrar).

## &#128642; Tecnologías utilizadas
Este proyecto utiliza las siguientes tecnologías:
- HTML5
- CSS3
- JS
- Bootstrap 5
- Vue.js
- Vite
- Bun

### &#128641; DevOps
- VS Code
- Git
- GitHub
- Vercel 


## &#128110; Cómo clonar el proyecto
1. Abre una terminal y ejecuta el siguiente comando:
```bash
git clone https://github.com/oscmunozb/firebase_1.git
```
2. Navega al directorio del proyecto:
```bash
cd firebase_1
```
3. Si estás usando VS Code, puedes abrir el proyecto ejecutando:
```bash
code .
```

## &#128679; Configuración del proyecto
### Instalar paquetes
```sh
bun install
```

### Compilación y ejecución
```sh
bun dev
```

### Personalizar configuración
Consulta la [Referencia de Configuración](https://vitejs.dev/config/).
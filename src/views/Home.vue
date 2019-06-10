<template>
    <ion-app :title="App">
        <ion-button @click="inicio" expand="full">
            Iniciar Sesión
        </ion-button>
        <ion-button @click="registro" expand="full">
            Registrarse
        </ion-button>
    </ion-app>
</template>

<script>
    import firebase from 'firebase';

    const config = {
        apiKey: "AIzaSyCElzy1P_QnGBjN8X5DQrIHAm2j_Y_NTDw",
        authDomain: "ionictest-a2f72.firebaseapp.com",
        databaseURL: "https://ionictest-a2f72.firebaseio.com",
        projectId: "ionictest-a2f72",
        storageBucket: "ionictest-a2f72.appspot.com",
        messagingSenderId: "361624898187",
        appId: "1:361624898187:web:a2548b5749bc09a3"
    };
    firebase.initializeApp(config);
    export default {
        name: 'home',
        methods: {
            inicio() {
                let alert = this.$ionic.alertController.create({
                    header: 'Inicia Sesión',
                    message: 'Ingresa tu correo y contraseña',
                    inputs: [{
                        name: 'correo',
                        id: 'correo',
                        type: 'email',
                        placeholder: 'Ingresa tu correo'
                    }, {
                        name: 'contrasena',
                        id: 'contrasena',
                        type: 'password',
                        placeholder: 'Ingresa tu contraseña'
                    }],
                    buttons: ['Cancelar', {
                        text: 'Ingresar', handler: () => {
                            let email = document.getElementById('correo').value,
                                contrasena = document.getElementById('contrasena').value;
                                firebase.auth().signInWithEmailAndPassword(email, contrasena).then(
                                // this.aler t('Bienvenido', 'Gracias por ingresar', ['Aceptar'], true)
                            );
                            this.$router.push({name: 'index'})
                        }
                    }]
                });
                alert.then(a => a.present());
            },
            alert(titulo, mensaje, botones, dismiss) {
                let alert = this.$ionic.alertController.create(
                    {
                        header: titulo,
                        message: mensaje,
                        buttons: botones,
                        backdropDismiss: dismiss,
                        translucent: true,
                    }
                );
                alert.then(a => a.present());
            },
            registro() {
                let alert = this.$ionic.alertController.create({
                    header: 'Registrate',
                    subHeader: 'Ingresa tus datos personales',
                    backdropDismiss: false,
                    inputs: [{
                        name: 'nombre',
                        id: 'nombre',
                        placeholder: 'Ingresa tu Nombre',
                        type: 'text',
                        required: true
                    }, {
                        name: 'apellido',
                        id: 'apellido',
                        placeholder: 'Ingresa tu Apellido',
                        type: 'text'
                    },
                        {
                            name: 'correo',
                            id: 'correo',
                            placeholder: 'Ingresa tu correo',
                            type: 'email'
                        },
                        {
                            name: 'contrasena',
                            id: 'contrasena',
                            placeholder: 'Ingresa tu contraseña',
                            type: 'password'
                        }
                    ],
                    buttons: ['Cancelar', {
                        text: 'Registrate', handler: () => {
                            let email = document.getElementById('correo').value,
                                contrasena = document.getElementById('contrasena').value;
                            firebase.auth().createUserWithEmailAndPassword(email, contrasena).then(
                                this.alert('¡Gracias por registrarte!', 'Bienvenido al sistema, por favor logueate en el alert de inicio de sesion', ['Aceptar'], true)
                            );
                        }
                    }]
                });
                alert.then(a => a.present())
            }
        }
    }
</script>

<style>
    @import "../assets/css/styles.css";
</style>
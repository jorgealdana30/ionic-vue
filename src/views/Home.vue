<template>
    <ionVuePage :title="App">
        <ion-button @click="inicio" expand="block">
            <ion-icon name="contact"></ion-icon>
            Iniciar Sesión
        </ion-button>
        <ion-button @click="registro" expand="block">
            Registrarse
        </ion-button>
    </ionVuePage>
</template>

<script>
    export default {
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
                            this.alert('Bienvenido', 'Gracias por ingresar', ['Aceptar'], true);
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
                            name: 'edad',
                            id: 'edad',
                            placeholder: 'Ingresa tu Edad',
                            type: 'number'
                        }],
                    buttons: ['Cancelar', {
                        text: 'Registrate', handler: () => {
                            this.alert('¡Gracias por registrarte!', 'Bienvenido al sistema, por favor logueate en el alert de inicio de sesion', ['Aceptar'], true);
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
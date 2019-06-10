<template>
    <ion-app>
        <ion-header>
            <ion-toolbar color="dark">
                <ion-buttons slot="start">
                    <ion-menu-button auto-hide="false">
                        <ion-icon name="menu"></ion-icon>
                    </ion-menu-button>
                </ion-buttons>
                <ion-buttons slot="secondary">
                    <ion-button>
                        <ion-icon slot="icon-only" name="search"></ion-icon>
                    </ion-button>
                    <ion-button color="danger">
                        <ion-icon slot="icon-only" name="more"></ion-icon>
                    </ion-button>
                </ion-buttons>
                <ion-title>Inicio</ion-title>
            </ion-toolbar>
        </ion-header>
        <ion-tabs>
            <ion-tab tab="home">Home Content</ion-tab>
            <ion-tab tab="settings">Settings Content</ion-tab>
            <ion-tab-bar slot="bottom">
                <ion-tab-button tab="home">
                    <ion-label>Inicio</ion-label>
                    <ion-icon name="home"></ion-icon>
                    <ion-badge>1</ion-badge>
                </ion-tab-button>
                <ion-tab-button tab="settings">
                    <ion-label>Perfil</ion-label>
                    <ion-icon name="person"></ion-icon>
                </ion-tab-button>
                <ion-tab-button @click="logout">
                    <ion-label>Salir</ion-label>
                    <ion-icon name="exit"></ion-icon>
                </ion-tab-button>
            </ion-tab-bar>
        </ion-tabs>

    </ion-app>

</template>

<script>
    export default {
        name: "Index",
        methods: {
            logout() {

            }
        }
    }
</script>

<style scoped>

</style>
<template>
    <ion-app>
        <ion-tabs>
            <ion-tab tab="index"></ion-tab>
            <ion-tab tab="settings"></ion-tab>
            <ion-tab-bar slot="bottom">
                <ion-tab-button tab="index">
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
        name: "settings"
    }
</script>

<style scoped>

</style>
<template>
    <ion-app>
            <ion-menu contentId="menu-content">
                <ion-header>
                    <ion-toolbar>
                        <ion-title>Menu Principal</ion-title>
                    </ion-toolbar>
                </ion-header>
            </ion-menu>
            <ion-router-outlet id="menu-content" main></ion-router-outlet>
        <ion-header>
            <ion-toolbar color="dark">
                <ion-buttons slot="start">
                    <ion-menu-toggle autoHide="false">
                    <ion-menu-button></ion-menu-button>
                    </ion-menu-toggle>
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
            <ion-card>
                <ion-item>
                    <ion-icon name="pin" slot="start"></ion-icon>
                    <ion-label>ion-item in a card, icon left, button right</ion-label>
                    <ion-button fill="outline" slot="end">View</ion-button>
                </ion-item>
                <ion-card-content>
                    This is content, without any paragraph or header tags,
                    within an ion-card-content element.
                </ion-card-content>
            </ion-card>
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
        name: "Index",
        methods: {
            logout() {
                this.$router.push('/')
            }
        }
    }
</script>

<style scoped>

</style>
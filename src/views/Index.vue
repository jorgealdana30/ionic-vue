<template>
    <ion-app>
        <Menu/>
        <Toolbar/>
        <ion-content>
            <ion-refresher slot="fixed" pulling-icon="arrow-dropdown"
                           pulling-text="Pull to refresh"
                           refreshing-spinner="circles"
                           refreshing-text="Refreshing..." @ionRefresh="doRefresh($event)">
            </ion-refresher>
        </ion-content>
        <ion-fab class="fab2" vertical="bottom" horizontal="end">
            <ion-fab-button>
                <ion-icon name="add"></ion-icon>
            </ion-fab-button>
        </ion-fab>
        <Tabs/>
    </ion-app>
</template>

<script>
    import Menu from './Menu';
    import Tabs from "./Tabs";
    import Toolbar from "./Toolbar";
    export default {
        name: "Index",
        components:{
            Tabs, Menu, Toolbar
        },
        methods: {
            doRefresh(event) {
                console.log('Begin async operation');
                setTimeout(() => {
                    console.log('Async operation has ended');
                    console.log(event)
                }, 2000);
            }
        }
    }
</script>

<style scoped>

</style>
<template>
    <ion-app>
        <Menu/>
        <Toolbar/>
        <Tabs/>
    </ion-app>
</template>

<script>
    import Tabs from "./Tabs";
    import Menu from "./Menu";
    import Toolbar from "./Toolbar";
    export default {
        name: "perfil",
        components: {Tabs, Menu, Toolbar}
    }
</script>

<style scoped>

</style>
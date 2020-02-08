<template>
    <v-app id="inspire">
        <left-drawer v-model="drawerLeft"></left-drawer>
        <v-app-bar app color="blue-grey" dark :clipped-left="true">
            <v-app-bar-nav-icon @click.stop="drawerLeft = !drawerLeft" />
            <v-toolbar-title>
                <v-img alt="Vuetify Logo" class="shrink mr-2" contain src="/assets/images/QuilityLogoHorizontalWhiteRGB.svg" transition="scale-transition" height="35px" />
            </v-toolbar-title>
            <v-spacer />
            <v-btn small text fab @click.stop="drawerRight = !drawerRight">
                <v-icon>fas fa-th</v-icon>
            </v-btn>
        </v-app-bar>
        <right-drawer v-model="drawerRight"></right-drawer>
        <v-content>
            <router-view></router-view>
        </v-content>
        <v-footer app color="blue-grey" class="white--text">
            <span>Symmetry</span>
            <v-spacer />
            <span>&copy; 2019</span>
        </v-footer>
    </v-app>
</template>
<script>
import LeftDrawer from './components/navigation/LeftDrawer';
import RightDrawer from './components/navigation/RightDrawer';


export default {
    props: {
        source: String,
    },
    data: function() {
        return {
            drawerLeft: !this.$vuetify.breakpoint.xs,
            drawerRight: false,
        }
    },
    components: {
        LeftDrawer,
        RightDrawer
    }
}
</script>
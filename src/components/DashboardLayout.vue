<!--@format-->

<template>
    <div class="dashboard">
       <v-navigation-drawer v-model="drawer" class="fullheight" width="256" app>
         <v-list-item>
            <v-list-item-content>
                <v-list-item-title class="title"> I Putu Rama Andika Putra </v-list-item-title>
            <v-list-item-subtitle> 180709897 </v-list-item-subtitle>
        </v-list-item-content>
    </v-list-item>

    <v-divider></v-divider>

    <v-list dense nav>
        <v-list-item
        v-for="item in items"
        :key="item.title"
        link
        tag="router-link"
        :to="item.to"
    >
        <v-list-item-content>
            <v-list-item-title> {{ item.title }} </v-list-item-title>
        </v-list-item-content>
    </v-list-item>
</v-list>
</v-navigation-drawer>
<v-app-bar app fixed height="75px">
    <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
    <VSpacer/>
    <v-toolbar-items>
        <v-btn text router><v-icon>mdi-power</v-icon></v-btn>
    </v-toolbar-items>

    <v-btn color="blue darken-1" text @click="setForm">
        Profile
    </v-btn>
    <v-btn color="blue darken-1" text @click="setForm">
        Logout
    </v-btn>
    </v-app-bar>
    <div class="fullheight pa-5">
        <router-view></router-view>
    </div>
</div>
</template>
<script>
export default {
    name: "Dashboard",
    data() {
        return {
            drawer: true,
            items: [
                { title: "Dashboard", to:"/dashboard" },
                { title: "Product", to:"/products" },
            ],
        };
    },
};
</script>

<style scoped>
.fullheight {
    min-height: 100vh !important;
}
.router {
    text-decoration: none;
    color: black;
}
</style>
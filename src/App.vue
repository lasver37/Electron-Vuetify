<template>
  <v-app id="inspire">
    <v-navigation-drawer
      v-model="drawer"
      app
    >
      <v-list dense>
        <v-list-item @click.stop="left = !left">
          <v-list-item-action>
            <v-icon>mdi-exit-to-app</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Open Temporary Drawer</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-navigation-drawer
      v-model="left"
      fixed
      temporary
    />

    <v-app-bar
      app
      color="blue-grey"
      dark
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title>Develop Arrange</v-toolbar-title>
      <v-spacer />
    </v-app-bar>

    <v-content>
      <v-container
      >
        <v-btn class="ma-2" tile outlined color="success" v-on:click="addFunc()">
          <v-icon left>mdi-pencil</v-icon> Add
        </v-btn>
        <v-btn class="ma-2" tile outlined color="success" v-on:click="editFunc()">
          <v-icon left>mdi-pencil</v-icon> Edit
        </v-btn>
        <v-btn class="ma-2" tile outlined color="success" v-on:click="removeFunc()">
          <v-icon left>mdi-pencil</v-icon> Remove
        </v-btn>

        <v-data-table
          :headers="headers"
          :items="desserts"
          :items-per-page="5"
          class="elevation-1"
        ></v-data-table>

      </v-container>
    </v-content>

    <v-footer
      app
      color="blue-grey"
      class="white--text"
    >
      <span>Vuetify</span>
      <v-spacer />
      <span>&copy; 2019</span>
    </v-footer>
  </v-app>
</template>

<script>
  export default {
    props: {
      source: String,
    },
    methods: {
      addFunc: function() {
        alert('addFunc');
      },
      editFunc: function() {
        alert('editFunc');
      },
      removeFunc: function() {
        alert('removeFunc');
      }
    },
    data: () => ({
      drawer: false,
      left: false,

      headers: [
          { text:'No.', align:'left', sortable:true, value:'no', width:'10%' },
          { text:'Title', align:'left', sortable:true, value:'title', width:'70%' },
          { text:'Date', align:'left', sortable:true, value:'date', width:'20%' },

        /*
          {
            text: 'Dessert (100g serving)',
            align: 'left',
            sortable: false,
            value: 'name',
          },
          { text: 'Calories', value: 'calories' },
          { text: 'Fat (g)', value: 'fat' },
          { text: 'Carbs (g)', value: 'carbs' },
          { text: 'Protein (g)', value: 'protein' },
          { text: 'Iron (%)', value: 'iron' },
        */
        ],
        desserts: [
          {
            no:1,
            title:'Electron 정리',
            date:'2019-12-08 21:09:52'
          },{
            no:2,
            title:'Vuetify 스터디',
            date:'2019-12-08 23:21:30'
          },{
            no:3,
            title:'ReactNative 정리',
            date:'2019-11-25 14:21:32'
          },{
            no:4,
            title:'Socket 정리',
            date:'2019-09-25 11:33:14'
          }
        /*
          {
            name: 'Frozen Yogurt',
            calories: 159,
            fat: 6.0,
            carbs: 24,
            protein: 4.0,
            iron: '1%',
          },
          {
            name: 'Ice cream sandwich',
            calories: 237,
            fat: 9.0,
            carbs: 37,
            protein: 4.3,
            iron: '1%',
          },
          {
            name: 'Eclair',
            calories: 262,
            fat: 16.0,
            carbs: 23,
            protein: 6.0,
            iron: '7%',
          },
          {
            name: 'Cupcake',
            calories: 305,
            fat: 3.7,
            carbs: 67,
            protein: 4.3,
            iron: '8%',
          },
          {
            name: 'Gingerbread',
            calories: 356,
            fat: 16.0,
            carbs: 49,
            protein: 3.9,
            iron: '16%',
          },
          {
            name: 'Jelly bean',
            calories: 375,
            fat: 0.0,
            carbs: 94,
            protein: 0.0,
            iron: '0%',
          },
          {
            name: 'Lollipop',
            calories: 392,
            fat: 0.2,
            carbs: 98,
            protein: 0,
            iron: '2%',
          },
          {
            name: 'Honeycomb',
            calories: 408,
            fat: 3.2,
            carbs: 87,
            protein: 6.5,
            iron: '45%',
          },
          {
            name: 'Donut',
            calories: 452,
            fat: 25.0,
            carbs: 51,
            protein: 4.9,
            iron: '22%',
          },
          {
            name: 'KitKat',
            calories: 518,
            fat: 26.0,
            carbs: 65,
            protein: 7,
            iron: '6%',
          },
        */
        ]
    }),
  }
</script>
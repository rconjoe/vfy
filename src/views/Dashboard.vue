<template>
    <div>
        <h1>Dashboard</h1>
        <v-data-table
            :headers="headers"
            :items="desserts"
            :items-per-page="5"
            class="elevation-1"
            @click:row="selectRow"
        ></v-data-table>
        <v-snackbar 
            v-model="snackbar">
          You have selected {{ currentItem }}
        <v-btn
            color="pink"
            text
            @click="snackbar = false"
        >
          Close
        </v-btn>
      </v-snackbar>
    </div>
</template>

<script>

export default {
    name: 'DashboardPage',
    data() {
        return {
            currentItem: '',
            snackbar: false,
            headers: [
                {
                    text: 'Dessert (100g serving)',
                    align: 'left',
                    sortable: false,
                    value: 'name'
                },
                { text: 'Calories', value: 'calories' },
                { text: 'Fat (g)', value: 'fat' },
                { text: 'Carbs (g)', value: 'carbs' },
                { text: 'Protein (g)', value: 'protein' },
                { text: 'Iron (%)', value: 'iron' }
            ],
            desserts: [
                {
                    name: 'Frozen Yogurt',
                    calories: 159,
                    fat: 6.0,
                    carbs: 24,
                    protein: 4.0,
                    iron: '1%'
                },
                {
                    name: 'Ice cream sandwich',
                    calories: 237,
                    fat: 9.0,
                    carbs: 37,
                    protein: 4.3,
                    iron: '1%'
                },
                {
                    name: 'Eclair',
                    calories: 262,
                    fat: 16.0,
                    carbs: 23,
                    protein: 6.0,
                    iron: '7%'
                },
                {
                    name: 'Cupcake',
                    calories: 305,
                    fat: 2.7,
                    carbs: 67,
                    protein: 4.3,
                    iron: '8%'
                },
                {
                    name: 'Gingerbread',
                    calories: 256,
                    fat: 16.0,
                    carbs: 49,
                    protein: 3.9,
                    iron: '16%'
                },
                {
                    name: 'Jelly bean',
                    calories: 275, 
                    fat: 0.0,
                    carbs: 94,
                    protein: 0.0,
                    iron: '0%'
                },
            ]
        }
    },
    methods: {
        selectRow(event) {
            this.snackbar = true
            this.currentItem = event.name
        }
    }

}
</script>


<style>
</style>


<template>
    <v-container>
        <v-row>
            <v-col md="6" sm="12">
                <v-btn class="decide-btn" to="/form" size="x-large" stacked="true" block="true" rounded="true">CREATE A TRIP</v-btn>
            </v-col>
            <v-col md="6" sm="12">
                <v-btn class="decide-btn" to="/inspire" size="x-large" stacked="true" block="true" rounded="true">INSPIRE ME!</v-btn>
            </v-col>
        </v-row>
    </v-container>
</template>

<script lang="ts" setup>
//
</script>

<style scoped>
.decide-btn{
    color: white;
    background: #EEA46C; 
}
</style>
<template>
    <v-row>
        <v-col v-for="(product, index) in products"
        cols="2">
        <v-card : title="product.title">
            <v-card-actions>
                <v-img :src="require(`@/assets/image/products/${product.thumbnail}`)"></v-img>
            </v-card-actions>
            <v-card-text>
                {{ product.title }}
            </v-card-text>
        </v-card>
        
        </v-col>

    </v-row>
</template>

import { defineComponent } from '@vue/composition-api'

export default(
    
)
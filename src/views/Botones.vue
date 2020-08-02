<template>
    <v-container>
        <v-layout>
            <v-flex>
                <v-btn>Texto</v-btn>
                <v-btn color="primary">Texto</v-btn>
                <v-btn dark color="blue">Texto</v-btn>
                <v-btn dark color="blue" text>Sin fondo</v-btn>
                <v-btn large color ="error">Sin fondo</v-btn>
                <v-btn small color ="error">Sin fondo</v-btn>
                <v-btn small :disabled="true" color ="error">Sin fondo</v-btn>
                <v-btn depressed color="blue">Texto</v-btn>


                <v-btn icon color="primary">
                    <v-icon >
                        mdi-forum
                    </v-icon>
                </v-btn>

                <v-btn class="mx-2" fab color="pink">
                   <v-icon>mdi-heart</v-icon>
                </v-btn>

                <v-btn rounded color="primary">
                    Redondeado
                </v-btn>

            </v-flex>
        </v-layout>
    </v-container>
</template>sas
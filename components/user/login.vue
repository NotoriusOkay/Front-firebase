<template>
    <v-card class="cardLogin">
        <v-card-title>Login</v-card-title>
        <v-card-text>
            <v-form v-model="formularioValido">
                <v-text-field label="Correo Electronico" 
                placeholder="Correo Electronico"
                v-model="correoElectronico"
                />
            </v-form>
        </v-card-text>
        <v-card-actions>
            Boton para iniciar sesion
        </v-card-actions>
    </v-card>
</template>

<script>
    export default {
        data() {
            return {
                formularioValido: false,
                correoElectronico: ''
            }
        }
    }
</script>

<style scoped>
    .cardLogin{
        background-color: #1A237E;
        border-radius: 10px;
        width: 500px;
        height: 300px;
    }
</style>
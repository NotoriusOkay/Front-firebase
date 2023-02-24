<template>
    <v-card class="cardLogin">
        <v-card-title class="title">Bienvenido de nuevo, Por favor inicia sesion!!</v-card-title>
        <v-card-text>
            <v-row justify="center" align="center">
                <v-col cols="4" align-self="center">
                    <img src="../../assets/images/Homero.png" class="imgLogin">
                </v-col>
                <v-col cols="8" align-self="center">
                    <v-form ref="formLogin">
                        <v-text-field label="Correo Electronico" 
                                      placeholder="Correo Electronico"
                                      v-model="correoElectronico"
                                      :rules="validarCorreo"
                />
                <v-text-field label="Password" 
                                      placeholder="Password"
                                      v-model="password"
                                      :rules="validarPassword"
                />
            </v-form>
                </v-col>
            </v-row>
        </v-card-text>
        <v-card-actions>
            <v-btn
            class="btnLogin"
            rounded
            block
            @click="loginBackend"
            >
                Login
            </v-btn>
        </v-card-actions>
    </v-card>
</template>

<script>
    export default {
        data() {
            return {
                correoElectronico: '',
                validarCorreo: [
                v => !v || /^\w+([.-]?\w+)*@\w+([.-]?\w+)*(\.\w{2,3})+$/.test(v) || 'E-mail must be valid'
                ],
                password: '',
                validarPassword: [
                    value => value.length >= 6 || 'Min 6 characters'
                ]
            }
        },
        methods: {
            loginBackend () {
                const valid = this.$refs.formLogin.validate()
                if(valid){
                    alert('Presionaste el boton')
                }else {
                    alert('No cumpliste con las reglas')
                }
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
        color: white;
    }

    .imgLogin{
        width: 100%;
        height: 100%;
    }

    .btnLogin{
        background-color: beige !important;
        color: black !important;
    }

    .title{
        font-size: 20px;
        justify-content: center;
        color: white;
        font-weight: 700;
    }
</style>
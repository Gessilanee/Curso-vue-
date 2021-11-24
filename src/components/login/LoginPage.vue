<template>
    <v-container fluid>
        <v-row justify="center">
            <v-col
                cols="12"
                md="4"
                lg="3"
                class="text-center"
            >
                <h6 class="display-1 text-uppercase">Login</h6>
                

                <v-text-field
                    v-model="token"
                    label="Token"
                />

                <v-btn
                    depressed
                    dark
                    block
                    color="primary"
                    class="mb-2"
                    @click="login"
                >
                    Login
                </v-btn>

                <v-btn
                    text
                    color="secondary"
                    @click="loginAsGuest"
                >
                    Entrar como Visitante
                </v-btn>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
    export default {
        name: 'LoginPage',
        data() {
            return {
                token: '',
            };
        },
        methods: {
            login() {
                if(this.token) {
                    this.$store.commit('setAuthToken', this.token);
                    this.$store.commit('setLogged', true);
                    this.$router.push('/book');
                } else{
                     this.$store.commit('showErrorMessage', 'Você deve informar  um Token');

                }
            },
            loginAsGuest() {
                this.$router.push('/book');
                
            },
        },
    };
</script>
//AIzaSyA6zhLRENrjUY4tf1XGcKuI0x1aUfHYUR0
<style scoped>

</style>
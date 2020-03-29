<template>
    <v-app>
        <div class="container">
            <div class="col-md-3 m-auto">
                <h5>Login</h5>

            </div>
            <nuxt-link to="/">Previous page</nuxt-link>
        </div>
    </v-app>
</template>

<script>
    import FormGroup from '@/components/Forms/FormGroup';
    export default {
        name: "about",
        data(){
            return {

            }
        },
        async asyncData(context){
            return {
                title: 'Login',

            }
        },
        components:{
            FormGroup
        }
    }
</script>

<style scoped>

</style>
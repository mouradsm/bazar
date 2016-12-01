<template>
    <div v-show="confirmation">
        <div>this is template body {{msg}}</div>
    </div>
</template>
<style scoped>
    body{
        background-color:#ff0000;
    }
</style>
<script>
    import bus from '../utils/events/bus'

    export default{
        mounted() {
            let vm = this
            bus.$on('termo-aceito', function(){
                vm.confirmation = true
            })
        },
        data(){
            return{
                msg:'hello vue',
                confirmation: false
            }
        }
    }
</script>

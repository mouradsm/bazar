<template >
    <div v-show="!confirmation">
        <div>this is template body</div>
        <el-button @click="confirmar">Let's do it</el-button>
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
        data(){
            return{
                msg:'hello vue',
                confirmation: false
            }
        },
        methods: {
            confirmar : function() {
              this.confirmation = !this.confirmation
              bus.$emit('termo-aceito')
            }
        }
    }
</script>

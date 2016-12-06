<template>
    <div v-show="!confirmation">
        <el-row>
            <el-col :span="8" :offset="8">
                <el-card class="box-card">
                    <div class="mensagem">
                        <h2>Bazar Neo Missio</h2>
                        Seja bem vindo ao primeiro bazar neo missio. O objetivo é gerar recursos para as atividades
                        sociais que estão sendo realizadas na basa da ONG no Rio de Janeiro. Se você quer vender
                        seus produtos usados em nosso bazar, é maior de 18 anos e concorda com nossos
                        <el-button type="text" @click="dialogVisible = true">TERMOS</el-button>
                        , inscreva-se clicando em <b>continuar</b>.
                    </div>
                    <el-button type="primary" @click="confirmar" class="confirmation">Continuar</el-button>
                </el-card>
            </el-col>

            <el-dialog title="Tips" v-model="dialogVisible" size="tiny">
                <span>Termos e condições blablablabla</span>
                <span slot="footer" class="dialog-footer">
            <!--<el-button @click="dialogVisible = false">Cancel</el-button>-->
            <el-button type="primary" @click="dialogVisible = false">Confirm</el-button>
        </span>
            </el-dialog>
        </el-row>
    </div>

</template>
<style scoped>
    body{
        background-color:#ff0000;
    }
    .confirmation {
        float: right;
        margin: 3% 0% 5%;
    }

    .mensagem {
        text-align: justify;
        font-family: 'Ubuntu',"Helvetica Neue",Helvetica,"PingFang SC","Hiragino Sans GB","Microsoft YaHei","微软雅黑",Arial,sans-serif;
    }

    .mensagem h2 {
        text-align: center;
    }



</style>
<script>
    import bus from '../utils/events/bus'

    export default{
        data(){
            return{
                msg:'hello vue',
                confirmation: false,
                dialogVisible: false
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

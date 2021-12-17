<template>
    <div class="label" :class="className">
        {{text}}BOOST
    </div>
</template>

<script>
    export default {
        name: "theLabel",
        props:{
            type:{
                type: String,
                default: 'face'
            }
        },
        computed:{
            text(){
                if (this.type === 'back') return 'CREAT ';
                return null;
            },
            className(){
                return `${this.type}-label`
            }

        }
    }
</script>

<style scoped>
    div.label{
        font-size: 11px;
        width: fit-content;
        border-radius: 20px;
    }
    .face-label{
        color: #CCD0DE !important;
        border: 2px solid #CCD0DE !important;
        margin-left: 5px !important;
        padding: 2px 5px !important;
    }
    .back-label{
          color: #4F5BD5 !important;
          background-color: #4F5BD51F !important;
          margin: 0 auto !important;
          padding: 5px 10px !important;
          font-weight: bolder !important;
      }
</style>

<template>
    <div class="back" @mouseenter="this.$emit('hover', true)"
         @mouseleave="this.$emit('hover', false)">
        <the-label type="back"/>
        <div class="separator">
            <span>
                Date Period
            </span>
            <h4>Pick Date Range:</h4>
            <div class="date">
                <span class="date">2020/9/10</span>
                <span>To</span>
                <span class="date">2020/9/10</span>
            </div>
        </div>
    </div>
</template>

<script>
    import theLabel from './the-label'
    export default {
        name: "back",
        components:{
            theLabel
        }
    }
</script>

<style scoped>
    div.back{
        width: 200px;
        height: 250px;
        background-color: white;
        border-radius: 5px;
        padding-top: 10px;
        box-sizing: border-box;
        display: block;
        transform: translateY(-3%);
        box-shadow: 1px 1px 5px #EAEAEA, -1px -1px 5px #EAEAEA;
    }
    div.separator{
        width: 100%;
        height: 20px;
        margin-top: 30px;
        border-top: 2px #A6ACBA dashed;
    }
    div.separator span{
        color: #A6ACBA;
        display: block;
        width: fit-content;
        background-color: white;
        transform: translateY(-8px);
        margin: 0 auto;
        font-size: 12px;
    }
    h4{
        color: #3C3C3C;
        font-weight: normal;
    }
    div.date{
        display: flex;
        justify-content: space-evenly;
        width: 80%;
        margin: 30px auto;
        height: fit-content;
    }
    span.date{
        color: #3C3C3C;
        font-weight: bolder;
        text-decoration: underline;
    }

</style>

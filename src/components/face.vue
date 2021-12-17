<template>
    <div
            class="face"
            @mouseenter="this.$emit('hover', true)"
            @mouseleave="this.$emit('hover', false)"
            @click.stop="this.$emit('wrongClick')"
    >
        <the-label />
        <div class="face-info">
            <span class="type">LIKING</span>
            <span class="value">100</span>
        </div>
    </div>
</template>

<script>
    import theLabel from "./the-label";
    export default {
        name: "face",
        components:{
            theLabel
        }
    }
</script>

<style scoped>
    div.face{
        width: 200px;
        height: 100px;
        background-color: white;
        border-radius: 5px;
        padding: 10px 15px 5px 15px;
        box-sizing: border-box;
        display: block;
        transform: translateY(-3%);
        box-shadow: 1px 1px 5px #EAEAEA, -1px -1px 5px #EAEAEA;
    }
    div.face-info{
        display: flex;
        justify-content: space-between;
        align-items: end;
        height: 60%;
    }
    span.type{
        color: #3C3C3C;
        font-size: 13px;
        line-height: 21px;
    }
    span.value{
        font-size: 20px;
        font-weight: bolder;
    }
</style>

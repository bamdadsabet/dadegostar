<template>
    <div class="button-container">
        <div
                class="plus-button"
                :class="{'is-clicked': isClicked, 'close': !isOpen}"
                @mouseenter="toggle(true)"
                @mouseleave="toggle(false)"
                @click.stop="click"
        >
           <div class="alert">
               <svg viewBox="0 0 26 26" focusable="true">
                   <path d="M10.5 9.3L1.8 0.5 0.5 1.8 9.3 10.5 0.5 19.3 1.8 20.5 10.5 11.8 19.3 20.5 20.5 19.3 11.8 10.5 20.5 1.8 19.3 0.5 10.5 9.3Z"></path>
               </svg>
           </div>
        </div>
        <back  v-if="isClicked" @hover="toggle"/>
        <face
                @hover="toggle"
                @wrongClick="wrongClick"
                v-else
        />
    </div>
</template>

<script>
    import face from "./face";
    import back from "./back";
    export default {
        name: "theButton",
        components:{
            face,
            back
        },
        props:{
            isClicked:{
                type: Boolean,
                default: false,
                required: false
          }
        },
        data(){
          return{
              isOpen: false,
          }
        },
        methods:{
            toggle(value){
                this.isOpen = value;
            },
            click(){
                this.$emit('clicked', this.$attrs.id)
            },
            wrongClick(){
               this.plusBtn.classList.add('wrong-click');
                setTimeout(()=>{
                    this.plusBtn.classList.remove('wrong-click');
                }, 400);
            }
        },
        mounted() {
            this.plusBtn = this.$el.querySelector('div.plus-button');
        }
    }
</script>

<style scoped>
    .close{
        transform: translateY(70%);
    }
    .is-clicked svg{
        fill: white;
    }
    .is-clicked{
        background-color: #4F5BD5 !important;
        transform: revert!important;
    }
    .wrong-click{
        background-color: skyblue !important;
        opacity: .5;
    }
    .wrong-click div.alert{
        border-color: #EAEAEA;
        background-color: skyblue !important;
        opacity: .5;
    }
    div.button-container{
        width: fit-content;
    }
    div.plus-button{
        background-color: white;
        width: 85%;
        margin: 0 auto;
        border-radius: 5px;
        height: 50px;
        box-sizing: border-box;
        cursor: pointer;
        transition: all .2s linear;
        padding: 2px 2px 5px 2px
    }
    svg{
        fill: #4F5BD5;
        width: 15px;
        transform: translateY(20%) rotate(-45deg);
    }
    div.alert{
        display: block;
        padding-top: 12px;
        margin: 2px;
        height: 25px;
        border: 2px transparent solid;
    }
</style>

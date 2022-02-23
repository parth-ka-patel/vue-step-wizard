<template>
    <div v-if="isActive && isVisible">
        <slot></slot>
    </div>
</template>

<script>
export default {
    name: 'tab-content',
    props:{
        selected: {
            default: false,
        },
        title: {
            type: String,
            required: true
        },
        visible:{
          default: true,
        }
    },
    data(){
        return{
            isActive: false,
            isValidated : false,
            isVisible : true,
        }
    },
    created(){
        this.isActive = this.selected;
        this.isVisible = this.visible;
    }
}
</script>
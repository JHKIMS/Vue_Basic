<template>
    <div v-if="modal == true" class="black-bg">
        <div class="white-bg">
            <h4>{{ onerooms[userClick].title }}</h4>
            {{ onerooms[userClick].content }} <br>
            {{ onerooms[userClick].price }}만원 <br>
            <button @click="modalClose">닫기</button>
        </div>
    </div>
</template>
<script>
export default {
    name: 'ModalVue',
    props : {
        onerooms : Array,
        userClick : Number,
        modal : Boolean,
    },
    methods :{
        modalClose(){
            this.$emit('modalClose')
        }
    }
}
</script>
<style>

</style>
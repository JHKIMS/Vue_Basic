<template>
    <div v-if="modal == true" class="black-bg">
        <div class="white-bg">
            <h4>{{ onerooms[userClick].title }}</h4>
            <p>{{ onerooms[userClick].content }} <br></p>
            <!-- <input @input="month = $event.target.value"> -->
            <input v-model.number="month">
            <p>{{month}}개월 선택함:{{ onerooms[userClick].price }}만원 <br></p>
            <button @click="modalClose">닫기</button>
        </div>
    </div>
</template>
<script>
export default {
    name: 'ModalVue',
    data(){
        return{
            month : 1,
        }
    },
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
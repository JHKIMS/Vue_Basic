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
    watch : {
        month(a){ //a: 변경후 데이터, b: 변경전 데이터
            this.month = 1;
            if(!isNaN(a)) alert('문자 불가능')
            // console.log(b);
            // if(a>=13) alert('13이상 입력X')
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
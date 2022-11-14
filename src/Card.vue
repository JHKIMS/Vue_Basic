<template>
    <div>
        <img :src="oneroom.image" class="room-img"> <!-- src같은 속성에 데이터 바인딩은 이런 방식으로-->
        <h4 @click="$emit('sampleName', oneroom.id)">{{ oneroom.title }}</h4>
        <p @click="funcModal">{{ oneroom.price }}만원</p>
    </div>
</template>
<script>
export default {
    name : "CardVue",
    props :{
        oneroom : Object,
    },
    /**
     * 이 메소드로 h4 click 부분 변경 가능 @click="funcModal"
     */
    methods :{
        funcModal(){
            this.$emit('sampleName', this.oneroom.id)
        }
    }
}
</script>
<style>

</style>
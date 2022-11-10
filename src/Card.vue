<template>
    <div>
        <img :src="oneroom.image" class="room-img"> <!-- src같은 속성에 데이터 바인딩은 이런 방식으로-->
        <h4>{{ oneroom.title }}</h4>
        <p>{{ oneroom.price }}만원</p>
    </div>
</template>
<script>
export default {
    name : "CardVue",
    props :{
        oneroom : Object,
    }
}
</script>
<style>

</style>
<!-- 컴포넌트를 만들고 싶으면
1. Vue파일 만들고
2.축약할 HTML 넣기 -->
<template>
    <div class="discount">
        <h4>지금 결제하면 {{amount}}% 할인</h4>
    </div>
</template>
<script>
export default {
    name: 'DiscountVue',
    data(){
        return{
            amount: 5,
        }
    },
    mounted(){
        let a; 
        a = setInterval(()=>{
            this.amount--;
            if(this.amount===0)clearInterval(a);
        }, 1000);

        
  }
}
</script>
<style>
    .discount{
        background-color: dodgerblue;
        color: white;
    }
</style>
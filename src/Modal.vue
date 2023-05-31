<template>
    <div class="black-bg" v-if="modalshow">
        <div class="white-bg">
            <h4>{{ rommdata[clickNum].title }}</h4>
            <img :src="rommdata[clickNum].image" alt="">
            <p>{{ rommdata[clickNum].content }}</p>
            <!-- <input type="text" @input="month = $event.target.value"/> -->
            <input v-model="month">
            <p>{{month}}개월 = {{ rommdata[clickNum].price * month}}원</p>
            <button @click="$emit('closeModal')">모달 닫기</button>
        </div>
    </div>

</template>

<script>
export default {
    name: 'Modal',
    data(){
        return{
            month:1,
        }
    },
    props:{
        rommdata: Object,
        clickNum:Number,
        modalshow:Boolean,
    }
}
</script>

<style>

</style>
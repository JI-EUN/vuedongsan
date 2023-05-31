<template>
    <div class="black-bg" v-if="modalshow">
        <div class="white-bg">
            <h4>{{ rommdata[clickNum].title }}</h4>
            <img :src="rommdata[clickNum].image" alt="">
            <p>{{ rommdata[clickNum].price }}원</p>
            <p>{{ rommdata[clickNum].content }}</p>

            <!-- <button @click="modal()">모달 닫기</button> -->
        </div>
    </div>

</template>

<script>
export default {
    name: 'Modal',
    props:{
        rommdata: Object,
        clickNum:Number,
        modalshow:Boolean,
    }
}
</script>

<style>

</style>
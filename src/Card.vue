<template>
  <div>
    <img :src="lists.image" alt="">
    <h4 @click="$emit('openModal',lists.id)">{{lists.title}}</h4>
    <p>{{lists.price}} 원</p>
  </div> 
</template>

<script>
export default {
    name:'Card',
    props:{
        lists:Object,
        number:Number
    }
}
</script>

<style>

</style>
<template>
    <div class="black-bg" v-if="openModal == true">
      <div class="white-bg">
        <h3>{{products[num].title}}</h3>
        <p>
          {{products[num].content}}
        </p>
        <div>{{products[num].price}}원</div>
        <Discount />
        <!-- <button @click="openModal = false">close</button> props는 수정해서 쓰면 안됌 props는 readonly -->
      </div>
    </div>
</template>

<script>
export default {
    name: 'Modal-name',
    props : {
        products: Array,
        num: Number,
        openModal: Boolean,  //데이터는 공유가 될텐데, 최상위 부모에게 선언해서 자식에게 전송해서 쓰자.
    }
}
</script>

<style>

</style>
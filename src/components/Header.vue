<template>
    <div>
        <nav class="menu">
            <a href="#" v-for="(menu, index) in navMenu" :key="index">{{menu}}</a>
        </nav>
    </div>
</template>

<script>
export default {
  name: 'Header-name',
  data(){ //data 보관함
    return {
      navMenu : ['Home', 'Products', 'About'],
    }
  },
}
</script>

<style>
.menu {
  padding:10px;
  background-color:darkblue;
  border-radius:10px;
  text-align:center;
}

.menu > a {
  display:inline-block;
  padding:5px;
  color:#fff
}
</style>
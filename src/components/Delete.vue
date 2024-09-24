<template>
  <div class="backdrop" @click.self="deleteModal">
    <div class="modal" :class="{danger:color==='delete'}">
      <slot>
        <h1>This is default slot</h1>
      </slot>
    </div>
  </div>
</template>

<script>
export default {
props:["color"],
methods:{
  deleteModal(){
    this.$emit("delete");
  }
}
}
</script>

<style scoped>
.backdrop{
  width: 100%;
  height: 100%;
  background:rgba(0, 0, 0, 0.5);
  position:fixed;
  top:0;
}
.modal{
  padding:20px;
  margin:200px auto;
  width:500px;
  background: #fff;
  border-radius:20px;
}
.danger{
  background: darkred;
  color: white;
}
</style>
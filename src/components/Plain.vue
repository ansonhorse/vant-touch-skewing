<!--
 不引用其他类库的示例

 @name Plain
 @author Anxon <ansonhorse@gmail.com>
-->
<template>
  <div class="main">
    <div class="item-desc">
      <h1 v-for="i in 80">{{ 'hello' + i}}</h1>
    </div>

    <div class="footer">
      <div class="col">
        <div class="div-button">div button</div>
      </div>
      <div class="col">
        <button type="button">real button</button>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'Plain',
    components: {},
  }
</script>

<style>
  .footer {
    position: fixed;
    left: 0;
    bottom: 0;
    width: 100%;
    background: #eee;
    padding: 10px 5px;
  }
  .col {
    float: left;
    width: 50%;
  }
  .div-button:active {
    background: #e48080;
  }
  .div-button {
    padding: 10px;
    background: #edb7a4;
  }
  button:active {
    background: #666;
  }
  button {
    background: #bb8ba5;
    padding: 11px;
    width: 100%;
  }
</style>

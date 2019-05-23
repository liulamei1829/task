<template>
  <div>
    <div class="footer">
      <p class="tips">已过期，如有疑问，请咨询医生</p>
      <button class="goto">去问医生</button>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
*{
  border: 0;
}
.footer{
  position: fixed;
  bottom: 0;
  width: 100%;
  height: 95px;
  background-color: #ccc;
}
.tips{
  font-size: 14px;
  line-height: 16px;
  color: #666;
  margin: 10px auto;
}
.goto{
display: block;
width: 345px;
height: 44px;
margin: 10px auto 15px;
border-radius: 22px;
background-image: linear-gradient(-90deg, #4F82FF 8%, #5C77FF 92%);
color:#fff;
font-size: 17px;
}

</style>

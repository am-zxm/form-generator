<template>
  <div>
    <router-view />
  </div>
</template>

<script>
export default {
  mounted() {
    // 取消开始的loading动画
    const preLoader = document.querySelector('#pre-loader')
    preLoader.style.display = 'none'
    alert('Page has been loaded') // alert() can take any message string as argument. It will be displayed as a message box.

    // fix: firefox 下 拖拽 会新打卡一个选项卡
    // https://github.com/JakHuang/form-generator/issues/15
    document.body.ondrop = event => {
      event.preventDefault()
      event.stopPropagation()
    }
  }
}
</script>

<template>
  <div>
    <div class="element" @click="addButton">
      <i class="iconfont icon-anniu"></i>
      <div>按钮</div>
    </div>
    <div class="element" @click="addImg">
      <i class="iconfont icon-picture_icon"></i>
      <div>图片</div>
    </div>
    <div class="element" @click="addText">
      <i class="iconfont icon-wenben"></i>
      <div>文本</div>
    </div>
    <div class="element" @click="addInput">
      <i class="iconfont icon-danhangshurukuang"></i>
      <div>输入框</div>
    </div>
  </div>
</template>

<script>
  import Button from "@/model/Button.js";
  import Img from "@/model/Img.js";
  import Input from "@/model/Input.js";
  import Text from "@/model/Text.js";

  export default {
    data() {
      return {};
    },
    methods: {
      addButton() {
        this.$store.commit(
          "addElement",
          new Button({
            text: "button",
            name: "ui-button"
          })
        );
      },
      addImg() {
        this.$store.commit(
          "addElement",
          new Img({
            text: "image",
            name: "ui-img"
          })
        );
      },
      addInput() {
        this.$store.commit(
          "addElement",
          new Input({
            text: "input",
            name: "ui-input"
          })
        );
      },
      addText() {
        this.$store.commit(
          "addElement",
          new Text({
            text: "text",
            name: "ui-text"
          })
        );
      }
    },
  };

</script>

<style lang="less" scoped>
  .element {
    padding: 8px 4px 8px 0;
    line-height: 1;
    text-align: center;
    border-left: 4px solid #fff;
    &:hover {
      border-left: 4px solid #4fc3f7;
      background-color: #f6f6f6;
      color: #1a76d2;
      cursor: pointer;
    }
    i {
      font-size: 32px;
    }
    div {
      font-size: 12px;
    }
  }

</style>

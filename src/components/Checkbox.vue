<template>
  <div class="checkbox">
    <input type="checkbox" class="checkbox__input" :style="{ marginLeft, marginRight }" :id="id" />
    <label :for="id" :class="{ 'cursor-pointer': id }">{{label}}</label>
  </div>
</template>

<script>
export default {
  name: "Checkbox",
  props: {
    label: String,
    marginRight: {
      type: String,
      default: "8px"
    },
    marginLeft: {
      type: String
    },
    id: String
  }
};
</script>  

<style lang="scss">
.checkbox {
  display: flex;
  align-items: center;
  height: fit-content;

  &__input {
    height: 18px;
    width: 19px;
    position: relative;
    cursor: pointer;

    &:after {
      content: "\00D7";
      display: block;
      background: #fff;
      background-image: url("https://cdn0.iconfinder.com/data/icons/slim-square-icons-basics/100/basics-21-32.png");
      pointer-events: none;
      font-size: 15px;
      position: absolute;
      top: 0;
      left: 0;
      height: 15px;
      width: 15px;
      color: transparent;
      transition: 0.25s all ease-in-out;
      border-radius: 3px;
      line-height: 15px;
      background-position: 0 15px;
      background-repeat: no-repeat;
      background-size: 15px 15px;
      border: 1px solid #ccc;
    }

    &:checked:after {
      background-position: 0 0;
    }
  }
}
</style>
<template>
  <header class="d-flex header">
    <Logo />
    <nav class="header-navigation">
      <ul class="d-flex header-menu">
        <li class="header-menu__item">Help</li>
        <li class="header-menu__item">Log In</li>
        <li class="header-menu__item header-menu__item--primary">Sign Up</li>
      </ul>
    </nav>
  </header>
</template>

<script>
import Logo from "./Logo";
export default {
  name: "Header",
  components: {
    Logo
  }
};
</script>

<style lang="scss">
$green: #88bc95;
$grey: #afb3b4;
$grey-hovered: #979898;

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 16px;
  background-color: #f6fafd;

  &-menu {
    align-items: center;
    &__item {
      cursor: pointer;
      color: $grey;
      transition: 0.3s;
      font-size: 16px;

      &:not(:last-child) {
        margin-right: 20px;
      }

      &:hover {
        color: $grey-hovered;
      }

      &--primary {
        color: $green;
        border: 1px solid $green;
        border-radius: 3px;
        padding: 5px 12px;

        &:hover {
          border: none;
          color: #fff;
          background-color: $green;
          border: 1px solid $green;
        }
      }
    }
  }
}
</style>
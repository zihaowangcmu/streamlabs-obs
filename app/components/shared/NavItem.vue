<template>
<li
  class="nav-item"
  :class="{ active: to === value, disabled: enabled == false }"
  @click="onClickHandler"
>
  <i v-if="ico" :class="ico" @click="onIconClickHandler"></i>
  <span class="nav-item__name"><slot></slot></span>
</li>
</template>

<script lang="ts" src="./NavItem.vue.ts"></script>

<style lang="less" scoped>
@import "../../styles/index";

.nav-item {
  cursor: pointer;
  list-style: none;
  border-left: 1px solid transparent;
  padding-left: 50px;
  opacity: 0.7;
  font-size: 14px;
  margin-bottom: 5px;
  display: flex;
  align-items: center;
  justify-content: flex-start;

  &.active {
    opacity: 1;
    .semibold;
    border-color: @navy;
    color: @navy;

    .fa,
    i {
      color: @navy;
    }
  }

  &:hover {
    opacity: 1;
  }

  &.disabled {
    opacity: 0.3;
    cursor: default;
  }

  .fa,
  i {
    color: #999;
    position: relative;
    margin-right: -15px;
    left: -25px;
    width: 16px;
  }
}

.nav-item__name {
  overflow: hidden;
  max-width: calc(~"100% - 20px");
  text-overflow: ellipsis;
  white-space: nowrap;
}

.night-theme {
  .nav-item {
    &.active {
      border-color: @white;
      color: @white;

      .fa,
      i {
        color: @white;
      }
    }
  }
}

</style>

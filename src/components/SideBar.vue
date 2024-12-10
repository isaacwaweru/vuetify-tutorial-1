<script setup>
import { defineEmits } from "vue";

const emits = defineEmits(["selectOption"]);

const selectOption = (isColor) => {
  emits("selectOption", isColor);
};
</script>

<template>
  <VNavigationDrawer expand-on-hover rail>
    <VList>
      <VListItem
        prepend-avatar="https://kg-farmers-s3.lon1.digitaloceanspaces.com/profile/8f100837-016b-4e7c-bb96-6cc0ba023ebe.jpg"
        subtitle="cb@gmailcom"
        title="Chris Brown"
      ></VListItem>
    </VList>

    <VDivider />

    <VList>
      <VListItem
        prepend-icon="mdi-image"
        title="Color Gallery"
        value="color"
        @click="selectOption(true)"
      />
      <VListItem
        prepend-icon="mdi-water"
        title="Grayspace Gallery"
        value="gray"
        @click="selectOption(false)"
      />
    </VList>
  </VNavigationDrawer>
</template>

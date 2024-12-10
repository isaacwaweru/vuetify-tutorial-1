<script setup>
import { defineProps } from "vue";

const props = defineProps(["isWithColor"]);

const copyUrl = async (url) => {
  await navigator.clipboard.writeText(url);
};
</script>

<template>
  <VCard class="mx-5 my-2 pa-3">
    <VRow>
      <VCol v-for="n in 204" :key="n" cols="4" sm="3" md="2" lg="1">
        <VCard
          @click="
            copyUrl(
              `https://picsum.photos/500/300?image=${n * 5 + 10}${
                props.isWithColor ? '' : '&grayscale'
              }`
            )
          "
        >
          <VImg
            :src="`https://picsum.photos/500/300?image=${n * 5 + 10}${
              props.isWithColor ? '' : '&grayscale'
            }`"
            :lazy-src="`https://picsum.photos/10/6?image=${n * 5 + 10}${
              props.isWithColor ? '' : '&grayscale'
            }`"
            aspect-ratio="1"
            cover
          >
            <template v-slot:placeholder>
              <VRow align="center" class="fill-height ma-0" justify="center">
                <VProgressCircular
                  color="grey-lighten-5"
                  indeterminate
                ></VProgressCircular>
              </VRow>
            </template>
          </VImg>
        </VCard>
      </VCol>
    </VRow>
  </VCard>
</template>

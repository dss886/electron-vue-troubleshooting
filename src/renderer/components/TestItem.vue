<template>
    <div class="test-item-wrapper">
        <img 
            v-if="icon !== ''" 
            :src="'/' + icon"
            class="icon"
        >
    </div>
</template>

<script lang="ts" setup>
interface Props {
    icon: string;
    title: string;
    subtitle?: string;
}
withDefaults(defineProps<Props>(), {
    icon: "",
    title: "",
    subtitle: "",
});
</script>

<style scoped>
.test-item-wrapper {
    display: inline-block;
}
.icon {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}

.icon:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
</style>
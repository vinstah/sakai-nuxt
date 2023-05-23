<script setup="props" lang="ts">
import { defineAsyncComponent } from 'vue';

const router = useRouter();
const props = defineProps<{ module: string }>();

console.log('asd', props);
const modules = {
    incidents: 'HelloWorld'
};
if (props.module == 'incidents') {
    const moduleComponent = defineAsyncComponent(() => import('./Empty.vue'));
} else {
    router.push('/error');
}
</script>

<template>
    <h1>herere</h1>
    <component :is="moduleComponent" />
</template>

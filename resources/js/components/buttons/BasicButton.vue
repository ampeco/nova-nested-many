<template>
    <component
        :is="component"
        class="focus:outline-none focus:ring rounded text-sm font-bold whitespace-nowrap inline-flex items-center justify-center"
        :class="size === 'sm' ? 'h-8 px-2' : 'h-9 px-3'"
    >
        <slot />
    </component>
</template>
<script>
    export default {
        props: {
            component: {
                type: String,
                default: 'button',
            },
            size: {
                type: String,
                default: 'lg',
            },
        },
    };
</script>

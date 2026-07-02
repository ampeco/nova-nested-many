<template>
    <component
        :is="component"
        class="focus:outline-none focus:ring rounded text-sm inline-flex items-center justify-center"
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
        },
    };
</script>

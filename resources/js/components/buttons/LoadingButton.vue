<template>
    <component v-bind="{ size, align, ...$attrs }" :is="component" ref="button">
        <span class="inline-flex items-center" :class="{ invisible: processing || loading }">
            <slot />
        </span>

        <span
            v-if="processing || loading"
            class="absolute"
            style="top: 50%; left: 50%; transform: translate(-50%, -50%)"
        >
            <Loader class="text-white" width="32" />
        </span>
    </component>
</template>

<script>
    import DefaultButton from './DefaultButton.vue';

    export default {
        components: { DefaultButton },

        props: {
            size: {
                type: String,
                default: 'lg',
            },

            align: {
                type: String,
                default: 'center',
                validator: v => ['left', 'center'].includes(v),
            },

            loading: {
                type: Boolean,
                default: false,
            },

            processing: {
                type: Boolean,
                default: false,
            },

            component: {
                type: String,
                default: 'DefaultButton',
            },
        },

        methods: {
            focus() {
                this.$refs.button.focus();
            },
        },
    };
</script>

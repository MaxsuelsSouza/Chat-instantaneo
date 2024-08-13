<script>
export default {
    emits: ['inserir'],

    props: {
        outlined: {
            type: Boolean,
            default: false
        },

        label: {
            type: String,
            default: () => 'Inserir'
        },

        route: {
            type: Object,
            default: () => null
        },

        icone: {
            type: String,
            default: 'pi pi-plus'
        }
    },

    methods: {
        inserir() {
            if (this.route) {
                this.$router.push(this.route);
                return;
            }
            this.$emit('inserir');
        }
    }
};
</script>

<template>
    <Button :label="label" size="large" :icon="icone" :class="`text-base bg-blue-700`" @click="inserir()" />
</template>

<template>
    <checkbox-group
        v-model="checkList"
        v-bind="$attrs"
    >
        <checkbox
            v-for="(item, index) in enumOptions"
            :key="index"
            :label="item.value"
        >
            {{ item.label }}
        </checkbox>
    </checkbox-group>
</template>

<script>
export default {
    name: 'CheckboxesWidget',
    props: {
        value: {
            default: () => [],
            type: [Array]
        },
        enumOptions: {
            default: () => [],
            type: [Array]
        }
    },
    computed: {
        checkList: {
            get() {
                return this.value;
            },
            set(value) {
                this.$emit('input', value);
            }
        }
    }
};
</script>

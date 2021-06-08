<template>
    <div>
        <van-field 
        :label="label" 
        :type="type" 
        :placeholder="placeholder"
        :rule="rule"
        v-model="content"
        />
    </div>
</template>

<script>
export default {
    data() {
        return {
            content: ''
        }
    },
    props: ['label', 'type', 'placeholder', 'rule'],
    watch: {
        content() {
            this.handlerule()
        }
    },
    methods: {
        handlerule() {
            const rule = new RegExp(this.rule)
            if(rule.test(this.content)) {
                this.$emit('inputChange', this.content)
            }
        }
    }
}
</script>
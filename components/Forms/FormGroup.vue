<template>
    <div :class="formGroupClass">
        <label class="material-label" v-if="label">{{ label }}</label>
        <input :type="type"
               :name="name"
               :readonly="readonly"
               :datasrc="datasrc"
               :minlength="minlength"
               :maxlength="maxlength"
               :autocomplete="autocomplete"
                class="form-control outline-0"
               :class="{ [formControlClass]:formControlClass, 'is-invalid': form.errors.has(name) }"
               :placeholder="placeholder"
               :value="value"
               @blur="blur"
               @input="setData"/>

        <has-error :form="form" :field="name"></has-error>
    </div>
</template>
<script>
    export default {
        // props: ['msg','name','form_group_class','label','form','field','type'],
        props: {
            form: {
                required: true,
            },
            name: {
                type: String,
                required: true,
            },
            label: {
                type: String,
                required: false,
            },
            formGroupClass: {
                type: String,
                required: false,
            },
            formControlClass: {
                type: String,
                required: false,
            },
            type: {
                type: String,
                required: false,
                default: 'text',
            },
            readonly: {
                type: Boolean,
                required: false,
                default: false,
            },
            placeholder: {
                type: String,
                required: false,
            },
            datasrc: {
                required: false,
            },
            minlength: {
                required: false,
            },
            maxlength: {
                required: false,
            },
            autocomplete: {
                required: false,
                default: 'on',
            },
            value:{
                required: false,
            }
        },
        methods: {
            setData(event){
                this.$emit('v-model',event.target.value);
            },
            test(event){
                alert(event.target.value)
            },
            blur(event){
                this.$emit('blur',event);
            },
        }
    }
</script>
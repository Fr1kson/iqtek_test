<template>
    <el-input
        v-model="inputValue"
        @input="changeInput"
        placeholder="Введите имя или id пользователя"
        clearable
    />
</template>

<script lang="ts" setup>
import { ref } from 'vue';

const inputValue = ref<string>('');
const emit = defineEmits(['change']);

const changeInput = () => {
    emit('change', inputValue.value);
};
</script>

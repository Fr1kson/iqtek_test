<template>
    <el-popconfirm
        title="Вы уверены что хотите удалить запись?"
        @confirm="confirmEvent"
        confirm-button-text="Да"
        cancel-button-text="Нет"
    >
        <template #reference>
            <el-button link type="primary" size="small">Удалить</el-button>
        </template>
    </el-popconfirm>
</template>

<script setup lang="ts">
const confirmEvent = () => {
    console.log('confirm!');
};
</script>

<template>
    <div>
        <el-button type="primary" @click="dialogVisible = true">Добавить пользователя</el-button>
        <el-dialog v-model="dialogVisible" title="Введите имя пользователя" width="30%">
            <el-input v-model="nameValue" placeholder="Введите имя" clearable />
            <template #footer>
                <span class="dialog-footer">
                    <el-button @click="dialogVisible = false">Отмена</el-button>
                    <el-button type="primary" @click="saveUser">Добавить</el-button>
                </span>
            </template>
        </el-dialog>
    </div>
</template>

<script lang="ts" setup>
import { ref } from 'vue';

const dialogVisible = ref<boolean>(false);
const nameValue = ref<string>('');

const saveUser = () => {
    console.log(1);
};
</script>

<template>
    <div>
        <el-button link type="primary" @click="dialogVisible = true" size="small"
            >Редактировать</el-button
        >
        <el-dialog v-model="dialogVisible" title="Введите имя пользователя" width="30%">
            <el-input v-model="nameValue" placeholder="Введите имя" clearable />
            <template #footer>
                <span class="dialog-footer">
                    <el-button @click="dialogVisible = false">Отмена</el-button>
                    <el-button type="primary" @click="saveUser">Сохранить</el-button>
                </span>
            </template>
        </el-dialog>
    </div>
</template>

<script lang="ts" setup>
import { ref } from 'vue';
import type { UserModel } from '@/models/UserModel.js';

interface UserListProps {
    user: UserModel;
}

const props = defineProps<UserListProps>();
const dialogVisible = ref<boolean>(false);
let nameValue = ref<string>('');
nameValue.value = props.user.name;

const saveUser = () => {
    console.log(1);
};
</script>

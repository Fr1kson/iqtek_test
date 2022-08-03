<template>
    <el-table :data="tableData" border stripe empty-text="Нет данных">
        <el-table-column prop="id" label="id" width="80" />
        <el-table-column prop="name" label="Имя" />
        <el-table-column label="Действия" width="200">
            <template #default="item">
                <div class="btn-container">
                    <DeleteUserComponent />
                    <EditUserComponent :user="item.row" />
                </div>
            </template>
        </el-table-column>
    </el-table>
</template>

<script lang="ts" setup>
import type { UserModel } from '@/models/UserModel.js';
import { onUpdated, ref } from '@vue/runtime-dom';
import EditUserComponent from './EditUserComponent.vue';
import DeleteUserComponent from './DeleteUserComponent.vue';

interface UserListProps {
    name: string;
}

const props = defineProps<UserListProps>();
const tableData = ref<UserModel[]>([]);

onUpdated(() => {
    tableData.value.filter(
        (user: UserModel) => user.name.toLowerCase().indexOf(props.name.trim().toLowerCase()) > -1,
    );
});
</script>

<style scoped lang="scss">
.btn-container {
    display: flex;
}
</style>

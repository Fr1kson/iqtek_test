<template>
    <section class="appBar">
        <SearchComponent class="appBar__search" @change="changeInput" />
        <AddNewUserComponent />
    </section>
    <section>
        <UserListComponent :name="searchName" />
    </section>
</template>

<script lang="ts" setup>
import { ref } from 'vue';
import SearchComponent from './components/SearchComponent.vue';
import UserListComponent from './components/UserListComponent.vue';
import AddNewUserComponent from './components/AddNewUserComponent.vue';

const searchName = ref<string>('');

const changeInput = (name: string) => {
    searchName.value = name;
};
</script>

<style lang="scss" scoped>
.appBar {
    margin-bottom: 25px;
    display: flex;
    justify-content: space-between;

    &__search {
        margin-right: 15px;
    }
}
</style>

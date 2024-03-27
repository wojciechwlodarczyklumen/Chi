<template>
  <div class="-p--4">
    <h1>Chi Vue 3</h1>

    <chi-search-input @chiInput="filterItems"></chi-search-input>
    <chi-dropdown visible-items="3" retain-selection button="Dropdown">
      <a v-for="item in filteredItems" class="chi-dropdown__menu-item" slot="menu">{{ item }}</a>
    </chi-dropdown>
  
  
    <!-- <DataTableClientView />
    <DataTableServerView />
    <ExpansionPanelView />
    <PaginationView />
    <DrawerView />
    <TooltipView />
    <SearchInputView />
    <SaveViewView />
    <CheckboxView />
    <TransferListView /> -->
  </div>
</template>

<script lang="ts" setup>
import { ref } from 'vue';

const items = [
  'Item 1',  
  'Item 2',  
  'Item 3',  
  'Item 4',  
  'Item 5'
];

const filteredItems = ref([...items]);

const filterItems = ev => {
  filteredItems.value = items.filter(item  => item.toLowerCase().includes(ev.detail.toLowerCase()));
}



import CheckboxView from './views/CheckboxView.vue';
import DataTableClientView from './views/DataTable/ClientSide/DataTableClientView.vue';
import DataTableServerView from './views/DataTable/ServerSide/DataTableServerView.vue';
import DrawerView from './views/DrawerView.vue';
import ExpansionPanelView from './views/ExpansionPanelView.vue';
import PaginationView from './views/PaginationView.vue';
import SaveViewView from './views/SaveView.vue';
import SearchInputView from './views/SearchInputView.vue';
import TooltipView from './views/TooltipView.vue';
import TransferListView from './views/TransferList/TransferListView.vue';
</script>

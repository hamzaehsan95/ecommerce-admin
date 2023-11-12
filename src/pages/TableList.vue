<template>
  <div class="row">
    <div class="col-12">
      <div class="mb-3">
        <base-button type="primary" fill>Add Product</base-button>
      </div>

      <card :title="table1.title">
        <div class="table-responsive">
          <base-table
            :data="table1.data"
            :columns="table1.columns"
            thead-classes="text-primary"
          >
          </base-table>
        </div>
      </card>
    </div>
  </div>
</template>
<script>
import { BaseTable } from "@/components";
const tableColumns = ["Name", "Category", "Level"];
const tableData = [
  {
    id: 1,
    name: "Laptop",
    category: "Electronics",
    level: "20",
  },
  {
    id: 2,
    name: "Smartphone",
    category: "Electronics",
    level: "15",
  },
  {
    id: 3,
    name: "LED TV",
    category: "Electronics",
    level: "12",
  },
  {
    id: 4,
    name: "Men's Jeans",
    category: "Clothing",
    level: "30",
  },
  {
    id: 5,
    name: "Women's Shoes",
    category: "Footwear",
    level: "9",
  },
  {
    id: 6,
    name: "Coffee Maker",
    category: "Appliances",
    level: "8",
  },
  {
    id: 7,
    name: "Fitness Tracker",
    category: "Electronics",
    level: "2",
  },
  {
    id: 8,
    name: "Backpack",
    category: "Accessories",
    level: "22",
  },
  {
    id: 9,
    name: "Cookware Set",
    category: "Kitchen",
    level: "25",
  },
  {
    id: 10,
    name: "Desk Chair",
    category: "Furniture",
    level: "29",
  },
];

export default {
  components: {
    BaseTable,
  },
  data() {
    return {
      table1: {
        title: "Inventory",
        columns: [...tableColumns],
        data: [...tableData],
      },
    };
  },
};
</script>
<style></style>

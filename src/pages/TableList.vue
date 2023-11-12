<template>
  <div class="row">
    <div class="col-12">
      <div class="mb-3">
        <base-button fill type="primary" @click="addProductModalVisible = true">
          Add Product
        </base-button>
      </div>

      <modal
        :show.sync="addProductModalVisible"
        class=""
        id="addProductModal"
        :centered="false"
        :show-close="true"
      >
        <div>
          <div class="col-md-12">
            <input
              label="Name"
              placeholder="Name"
              v-model="product.name"
              type="text"
              class="text-dark form-control mt-3"
            />
          </div>
          <div class="col-md-12">
            <input
              label="Category"
              placeholder="Category"
              v-model="product.category"
              class="text-dark form-control mt-3"
            />
          </div>
          <div class="col-md-12">
            <input
              label="Level"
              placeholder="Level"
              v-model="product.level"
              class="text-dark form-control mt-3"
            />
          </div>

          <base-button
            fill
            type="primary"
            @click="addProduct()"
            class="ml-3 mt-3"
          >
            Add
          </base-button>
        </div>
      </modal>

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
import Modal from "@/components/Modal";
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
const initialProduct = {
  name: "",
  category: "",
  level: null,
};

export default {
  components: {
    BaseTable,
    Modal,
  },
  data() {
    return {
      addProductModalVisible: false,
      product: { ...initialProduct },
      table1: {
        title: "Inventory",
        columns: [...tableColumns],
        data: [...tableData],
      },
    };
  },
  methods: {
    addProduct() {
      this.table1 = {
        ...this.table1,
        data: [
          ...tableData,
          {
            id: this.table1.data.length,
            name: this.product.name,
            category: this.product.category,
            level: this.product.level,
          },
        ],
      };

      this.product = { ...initialProduct };

      this.addProductModalVisible = false;
    },
  },
};
</script>
<style></style>

<template>
  <div>
    <v-data-table
      :headers="headers"
      :items="Data.data"
      :page.sync="page"
      :items-per-page="Data.per_page"
      hide-default-footer
      class="elevation-1"
    >
      <!-- Avatars -->
      <template v-slot:item.avatar="{ item }">
        <v-avatar>
          <img :src="item.avatar" />
        </v-avatar>
      </template>
    </v-data-table>
    <!-- pagination -->
    <div class="text-center pt-2">
      <v-pagination v-model="page" :length="Data.total_pages"> </v-pagination>
    </div>
  </div>
</template>
<script>
export default {
  async fetch() {
    this.Data = await fetch(`https://reqres.in/api/users?page=1`).then((res) =>
      res.json()
    );
  },
  data() {
    return {
      hasan: 5,
      Data: [],
      page: 1,
      pageCount: [],
      itemsPerPage: 10,
      headers: [
        {
          text: "Last Name",
          align: "start",
          sortable: true,
          value: "last_name",
        },
        { text: "First Name", value: "first_name" },
        { text: "Email", value: "email" },
        { text: "Avatar", value: "avatar" },
      ],
    };
  },
  watch: {
    async page() {
      console.log(this.page);
      this.Data = await fetch(
        `https://reqres.in/api/users?page=${this.page}`
      ).then((res) => res.json());
    },
  },
};
</script>
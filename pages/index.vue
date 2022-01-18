<template>
  <div class="custom-grid h-full gap-6">
    <aside
      class="p-4 border-2 border-dashed border-black rounded-md bg-gray-200 overflow-auto"
    >
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Molestiae
      voluptatum labore aperiam vero sit dolores debitis, id eius quasi aut non
      voluptatibus vel mollitia dolorum sequi officiis a repellat fuga? Lorem
      ipsum dolor sit amet consectetur adipisicing elit. Quos, velit iste?
      Molestiae corporis commodi adipisci, nemo ratione eaque quasi quos omnis,
      laudantium voluptates soluta maxime deleniti quibusdam fugiat eveniet
      dignissimos. Lorem ipsum dolor sit, amet consectetur adipisicing elit.
      Culpa quos, optio expedita omnis dolorum natus accusantium est, accusamus
      eum earum fuga similique cupiditate distinctio officiis magnam architecto
      ad repellat excepturi.
    </p>
    </aside>
    <section
      class="border-2 border-dashed border-black rounded-md overflow-auto bg-gray-200"
    >
      <S2Table
        :headers="headers"
        :data-source="users"
      />
    </section>
  </div>
</template>

<script>
const REQUEST_URL = 'https://s2grupo-b4529-default-rtdb.europe-west1.firebasedatabase.app/users.json';

export default {
  name: 'IndexPage',
  data: () => ({
    headers: [
      {
        label: 'Name',
        key: 'name'
      },
      {
        label: 'Available',
        key: 'available'
      },
      {
        label: 'Age',
        key: 'age'
      },
      {
        label: 'Last login',
        key: 'last_login'
      }
    ],
    users: []
  }),
  created() {
    this.loadUsers();
  },
  methods: {
    async loadUsers() {
      try{
        this.users = await this.$axios.$get(REQUEST_URL);
      }catch (e) {
        console.error(e); // eslint-disable-line no-console
      }
    }
  }
}
</script>

<style scoped>
.custom-grid {
  display: grid;
  grid-template-columns: 20rem minmax(0, 1fr);
}
</style>

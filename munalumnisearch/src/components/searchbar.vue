<template>
  <div id="searchbar2">
    <h1 style="font-size: 80px; margin: -20px">Continue the Legacy</h1>
    <h3>Connect with HMMUN Alumni</h3>
    <div class="search-wrapper panel-heading col-sm-12">
      <input
        id="search"
        type="search"
        pattern=".*\S.*"
        required
        v-model="search"
      />
      <span class="caret"></span>
      <br />
    </div>
    <table>
      <thead>
        <tr>
          <!-- <th>------</th> -->
          <th>Name</th>
          <th>Position</th>
          <th>LinkedIn</th>
          <th>Full Profile</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="product in filteredProducts" :key="product.id">
          <!-- <td data-title="id">{{ product.id }}</td> -->
          <!-- <td><img v-bind:src="product.image" /></td> -->
          <td data-title="name">{{ product.name }}</td>
          <td data-title="position">{{ product.position }}</td>
          <td data-title="LinkedIn">{{ product.LinkedIn }}</td>
          <td class="select">
            <div class="button" @click="isDetailsOpen = !isDetailsOpen">
              Select
            </div>
          </td>
        </tr>
      </tbody>
    </table>

    <Details :isDetailsOpen="isDetailsOpen" />
  </div>
</template>

<script>
import Details from "@/components/details.vue";
export default {
  data() {
    return {
      products: [
        {
          id: 1,
          image:
            "https://pbs.twimg.com/profile_images/1138463345277898753/D6SrWJPH_400x400.jpg",
          name: "Arman Kumar",
          position: "Incoming Summer Analyst",
          LinkedIn: "arman-kumar",
        },
        {
          id: 2,
          image:
            "https://pbs.twimg.com/profile_images/1138463345277898753/D6SrWJPH_400x400.jpg",
          name: "Connor Morris",
          position: "Research Assistant",
          LinkedIn: "connor-morris-123",
        },
        {
          id: 3,
          image:
            "https://pbs.twimg.com/profile_images/1138463345277898753/D6SrWJPH_400x400.jpg",
          name: "Shant Amerkanian",
          position: "Polticial Policy Intern",
          LinkedIn: "shant438",
        },
        {
          id: 4,
          image:
            "https://pbs.twimg.com/profile_images/1138463345277898753/D6SrWJPH_400x400.jpg",
          name: "Julia Hornstein",
          position: "Incoming Summer Analyst",
          LinkedIn: "julia-horn",
        },
        {
          id: 5,
          image:
            "https://pbs.twimg.com/profile_images/1138463345277898753/D6SrWJPH_400x400.jpg",
          name: "Garo Amerkanian",
          position: "Sector Head - Consumer Staples",
          LinkedIn: "garo-amerkanian-529976215",
        },
        {
          id: 6,
          image:
            "https://pbs.twimg.com/profile_images/1138463345277898753/D6SrWJPH_400x400.jpg",
          name: "Avi Amerkanian",
          position: "Sector Head - Consumer Staples",
          LinkedIn: "garo-amerkanian-529976215",
        },
      ],
      search: "",
      isDetailsOpen: false,
    };
  },
  components: {
    Details,
  },
  computed: {
    filteredProducts() {
      return this.products.filter((p) => {
        return p.name.toLowerCase().indexOf(this.search.toLowerCase()) != -1;
      });
    },
  },
  methods: {
    toggleDetails() {
      this.isDetailsOpen = !this.isDetailsOpen;
    },
  },
};
</script>

<style lang="scss">
:root {
  --rad: 0.7rem;
  --dur: 0.3s;
  --color-dark: #2f2f2f;
  --color-light: #fff;
  --color-brand: #57bd84;
  --font-fam: "Lato", sans-serif;
  --height: 5rem;
  --btn-width: 6rem;
  --bez: cubic-bezier(0, 0, 0.43, 1.49);
}

* {
  box-sizing: border-box;
}

html.open,
body.open {
  height: 100%;
  overflow: hidden;
}

html {
  padding: 40px;
  font-size: 62.5%;
}

img {
  width: 51px;
  height: 51px;
  margin-right: -40px;
}

body {
  padding: 20px;
  background-color: #5bb9b8;
  line-height: 1.6;
  -webkit-font-smoothing: antialiased;
  color: #fff;
  font-size: 1.6rem;
  font-family: "Lato", sans-serif;
}

p {
  text-align: center;
  margin: 20px 0 60px;
}

main {
  background-color: #2c3845;
}

h1 {
  text-align: center;
  font-weight: 300;
}

table {
  display: block;
}

tr,
td,
tbody,
tfoot {
  display: block;
}

thead {
  display: none;
}

tr {
  padding-bottom: 10px;
  margin: 100px;
}

td {
  padding: 10px;
  text-align: center;
}

tr.spaceUnder > td {
  padding-bottom: 1em;
}
td:before {
  content: attr(data-title);
  color: #7a91aa;
  text-transform: uppercase;
  font-size: 1.4rem;
  padding-right: 10px;
  display: block;
}

table {
  width: 100%;
  border-collapse: collapse;
}

th {
  text-align: left;
  font-weight: 700;
}

thead th {
  background-color: #202932;
  color: #fff;
  border: 1px solid #202932;
}

tfoot th {
  display: block;
  padding: 10px;
  text-align: center;
  color: #b8c4d2;
}

@media (min-width: 460px) {
  td {
    text-align: left;
  }
  td:before {
    display: inline-block;
    text-align: right;
    width: 140px;
  }

  .select {
    padding-left: 160px;
  }
}
@media (min-width: 720px) {
  table {
    display: table;
  }

  tr {
    display: table-row;
  }

  td,
  th {
    display: table-cell;
  }

  tbody {
    display: table-row-group;
  }

  thead {
    display: table-header-group;
  }

  tfoot {
    display: table-footer-group;
  }

  td {
    border: 3px solid #28333f;
  }
  td:before {
    display: none;
  }

  td,
  th {
    padding: 10px;
  }

  tr:nth-child(2n + 1) td {
    background-color: #242e39;
  }

  tr:nth-child(2n) td {
    background-color: #1e262f;
  }

  tfoot th {
    display: table-cell;
  }

  .select {
    padding: 10px;
  }
}

// Setup
body {
  background: var(--color-dark);
  align-items: center;
  justify-content: center;
  min-height: 100vh;
}
html {
  box-sizing: border-box;
  height: 100%;
  font-size: 10px;
}

// Main styles
form {
  position: relative;
  width: 30rem;
  background: var(--color-brand);
  border-radius: var(--rad);
}
input,
button {
  height: var(--height);
  font-family: var(--font-fam);
  border: 0;
  color: var(--color-dark);
  font-size: 1.8rem;
}
input[type="search"] {
  // <-- shold probably remove this for better accessibility, adding for demo aesthetics for now.
  width: 100%;
  background: var(--color-light);
  padding: 0 1.6rem;
  margin-bottom: 25px;
  border-radius: var(--rad);
  appearance: none; //for iOS input[type="search"] roundedness issue. border-radius alone doesn't work

  z-index: 1;
}
</style>

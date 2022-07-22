<!-- Personal fac Content-->
<template>
  <b-container class="bv-example-row">
  <b-row md="6">
    <!--Input Form -->
    <b-col class="column">
    <div>
    <b-form @submit="onSubmit" @reset="onReset" v-if="show">
    <h6> Add a new administrator </h6>
        <b-form-input
          id="input-1"
          class="inputfield"
          v-model="form.email"
          placeholder="First Name"
          required
        ></b-form-input>

        <b-form-input
          id="input-2"
          class="inputfield"
          v-model="form.name"
          placeholder="Last Name"
          required
        ></b-form-input>

        <b-form-input
          id="input-2"
          class="inputfield"
          v-model="form.name"
          placeholder="Email Address"
          required
        ></b-form-input>

        <b-form-input
          id="input-2"
          class="inputfield"
          v-model="form.name"
          placeholder="Password"
          required
        ></b-form-input>

      <b-button type="submit">Submit</b-button>
    </b-form>
  </div>
    </b-col>
    <!--Content Table-->
    <b-col>
      <h6> Administrator Management </h6>
       <table>
        <thead>
          <tr>
            <th> ID </th>
            <th> 
              <i 
              class="fas fa-chevron-down">
              </i> 
              Name 
              </th>
            <th> 
              <i 
              class="fas fa-chevron-down">
              </i>
              Status
              </th>
            <th> 
              <i 
              class="fas fa-chevron-down">
              </i> Action </th>            
          </tr>
        </thead>
    <tbody>
    <tr>
      <td> A001 <br>
      <p> 03/29/2022</p> 
      </td>
      <td> Josh Goodwin <br>
      <p>josh_good@pac.com</p>
      </td>
      <td>
        <i 
        class="fas fa-check">
        </i> 
        Enabled 
        </td>
      <td>
        <i 
        class="fas fa-ellipsis-h" 
        id="iconcircle">
        </i>
      </td>
    </tr>
    <tr class="data">
      <td> A002  <br>
      <p> 03/27/2022 </p> 
      </td>
      <td> Administrator3 <br>
      <p>admin3@pac.com</p>
      </td>
      <td>
        <i 
        class="fa-solid fa-bell-slash">
        </i> 
        Disabled
        </td>
      <td>
        <i class="fas fa-ellipsis-h" 
        id="iconcircle">
        </i>
        </td>
    </tr>
  </tbody>
</table>
<!-- Pagnition Navigation-->
  <div class="overflow-auto">
    <b-pagination-nav 
    :link-gen="linkGen" 
    :number-of-pages="10" 
    use-router>
    </b-pagination-nav>
  </div>
    </b-col>
  </b-row>
</b-container>
</template>

<script>
  export default {
     name: 'Form-admin',
    data() {
      return {
        form: {
          email: '',
          name: '',
          food: null,
          checked: []
        },
        show: true,
        methods: {
      linkGen(pageNum) {
        return pageNum === 1 ? '?' : `?page=${pageNum}`
      }
    }
      }
    },
    methods: {
      onSubmit(event) {
        event.preventDefault()
        alert(JSON.stringify(this.form))
      },
      onReset(event) {
        event.preventDefault()
        // Reset our form values
        this.form.email = ''
        this.form.name = ''
        this.form.food = null
        this.form.checked = []
        // Trick to reset/clear native browser form validation state
        this.show = false
        this.$nextTick(() => {
          this.show = true
        })
      }
    }
  }
</script>


<style>
@import url("https://fonts.googleapis.com/css?family=Roboto+Condensed");

.bv-example-row{
  top: 50px;
  bottom: 0px;
  left: 3%;
  box-sizing: border-box;
  position: relative;
  width: 560px;
  background: #FFFFFF;
}

.inputfield{
  margin: 20px;
  box-shadow: 0 2px 2px 0 rgba(0, 0, 0, 0.2), 0 3px 10px 0 rgba(0, 0, 0, 0.19);
  padding: 60px;
}

button.btn.btn-secondary{
  background-color: #B22234;
  width: 180px;
  height: 50px;
  box-shadow: 0px 8px 16px rgba(0, 0, 0, 0.25);
  border-radius: 8px;
  flex: none;
  order: 0;
  flex-grow: 0;
  margin-left:35%;
}

h6{
  font-family: "Roboto", sans-serif;
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  font-feature-settings: 'pnum' on, 'lnum' on;
  color: #333333;
  flex: none;
  order: 0;
  flex-grow: 0;
  margin: 15px;
}

table {
  border-collapse: collapse;
  border-spacing: 0;
  width: 100%;
}

th {
  text-align: left;
  padding: 8px;
}

th {
  text-align: left;
  padding: 8px;
  font-family: "Roboto", sans-serif;
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 19px;
  color: #8793A3;
}

td{
  font-family: 'Open Sans', "Roboto", sans-serif;
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 22px;
  color: #333333;

}

td p {
  font-weight: 400;
  font-size: 12px;
  line-height: 16px;
  color: #8793A3;
}

svg#iconcircle.svg-inline--fa.fa-ellipsis{
  border: 1px solid black;
  border-radius: 50%;
  padding: 10px;
}

div.row{
  border: 1px solid rgba(135, 147, 163, 0.25);
  border-radius: 16px
}

div.col{
  padding-left: 20px;
  padding-right: 40px;
  padding-top: 30px;
  padding-bottom: 140px;
}

div.column.col{
  border-right: 1px solid rgba(135, 147, 163, 0.25);
  height: 500px;
}

div.overflow-auto{
  margin-top: 100px;
  padding-left: 250px;
}

@media (max-width: 900px) {
    div.bv-example-row.container{
      left: 50px;
}
    div.overflow-auto{
      margin-top: 100px;
      padding-left: 100px;
}
}
@media (max-width: 600px) {
    div.bv-example-row.container{
      left: 60px;
      max-width: 350px;
}

    table {
      width: 200px;
    }

    div.overflow-auto{
      margin-top: 100px;
      padding-left: 60px;
    }
}
</style>
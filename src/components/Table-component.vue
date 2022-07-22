<template>
  <div>
    <b-container 
    class="bv-example-row" >
    <b-row lg="4">
      <!--Search Bar-->
        <b-col>
            <div>
                <b-input-group 
                size="sm">
                <b-form-input 
                type="search" 
                placeholder="Search Users">
                </b-form-input>
                <b-input-group-prepend 
                is-text>
                  <b-icon 
                  icon="search">
                  </b-icon>
                </b-input-group-prepend>
              </b-input-group>
                </div>
        </b-col>
        <!--Dropdow menu-->
        <b-col 
        class="drop">
            <b-dropdown 
            text="Date" 
            variant="outline-primary" 
            class="m-2">
                <b-dropdown-item href="#">Action</b-dropdown-item>
                <b-dropdown-item href="#">Another action</b-dropdown-item>
                <b-dropdown-item href="#">Something else here</b-dropdown-item>
            </b-dropdown>
        </b-col>
        <!--Dropdow menu-->
        <b-col>
                <b-dropdown 
                text="User Type" 
                variant="outline-primary" 
                class="m-2" >
                <b-dropdown-item href="#">Action</b-dropdown-item>
                <b-dropdown-item href="#">Another action</b-dropdown-item>
                <b-dropdown-item href="#">Something else here</b-dropdown-item>
                </b-dropdown>
        </b-col>
        <!-- Reset button-->
        <b-col>
            <div>
                <b-button>Reset Filter</b-button>
            </div>
        </b-col>
        <!--Add New User -->
        <b-col>
            <div>
                <b-button pill variant="warning">Create User</b-button>
            </div>
        </b-col>
     </b-row>
     <!--Table Content-->
    <template>
  <div>
    <b-table 
    small 
    :fields="fields" 
    :items="items" 
    responsive="sm" 
    borderless >
      <!--Check status -->
      <template #cell(ustatus)="data">
      <b-icon-bookmark-check-fill
        variant="success"
        v-if="data.item.ustatus === 'Enabled'"
        >
        </b-icon-bookmark-check-fill>  
         <b-icon-bookmark-x-fill
          variant="danger"
         v-else
        ></b-icon-bookmark-x-fill>
      </template>

      <!-- User Actions -->
      <template #cell(actions)="data">
        <b-row>
          <b-col cols="7">
            <b-list-group></b-list-group>
            <b-icon-pencil-fill
              class="action-item"
              variant="primary"
              @click="getRowData(data.item.id)"
              >
              </b-icon-pencil-fill>
              </b-col>

              <b-col cols="1">
                <b-icon-trash-fill
                  class="action-item"
                  variant="danger"
                  @click="showDeleteModal(data.item.id)"
                  >
                  </b-icon-trash-fill>
                </b-col>
              </b-row>
            </template>

      <!-- View More action-->
      <template #cell(vmore)="">
        <b-icon-chevron-compact-right-fill 
        aria-hidden="true">
        </b-icon-chevron-compact-right-fill>
      </template>
    </b-table>
  </div>
</template>
</b-container>
  </div>
</template>

   
<script>
export default {
    name: 'Table-component',
     data() {
       return {
      //Table feilds
        fields: [
         {
           key: 'ID',
           label: 'ID',
           sortable: true,
         },
         {
           key: 'uname',
           label: 'User Name',
         },
         {
           key: 'cno',
           label: 'Contact No.',
         },
         {
           key: 'joined',
           label: 'Joined',
           sortable: true
         },
         {
           key: 'utype',
           label: 'User Type'
         },
         {
           key: 'ustatus',
           label: ''
         },
         {
           key: 'actions',
           label: 'Actions'
         },
         {
           key: 'vmore', 
           label: 'View More'
         },
        ],
        items: [
          {
            ID: '1', 
            uname: 'John Doe',
            cno: '0714163338',
            joined: '01-04-2021',
            utype: 'Collection',
            ustatus: 'Enabled',
            actions: 'fa-search',
            vmore: ''
          },
          {
            ID: '2',
            uname: 'John Doe',
            cno: '0714163338',
            joined: '01-04-2021',
            utype: 'Collection',
            ustatus: 'Disabled',
            actions: 'fa-search',
            vmore: ''
          }
        ],
      }
    }
}
</script>
    
<style>
    nav {
        list-style: none;
    }
    .dropdown.b-dropdown.m-2.btn-group{
        width: 150px;
    }

    button.btn.btn-secondary{
        margin-top: 10px;
    }

    /* button.btn.btn-warning.rounded-pill{
        position: relative;
        left : 100px;
        margin-top:10px;
        padding-right: 25px;
    } */

    .bv-example-row{
       top: 50px;
      bottom: 0px;
      left: 3%;
      box-sizing: border-box;
      position: relative;
      width: 560px;
      background: rgb(240, 239, 239);
      padding: 20px;
      margin-top:10px;
    }
    @media(max-screen: 500px){
      div.bv-example-row.container{
          margin-left: 150px;
          position: relative;
    }
    }
</style>
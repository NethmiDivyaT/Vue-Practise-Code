<template>
  <div>
  <b-nav 
  vertical class="w-25"
  >
    <b-nav-item >
        <i 
        id="icon" 
        class="fa-solid fa-table-cells-large fa-2x"
        >
        </i>
    </b-nav-item>
    <b-nav-item>
        <i 
        id="icon" 
        class="fa-solid fa-users fa-2x"
        >
        </i>
    </b-nav-item>
    <b-nav-item>
        <i 
        id="icon" 
        class="fa-solid fa-video fa-2x"
        >
        </i>
    </b-nav-item>
    <b-nav-item>
        <i 
        id="icon" 
        class="fas fa-ad fa-2x"
        >
        </i>
    </b-nav-item>
    <b-nav-item>
        <i 
        id="icon" 
        class="fas fa-users-cog fa-2x"
        >
        </i>
    </b-nav-item>
    <b-nav-item>
        <i 
        id="icon" 
        class="fas fa-folder-open fa-2x"
        >
        </i>
    </b-nav-item>
    <b-nav-item>
        <i 
        id="icon" 
        class="fas fa-info-circle fa-2x"
        >
        </i>
    </b-nav-item>
    <b-nav-item>
        <i 
        id="icon" 
        class="fas fa-cog fa-2x "
        >
        </i>
    </b-nav-item>
  </b-nav>
</div>
</template>

<script>
export default {
    name: 'side_Bar'
}
</script>

<style scoped>
.w-25{
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
    padding-left: 15px;
    padding-top:20px;
    padding-bottom: 35px;
    max-width: 100px;
    position: absolute;
    line-height: 55px;
    background: rgb(29, 84, 235);
  }
svg{
  color: white;
}

svg:hover{
  color: #B22234;
}
 i{
    line-height: 10px;
 }


</style>
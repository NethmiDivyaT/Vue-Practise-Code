<template>
<b-navbar 
variant="faded" 
type="light" 
class="Navigation"
>
    <b-navbar-brand 
    href="#" 
    class="admin"
    >
      <b-img 
      :src="require('../assets/logo.png')" 
      fluid 
      alt="Responsive image"
      >
      </b-img>
      User Management
      <span 
      class="ct"
      > 
        <i 
        class="fas fa-user-circle"
        >
        </i>
      Master Admin 
      </span>
    </b-navbar-brand>
  </b-navbar>
</template>

<script>
export default {
  name: 'NavBar',
  data() {
    return {
      
    }
  }
}
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css?family=Roboto+Condensed");
  .admin{
    font-family: "Roboto", sans-serif;
    text-decoration-color: black;
    font-weight: 500;
    font-size: 22px;
    line-height: 26px;
    display: flex;
    align-items: center;
    letter-spacing: 0.3px;
  }

  .ct{
    position: absolute;
    float:left;
    padding-left: 10px;
    padding-right: 10px;
    font-family: "Roboto", sans-serif;
    font-style: normal;
    font-weight: 300;
    font-size: 16px;
    align-items: flex-end;
    right: 3%;
    letter-spacing: 0.2px;
  }

  svg.svg-inline--fa.fa-circle-user{
    color : blue;
  }

  .Navigation{
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  }
</style>>

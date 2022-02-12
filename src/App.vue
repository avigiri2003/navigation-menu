<template>
  <div id="app">
    <!--<button  
        v-for="(section, index) in sections" 
        :key='index' 
        @click="selectSection(index)"
        :class="[selectedIndex === index ? 'selected' : 'unselected']"
      >
      {{section}}
    </button>-->

    <nav>
      <a href="#" 
        v-for="(section, index) in sections" 
        :key='index'
        @click="selectSection(index)"
        :class="[selectedIndex === index ? 'selected' : 'unselected']"
      >
      {{section}}
      </a>
    </nav>

    <p>
      You are in the <b>{{ selectedSection }} </b> section of this portal.
    </p>
  </div>
</template>

<script>

export default {
  name: 'app',
  components: {
  },
  data(){
    return{
      selectedSection: '',
      sections: ["Home", "Services", "Offers", "My Bookings", "My profile"],
      selectedIndex: null
    }
  },
  methods:{
    selectSection(index){
      this.selectedSection = this.sections[index];
      this.selectedIndex = index;
    }
  },
  created(){
    this.selectedSection = this.sections[0];
    this.selectedIndex = 0;
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
nav{
    display:inline-block;
    /*margin:60px auto 45px;*/
    background-color:#5597b4;
    box-shadow:0 1px 1px #ccc;
    border-radius:2px;
}
nav a{
    display:inline-block;
    padding: 18px 30px;
    /*color:#fff !important;*/
    font-weight:bold;
    font-size:16px;
    text-decoration:none !important;
    line-height:1;
    /*text-transform: uppercase;*/
    background-color:transparent;
}
nav a:first-child{
    border-radius:2px 0 0 2px;
}
nav a:last-child{
    border-radius:0 2px 2px 0;
}
p{
    font-size:20px;
    font-weight:bold;
    color:#7d9098;
}

p b{
    /*color:#ffffff;*/
    display:inline-block;
    padding:5px 10px;
    background-color:#c4d7e0;
    border-radius:2px;
    /*text-transform:uppercase;*/
    font-size:18px;
}
.unselected{
  background: lightblue;
  border:none;
}
.selected{
  background:lightpink;
  border:none;
}
</style>

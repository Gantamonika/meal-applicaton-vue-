<template>

  <div class="search" >
    <br />
    <!-- <input type="text" v-model="search" placeholder="Search Meal.."/> -->
    <input
      type="text"
      @keyup.enter="getMeal"
      v-model="search"
      placeholder="Search Meal.."
    />
    
    <button @click="getMeal" >Search</button>
    
    
     
    <br />
  </div>
 
  <br />

  <div v-if="meals!==null">
    <div class="item" v-for="item in meals" v-bind:key="item.idMeal">
      <div class="car-mar">
        <div class="row blk">
          <div class="row" style="margin-top: 3%">
            <div class="col-sm-6">
              <div class="Mcard-body">
                <img
                  :src="item.strMealThumb"
                  alt="Trulli"
                  style="margin:auto"
                  height="433"
                /><br />
                <b>{{ item.strMeal }}</b>
              </div>
            </div>
            <div class="col-sm-3 d-flex">
              <div class="Mcard-body ing">
                <h5 class="Mcard-title">
                  <br />
                  <b>About</b>
                  <br />
                  <br />
                  <li>Meal Id: {{ item.idMeal }}</li>
                  <li>Name: {{ item.strMeal }}</li>
                  <li>Category: {{ item.strCategory }}</li>
                  <li>Location: {{ item.strArea }}</li>
                </h5>
                <br />
              </div>
            </div>


            <div class="col-sm-3 d-flex">
              <div class="Mcard-body wd">
                <h5 class="Mcard-title">
                  <b>Ingredients</b><br /><br />
                  <li>{{ item.strIngredient1 }}, {{ item.strMeasure1 }}</li>
                  <li>{{ item.strIngredient2 }}, {{ item.strMeasure2 }}</li>
                  <li>{{ item.strIngredient3 }}, {{ item.strMeasure3 }}</li>
                  <li>{{ item.strIngredient4 }}, {{ item.strMeasure4 }}</li>
                  <li>{{ item.strIngredient5 }}, {{ item.strMeasure5 }}</li>
                  <li>{{ item.strIngredient6 }}, {{ item.strMeasure6 }}</li>
                  <li>{{ item.strIngredient7 }}, {{ item.strMeasure7 }}</li>
                  <li>{{ item.strIngredient8 }}, {{ item.strMeasure8 }}</li>
                  <li>{{ item.strIngredient9 }}, {{ item.strMeasure9 }}</li>
                </h5>
              </div>
            </div>
          </div>
          <div style="padding-right:40px " >
          <iframe height="420" width="100%" :src="'https://www.youtube.com/embed/' + item.strYoutube.substring(32)"></iframe>
          </div>
          <div class="row">
            <div class="col-sm-12" style="padding:4px">
              <div class="Mcard-body">
                <h5 class="Mcard-title">
                  <b>Recipe</b>
                  <br />
                  <br />
                  <h5>{{ item.strInstructions }}</h5>
                </h5>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>

  <div class="err" v-else>
    <h1>  Oops..!!! <br/>
      Recipe is not available, try for New one.
    </h1>
    </div>

</template>
<script>
import Axios from "axios";
export default {
  name: "Search",

  data() {
    return {
      meals: [],
      loading: false,
      err: "",
      strMeal: "",
      youtubeVid: [],
      searchClick:1,
    };
  },

  methods: {
    getMeal() {
      this.searchClick--;
      this.loading = true;
      console.log(this.strMeal);
      Axios.get(
        "https://www.themealdb.com/api/json/v1/1/search.php?s=" + this.search
      )
        .then((response) => {
          console.log(response.data);
          this.meals = response.data.meals;  
          this.loading = false;

        })
        .catch((err) => {
          this.loading = false;
          this.err = "Something went Wrong";
          console.log("Error", err);
        });
    },
  },
};
</script>
<style>

td {
  border: 1px solid black;
  border-collapse: collapse;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  margin-top: 0px;
}
th {
  text-align: center;
  padding-top: 20px;
}
.car-mar {
  border: 2px solid white;

  margin-left: 1%;
}
td {
  padding-bottom: 20px;
  padding-left: 30px;
  padding-right: 40px;
  text-align: initial;
}
.wd {
  width: 100%;
}
p {
  text-align: center;
  width: 100%;
  padding-bottom: 30%;
}
.ing {
  margin-left: 15% !important;
}

h2 {
  text-align: center;
}
h5 {
  color: black;
}
.row {
  text-align: center;
}

img {
  border-radius: 12px;
}
.blk {
  background-color: black;
  border-radius: 10px;
  width: 100.6%;
}
.Mcard-title {
  text-align: center;
}

.container {
  position: relative;
  width: 100%;
  max-width: 400px;
}

.container img {
  width: 100%;
  height: auto;
}

.container .btn {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);
  background-color: #555;
  color: white;
  font-size: 16px;
  padding: 12px 24px;
  border: none;
  cursor: pointer;
  border-radius: 5px;
  text-align: center;
}

.container .btn:hover {
  background-color: black;
}
.search {
  text-align: center;
  font-family: "Brush Script MT", cursive;
}
li {
  color: black;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: left;
}.err{
  transition-delay: 5ms !important;
}
</style>

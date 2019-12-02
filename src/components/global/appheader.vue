<template>
  <div class="container">
    <div class="row">
      <div class="col-12 text-center">
        <div class="c">
          <b-navbar toggleable="md" type="dark" variant="info">
            <b-navbar-brand href="#" :key="arr.words" v-for="arr in array">
              {{ arr.words }} </b-navbar-brand
            >|
              <img
              v-if="array[0].done==false"
              class="eg"
              src="../../../img/eg.jpg"
            />
              <img
              v-if="array[0].eg== false"
              class="eg"
              src="../../../img/eg.jpg"
            />
             <img
              v-else-if="array[0].ks== false"
              class="eg"
              src="../../../img/su.png"
            />
             <img
              v-else-if="array[0].UA== true"
              class="eg"
              src="../../../img/am.png"
            />
             
            <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
            <b-collapse id="nav-collapse" is-nav>
              <b-navbar-nav>
                <span class="ship" :v-if="moveeg" id="ship" :key="arr.words" v-for="arr in array">ship to {{arr.words}}</span>
                <b-nav-item-dropdown  text=""  left class="change image shipnav">
                  <b-dropdown-item
                    class="change"
                    @click="testcontaryEgy"
                    href="#"
                  >
                    {{ egypt }}
                    <img class="eg" src="../../../img/eg.jpg" alt />
                  </b-dropdown-item>
                  <b-dropdown-item
                    class="change"
                    @click="testcontaryKsa"
                    href="#"
                  >
                    {{ Ksa }}
                    <img class="eg ks" src="../../../img/su.png" alt />
                    <div class="su"></div>
                  </b-dropdown-item>
                  <b-dropdown-item
                    class="change"
                    @click="testcontaryUAe"
                    href="#"
                  >
                    {{ UAE }}
                    <img class="eg ua" src="../../../img/am.png" alt />
                    <div class="em"></div>
                  </b-dropdown-item>
                </b-nav-item-dropdown>
                
              </b-navbar-nav>
              <!-- Right aligned nav items -->
              <b-navbar-nav class="ml-auto">
                <b-navbar-brand href="#" :key="arr.words" v-for="arr in array">
                  <i class="fas fa-car-side"></i> FREE DELIVERY - OVER
                  <span class="words">{{ arr.words }}</span>
                </b-navbar-brand>

                <!-- Using 'button-content' slot -->
                <b-navbar-brand href="#">
                  <i class="far fa-check-circle"></i> FREE & EASY RETURNS
                </b-navbar-brand>
                <!--best deal-->
                <b-navbar-brand href="#">
                  <i class="far fa-bell"></i>BEST DEALS
                </b-navbar-brand>
              </b-navbar-nav>
            </b-collapse>
          </b-navbar>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
//import func from '../../../vue-temp/vue-editor-bridge';
export default {
  name: "appheader",
  data: function() {
    return {
      array: [{ words: "egypt", done: false }],
      egypt: "egypt",
      Ksa: "Ksa",
      UAE: "UAE",
    };
  },
  methods: {
    testcontaryEgy: function() {
      this.array.push({ words: this.egypt, done: false });
      if (this.array.length > 1) {
        this.array.length = "";
        this.array.push({ words: this.egypt, done: true, eg: false }); 
      }
    },
    testcontaryKsa: function() {
      this.array.push({ words: this.Ksa, done: false  });
      if (this.array.length > 1) {
        this.array.length = "";
        this.array.push({ words: this.Ksa, done: true , ks:false  });
      }
    },
    testcontaryUAe: function() {
      this.array.push({ words: this.UAE, done: false });
      if (this.array.length > 1) {
        this.array.length = "";
        this.array.push({ words: this.UAE, done: true, UA:true });
      }
    },
    moveeg: function() {
     this.array.forEach(e => {
       if(e.words == 'egypt'){
         let move = document.getElementById('ship');
         move.style.right="80rem";
       }
     });
    }
  }
};
</script>
<style lang="scss" scoped>
* {
  font-family: "Cormorant Garamond", serif;
  font-family: "Volkhov", serif;
  font-size: 20px;
  .eg {
    width: 25px;
    height: 25px;
  }

  .container {
    max-width: 100%;
    background-color: #feee00 !important;
    position: relative;
    .ship{
      position:absolute;
      bottom:.9rem;
      right:70rem
    }
    .shipnav{
      position:absolute;
      top:50%;
      right:91.2%;
    }
    .col-12 {
      padding: 0 !important;
      margin: 0 10% !important;
      max-width: 70%;
      .bg-info {
        background-color: #feee00 !important;
      }
      .words {
        font-size: 20px;
        margin-left: 5px;
        margin-right: 5px;
        color: rgb(221, 99, 243);
      }
      a {
        color: black !important;
      }
      .ml-auto {
        a {
          font-size: 15px;
        }
      }
      .change,
      span {
        color: black;
      }
      .image {
        .eg {
         width: 25px;
         height: 25px;
         margin-left: 40px;
        }
        .ks {
          margin-left: 58px;
        }
        .ua {
          margin-left: 50px;
        }
      }
      .nav-item .b-nav-dropdown .dropdown .change,
      .dropdown-menu .dropdown-menu-right {
        color: red;
      }
    }
  }
}
</style>

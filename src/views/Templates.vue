<template>
  <div class="templates"> 
    
    
    <v-container class="my-5 widthsite">
        
        
        <h1 class="subheading grey--text temcenter">Templates</h1>
      <v-layout row justify-start class="mb-3">
        <v-btn small flat color="grey" class="marginized" @click="sort('title')">
            <v-icon
            left
            small
          >
            mdi-folder
          </v-icon>
          <v-icon
            v-if="sortBy === 'title'"
            small
          >
            mdi-sort-{{ sortDirection }}
          </v-icon>
          <span class="caption text-lowercase">sort by name</span>
        </v-btn>
        <v-btn small flat class="" @click="sort('price')">
           <v-icon
            left
            small
          >
            mdi-cash
          </v-icon>
          <v-icon
            v-if="sortBy === 'price'"
            small
            
          >
            mdi-sort-{{ sortDirection }}
          </v-icon>
          <span class="caption text-lowercase">sort by price</span>
        </v-btn>
      </v-layout>
      
      <v-card flat v-for="project in projects" :key="project.title">
        <v-layout row wrap :class="`hovereff pa-3 project ${project.status}`">
          <v-flex xs12 md4>
           
            <v-img
              v-bind:src="project.image"
              height="170"
              width="500"
              class="grey darken-4"
            ></v-img>
            <v-card-title class="title"> {{ project.title }} </v-card-title>
         
            
          </v-flex>
          
          <v-flex xs6 sm4 md2 class="marginized4" >
            <div class="caption grey--text">Price</div>
            <div>{{ project.price }}</div>
          </v-flex>
          <v-flex xs6 sm4 md2>
            <div class="caption grey--text">Features</div>
            <div><v-icon class="marginized3" small color="green">{{ project.icon }}</v-icon>{{ project.features }}</div>
            <div><v-icon class="marginized3" small color="green">{{ project.icon1 }}</v-icon>{{ project.features1 }}</div>
            <div><v-icon class="marginized3" small color="green">{{ project.icon2 }}</v-icon>{{ project.features2 }}</div>
            <div><v-icon class="marginized3" small color="green">{{ project.icon3 }}</v-icon>{{ project.features3 }}</div>
          </v-flex>
          <v-flex xs2 sm4 md2>
            <div class="right marginized5">
              <v-btn depressed class="marginized6 white--text" color="#673AB7 ">Preview</v-btn>
              <v-btn depressed color="green" class="marginized6 white--text">Purchase</v-btn>
            </div>
          </v-flex>
        </v-layout>
        <v-divider></v-divider>
      </v-card>

    </v-container>
   
  </div>
</template>

<script>
import { VBreakpoint } from 'vue-breakpoint-component'
export default {
  data() {
    return {
     components: {
      VBreakpoint
     },
      projects: [
        { image: 'https://i.imgur.com/foznWf5.png', title: 'Gradient Theme', price: '$20', icon: 'mdi-check-bold',icon1: 'mdi-check-bold', status: 'complete', features: 'Fully Coded Website',features1: 'TOS & FAQ Pages'  ,   content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
        { image: 'https://ak1.picdn.net/shutterstock/videos/1038250241/thumb/9.jpg', title: 'Dark Theme', price: '$15', icon: 'mdi-check-bold',icon1: 'mdi-check-bold',status: 'complete', features: 'Fully Coded Website',features1: 'TOS & FAQ Pages'  ,   content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
        { image: 'https://ak1.picdn.net/shutterstock/videos/1038250241/thumb/9.jpg', title: 'Nulled Theme', price: '$25', icon: 'mdi-check-bold',icon1: 'mdi-check-bold', status: 'complete', features: 'Fully Coded Website',features1: 'TOS & FAQ Pages'  ,   content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
        { image: 'https://ak1.picdn.net/shutterstock/videos/1038250241/thumb/9.jpg', title: 'Simple Theme', price: '$10', icon: 'mdi-check-bold',icon1: '', status: 'complete', features: 'Fully Coded Website'  ,features1: ''  ,   content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
      ]
    }
  },
  methods: {
    sort (prop) {
      if (prop === this.sortBy) {
        // reverse sort order if requested sort is the same as current
        this.sortDirection = this.sortDirection === 'ascending' ? 'descending' : 'ascending';
      } else {
        // otherwise sort order is ascending
        this.sortDirection = 'ascending';
      }
      this.sortBy = prop;
      this.projects.sort((aa, bb) => {
        if (aa[prop] === bb[prop]) {
          
          if (aa.price.unix() < bb.price.unix()) {
            return -1;
          } else if (aa.price.unix() > bb.price.unix()) {
            return 1;
          } else {
            return 0;
          }
        } else if (aa[prop] < bb[prop]) {
          return this.sortDirection === 'ascending' ? -1 : 1;
        } else if (aa[prop] > bb[prop]) {
          return this.sortDirection === 'ascending' ? 1 : -1;
        }
      });
    }
  }
};
</script>

<style>
.project.complete{
  border-left: 4px solid #673AB7;
}
.project.ongoing{
  border-left: 4px solid #ffaa2c;
}
.project.overdue{
  border-left: 4px solid #f83e70;
}
.v-chip.complete{
  background: #3cd1c2;
}
.v-chip.ongoing{
  background: #ffaa2c;
}
.v-chip.overdue{
  background: #f83e70;
}

.temcenter{
    margin-bottom: 30px;
}

.marginized{
    margin-right: 15px;
}

.marginized2{
    margin-left: 15px;
}
.marginized3{
    padding-bottom: 3px;
    padding-right: 3px;
}
.marginized4{
    margin-left: 20px;
    padding-right: 3px;
}

.marginized5{
    margin-left: 100px;
    
}

.marginized6{
    width: 190%;;
    margin-top: 20px;
}

.widthsite{
    width: 75%;
}

.hovereff:hover {
    color:#673AB7;
    background-color: #EDE7F6;

}
</style>
<template>
  <div>
    <div class="contanier-fluid">
      <div class="m-4">
        <div class="container text-center">
          <div class="col-sm-6">
            <h2 class="text-left"> Shape </h2>
            <div class="row row-cols-auto">
              <div v-for="shape in shapes">
              <div class="col-sm-2" style="cursor: pointer;">
                <div @click.prevent="selColor(shape.namesofshape, shape.name)">{{ shape.namesofshape }}</div>
              </div>
              </div>
            </div>
            </div>
            <br/>
            
          <div class="col-sm-6">
            <h2 class="text-left">Color </h2>
            <div class="row row-cols-auto">
            
              <div v-for="shape in shapes">
              <div class="col-sm-2" style="cursor: pointer;"  >
                <div v-bind:class="getColor(shape.name)"></div>
              </div>
              </div>
            </div>
            </div>
          </div>
    </div>
  </div>
    <div class="container text-center">
      <div class="m-4">
        <div class="row">
          <div v-for="shape in shapes">
              <div class="col-sm-4">
                  <div class="card" style="width: 18rem;">
                      <div class="card-body" v-show="shape.visible">
                      <div v-bind:class="getColor(shape.name)" v-show="shape.visible"></div>
                      </div>
                    </div>
                </div>
            </div>
            
          </div> 
        </div>
      </div>
      </div>
</template>
<style>
.dot {
  height: 25px;
  width: 25px;
  background-color: #ff0000;
  border-radius: 50%;
  display: inline-block;
}
.dot2 {
  height: 25px;
  width: 25px;
  background-color: #198753;
  border-radius: 50%;
  display: inline-block;
}
.dot3 {
  height: 25px;
  width: 25px;
  background-color: #0056ba;
  border-radius: 50%;
  display: inline-block;
}
.dot4{
  height: 25px;
  width: 25px;
  background-color: #fdf906;
  border-radius: 50%;
  display: inline-block;
}
.dot5 {
  height: 25px;
  width: 25px;
  background-color: #515800;
  border-radius: 50%;
  display: inline-block;
}
.dot6 {
  height: 25px;
  width: 25px;
  background-color: #000000;
  border-radius: 50%;
  display: inline-block;
}
.content{
  width: 5%;
  height: 40px;
  display: inline-block;
}
</style>
<script>
//import Header from '../components/Header.vue';
export default {
    name: "IndexPage",
  //  components: { Header }
  data() {
  
  return {
    shapes: [
      {
        name:'red',
        smallshape: 'red',
        namesofshape:'cube',
        visible: true,
       },    
       {
        name:'Green',
        smallshape: 'Green',
        namesofshape:'box',
        visible: true,
       },   
       {
        name:'blue',
        smallshape:'blue',
        namesofshape:'triangle',
        visible: true,
       } ,   
       {
        name:'yellow',
        smallshape: 'yellow', 
        namesofshape:'round',
        visible: true,
       },   
       {
        name:'orange',
        smallshape:'orange',
        namesofshape:'circle',
        visible: true,
       } ,  
       {
        name:'black',
        smallshape: 'black',
        namesofshape:'rectangle',
        visible: true,
       }    
      ],
      color:{
              'red':'dot',
              'Green':'dot2',
              'blue':'dot3',
              'yellow':'dot4',
              'orange':'dot5',
              'black':'dot6',
            }
        }
      },
      methods: {
          getColor(name) {
           // console.log(name);
            return this.color[name]
          },
          getshape(namesofshape) {
            return this.color[namesofshape]
          },
          filteredP: function (name) {
            var self = name;
           // console.log(self);
            return this.shapes.filter(function (name) {
                return console.log(name.namesofshape  === name);
            });
          },
          selColor(shapename, color) {
            this.shapes.forEach((e) => {
              if (e.name == color) {
              //  alert(e.name + ' = ' + color);
                e.visible = true;
              } else {
                e.visible = false;
              }
            }) 
          }
        }
       }
    
    

  
</script>

<template>
  <v-carousel v-model="model" 
   
        height="100%"
        :continuous="false"
    >
      
    <v-carousel-item
      v-for="(pic, i) in picture"
      :key="i"  
    >
      <v-sheet
     :color="pic.color"
      height="100%"
     
      >
        <v-row
          class="fill-height"
          align="center"
          justify="center"
        >
          <div class="display-2">
            <v-card color ="#7E57C2" elevation="24" loading="" shaped>
                
                            <v-list-item>
                <v-list-item-content >
                    
                    
                      <h5 align="center">  Карточка пользователя:</h5> 
                      
                
                    <v-list-item>
                        <div>
                            <div>
                             <p> </p>
                            <p> Имя: <font size="7" color = "#37474F">{{pic.name}} </font></p>                        
                            <p>Фамилия: <font size="7" color = "#37474F"> {{pic.surname}}</font></p>
                            <p>Возраст: <font size="7" color = "#37474F"> {{pic.age}}</font></p>
                            

                            </div>
                        </div>
                    </v-list-item>
                </v-list-item-content>
                
    <v-list-item-avatar size="200" >
                  
                    <v-img
                    :src="pic.pic" 
                    >
                    </v-img>
                </v-list-item-avatar>

      
            
                  
            </v-list-item>
        <v-card-actions>
             

                    <v-spacer></v-spacer>

                    <v-btn
                        icon
                        @click="Show = !Show"
                    >
                    <v-icon>{{ Show ? 'mdi-chevron-up' : 'mdi-chevron-down'  }} </v-icon>
                    
                    </v-btn>
                    
            </v-card-actions>
            
            </v-card>   
<transition name="fade">
    <card v-if="Show"> 
       
        <v-card color = "white" class="card"> 
           <h6> Отзыв:   <font class="font_2" size="5" italic color = "Black">{{pic.text}} </font></h6>
        </v-card>
    
    </card>
  </transition>
          </div>
        </v-row>
      </v-sheet>

    </v-carousel-item>
  </v-carousel>
</template>

<script>
  export default {
    data: () => ({
      model: 0,
      colors: [
        'primary',
        'secondary',
        'yellow darken-2',
        'red',
        'orange',
      ],
      Show:false,
      
      picture:[ {
          pic: "https://cs4.pikabu.ru/post_img/big/2014/03/19/10/1395243232_1089834701.jpg",
          color: '#2E8B57',
          surname:"Karavash",
          name:"Max",
          age:"15",
          text:"  очень красивый сайт"
          
      },
      {
           pic: "https://cdn.fishki.net/upload/post/2017/10/08/2399690/tn/pembroke-welsh-corgi-vancouver-1.jpg",
          color: '#006633',
          surname:"Arhipov",
          name:"Artur",
          age:"35",
          text:"могло быть и лучше"
      },
      {

 pic: "https://img4.goodfon.ru/wallpaper/nbig/8/70/shchenok-sobachka-boke-kappa-mylnyi-puzyr.jpg",
          color: '#009B77',
          surname:"Udincev",
          name:"Gleb",
          age:"21",
          text:"красивая картинка"
      },
      {
 pic: "https://bigpicture.ru/wp-content/uploads/2012/10/doggy031-800x613.jpg",
          color: '#287233',
          surname:"Voropaev",
          name:"Sergey",
          age:"17",
          text:"не хватает информации"
      },
      {
 pic: "https://bipbap.ru/wp-content/uploads/2017/10/foto2-640x477.jpg ",
          color: '#507D2A',
          surname:"Milk",
          name:"Masha",
          age:"18",
          text:"удобная навигация"
      },
      ]
    }),
  }
</script>

<style>
 .text
 {
     font-size:x-large
 }
 .fade-enter-active, .fade-leave-active {
  transition: opacity .5s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active до версии 2.1.8 */ {
  opacity: 0;
}
.card
{
   background: white;
   color: aliceblue;
}
.font_2
{
    font-style: italic;
    font-weight: 100
}
h6 {
    color: black;
    font-weight: bolder
}
h5 {
    color: #353831;
}
p {
    color: #242323;
}
</style>
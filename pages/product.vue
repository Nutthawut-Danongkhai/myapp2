<template>
  <Head>
    <Title>DEW NAJA SHOP</Title>
  </Head>
  <div v-if="pending">
    Loading ...
  </div>
  <div v-else>
    <div class="container d-flex justify-content-center">
      <form class="w-50 my-5 ">
        <div class="input-group flex-nowrap w-100">
          <input type="text" class="form-control shadow-none" placeholder="Search" aria-label="Username"
            aria-describedby="addon-wrapping">
          <button type="submit" class="btn btn-success"><i class="bi bi-search"></i></button>
        </div>

      </form>
    </div>
    <div class="container">
      <div class="grid mb-5">
        <div class="content" v-for="product in Products" :key="product.id">
          <div class="item w-100 h-100 rounded-1" style="border: 0.1px solid black;">
            <div class="content p-3 " style="height: 90%;">
              <img class="priceimg w-50" :src="product.image">
              <h6 class="text-center mt-3">{{ product.title }}</h6>
              <button type="button" class="btn btn-info mt-5 text-white" @click="togglevisible" >Info</button>
              <div v-show="isvisible">
                <h5>game information :</h5>
                <p>{{ product.gameInfo }}</p>
              <p>studio : {{ product.studio }}</p>
              <p>price : {{ product.price }}</p>
              </div>
            </div>

          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>



export default {
  data() {
    return {
      Products: [
        {
          id: "1",
          title: "Plants Vs. Zombies: Garden Warfare 2",
          price : "",
          image: "https://upload.wikimedia.org/wikipedia/en/e/e5/PvZ_Garden_Warfare_2.jpg",
          studio: "PopCap Games",
          gameInfo : "Plants vs. Zombies: Garden Warfare 2 is a 2016 Third Person Shooter video game developed by PopCap Games and published by Electronic Arts. It was released for PlayStation 4, Windows and Xbox One. It is the sequel to Plants vs. Zombies: Garden Warfare. Garden Warfare The game was released in February 2016."
        },
        {
          id: "2",
          title: "Plants Vs. Zombies: Garden Warfare",
          price : "",
          image: "https://upload.wikimedia.org/wikipedia/en/5/5d/Garden_Warfare_cover_art.png",
          studio: "PopCap Games",
          gameInfo : "Plants vs. Zombies: Garden Warfare is a third-person shooter video game. and multiplayer tower defense It is the third game in the Plans series."
  
        },
        {
          id: "3",
          title: "Team Fortress 2",
          price : "",
          image: "https://upload.wikimedia.org/wikipedia/en/5/5f/Tf2_standalonebox.jpg",
          studio: "Valve Corporation",
          gameInfo : "Team Fortress 2 is a first-person shooter and multiplayer video game developed by Valve. Corporation that by the game was developed from Team Fortress Classic, which was developed from the Quake game mod again."
        },
        {
          id: "4",
          title: "Left 4 Dead 2",
          price : "",
          image: "https://upload.wikimedia.org/wikipedia/en/b/ba/Left4Dead2.jpg",
          studio: "Valve Corporation",
          gameInfo : "Left 4 Dead 2 is a 2009 first-person shooter developed and published by Valve. The sequel to Turtle Rock Studios' Left 4 Dead and the second game in the Left 4 Dead series was released for Microsoft Windows and Xbox 360. in November 2009, Mac OS X in October 2010 and Linux in July 2013."
        },

      ],
      isvisible: false,
    }
  },
  methods:{
    togglevisible() {
            this.isvisible = !this.isvisible
        }
  }

}
</script>

<style scope>
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  column-gap: 16px;
  row-gap: 30px;
}

.item:hover {
  box-shadow: -2px 5px 32px -11px rgba(0, 0, 0, 0.86);
}

.item {
  transition: 0.2s;
}

.priceimg {
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 50%;
}
</style>
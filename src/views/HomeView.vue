<template>
  <div id="mainElement" class="px-3 position-relative">
    <img :src="escenas[activeItem].img" />

    <div class="position-absolute">
      <ButtonsComp @new="movePosition"></ButtonsComp>

      <EscenaComp
        v-for="(item, index) in escenas"
        :key="index"
        :myEscena="item.txt"
        :myimg="item.img"
        :class="[{ active: activeItem === index }, masClases]"
      >
      </EscenaComp>
    </div>
  </div>
</template>

<script>
import ButtonsComp from "@/components/ButtonsComp";
import EscenaComp from "@/components/EscenaComp";

export default {
  components: {
    ButtonsComp,
    EscenaComp,
  },
  data() {
    return {
      escenas: [
        {
          txt: "El nostre heroi estava surant per l'espai sideral quan a la llunyania va albirar una nau espacial",
          img: "/statics/1.jpg",
        },
        {
          txt: "Sentia curiositat per l'interior de la nau i es va posar a inspeccionar-la. Va arribar a una sala amb dues portes.",
          img: "/statics/2.jpg",
        },
        {
          txt: "L'heroi va decidir travessar la porta que el portava a casa",
          img: "/statics/3.jpg",
        },
        {
          txt: "Mentrestant, altres heroes no van tenir tanta sort en la seva elecció ...",
          img: "/statics/4.jpg",
        },
      ],
      activeItem: 0,
      masClases:
        "my-4 border border-3 border-dark rounded-pill heigthCustom d-flex  justify-content-center align-items-center",
    };
  },
  methods: {
    movePosition: function (option) {
      switch (option) {
        case 1:
          if (this.activeItem == 0) this.activeItem = this.escenas.length - 1;
          else this.activeItem--;
          break;
        case 2:
          if (this.activeItem === this.escenas.length - 1) this.activeItem = 0;
          else this.activeItem++;
          break;
        default:
      }
    },
  },
};
</script>
<style scoped>
.active {
  background-color: pink;
}
#mainElement > div {
  width: 100%;
}

#mainElement {
  height: 80vh;
}

#mainElement img {
  width: 100%;
}
div > div {
  top: 0;
}
</style>

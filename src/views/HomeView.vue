<template>
  <div>
    <div id="greetings">
      <div class="hey">Hey there!</div>
      <div class="title">안녕하세요.</div>
      <div classs="title">톡톡 튀는 아이디어와</div>
      <div class="title">정확한 근거로 고객의 니즈를 파악하는 서비스 기획자</div>
      <div class="title">김세민입니다!</div>
    </div>
  </div>
  <div>
    <div id="skills">
      <div class="header">Technical Skills</div>
      <v-container>
        <v-row align-content="center">
          <v-col cols="3"><v-img src="../assets/skills/html5.png" class="skillItem"></v-img></v-col>
          <v-col cols="3"><v-img src="../assets/skills/css.png" class="skillItem"></v-img></v-col>
          <v-col cols="3"><v-img src="../assets/skills/javascript.png" class="skillItem"></v-img></v-col>
          <v-col cols="3"><v-img src="../assets/skills/wordpress.png" class="skillItem"></v-img></v-col>
        </v-row>
        <v-row align-content="center">
          <v-col cols="3"><v-img src="../assets/skills/java.png" class="skillItem"></v-img></v-col>
          <v-col cols="3"><v-img src="../assets/skills/mysql.png" class="skillItem"></v-img></v-col>
          <v-col cols="3"><v-img src="../assets/skills/AdobeXD.png" class="skillItem"></v-img></v-col>
          <v-col cols="3"><v-img src="../assets/skills/figma.png" class="skillItem"></v-img></v-col>
        </v-row>
      </v-container>
    </div>
  </div>

  <div>
    <div id="timeline">
      <div class="header">Timeline</div>
      <v-container>
        <v-row>
          <v-col cols="3" class="timeline-col">
            <v-img class="timeline-item" src="../assets/2020.png" data-aos="fade-up"></v-img>
          </v-col>
          <v-col cols="9" data-aos="fade-up" class="info">
            <v-row class="info-header">명지전문대 정보통신공학과</v-row>
            <v-row>전문학사 졸 (2023.02)</v-row>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="3" class="timeline-col"><v-img class="timeline-item" src="../assets/2022.png"
              data-aos="fade-up"></v-img></v-col>
          <v-col cols="9" data-aos="fade-up" class="info">
            <v-row class="info-header">하계 글로벌 진로취업연수</v-row>
            <v-row>- International Mentor Group Australia</v-row>
            <v-row>- Samsung SDS Australia</v-row>
            <v-row>- 2022.07 수료</v-row>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="3" class="timeline-col"><v-img class="timeline-item" src="../assets/2023.png"
              data-aos="fade-up"></v-img>
          </v-col>
          <v-col cols="9" data-aos="fade-up" class="info">
            <v-row class="info-header">명지전문대 정보통신공학과 전공심화 과정</v-row>
            <v-row>신입학 (2023.02)</v-row>
          </v-col>
        </v-row>
      </v-container>
    </div>
  </div>

  <div id="portfolio">
    <div class="header">Portfolio</div>
    <div class="cap">썸네일을 클릭해보세요!</div>
    <div class="list">
      <v-img class="item" src='../assets/kimjangtalk.png' cover @click="movePage('/kimjangtalk-businessmodel')"></v-img>
      <v-img class="item" src='../assets/report.png' cover @click="movePage('/business-plan')"></v-img>
      <v-img class="item" src='../assets/GreenEarth.png' cover @click="movePage('/green-earth')"></v-img>
      <v-img class="item" src='../assets/RestInPet.png' cover @click="movePage('/rest-in-pet')"></v-img>
    </div>
  </div>

  <div id="contact">
    <div class="header">Contact</div>
    <v-row>
      <v-col class="contact"><v-icon icon="mdi-phone"></v-icon><span> +82 010-9259-6758</span></v-col>
      <v-col class="contact"><v-icon icon="mdi-email-outline"></v-icon><span> seminik62@gmail.com</span></v-col>
      <v-col class="contact"><v-icon icon="mdi-github"></v-icon><a href="https://github.com/SeminKiim">Click
          Here!</a></v-col>
    </v-row>

  </div>
</template>

<script>
import { defineComponent } from 'vue';

// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from 'swiper/vue';

// Import Swiper styles
import 'swiper/css';

import aos from 'aos'

export default defineComponent({
  name: 'HomeView',

  components: {
    Swiper,
    SwiperSlide,
  },

  setup() {
    const onSwiper = (swiper) => {
      console.log(swiper);
    };
    const onSlideChange = () => {
      console.log('slide change');
    };
    return {
      onSwiper,
      onSlideChange,
    };
  },

  mounted() {
    aos.init();
  },

  methods: {
    movePage(path) {
      this.$router.push(path)
    }
  }
});
</script>

<style lang="less">
#greetings {
  height: 100vh;
  color: #6b4d38;
  font-size: 3rem;
  background-color: #f7f2f0;
  padding: 12%;
  font-weight: bold;

  .hey {
    font-size: 2.5em;
    text-align: center;
    margin-bottom: 50px;
    font-weight: bolder;
  }
}

#skills {
  color: #f7f2f0;
  font-size: 1.3rem;
  background-color: #6b4d38;
  padding: 10%;
  flex-grow: 0;

  .skillItem {
    width: 10vw;
    margin: 30px;
  }
}

#timeline {
  color: #6b4d38;
  font-size: 1.3rem;
  background-color: #f7f2f0;
  padding: 10%;

  .timeline-col {
    padding: 0;
  }

  .info {
    padding: 11%;

    .info-header {
      font-size: 1.5em;
    }
  }
}

#portfolio {
  color: #f7f2f0;
  font-size: 1.3rem;
  background-color: #6b4d38;
  text-align: center;
  padding: 10%;

  .list {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    grid-gap: 10px;
    margin-top: 50px;

    .item {
      width: 100%;
      background-position: center center;
      background-size: cover;
      border-radius: 5px;
      //비율 1:1
      aspect-ratio: 16/9;
    }
  }

  .cap {
    color: #DDDDEE;
  }
}

#contact {
  color: #6b4d38;
  font-size: 1.3rem;
  background-color: #f7f2f0;
  padding: 10%;

  .contact {
    text-align: center;
  }
}

.header {
  text-align: center;
  font-size: 3.2rem;
  margin-bottom: 50px;

}
</style>
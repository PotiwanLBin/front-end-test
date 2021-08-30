<template>
  <div class="d-flex">
    <!-- loginbar -->
    <div style="width: 100%">
      <div class="loginbar d-flex mx-auto" style="width: 70%">
        <v-row align="center" justify="center">
          <v-spacer></v-spacer>
          <v-btn icon><v-icon>mdi-account </v-icon> </v-btn>
          <span class="mr-5">ลงชื่อเข้าใช้</span>
        </v-row>
      </div>

      <div class="hidden-xs-only">
        <v-bottom-navigation
          class="navbar"
          :value="value"
          color="yellow"
          dark
          height="75px"
        >
          <v-toolbar-items class="hidden-xs-only" style="width: 70%">
            <div>
              <v-img src="logo.png" />
            </div>
            <v-spacer></v-spacer>
            <v-btn><span>หน้าหลัก</span></v-btn>
            <v-btn><span>องค์ความรู้</span></v-btn>
            <v-btn><span>ข่าวสาร</span></v-btn>
            <v-btn><span>แวดวง ศกอ.</span></v-btn>
            <v-btn><span>ถาม-ตอบ</span></v-btn>
            <v-btn><span>ติดต่อเรา</span> </v-btn>
            <v-btn icon><v-icon>mdi-magnify</v-icon> </v-btn>
          </v-toolbar-items>
        </v-bottom-navigation>
      </div>
      <div
        class="item-wrapper p-2 d-flex flex-column mx-auto"
        style="width: 70%"
      >
        <v-carousel hide-delimiters>
          <v-carousel-item
            v-for="(item, i) in items"
            :key="i"
            :src="item.src"
            reverse-transition="fade-transition"
            transition="fade-transition"
          >
            <v-row
              class="tb title fill-height ml-0"
              align="center"
              justify="center"
              >{{ item.title }}</v-row
            >
          </v-carousel-item>
        </v-carousel>
      </div>

      <div class="ads d-flex flex-column" dark>
        <span style="color: white" class="mx-auto mt-5 mb-2"
          >คุณสามารถลงทะเบียนสมาชิก เพื่อใช้งานระบบ
        </span>
        <v-btn class="mx-auto mb-2" rounded color="rgb(4, 90, 4)" dark>
          เข้าใช้งาน / สมาชิก
        </v-btn>
      </div>

      <div
        class="item-wrapper p-2 d-flex flex-column mx-auto"
        style="width: 70%"
      >
        <div class="d-flex pt-5 pr-5">
          <v-icon color="rgb(4, 90, 4)">mdi-rss</v-icon>
          <span class="color-text mr-auto">องค์ความรู้</span>
        </div>

        <hr class="solid" />
        <div>
          <v-row class="pt-5">
            <v-col v-for="item in items2" :key="item.id" cols="12" md="3">
              <v-card outlined>
                <v-img
                  class="white--text align-end"
                  height="200px"
                  :src="item.src"
                >
                </v-img>
                <v-card-title>{{ item.title }}</v-card-title>

                <v-card-text class="text--primary">
                  <div>{{ item.description }}</div>
                </v-card-text>

                <v-card-subtitle
                  ><v-icon>mdi-tag</v-icon>{{ item.subtitle }}</v-card-subtitle
                >
              </v-card>
            </v-col>
          </v-row>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.loginbar {
  height: 30px;
  background-color: rgb(255, 255, 255);
}
.navbar {
  background-color: rgb(4, 90, 4);
}
.tb {
  color: white;
  background: rgba(0, 0, 0, 0.2);
  height: 50px;
  width: 100%;
  padding: 0px;
  position: absolute;
  bottom: 0%;
}

.ads {
  height: 100px;
  background-color: black;
}
.color-text {
  color: rgb(4, 90, 4);
  font-size: 24px;
}
.box {
  height: 50px;
  width: 100px;
}

.item-wrapper {
  height: 500px;
}
hr.solid {
  border-top: 3px solid rgb(4, 90, 4);
}

.item {
  height: 200px;
  width: 200px;
  padding: 20px;
  background-color: pink;
  background-image: url("https://picsum.photos/200/300");
}
</style>

<script>
export default {
  data() {
    return {
      items: [
        {
          src: "img1.png",
          title: "รายการเศรษฐกิจเพื่อประชาชน",
        },
        {
          src: "img2.png",
          title: "รายการเศรษฐกิจเพื่อประชาชน",
        },
        {
          src: "img3.png",
          title: "รายการเศรษฐกิจเพื่อประชาชน",
        },
      ],

      items2: [
        {
          id: 1,
          title: "ข้าวไทย? ชาวนาไทย ทำอย่างไรจะยั่งยืน",
          subtitle: "พืชเกษตร",
          description:
            "บริหารจัดการสินค้าการเกษตรห่วงโช่ ณ สำนักงานเศรษฐกิจการเกษตร",
          src: "news2.jpg",
        },
        {
          id: 2,
          title: "ข้าวไทย? ชาวนาไทย ทำอย่างไรจะยั่งยืน",
          subtitle: "พืชเกษตร",
          description:
            "บริหารจัดการสินค้าการเกษตรห่วงโช่ ณ สำนักงานเศรษฐกิจการเกษตร",
          src: "news3.jpg",
        },
        {
          id: 3,
          title: "ข้าวไทย? ชาวนาไทย ทำอย่างไรจะยั่งยืน",
          subtitle: "พืชเกษตร",
          description:
            "บริหารจัดการสินค้าการเกษตรห่วงโช่ ณ สำนักงานเศรษฐกิจการเกษตร",
          src: "news2.jpg",
        },
        {
          id: 4,
          title: "ข้าวไทย? ชาวนาไทย ทำอย่างไรจะยั่งยืน",
          subtitle: "พืชเกษตร",
          description:
            "บริหารจัดการสินค้าการเกษตรห่วงโช่ ณ สำนักงานเศรษฐกิจการเกษตร",
          src: "news3.jpg",
        },
      ],
    };
  },
};
</script>
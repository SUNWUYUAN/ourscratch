<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <img src="https://cdn.wuyuan.dev/img/scratch-logo.svg"> <span class="mr-2"> </span><span class="mr-2"> </span>
      <v-btn href="https://wuyuan.dev/ourscratch-gui" target="_blank" text>
        <span class="mr-2">创作</span>
      </v-btn>
      <v-btn href="" target="_blank" text>
        <span class="mr-2">发现</span>

      </v-btn>
      <v-btn href="https://ourscratch.wuyuan.dev/about" target="_blank" text>
        <span class="mr-2">关于</span>

      </v-btn>
      <v-spacer></v-spacer>

      <v-btn href="https://github.com/sunwuyuan/ourscratch" target="_blank" text>
        <span class="mr-2">获取您的论坛</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>


    <v-main>
      <template>
        <v-carousel cycle height="400" hide-delimiter-background show-arrows-on-hover v-ripple>
          <v-carousel-item v-for="(slide, i) in slides" :key="i">
            <v-sheet :color="colors[i]" height="100%">
              <v-row class="fill-height" align="center" justify="center">
                <div class="text-h2" style="color:#ffffff">
                  {{ slide }}
                </div>
              </v-row>
            </v-sheet>
          </v-carousel-item>
        </v-carousel>
      </template> <template>
        <v-row justify="center">

          <v-dialog v-model="dialog" fullscreen hide-overlay transition="dialog-bottom-transition">
            <template v-slot:activator="{ on, attrs }">
              <v-container>
                <v-row v-bind="attrs" v-on="on">
                  <v-col v-for="card in cards" :key="card.title" :sm="card.flex">
                    <v-col>
                      <v-card v-ripple min-height="150"
                        @click="ProjectSrc = card.link, ProjectTitle = card.title, ProjectName = card.name, walineurl = 'https://hjdsfakfhsa.wuyuan.dev/' + card.title">
                        <v-img :src="card.src" class="white--text align-end"
                          gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.2)" height="auto">
                          <v-card-title></v-card-title>
                        </v-img>

                        <v-card-actions>
                          <v-text v-text="card.title" class="subtitle-1"></v-text>


                          <v-spacer></v-spacer>



                          <v-img lazy-src="https://img.wuyuan.dev/logo.png" max-height="30" max-width="30"
                            src="https://img.wuyuan.dev/logo.png"></v-img>
                          <v-text v-text="card.name" class="subtitle-2"></v-text>
                        </v-card-actions>
                      </v-card>
                    </v-col>

                  </v-col>
                </v-row>

              </v-container>
            </template>
            <v-card>
              <v-toolbar dark color="primary">
                <v-btn icon dark @click="dialog = false">
                  <v-icon>mdi-close</v-icon>
                </v-btn>
                <v-toolbar-title>作品</v-toolbar-title>
                <v-spacer></v-spacer>
                <v-toolbar-items>


                </v-toolbar-items>
              </v-toolbar>
              <template>

                <v-row align="center" justify="space-around">

                  <v-spacer></v-spacer>
                  <iframe v-bind:src="ProjectSrc" allowtransparency="true" width="500" height="450" frameborder="0"
                    scrolling="no" allowfullscreen>
                  </iframe>


                  <v-card class="mx-auto" min-width="344">

                    <v-card-text>
                      <div>scratch3作品</div>
                      <p class="text-h4 text--primary">
                        {{ ProjectTitle }}
                      </p>
                      <p>作者</p>
                      <div class="text--primary">
                        {{ ProjectName }}
                      </div>
                    </v-card-text>


                    <iframe v-bind:src="walineurl" width="344" height='400' frameborder="0"> </iframe>


                  </v-card>
                  <v-spacer></v-spacer>
                </v-row>


              </template>

            </v-card>
          </v-dialog>
        </v-row>

      </template>

    </v-main>
  </v-app>
</template>



<script>
export default {
  data: () => ({
    cards: [
      { title: '博客', src: 'https://cdn.wuyuan.dev/img/wz_wuyuan~dev.jpeg', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" },
      { title: '网站状态', src: 'https://cdn.wuyuan.dev/img/网页捕获_31-7-2022_143648_status.wuyuan.dev.jpeg', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Dress_Up_Tera.sb3', name: '孙悟元', flex: "3" },
      { title: '网页sans启动器', src: 'https://cdn.wuyuan.dev/img/20220731144055.png', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" },
      { title: 'Best airlines', src: 'https://codeyuan.tk/bj.png', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" },
      { title: 'Best airlines', src: 'https://codeyuan.tk/bj.png', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" }, { title: '博客', src: 'https://cdn.wuyuan.dev/img/wz_wuyuan~dev.jpeg', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" },
      { title: '网站状态', src: 'https://cdn.wuyuan.dev/img/网页捕获_31-7-2022_143648_status.wuyuan.dev.jpeg', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" },
      { title: '网页sans启动器', src: 'https://cdn.wuyuan.dev/img/20220731144055.png', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" },
      { title: 'Best airlines', src: 'https://codeyuan.tk/bj.png', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" },
      { title: 'Best airlines', src: 'https://codeyuan.tk/bj.png', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" }, { title: '博客', src: 'https://cdn.wuyuan.dev/img/wz_wuyuan~dev.jpeg', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" },
      { title: '网站状态', src: 'https://cdn.wuyuan.dev/img/网页捕获_31-7-2022_143648_status.wuyuan.dev.jpeg', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" },
      { title: '网页sans启动器', src: 'https://cdn.wuyuan.dev/img/20220731144055.png', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" },
      { title: 'Best airlines', src: 'https://codeyuan.tk/bj.png', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" },
      { title: 'Best airlines', src: 'https://codeyuan.tk/bj.png', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" }, { title: '博客', src: 'https://cdn.wuyuan.dev/img/wz_wuyuan~dev.jpeg', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" },
      { title: '网站状态', src: 'https://cdn.wuyuan.dev/img/网页捕获_31-7-2022_143648_status.wuyuan.dev.jpeg', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" },
      { title: '网页sans启动器', src: 'https://cdn.wuyuan.dev/img/20220731144055.png', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" },
      { title: 'Best airlines', src: 'https://codeyuan.tk/bj.png', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" },
      { title: 'Best airlines', src: 'https://codeyuan.tk/bj.png', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" }, { title: '博客', src: 'https://cdn.wuyuan.dev/img/wz_wuyuan~dev.jpeg', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" },
      { title: '网站状态', src: 'https://cdn.wuyuan.dev/img/网页捕获_31-7-2022_143648_status.wuyuan.dev.jpeg', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" },
      { title: '网页sans启动器', src: 'https://cdn.wuyuan.dev/img/20220731144055.png', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" },
      { title: 'Best airlines', src: 'https://codeyuan.tk/bj.png', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" },
      { title: 'Best airlines', src: 'https://codeyuan.tk/bj.png', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" }, { title: '博客', src: 'https://cdn.wuyuan.dev/img/wz_wuyuan~dev.jpeg', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" },
      { title: '网站状态', src: 'https://cdn.wuyuan.dev/img/网页捕获_31-7-2022_143648_status.wuyuan.dev.jpeg', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" },
      { title: '网页sans启动器', src: 'https://cdn.wuyuan.dev/img/20220731144055.png', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" },
      { title: 'Best airlines', src: 'https://codeyuan.tk/bj.png', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" },
      { title: 'Best airlines', src: 'https://codeyuan.tk/bj.png', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" }, { title: '博客', src: 'https://cdn.wuyuan.dev/img/wz_wuyuan~dev.jpeg', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" },
      { title: '网站状态', src: 'https://cdn.wuyuan.dev/img/网页捕获_31-7-2022_143648_status.wuyuan.dev.jpeg', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" },
      { title: '网页sans启动器', src: 'https://cdn.wuyuan.dev/img/20220731144055.png', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" },
      { title: 'Best airlines', src: 'https://codeyuan.tk/bj.png', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" },
      { title: 'Best airlines', src: 'https://codeyuan.tk/bj.png', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" }, { title: '博客', src: 'https://cdn.wuyuan.dev/img/wz_wuyuan~dev.jpeg', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" },
      { title: '网站状态', src: 'https://cdn.wuyuan.dev/img/网页捕获_31-7-2022_143648_status.wuyuan.dev.jpeg', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" },
      { title: '网页sans启动器', src: 'https://cdn.wuyuan.dev/img/20220731144055.png', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" },
      { title: 'Best airlines', src: 'https://codeyuan.tk/bj.png', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" },
      { title: 'Best airlines', src: 'https://codeyuan.tk/bj.png', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" }, { title: '博客', src: 'https://cdn.wuyuan.dev/img/wz_wuyuan~dev.jpeg', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" },
      { title: '网站状态', src: 'https://cdn.wuyuan.dev/img/网页捕获_31-7-2022_143648_status.wuyuan.dev.jpeg', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" },
      { title: '网页sans启动器', src: 'https://cdn.wuyuan.dev/img/20220731144055.png', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" },
      { title: 'Best airlines', src: 'https://codeyuan.tk/bj.png', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" },
      { title: 'Best airlines', src: 'https://codeyuan.tk/bj.png', link: 'https://scratch-beta.codelab.club/player.html?sb3url=' + 'https://adapter.codelab.club/sb3/Pong_Starter.sb3', name: '孙悟元', flex: "3" },
    ],
    colors: [
      'primary',

    ],
    slides: [
      'OurScratch,每个工作室的专属论坛',

    ],
    dialog: false,
    notifications: false,
    sound: true,
    widgets: false,


  }),


}
</script>

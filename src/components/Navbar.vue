<template>
  <div class="navbar-main">
    <!-- size lg -->

    <!-- <v-app-bar class="d-none d-sm-flex" color="teal lighten-3" fixed>

      <v-toolbar-items class="d-flex align-center">
        <v-toolbar-title>
          <router-link to="/">
            <v-img
              class="ml-3"
              width="100"
              height="45"
              src="data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wCEAAkGBw8SEhUSEhAVFRURERMVEhYYFRcVERYYFRUaFhUVGRUYHSggGBolHRUVITEhJSktLi4uFx8zODMtNygtLisBCgoKDg0OGxAQGzUlHyY3LS0tLS8tLSstKystLS0vLS4rLS8tNy0rLS0rLS0tLS0tLS0tLS0tNysrKzc3LTctLf/AABEIAOAA4AMBIgACEQEDEQH/xAAbAAEAAgMBAQAAAAAAAAAAAAAABQYBAwQCB//EAEIQAAIBAgQDBAYHBAkFAAAAAAABAgMRBAUSIQYxQRNRYXEiMlSBkaEWQlKxwdHwFHKSsgcVJGJzgoOUwjM0NZOi/8QAGgEBAAMBAQEAAAAAAAAAAAAAAAIDBAEFBv/EACwRAQACAQMCAwcFAQAAAAAAAAABAhEDEiEEMSIyQhMUUVJhcaEjQYGRsRX/2gAMAwEAAhEDEQA/APuIAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAwzDA9AxEyAB5uEzmR6AB0AAAAAAAAAAAAAAAAAAAAAAAADFzJ5A58xx1OjB1KktMVa78+RWs+znXPCrD1fRq1W5Si1vGNtS+Zp/pNxNqFOn1nVu/KCf4uJB5Rh71KUelLBVKj/eqKUvucfgNK36k8cRC3V0YjQi+eZnD6FHNsNy7aH8SO1TVrre/I+Q2291iwYjPsTBqMJ2jGELLTF/VT3bVzJPVRWM2hdXpLXnFZ/ta86xC7OajK0kk3Z7rci+G68nVacm/RfNt/eaK1Vy7WT5yowbty+qcuErShCtODtKNCbi+qfQq6i23qK4+EPP05m9tv1x+V4UjOo+JriHGe1VfPtJb/ADM/SDGe1VP/AGS/M0e8R8Hr/wDM1PjD7VqMpnzjgPN8RUxDhOtOcdDbUnqSfR3fI+jw5FtL7oyxa2jOlbbLIAJqgAAAAAAAAAAAAAAAAAAGQOb8QxoVY09Dlezb5WuTzKFxgv7VH92H3leraa1zCenWLThxf0j1XPEUqa3tD5zlb8EduQ0k546fSnR7KPdaMLf8SJzdupmdrepKPwhG9/LYsPCdP+w16nWvKtL3adK+aZLS8upb+Gjq/DGlT6ZVE7cw9f8AyQ/kRxL9fiduZbT/AMsP5EeRr+V6PSeefssD5VP8Cn/xPGV1FHtJOWnTRm72va3W3U9vlU/wKd+/6ppwNLXGtHVpUqM1e17X62Rq18e8aee2IfNxMxMzHxn/AFFrO4+1v/bxH9dx9sf+3icX0aj7VD+Cf5D6NR9qp/wVPyPTx0Md7/k966lIQz+3LHSXlQS+4s+W8XYWpKFJSk5yaim4WTb6+G5SPo1H2qH8FT8juyPIFDEUp/tMXoqRdlCd3Z8t1Y7no4jwX5+7ntta0+KFvlxElif2fs36yjq8Wu7uJ0+f1P8AyP8Arw/A+gGbTtnLbesRjAACxWAAAAAAAAAAAAAAAAMoHGjtiE/7kbd2xfmRue1HTozqKEZSgrrUrq11f5XKtWuap6dsSqcOLJbN0Kblazl1fR3NlLjCUVpjQppK+ybt4kpkOb06sJyqxpx7NrokrO++/kbsPnFCq6kaNOLlCN4uSUYvv3tt7yuN2PMtnHyoT6Wv2al+vcHxe3zw1J/ryJyrnOGp1FSqRinpi5SSTgm/dy8Tk4hzqNFwVKFKeqLbdk14cjk5j1Oxj5XB9MZ+z099ub+AXGElyw9P4stmDpRlTjKVOKcopvZc2uhwcR1+wpdpCnBtNJ3jdb+RKa2xnKETTONqA+l0vZqX69w+lz9npfr3E1lebUJUO1qqnFqUk0orpySXNmcLmdOtGTo04XjOMbTsvRfW/ue3gRxM+p3FflQn0vfs9L9e4yuMJc1h6d+nMnIZ1hO1lSkoxcXZSaWlu3fbYj86zrs63Z06dKStHdxu7y7reFhOY9RERPpVevjJzqurynKWrbpyt9xasn4rUrQrrS+k16r810LNGhH7EV7kQuccMUqt5QtCfX7L81080djSvXmJJvS3Ewnac00mndNbO90z1c+eUsTi8DPS16Ld7PenLyfT3HZiuLK0pQVGOndXTs22+nkT9tH790fZT+3ZeEZNdG9ldWdldePU2FyoAAAAAAAAAAAAwBk1V6SlFxa2kmn5PZmwNAfL8wwDw9XTUi3FO6fLVHwfeTuPzDCSwcoUdMX6N4NWnz/+vMtWOy+nWjpqRuunRryfQreI4JV/Qr2XdKN38U19xmnTtWfDyv31t3ap5hg/2SnCrapKNNWS9ZPl631fj7iHyDLJV6q29CO8n0S7r95P4XgqCd6lZyXdGOn53bLLhcJTpxUYRUUui/W4jTtaY3E3rWPC2xW33HNmWCjWpypv6ytfufRnVcM0Yzwozh8tjQVGso4iDai/Sina670+qJviXHYaph6caMo2VVPQvRkrQlu0/PmWnMsoo11aot1yktpL3lercE7+jX27nDf4qRn9neuYq0b6W8zzxBmGCnTUbKpU0pJx5Rsus+T8tzh4Syp1KiqyXoU3dO2zkuXw/Al8FwbTi71Kjn4JaY+/dtllpUYxSjFJJckuSO105mc2Rm8RGKvYFhY0KUfndDXQqLQpvQ9MfG21vErHBuUSlPtpxaUPVurNya52fcXdoJFdtOJmJTi8xWYEjIBYgAAAAAAAAGDJhgQ+a8Q08PPRKMm2r7JW+84vpnQ+xP5fmRHGSX7TG/LRG/xZPU8JltldUL2V/Sj+Zn3Wm0xErttYiJluy3iPD1pKKbjJ8lLa/k+RMJnzbO4UY11+zb8mtO61d0ZdS8ZnmtPDxUpvd8or1myVL98o3p22pIFSjxpG+9KSX7yuWHA4+FWHaQlddejT6p9xOt627IzWYdgKzjuL6UJOMIudna97R27u83ZZxTRqyUHeEnyvZpvuuhGpWZxEu7LYzh0Y/PqdKqqLjJyk47q1vSdl1Je5RuI/++h/o/zFgzrPqeHaTTlJ76U1dLvZCt+bZdmnEYTLZCZhxNQpvSrzkuajyT8zlzzN5/sylpdOVV2Sb9JRtdvblfl7zm4ayCnOCq1Vq1epFu0bd772XK3RQ4xpN2lSkl3q0vlzJ/C4uFSKlCSkn3fd4HDiuH8LONuyjHucVZ+dlz95mKw+CpdyXX60n+YEqCqPjON/+i7d+pX+FjqhxVSlOMIwk9dlfZJN9LAWEFfxfFFOnVlTlCXotrUmrO3gctHjGMpJdjLfud5fACy1K8Y85JebSNiZ87z/ADWNepGSg46FZpvre/QtOSZ/GvLs1Bx0xTu2rdwE4AAAAAAAAYkZMMChcaRviV4wivi2SEODKbSfbS3XcjTxZgK866lTpyklBbpbXvc1RxebJW0z2/uRMk4i05hpiZmsYlx47B1MDVhOMlLm4u3Oz3i0+T8TbmVVYjGU1L1Jdkkn3Ss/xMxyfHYmadW6XWUrbLwiiT4i4fm9NSgt4RjHT9a0fVa8TkVnvEcOzMcZnlM4rK6Eqbp6IpW22Sa8blHy7EzhTxEIt2cOnJela/wfzO+rmGZTj2XZyV1ZtQtJ+/kS2R8O6KM41fWrKztvpXT3/kTnxzxGEInZ35aOC8BTdJ1HFOTk4772S6HHxngoU5QnBaXO90lbeNrP5mulRx2Dk1CGqLf2dUX496Z6pZdi8ZUUqy0xW12rbX5RRH07ccu+rdnhyZ7Xk61Kdry7OlK3j0XyOnhulCviJTrTvNPUovq/yXKx1Z3l1V4unKFOThHsldLb0XubOIchqKfb4dPVe8ox5p/aj59w2zmZd3RjDbxxTeinK20ZtP3q6+5krw1XjPDwt9WOl+aNWFUsTQcK9KUG1aXTdbqSK68BjsJJundx74rVF91495qieGeYwvhTON6jdSnG+2m/xfM56mY5jWWjRNX+zBx+bOqvw9iZ0I6pJ1KfqrrpfNaur6nXFjwmXUYU1BQi1p32Tv4lOxeFhSxsYQ5dpBrwvZtfM6MPmmYU49mqTbWycoScl772fwNNLKsWsRCdSEnecZSlzS33QCrho1MwlCXquq7+Sje3yLisvoei1SgnF3Voru8Cu0sDW/rB1Ozlo1yeq21nCyLagKTxlTUatPTFL0OiS+t4Fww1CCSajFOy3SSZBcXZVUq6alNanBNSS52vdNDIMZjJT01oNQUbX0W3XK7AsgCAAAAAAAMNGQB5sLHoAYsLGQB40mUj0APNhpPQA82M2MgDFjDR6AGLGQAPNjNjIAxYyABhoxY9AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA//9k="
            />
          </router-link>
        </v-toolbar-title>
        <v-text-field
          class="input-search-lg"
          solo
          label="Search Book OR Author"
          clearable
        ></v-text-field>
      </v-toolbar-items>

      <v-spacer></v-spacer>

      <v-toolbar-items class="d-flex align-center">
        <router-link to="/">
          <div>
            <v-icon color="white">mdi-cart</v-icon>
            <v-btn
              class="white--text font-weight-bold btn-counter-cart-lg"
              color="orange"
              fab
              >0</v-btn
            >
          </div>
        </router-link>
        <router-link to="/">
          <span class="ml-3" style="color: #000">ورود</span>
        </router-link>
        <router-link to="/">
          <span class="ml-3" style="color: #000">ثبت نام</span>
        </router-link>
      </v-toolbar-items>
    </v-app-bar> -->

    <v-app-bar
      class="hidden-sm-and-down align-center"
      color="teal lighten-3"
      fixed
    >
      <v-col>
        <router-link to="/">
            <v-img
              class="ml-3"
              width="100"
              height="45"
              src="data:image/jpeg;base64,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"
            />
          </router-link>
      </v-col>

      <v-spacer />
      <v-row align-center class="d-none d-sm-flex pl-2">
        <v-spacer />
        <v-text-field
          class="input-search-lg"
          solo
          label="Search Book OR Author"
          clearable
        ></v-text-field>
        <v-spacer />
      </v-row>
      <v-spacer />
      <router-link to="/">
          <div class="mx-2">
            <v-icon color="white">mdi-cart</v-icon>
            <v-btn
              class="white--text font-weight-bold btn-counter-cart-lg"
              color="orange"
              fab
              >0</v-btn
            >
          </div>
        </router-link>
        <router-link to="/">
          <span class="mx-2 white--text font-weight-bold">Login</span>
        </router-link>
        <router-link class="mx-2" to="/">
          <v-icon color="white" style="text-decoration: underline">mdi-format-color-fill</v-icon>
        </router-link>
        <a href="#" class="mx-2 white--text font-weight-bold">
          <v-icon color="white">mdi-github</v-icon>
          <span>GitHub</span>
        </a>
    </v-app-bar>

    <!-- size mobile -->
    <v-app-bar class="d-flex" color="white">
      <v-app-bar-nav-icon @click="drawer = true"></v-app-bar-nav-icon>
      <v-toolbar-title class="d-flex align-center">
        <v-img
          width="50"
          height="22"
          src="https://faradars.org/next/svg/faradars-row.svg"
        />
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn text>
        <v-icon class="mr-2">mdi-search-web</v-icon>
      </v-btn>
    </v-app-bar>

    <v-navigation-drawer v-model="drawer" absolute temporary right>
      <v-divider></v-divider>
      <v-list nav dense>
        <v-list-item-group color="primary">
          <v-list-item>
            <v-list-item-content class="mt-1">
              <v-list-item-title>
                <v-icon large>mdi-close</v-icon>
              </v-list-item-title>
            </v-list-item-content>
          </v-list-item>
          <v-list-item>
            <v-list-item-content class="mt-2">
              <v-list-item-title>
                <v-icon>mdi-key-variant</v-icon>
                <span class="subtitle-1 mr-1">ورود</span>
              </v-list-item-title>
            </v-list-item-content>
          </v-list-item>
          <v-list-item>
            <v-list-item-content class="mt-2">
              <v-list-item-title>
                <v-icon>mdi-account-lock</v-icon>
                <span class="subtitle-1 mr-1">ثبت نام</span>
              </v-list-item-title>
            </v-list-item-content>
          </v-list-item>

          <v-list-item>
            <v-list-item-content class="mt-2">
              <v-list-item-title>
                <v-icon>mdi-view-dashboard</v-icon>
                <span class="subtitle-1 mr-1">همه آموزش ها</span>
                <v-icon class="mr-10">mdi-chevron-left</v-icon>
              </v-list-item-title>
            </v-list-item-content>
          </v-list-item>

          <v-list-item>
            <v-list-item-content class="mt-2">
              <v-list-item-title>
                <v-icon>mdi-account-details-outline</v-icon>
                <span class="subtitle-1 mr-1">تدریس درفرادرس</span>
                <v-icon class="mr-8">mdi-chevron-left</v-icon>
              </v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      drawer: false,
      group: null,
    };
  },
};
</script>

<style scoped>
.input-search-lg {
  width: 380px;
  max-height: 48px;
}
.btn-counter-cart-lg {
  margin-bottom: 27px;
  max-height: 22px;
  max-width: 22px;
  font-size: 14px;
}
</style>
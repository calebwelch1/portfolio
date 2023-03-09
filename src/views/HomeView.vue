<script lang="ts">
// import jQuery from 'jquery'
import $ from 'jquery'
// import pJs from './particles.js'

export default {
  data() {
    return { 
      showAbout:false,
      showContact: false,
      showWork: false,
     }
  },
  mounted() {
    setTimeout(function(){
    $("#loading").addClass("animated fadeOut");
    setTimeout(function(){
      console.log('mounted');
      $("#loading").removeClass("animated fadeOut");
      $("#loading").css("display","none");
      $("#box").css("display","none");
      $("#about").removeClass("animated fadeIn");
      $("#contact").removeClass("animated fadeIn");
      $("#work").removeClass("animated fadeIn");
    },1000);
},1500);
  },
  methods: {
//     showabout(){
//     $("#about_container").css("display","inherit");
//     $("#about_container").addClass("animated slideInLeft");
//     setTimeout(() => {
//         $("#about_container").removeClass("animated slideInLeft");
//     },800);
// },
closeabout(){
    $("#about_container").addClass("animated slideOutLeft");
    setTimeout(function(){
        $("#about_container").removeClass("animated slideOutLeft");
        $("#about_container").css("display","none");
    },800);
},
showwork(){
    $("#work_container").css("display","inherit");
    $("#work_container").addClass("animated slideInRight");
    setTimeout(function(){
        $("#work_container").removeClass("animated slideInRight");
    },800);
},
closework(){
    $("#work_container").addClass("animated slideOutRight");
    setTimeout(function(){
        $("#work_container").removeClass("animated slideOutRight");
        $("#work_container").css("display","none");
    },800);
},
showcontact(){
    $("#contact_container").css("display","inherit");
    $("#contact_container").addClass("animated slideInUp");
    setTimeout(function(){
        $("#contact_container").removeClass("animated slideInUp");
    },800);
},
closecontact(){
    $("#contact_container").addClass("animated slideOutDown");
    setTimeout(function(){
        $("#contact_container").removeClass("animated slideOutDown");
        $("#contact_container").css("display","none");
    },800);
},
  },
  created() {
    // this.plus()
    // console.log(this.a) // => 2
  }
}
</script>

<template>
  <main>
    <html lang="en">
<body>
    <div id="loading">
        <div id="spinner"></div>
    </div>
    <!-- <div id="particles-js"></div> -->
    <div id="box">
        <div class="box1 onlywide animated bounceOutLeft" style="animation-delay:1.7s;"></div>
        <div class="box2 onlywide animated bounceOutLeft" style="animation-delay:1.8s;"></div>
        <div class="box2 onlywide animated bounceOutLeft" style="animation-delay:1.9s;"></div>
        <div class="box2 animated bounceOutRight" style="animation-delay:1.9s;"></div>
        <div class="box2 onlywide animated bounceOutRight" style="animation-delay:1.8s;"></div>
        <div class="box2 onlywide animated bounceOutRight" style="animation-delay:1.7s;"></div>
    </div>
    <a id="about" @click="showAbout = !showAbout" class="animated fadeIn" style="animation-delay:2.2s;">about</a>
    <a id="work" @click="showWork = !showWork" class="animated fadeIn" style="animation-delay:2.2s;">work</a>
    <a id="contact" @click="showContact = !showContact" class="animated fadeIn" style="animation-delay:2.2s;">contact</a>
    <div id="middle" class="animated slideInDown" style="animation-delay:2.0s;">
        <h1>caleb welch</h1>
        <h2>Artist /  Software Developer / Human</h2>
        <div id="menu">
            <a @click="showAbout = !showAbout">about</a>
            <a @click="showWork = !showWork">work</a>
            <a @click="showContact = !showContact">contact</a>
        </div>
        <table>
                <tr>
                    <td class="animated zoomIn" style="animation-delay:2.2s;"><a class="social"><i class="fab fa-facebook"></i></a></td>
                    <td class="animated zoomIn" style="animation-delay:2.4s;"><a class="social"><i class="fab fa-twitter"></i></a></td>
                    <td class="animated zoomIn" style="animation-delay:2.6s;"><a class="social"><i class="fab fa-instagram"></i></a></td>
                    <td class="animated zoomIn" style="animation-delay:2.8s;"><a class="social"><i class="fab fa-dribbble"></i></a></td>
                </tr>
        </table>
    </div>
    <Transition name="work">
    <div v-if="showWork" id="work_container" class="container" style="display: inherit;">
        <div @click="showWork = !showWork">&gt;</div>
        <h1>works.</h1>
        <section>
            <h2>work title</h2>
            <p>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
            </p>
            <div id="used">
                <div><i class="fas fa-circle"></i>&nbsp;HTML5</div>
                <div><i class="fas fa-circle"></i>&nbsp;CSS3</div>
                <div><i class="fas fa-circle"></i>&nbsp;Javascript</div>
            </div>
            <button class="btn_one">button 1</button>
            <button class="btn_two">button 2</button>
        </section>
    </div>
  </Transition>
    <Transition name="about">
    <div v-if="showAbout" id="about_container" class="container" style="display: inherit;">
            <div @click="showAbout = !showAbout">&lt;</div>
            <h1>about.</h1>
            <section>
                <h2>about me</h2>
                <p>
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                </p>
                <p>
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                </p>
            </section>
            <section>
                <h2>skills</h2>
                <p>
                    i do eveything ;)
                </p>
            </section>
        </div>
      </Transition>
      <Transition name="contact">
          <div v-if="showContact" id="contact_container" class="container" style="display: inherit;">
            <div @click="showContact = !showContact">v</div>
            <h1>contact.</h1>
            <section>
                <h2>contact me</h2>
                <p>
                    <form>
                        <input type="text" placeholder="name" required>
                        <input type="email" placeholder="email" required><br>
                        <textarea placeholder="your message" required rows="5"></textarea><br>
                        <button class="btn_one">send</button>
                    </form> 
                </p>
            </section>
        </div>
      </Transition>
        <div id="footer">
            made on earth by a human <br> <a href="https://imfunniee.github.io">imfunniee</a>
        </div>
    <!-- <script src="index.js" type="text/javascript"></script>
    <script src="particles.js"></script>
    <script src="app.js"></script> -->
</body>
</html>
  </main>
</template>
<style>
.about-enter-active {
  transition: all 0.5s ease-out;
}

.about-leave-active {
  transition: all 0.5s ease-out;
}

.about-enter-from,
.about-leave-to {
  transform: translateX(-200px);
  opacity: 0;
}

.work-enter-active {
  transition: all 0.5s ease-out;
}

.work-leave-active {
  transition: all 0.5s ease-out;
}

.work-enter-from,
.work-leave-to {
  transform: translateX(200px);
  opacity: 0;
}


.contact-enter-active {
  transition: all 0.5s ease-out;
}

.contact-leave-active {
  transition: all 0.5s ease-out;
}

.contact-enter-from,
.contact-leave-to {
  transform: translateY(200px);
  opacity: 0;
}
</style>


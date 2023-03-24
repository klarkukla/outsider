<template>
<div>

    <!-- overlay -->
    <div id="overlay" v-bind:class="{ visible: showOverlay }">
      <div class="content">
        <a class="bt-close" v-on:click="showOverlay = false"><img src="@/assets/img/ui/close-cream.svg" alt="Close"></a>
        <!-- <a href="/newsletter.html" target="blank" class="bt-primary">{{translatedTxt.newsletter}}</a> -->
        <a href="/henry-darger-collections.html" target="blank" class="bt-primary">{{translatedTxt.ccollections}}</a>
      </div>
      <img src="@/assets/img/ui/overlay.svg" alt="Overlay" class="bg">
    </div>

    <div id="mobile-overlay" v-if="isMobile"></div>

    <div id="scrolldown" v-bind:class="{ hidden: !showScroll }">
      <div class="txt">{{translatedTxt.scroll}}</div>
      <img src="@/assets/img/ui/scroll.svg">
    </div>

    <div class="space" v-if="!isMobile"></div>
    <div class="space" v-if="!isMobile"></div>

    <!-- embed youtube -->
    <div class="video-container">
      <iframe width="560" height="315" src="https://www.youtube.com/embed/videoseries?list=PL6c_5GyF9mZQXOmzXyQ5WsqcjZ3GnWYaL" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
    </div>

    <div class="space" v-if="!isMobile"></div>
    
    <div class="cloud left" id="c0">
      <div class="content">
        <p class="big"><span v-html="translatedTxt.c0.big"></span></p>
        <p class="subtitle">{{translatedTxt.c0.subtitle}}</p>
      </div>    
      <img src="@/assets/img/ui/clouds/c0.svg" class="cb" v-if="!isMobile">
    </div>

    <div class="space"></div>

    <div class="cloud right" id="c1">
      <div class="content">
        <p class="quote"><span v-html="translatedTxt.c1"></span></p>
        <p class="signature">- Henry Darger</p>
      </div>
      <img src="@/assets/img/ui/clouds/c1.svg" class="cb" v-if="!isMobile">
    </div>

    <div class="space"></div>

    <div class="cloud left" id="c2">
      <div class="content">
        <p class="quote">{{translatedTxt.c2.quote}}</p>
        <p class="signature">- FIP</p>
      </div>
      <img src="@/assets/img/ui/clouds/c2.svg" class="cb" v-if="!isMobile">
    </div>

    <div class="space"></div>

    <!-- album -->
    <div class="cloud" id="album">
      <img src="@/assets/img/ui/clouds/c-album-mobile.png" alt="Album" class="cb ci" v-if="isMobile">
      <img src="@/assets/img/ui/clouds/c-album.png" alt="Album" class="cb ci" v-if="!isMobile">
      <div class="content center-text">     
        <a href="http://smarturl.it/outsiderdarger" target="blank" class="bt-primary">{{translatedTxt.c2.bt}}</a>
      </div> 
    </div>

    <div class="space"></div>

    <div class="cloud right" id="c3">
      <div class="content">
        <p><span v-html="translatedTxt.c3"></span></p>
      </div>
      <img src="@/assets/img/ui/clouds/c3.svg" class="cb" v-if="!isMobile">
    </div>

    <div class="space"></div>

    <!-- videos -->
    <div class="cloud interstitial" id="videos">
      <img src="@/assets/img/ui/clouds/c-videos-mobile.png" alt="Videos" class="cb ci" id="c-clips" v-if="isMobile">
      <img src="@/assets/img/ui/clouds/c-videos.png" alt="Videos" class="cb ci" id="c-clips" v-if="!isMobile">
      <div class="content center-text">
        <a href="https://www.youtube.com/watch?v=G8h12wI1tDc&list=PL6c_5GyF9mZQXOmzXyQ5WsqcjZ3GnWYaL" target="blank" class="bt-primary">{{translatedTxt.cvideos}}</a>
      </div>     
    </div>

    <div class="space"></div>

    <div class="cloud left" id="c15">
      <div class="content">
        <p class="quote">{{translatedTxt.c15}}</p>
      </div>
      <img src="@/assets/img/ui/clouds/c15.svg" class="cb" v-if="!isMobile">
    </div>

    <div class="space"></div>

    <div class="cloud right" id="c4">
      <div class="content">
        <p><span v-html="translatedTxt.c4"></span></p>
      </div>
      <img src="@/assets/img/ui/clouds/c4.svg" class="cb" v-if="!isMobile">
    </div>

    <div class="space"></div>

    <!-- podcasts -->
    <div class="cloud interstitial" id="podcasts">
      <div class="content center-text">
        <iframe v-bind:src="translatedTxt.podcastLink" scrolling="no" frameborder="0" style="border:none;overflow:hidden;"></iframe>
        <a v-bind:href="translatedTxt.morepodcastsLink" target="blank" class="bt-primary">{{translatedTxt.cpodcasts}}</a>
      </div>
      <img src="@/assets/img/ui/clouds/c-podcasts.png" alt="Podcasts" class="cb ci" id="c-podcasts" v-if="!isMobile">
    </div>

    <div class="space"></div>

    <div class="cloud left" id="c16">
      <div class="content">
        <p class="quote">{{translatedTxt.c16}}</p>
        <p class="signature" v-if="this.lang = 'fr'">- Les Inrocks</p>
      </div>
      <img src="@/assets/img/ui/clouds/c16.svg" class="cb" v-if="!isMobile">
    </div>

    <div class="space"></div>

    <!-- collections -->
    <div class="cloud interstitial" id="collections">
      <img src="@/assets/img/ui/clouds/c-collections-mobile.png" alt="Collections around the globe" class="cb ci" id="c-collections" v-if="isMobile">
      <img src="@/assets/img/ui/clouds/c-collections.png" alt="Collections around the globe" class="cb ci" id="c-collections" v-if="!isMobile">
      <div class="content center-text">
        <a href="/henry-darger-collections.html" target="blank" class="bt-primary">{{translatedTxt.ccollections}}</a>
      </div>    
    </div>

    <div class="space"></div>

    <div class="cloud right" id="c5">
      <div class="content">
        <p><span v-html="translatedTxt.c5.p0"></span></p>
        <p><span v-html="translatedTxt.c5.p1"></span></p>       
      </div>
      <img src="@/assets/img/ui/clouds/c5.svg" class="cb" v-if="!isMobile">
    </div>

    <div class="space"></div>

    <!-- tour -->
    <div class="cloud interstitial" id="tour">
      <img src="@/assets/img/ui/clouds/c-tour-mobile.png" alt="Tour" class="cb ci" id="c-tour" v-if="isMobile">
      <img src="@/assets/img/ui/clouds/c-tour.png" alt="Tour" class="cb ci" id="c-tour" v-if="!isMobile">
      <div class="content">
        <a href="https://www.songkick.com/artists/3653951" class="songkick-widget" data-theme="light" data-track-button="on" data-detect-style="true" data-background-color="transparent" data-locale="en">Philippe Cohen Solal tour dates</a>
      </div>
      <div class="content center-text">
        <a href="https://www.songkick.com/artists/3653951-philippe-cohen-solal" target="blank" class="bt-primary">{{translatedTxt.ctour}}</a>
      </div>
    </div>
    
    <div class="space"></div>

    <div class="cloud left" id="c6">
      <div class="content">
        <p class="quote">{{translatedTxt.c6}}</p>
        <p class="signature">- Mike Lindsay</p>
      </div>
      <img src="@/assets/img/ui/clouds/c6.svg" class="cb" v-if="!isMobile">
    </div>

    <div class="space"></div>

    <!-- twitter -->
    <div class="cloud twitter">
      <div class="content center-text">
        <a class="twitter-timeline" data-width="300" data-height="320" href="https://twitter.com/outsider_online?ref_src=twsrc%5Etfw">Tweets by outsider_online</a> 
        <a href="https://twitter.com/outsider_online" target="blank" class="bt-primary">{{translatedTxt.ctwitter}}</a>
      </div>
      <img src="@/assets/img/ui/clouds/c14.svg" class="cb" v-if="!isMobile">
    </div>

    <div class="space"></div>

    <!-- press -->
    <div class="cloud interstitial" id="press">
      <img src="@/assets/img/ui/clouds/c-press-mobile.png" alt="Press" class="cb ci" id="c-press" v-if="isMobile">
      <img src="@/assets/img/ui/clouds/c-press.png" alt="Press" class="cb ci" id="c-press" v-if="!isMobile">
      <div class="content center-text">
        <a href="https://linktr.ee/outsiderpress" target="blank" class="bt-primary">{{translatedTxt.cpress}}</a>
      </div>   
    </div>

    <div class="space"></div>

    <h2 class="bigtitle">HENRY DARGER</h2>

    <div class="space"></div>

    <div class="cloud right" id="c7">
      <div class="content">
        <p class="quote">{{translatedTxt.c7}}</p>
        <p class="signature">- Henry Darger</p>
      </div>
      <img src="@/assets/img/ui/clouds/c7.svg" class="cb" v-if="!isMobile">
    </div>

    <div class="space"></div>

    <!-- <img src="@/assets/img/ui/darger.png" alt="Darger" id="c-darger"> -->

    <div class="cloud left" id="c8">
      <div class="content">
        <p><span v-html="translatedTxt.c8.p0"></span></p>
        <p><span v-html="translatedTxt.c8.p1"></span></p>
        <br>
        <p><a href="http://www.officialhenrydarger.com/" target="blank" class="bt-primary">{{translatedTxt.c8.bt}}</a></p>
      </div>
      <img src="@/assets/img/ui/clouds/c8.png" class="cb" v-if="!isMobile">
    </div>

    <div class="space"></div>

    <h2 class="bigtitle">{{translatedTxt.theband}}</h2>

    <div class="space"></div>

    <div class="cloud right" id="c9">
      <div class="content">
        <img src="@/assets/img/ui/avatar0.png" alt="Philippe" class="avatar">
        <div class="name">PHILIPPE COHEN SOLAL</div>
        <div class="role">{{translatedTxt.c9.role}}</div>
        <p><span v-html="translatedTxt.c9.bio"></span></p>
        <br>
        <a href="https://yabasta-records.com/en/philippe-cohen-solal" target="blank" class="persolink">{{translatedTxt.moreinfos}}</a>
      </div>
      <img src="@/assets/img/ui/clouds/c9.svg" class="cb" v-if="!isMobile">
    </div>

    <div class="space"></div>

    <div class="cloud left" id="c10">
      <div class="content">
        <img src="@/assets/img/ui/avatar1.png" alt="Mike" class="avatar">
        <div class="name">MIKE LINDSAY</div>
        <div class="role">{{translatedTxt.c10.role}}</div>
        <p><span v-html="translatedTxt.c10.bio"></span></p>
        <br>
        <a href="http://www.mike-lindsay.com" target="blank" class="persolink">{{translatedTxt.moreinfos}}</a>
      </div>
      <img src="@/assets/img/ui/clouds/c10.svg" class="cb" v-if="!isMobile">
    </div>

    <div class="space"></div>

    <div class="cloud right" id="c11">
      <div class="content">
        <img src="@/assets/img/ui/avatar2.png" alt="Adam" class="avatar">
        <div class="name">ADAM GLOVER</div>
        <div class="role">{{translatedTxt.c11.role}}</div>
        <p><span v-html="translatedTxt.c11.bio"></span></p>
        <br>
        <!-- <a href="#" target="blank" class="persolink">> More infos</a> -->
      </div>
      <img src="@/assets/img/ui/clouds/c11.svg" class="cb" v-if="!isMobile">
    </div>

    <div class="space"></div>

    <div class="cloud left" id="c12">
      <div class="content">
        <img src="@/assets/img/ui/avatar3.png" alt="Hannah" class="avatar">
        <div class="name">HANNAH PEEL</div>
        <div class="role">{{translatedTxt.c12.role}}</div>
        <p><span v-html="translatedTxt.c12.bio"></span></p>
        <br>
        <a href="http://www.hannahpeel.com" target="blank" class="persolink">{{translatedTxt.moreinfos}}</a>
      </div>
      <img src="@/assets/img/ui/clouds/c12.svg" class="cb" v-if="!isMobile">
    </div>

    <div class="space"></div>

    <h2 class="bigtitle">{{translatedTxt.theart}}</h2>

    <div class="space"></div>

    <div class="cloud right" id="c14">
      <div class="content">
        <img src="@/assets/img/ui/avatar5.png" alt="Pascal" class="avatar">
        <div class="name">PASCAL GARY (AKA PHORMAZERO)</div>
        <div class="role">{{translatedTxt.c14.role}}</div>
        <p><span v-html="translatedTxt.c14.bio"></span></p>
        <br>
        <a href="http://www.phormazero.com/" target="blank" class="persolink">{{translatedTxt.moreinfos}}</a>
      </div>
      <img src="@/assets/img/ui/clouds/c14.svg" class="cb" v-if="!isMobile">
    </div>

    <div class="space"></div>

    <div class="cloud left" id="c13">
      <div class="content">
        <img src="@/assets/img/ui/avatar4.png" alt="Hannah" class="avatar">
        <div class="name">GABRIEL JACQUEL</div>
        <div class="role">{{translatedTxt.c13.role}}</div>
        <p><span v-html="translatedTxt.c13.bio"></span></p>
        <br>
        <a href="https://rainboxprod.coop/en/" target="blank" class="persolink">{{translatedTxt.moreinfos}}</a>
      </div>
      <img src="@/assets/img/ui/clouds/c13.svg" class="cb" v-if="!isMobile">
    </div>

    <div class="space"></div>

    <!-- making-of -->
    <!-- <div class="cloud interstitial" id="making-of">
      <img src="@/assets/img/ui/clouds/c-makingof-mobile.png" alt="Making Of" class="cb ci" id="c-makingof" v-if="isMobile">
      <img src="@/assets/img/ui/clouds/c-makingof.png" alt="Making Of" class="cb ci" id="c-makingof" v-if="!isMobile">
      <div class="content center-text">
        <a target="blank" class="bt-primary disabled">Making-of</a>
        <div class="alert">Coming soon !</div>
      </div>  
    </div>

    <div class="space"></div> -->

    <!-- shop -->
    <div class="cloud interstitial" id="shop">
      <img src="@/assets/img/ui/clouds/c-shop-mobile.png" alt="Shop" class="cb ci" id="c-shop" v-if="isMobile">
      <img src="@/assets/img/ui/clouds/c-shop.png" alt="Shop" class="cb ci" id="c-shop" v-if="!isMobile">
      <div class="content center-text">
        <a href="https://yabasta-records.com/categorie-produit/outsider" target="blank" class="bt-primary">{{translatedTxt.shop}}</a>
      </div> 
    </div>
    
    <div class="space"></div>
    <div class="space"></div>

    <footer id="footer">
      <p class="lasttext">{{translatedTxt.last}}</p>
      <div class="content">
        <div class="row">
          <div class="column2">
            <a href="/newsletter.html" target="blank" class="bt-primary">{{translatedTxt.newsletter}}</a>
          </div>
          <div class="column2 nomargin" id="contact">
            <div class="title">{{translatedTxt.contactus}}</div>
            <p>{{translatedTxt.sendemail}} <a href="mailto:contact@outsideronline.co">contact@outsideronline.co</a></p>

            <!-- <form class="contact-form" @submit.prevent="sendEmail">
              <input type="text" name="user_name" placeholder="Name" class="mb w50">
              <input type="email" name="user_email" placeholder="Email" class="mb w50 nomargin">
              <textarea name="message" placeholder="Message" class="w100"></textarea>
              <button type="submit">Send</button>
            </form> -->
            <!-- {{emailResponse}} -->
            
          </div>
        </div>
        <div class="clearfix"></div>
        <hr>
        <div class="row">
          <div class="column2">
            <a href="https://yabasta-records.com" target="blank" class="logo"><img src="@/assets/img/ui/logo-yabasta.svg"></a>
            <a href="https://fb.com/philippecohensolalofficial" target="blank" class="logo"><img src="@/assets/img/ui/logo-fb.svg"></a>
            <a href="https://www.instagram.com/philippecohensolal/" target="blank" class="logo"><img src="@/assets/img/ui/logo-insta.svg"></a>
            <a class="logo"><img src="@/assets/img/ui/logo-lm.png"></a>
          </div>
          <div class="column2 nomargin"> 
            <a href="https://open.spotify.com/album/02tG8xdQhgLxZHxb50SEC4?si=ZWPbWQVRTQ-yWYAw_kGLZg" target="blank" class="logo"><img src="@/assets/img/ui/logo-spotify.svg"></a>
            <a href="https://music.apple.com/fr/album/outsider-feat-adam-glover/1535924537?uo=4&ls=1&app=music&at=11lEW&ct=v0zuwf" target="blank" class="logo"><img src="@/assets/img/ui/logo-apple.svg"></a>
            <a href="https://www.amazon.com/dp/B08L81Z756?tag=smarturl-pivot-20" target="blank" class="logo"><img src="@/assets/img/ui/logo-amazon.svg"></a>
          </div>         
        </div>
        <div class="clearfix"></div>
        <div class="row">
          <div class="column2">
            <p class="minitext">
              <span v-html="translatedTxt.footer.credits0"></span>
              <br>{{translatedTxt.footer.credits1}} <a href="https://rainboxprod.coop" target="blank">Gabriel Jacquel</a>.
              <br>{{translatedTxt.footer.credits4}}.
              <br>{{translatedTxt.footer.credits2}} <a href="http://www.thmslhst.com/" target="blank">Thomas Lhoest</a>.      
              {{translatedTxt.footer.credits3}} © <span>{{date}}</span>.
            </p>
          </div>
          <div class="column2 nomargin">
            <p class="minitext">
              {{translatedTxt.footer.credits5}}
            </p>
            <a href="https://www.pictanovo.com/" target="blank" class="logo"><img src="@/assets/img/ui/pictanovo.png" alt="Pictanovo"></a>
            <a href="https://www.adami.fr/" target="blank" class="logo"><img src="@/assets/img/ui/adami.png" alt="Adami"></a>
            <a href="https://www.scpp.fr/" target="blank" class="logo"><img src="@/assets/img/ui/scpp.png" alt="SCPP"></a>
          </div>
        </div>
      </div>
      <img src="@/assets/img/ui/clouds/footer.svg" id="c-footer">
    </footer>
</div>
</template>

<script>
//import emailjs from 'emailjs-com'
import { EventBus } from "@/event-bus.js"

export default {
  name: 'Home',
  data() {
    return {
      showNewsletter: true,
      showScroll: true,
      isMobile: false,
      date: null,
      emailResponse: '',
      showOverlay: false,
      lang: 'en',
      translatedTxt: {},
      text: {
        en: {
          newsletter: "Subscribe to our newsletter !",
          c0: {
              "big": "A <strong>musical album</strong> and <strong>transmedia project</strong>",
              "subtitle": "by Philippe Cohen Solal & Mike Lindsay"
          },
          c1: "« This is my story, this <br> is my song »",
          c2: {
              "quote": "« Both majestic and baroque »",
              "bt": "Listen to the album"
          },
          c3: "<strong>OUTSIDER</strong> transports us into Henry Darger's imaginary and 'unreal realm' by <strong>mixing music and dreamlike imagery</strong>. Based on animations, this video creation invites the spectator to immerse himself in <strong>the hallucinatory world of this phenomenal artist</strong>.",
          cvideos: "Watch videos",
          c15: "Music, visual arts and storytelling",
          c4: "« I dream that this transmedia project <strong>brings together past, present and future</strong>. I would like that through this audiovisual and interactive creation inspired by the work and life of the most famous outsider artist, the public questions <strong>the role and relationship of celebrity to the necessity of art</strong>. » <br><br> - Philippe Cohen Solal",
          cpodcasts: "More podcasts",
          c16: "« Romantic and stunning concept album »",
          c5: {
              p0: "In North Side Chicago, in the middle of the 20th century, there was a reclusive hospital janitor who lived in one room – and <strong>who turned out to be an artistic genius</strong>. <strong>Henry Darger invented a whole world inside that room, making hundreds of paintings and collages, and writing fantasy novels that were 15,000 pages long</strong>. His work told the story of an ongoing battle between good and evil, where rampaging armies battled a band of brave children called The Vivian Girls.",
              p1: "Nearly a half century after Darger’s death, <strong>Gotan Project’s Philippe Cohen Solal and Tunng’s Mike Lindsay present OUTSIDER</strong>, a tapestry of ten warm and resonant, rapturous pop songs and gorgeous visuals that transmit and translate Darger’s story into the current day.<strong>These are heart-soaked instant classics, brought to life in remarkable style by singers Adam Glover and Hannah Peel</strong>. These are not your average love songs."
          },
          ctour: "Upcoming gigs",
          c6: "« It sounds like a very twisted long-forgotten musical, with an evil twist and a very innocent blanket wrapped around it. It’s classic, it’s beautiful and it’s experimental »",
          ctwitter: "Follow Outsider",
          cpress: "They talk about us",
          c7: "« I hated to see the day come when I will be grown up. I never wanted to. I wished to be young always »",
          c8: {
              p0: "<strong>HENRY DARGER (1892-1973) was a reclusive hospital janitor and dishwasher who led a secret life as a prolific visual artist and epic novelist</strong>. His vast collection of creative work was discovered in 1972 when his two-room apartment in Chicago was cleared out shortly before he died. Over some 350 watercolor, pencil, collage and carbon-traced drawings, most of them stitched into three enormous 'albums', as well as seven typewritten hand-bound books, thousands of bundled sheets of typewritten text, and numerous journals, ledgers and scrapbooks were discovered.",
              p1: "Darger's unpublished 15,000-page typewritten fantasy novel, <strong>The Story of the Vivian Girls, in What Is Known as the Realms of the Unreal, of the Glandeco-Angelinian War Storm, Caused by the Child Slave Rebellion</strong> — or, for short, In the Realms of the Unreal — and its 8,500-page handwritten sequel of sorts, Further Adventures of the Vivian Girls in Chicago, were the sagas upon which he based several hundred panoramic 'illustrations', many of them double-sided and more than 9 feet in length.",
              bt: "Read full bio"
          },
          ccollections: "Darger around the world",
          theband: "THE BAND",
          c9: {
              role: "Keyboards & electronics",
              bio: "<strong>The million-selling artist, producer, composer and co-founder of Gotan Project, Philippe Cohen Solal</strong> has also collaborated with numerous artists like Salif Keita, Angelique Kidjo, Horace Andy, Adrien Brody, Roberto Fonseca, Dorfmeister, Chassol, Bobby Mc Ferrin..."
          },
          moreinfos: "> More infos",
          c10: {
              role: "Guitar, bass & electronics",
              bio: "<strong>Mercury Music Prize winning producer, Mike Lindsay</strong> is most known for being the co-founder, composer and producer of UK acid folk band <strong>Tunng</strong>. He has co-written and produced many albums for a wide range of artists including Speech Debelle's Mercury Music prize winning album 'Speech Therapy', Jon Hopkins, Farao, DuBlonde, Low Roar, Beth Jeans Houghton, Serafina Steer, Cibelle and Laura J Martin..."
          },
          c11: {
              role: "Lead singer",
              bio: "<strong>Adam Glover is a recording artist originally from Manchester</strong>, UK, where his love for crooning first began. After graduating from the university of Westminster as a Bachelor of Musicology, Adam resided in Los Angeles working with some of the music industry's top producers."
          },
          c12: {
              role: "Keyboards, violin, trombone, vocals",
              bio: "<strong>Emmy-nominated and RTS winning composer</strong>, with a flow of solo albums and collaborative releases, <strong>Hannah joins the dots between science, nature and the creative arts</strong>, through her explorative approach to electronic, classical and traditional music."
          },
          theart: "THE TEAM",
          c14: {
              role: "Visual artist, Artistic director",
              bio: "<strong>In 2000, Pascal Gary creates phormazero</strong>, a creative studio with diverse outpouring including live visuals, installations, music-videos and unique visual concepts for international festivals, contemporary art festivals, luxury industries, designers, and broadcast shows."
          },
          c13: {
              role: "Director & animator",
              bio: "<strong>Animator on many films</strong> : The Wallet, Signs of life, Edmond was a donkey, The Head vanished, The Ogre, or Roughhouse… He directed three short films RectoVerso, Beuuââârk !!!, Ludwig Demon's. Co-directed Breakout and La Ferté - Un Cercueil de Béton. <strong>Co-founded Studio train train</strong>, he joined forces with the production company <strong>Rainbox</strong> for his new project Pylône."
          },
          shop: "Visit our shop",
          contactus: "Contact us",
          sendemail: "Send an email to",
          last: "This project is also an opportunity to highlight the strength of the singularity for which Darger is one of the most powerful symbols. Witnessing this infinite wealth, which is often ignored, to encourage the revelation to the world of this part of genius.",
          footer: {
            credits0: "<strong>OUTSIDER</strong>, a musical album & transmedia project inspired by Henry Darger.",
            credits1: "Drawings & animations by",
            credits2: "Website by",
            credits3: "All rights reserved",
            credits4: "Production & Development Consultant : Laurent Maillaud",
            credits5: "Co-financed by PICTANOVO as part of Fonds Nouveaux Médias with the help of Région Hauts de France and the Centre National de la Cinématographie et de l’image animée."
          },
          scroll: "SCROLL DOWN",
          podcastLink: "https://embed.acast.com/outsider-the-amazing-story-of-henry-darger",
          morepodcastsLink: "https://smarturl.it/outsider.podcast.en"
        },

        fr: {
          newsletter: "Inscrivez-vous à notre newsletter !",
          c0: {
              big: "Un <strong>album musical</strong> et <strong>projet transmédia</strong>",
              subtitle: "par Philippe Cohen Solal & Mike Lindsay"
          },
          c1: "« Ceci est mon histoire, ceci <br> est ma chanson »",
          c2: {
              quote: "« Majestueux et baroque »",
              bt: "Écouter l'album"
          },
          c3: "<strong>OUTSIDER</strong> nous transporte dans l'univers d’Henry Darger en mixant <strong>musique et imagerie onirique</strong>, invitant le spectateur à s’immerger dans <strong>le monde hallucinatoire de cet artiste phénoménal</strong>.",
          cvideos: "Regarder plus de vidéos",
          c15: "Musique, arts visuels et narration",
          c4: "« J’aimerais que grâce à cette création audiovisuelle et interactive inspirée par le travail et la vie de l'artiste le plus célèbre de l'Art Brut, le public s'interroge sur le <strong>rôle et le rapport de la célébrité à la nécessité de l'art</strong>. » <br><br> - Philippe Cohen Solal",
          cpodcasts: "Plus de podcasts",
          c16: "« Concept-album romantique et renversant »",
          c5: {
              p0: "<strong>L'oeuvre développée tout au long de sa vie (1892-1973) par Henry Darger</strong> a été découverte juste avant sa mort, dans le fourbi d’une chambre qu’il occupait au 851 Webster Avenue à Chicago. Un roman épique de plus de 15.000 pages et plus de 350 peintures évoquant une guerre interminable sur une planète imaginaire, déclenchée par la rébellion d’enfants tenus en esclavage, menée par les “Vivian Girls”. Univers rencontrant aujourd'hui encore un écho important dans le monde de l’art.",
              p1: "Près d'un demi-siècle après la mort de Darger, <strong>Philippe Cohen Solal (Gotan Project) et Mike Lindsay (Tunng) présentent OUTSIDER</strong>. La beauté de l’album naît de la collision entre l’opulence des mélodies, chœurs et arrangements et l’étrangeté de ces ambiances où se bousculent effets analogiques, archives et sons pas toujours identifiables. Comme un vernis qui se craquèle pour souligner encore davantage la beauté."
          },
          ctour: "Prochains événements",
          c6: "« Cela ressemble à une comédie musicale dérangée qui aurait été longuement oubliée,  où la malice se draperait d’innocence. C’est intemporel, beau et expérimental »",
          ctwitter: "Suivre Outsider",
          cpress: "La presse en parle",
          c7: "« Je n’ai jamais voulu grandir. J’aurais voulu rester  toujours enfant. »",
          c8: {
              p0: "<strong>Henry Darger est l’une des figures mythiques du XXe siècle et un représentant majeur de l’art brut</strong>. Autodidacte et longtemps resté en marge du monde de l’art, Henry Darger a créé, dans une œuvre unique, un monde singulier et étrange, mêlant imaginaire, récit historique et culture populaire américaine.",
              p1: "Son roman fantastique dactylographié inédit de 15000 pages, <strong>“L’Histoire des Vivian Girls dans ce qui est connu sous le nom des royaumes de l’irréel et de la catastrophe de la Guerre glandelico-angelinienne causée par la révolte des enfants esclaves” - ou “Dans les Royaumes de l’Irréel” - et sa suite manuscrite de 8500 pages “Nouvelles aventures des Vivian Girls à Chicago”</strong> étaient les sagas sur lesquelles il a basé plusieurs centaines d’illustrations panoramiques, beaucoup d'entre elles recto-verso mesurant près de 3 mètres de longueur.",
              bt: "Lire la biographie complète"
          },
          ccollections: "Darger dans les musées",
          theband: "LE GROUPE",
          c9: {
              role: "Claviers, banjo et électronique",
              bio: "<strong>Depuis plus de trois décennies maintenant, Philippe Cohen Solal a fait sa marque en tant qu'architecte de musique électronique et compositeur autodidacte</strong>, ayant collaboré avec nombreux artistes renommés Salif Keita, Angelique Kidjo, Horace Andy, Adrien Brody, Roberto Fonseca, Dorfmeister, Chassol, Bobby McFerrin..."
          },
          moreinfos: "> Plus d'infos",
          c10: {
              role: "Guitare, basse & électronique",
              bio: "<strong>Producteur lauréat du Mercury Music Prize</strong>, Mike Lindsay est surtout connu pour être le co-fondateur, compositeur et producteur du groupe britannique Tunng, considéré comme un des pionniers du genre 'Folktronica', et LUMP avec Laura Marling. Il a également co-écrit et produit de nombreux albums pour un large éventail d'artistes : l'album primé 'Speech Therapy' de Speech Debelle, Jon Hopkins, Farao, Low Roar..."
          },
          c11: {
              role: "Chant",
              bio: "<strong>Adam Glover est un artiste originaire de Manchester</strong>, au Royaume-Uni, où son amour pour le crooning a commencé. Titulaire d’un baccalauréat en musicologie de l'Université de Westminster, Adam réside entre Manchester et Los Angeles, où il travaille avec les meilleurs producteurs."
          },
          c12: {
              role: "Chant, claviers, trombone et violons",
              bio: "<strong>Hannah Peel, artiste nord-irlandaise nommée aux Emmy Awards</strong>, chanteuse, multi-instrumentiste, compositrice électronique décrite par The Observer comme «une grande chanteuse et une Delia Derbyshire de notre époque»."
          },
          theart: "L'ÉQUIPE",
          c14: {
              role: "Vidéaste, directeur artistique",
              bio: "<strong>En 2000, Pascal Gary crée phormazero</strong>, un studio de création aux productions comprenant des visuels en direct, des installations, des vidéos musicales et des concepts visuels uniques pour la télévision, les festivals de musique et d'art contemporain, l’industrie du luxe et de la mode."
          },
          c13: {
              role: "Réalisateur et animateur",
              bio: "<strong>Animateur sur de nombreux films</strong> : Le Portefeuille, Signes de vie, Chahut, Edmond était un âne, Une tête disparaît, L’Ogre, Rivage, ou encore Roughhouse…Il réalise trois courts-métrages RectoVerso, Beuuââârk !!!, Les Démons de Ludwig. Co-réalise L’évasion et La Ferté - Un Cercueil de Béton. Après avoir co-fondé le Studio train train, il s'associe à la boîte de production Rainbox pour son nouveau projet Pylône."
          },
          shop: "Visitez notre boutique",
          contactus: "Contactez-nous",
          sendemail: "Envoyez un email à",
          last: "Ce projet est aussi l'occasion de mettre en lumière la force de la singularité dont Darger est un des puissants symboles, de témoigner de cette richesse infinie, trop souvent ignorée, pour encourager la révélation au monde de cette part de génie.",
          footer: {
              credits0: "<strong>OUTSIDER</strong>, un album musical et projet transmédia inspiré par Henry Darger.",
              credits1: "Dessins & animations par",
              credits2: "Site internet par",
              credits3: "Tous droits réservés",
              credits4: "Consultant production & développement : Laurent Maillaud",
              credits5: "Production cofinancée par PICTANOVO dans le cadre du Fonds Nouveaux Médias avec le soutien de la Région Hauts-de-France et du Centre National du Cinéma et de l’image animée."
          },
          scroll: "SCROLLER",
          podcastLink: "https://embed.acast.com/outsider-histoire-henry-darger",
          morepodcastsLink: "https://smarturl.it/outsider.podcast"
        }
      }
    }
  },
  mounted() {
    // fetch('/data/txt.json')
    //   .then(r => r.json())
    //   .then(json => {
    //     this.text = json.text[this.lang]
    //   })

    let twitterScript = document.createElement('script')
    twitterScript.setAttribute('src', 'https://platform.twitter.com/widgets.js')
    document.head.appendChild(twitterScript)

    let skScript = document.createElement('script')
    skScript.setAttribute('src', '//widget.songkick.com/3653951/widget.js')
    document.head.appendChild(skScript)
  },
  created() {
    let that = this
    window.addEventListener('scroll', hideScrollHandler)
    function hideScrollHandler() {
      that.showScroll = false
      window.removeEventListener('scroll', hideScrollHandler)
    }

    window.addEventListener('scroll', showOverlay)
    function showOverlay() {    
      if(window.pageYOffset > 8000){
        that.showOverlay = true
        window.removeEventListener('scroll', showOverlay)
      }
    }

    if(window.innerWidth <= 414)
      this.isMobile = true

    this.date = new Date().getFullYear()

    this.translatedTxt = this.text[this.lang]
    EventBus.$on('langChanged', this.langChangedHandler)
  },
  methods: {
    // sendEmail(e) {
    //   let that = this
    //   emailjs.sendForm('service_gw9j3rs', 'template_ngoxb8p', e.target, 'user_QNhhPaiTt2jfg3bENI2Xi')
    //     .then((result) => {
    //         console.log('SUCCESS!', result.status, result.text)
    //         that.emailResponse = 'Your message has been sent !'
    //     }, (error) => {
    //         console.log('FAILED...', error)
    //         that.emailResponse = "Oops ! An error occured :/"
    //     })
    // }
    
    langChangedHandler(lang){
      this.lang = lang
      this.translatedTxt = this.text[this.lang]
      this.$forceUpdate()
    }
  }
}
</script>
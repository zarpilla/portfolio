<template>
  <div>
    <div class="container">
      <div class="content">
        <h1>PORTFOLIO</h1>
        <p>Some works</p>

        <nav class="level is-hidden-mobile">
          <div class="level-right">
            <p v-for="cat in categories" v-bind:key="cat.id" class="level-item">
              <span v-if="category == cat.id">{{ cat.name }}</span>
              <a @click="category = cat.id" v-if="category != cat.id">{{ cat.name }}</a>
            </p>
          </div>
        </nav>
      </div>
    </div>

    <div class="container-fluid">
      <div class="columns is-desktop portfolio">
        <div class="column is-4">
          <div class="img-container" v-for="(item, index) in items1" v-bind:key="index">
            <Project v-bind:item="item" v-bind:category="category"></Project>
          </div>
        </div>
        <div class="column is-4">
          <div class="img-container" v-for="(item, index) in items2" v-bind:key="index">
            <Project v-bind:item="item" v-bind:category="category"></Project>
          </div>
        </div>
        <div class="column is-4">
          <div class="img-container" v-for="(item, index) in items3" v-bind:key="index">
            <Project v-bind:item="item" v-bind:category="category"></Project>
          </div>
        </div>
      </div>
    </div>

    <div class="container">
      <div class="content">
        <h1>CONTACT</h1>
        <p>hola@webcoop.cat</p>
      </div>
    </div>
  </div>
</template>

<script>
import Project from '~/components/Project.vue'

export default {
  components: {
    Project
  },
  data () {
    return {
      category: 'all'
    }
  },
  async asyncData ({ params }) {
    const cats = await [
      {
        id: 'all',
        name: 'All'
      },
      {
        id: 'javascript',
        name: 'Javascript'
      },
      {
        id: 'angular',
        name: 'Angular'
      },
      {
        id: 'vue',
        name: 'Vue'
      },
      {
        id: 'node',
        name: 'Node'
      },
      {
        id: 'nuxt',
        name: 'Nuxt'
      },
      {
        id: 'speed',
        name: 'Awesome page speed'
      },
      {
        id: 'aws',
        name: 'AWS'
      },
      {
        id: 'spa',
        name: 'SPA'
      },
      {
        id: 'firebase',
        name: 'Firebase'
      },
      {
        id: 'wordpress',
        name: 'Wordpress'
      },
      {
        id: 'woocommerce',
        name: 'Woocommerce'
      },
      {
        id: 'php',
        name: 'PHP'
      }
    ]

    const items = await [
      {
        name: 'Website',
        type: 'Frontend: Nuxt',
        href: 'https://webcoop.cat',
        img: 'https://res.cloudinary.com/dxk1jxscn/image/fetch/v1590397433/https://webcoop.cat/_nuxt/img/3801dd1.jpg',
        alt: '',
        client: 'webcoop.cat',
        tags: ['vue', 'nuxt', 'javascript', 'speed']
      },
      {
        name: 'Map widget',
        type: 'Frontend: Angular, Backend: Node,AWS',
        href: 'https://map.closer2Event.com/?event=cruilla',
        img: 'https://res.cloudinary.com/dxk1jxscn/image/upload/v1590499908/Screenshot_2020-05-26_RebusTech_uoah8o.png',
        alt: '',
        client: 'Closer2Event',
        tags: ['angular', 'node', 'aws', 'javascript', 'spa']
      },
      {
        name: 'Custom LMS',
        type: 'Frontend: Vue, Backend: Firebase',
        href: 'https://educov.cat',
        img: 'https://res.cloudinary.com/dxk1jxscn/image/upload/v1590501979/Screenshot_2020-05-26_EDUCOV_-_Reptes_i_recursos_educatius_en_directe_p%C3%BAblics_gratu%C3%AFts_i_oberts_hwm4sg.png',
        alt: '',
        client: 'webcoop.cat',
        tags: ['vue', 'firebase', 'javascript', 'spa']
      },
      {
        name: 'Website',
        type: 'Frontend: Nuxt',
        href: 'https://closer2Event.com',
        img: 'https://res.cloudinary.com/dxk1jxscn/image/upload/v1590500031/Screenshot_2020-05-26_Showcases_-_Closer2event_zn3rxa.png',
        alt: '',
        client: 'Closer2Event',
        tags: ['vue', 'nuxt', 'javascript']
      },
      {
        name: 'This portfolio',
        type: 'Frontend: Nuxt',
        href: 'https://demo.webcoop.cat/portfolio',
        img: 'https://res.cloudinary.com/dxk1jxscn/image/upload/v1590506832/Screenshot_2020-05-26_portfolio_pjoz5g.png',
        alt: '',
        client: 'webcoop.cat',
        tags: ['vue', 'nuxt', 'speed', 'javascript']
      },
      {
        name: 'Dashboards',
        type: 'Frontend: AngularJs, Backend: .Net',
        href: 'https://cloud.mapex.es/dashboards/',
        img: 'https://res.cloudinary.com/dxk1jxscn/image/upload/v1590500261/Screenshot_2020-05-26_Detalle_de_m%C3%A1quina_dark_theme_-_Mapex_Dashboards_1_sakr4i.png',
        alt: '',
        client: 'Mapex',
        tags: ['angularjs', 'net', 'javascript']
      },
      {
        name: 'VR backoffice',
        type: 'Frontend: Vue, Backend: PHP, Stripe',
        href: 'https://www.lightboxar.com/app/',
        img: 'https://res.cloudinary.com/dxk1jxscn/image/upload/v1590501553/Screenshot_2020-05-26_Lightbox_-_Immersive_product_visualization_yyrgze.png',
        alt: '',
        client: 'Virtual Age',
        tags: ['vue', 'php', 'javascript']
      },
      {
        name: 'Dynamic compilation',
        type: 'Frontend: Angular, Backend: .Net Core',
        href: 'https://mapexcloud2.azurewebsites.net/',
        img: 'https://res.cloudinary.com/dxk1jxscn/image/upload/v1590501412/Screenshot_2020-05-26_Developer_Tools_-_Mapex_ggw6bq.png',
        alt: '',
        client: 'Mapex',
        tags: ['angular', 'net', 'javascript', 'spa']
      },
      {
        name: 'IoT Agro Sensors',
        type: 'Frontend: Angular',
        href: 'https://app.sigrow.com/webapp/',
        img: 'https://res.cloudinary.com/dxk1jxscn/image/upload/v1590501729/Screenshot_2020-05-26_SIGROW_l3orzt.png',
        alt: '',
        client: 'Sigrow',
        tags: ['angular', 'javascript', 'spa']
      },
      {
        name: 'SPA',
        type: 'Frontend: Vue, Backend: Firebase',
        href: 'https://suportdarrel.webcoop.cat/',
        img: 'https://res.cloudinary.com/dxk1jxscn/image/upload/v1590502939/7c2bd0c_c1zvsf.png',
        alt: '',
        client: "Suport d'Arrel",
        tags: ['vue', 'firebase', 'javascript', 'spa']
      },
      {
        name: 'SPA',
        type: 'Frontend: HTML, Javascript',
        href: 'https://demo.webcoop.cat/sismograf',
        img: 'https://res.cloudinary.com/dxk1jxscn/image/upload/v1590507227/Screenshot_2020-05-26_sismograf_jfd0do.png',
        alt: '',
        client: 'Sismògraf ESS',
        tags: ['javascript', 'javascript', 'spa']
      },
      {
        name: 'Ecommerce',
        type: 'Woocommerce',
        href: 'https://ekomercat.com',
        img: 'https://res.cloudinary.com/dxk1jxscn/image/upload/v1590502277/Screenshot_2020-05-26_L_EKOmERCAT_El_petit_mercat_de_productors_ecol%C3%B2gics_de_proximitat_i_artesans_ybnhht.png',
        alt: '',
        client: 'webcoop',
        tags: ['wordpress', 'php', 'woocommerce']
      },
      {
        name: 'Ecommerce',
        type: 'Woocommerce',
        href: 'https://planasforestaljardineria.com',
        img: 'https://res.cloudinary.com/dxk1jxscn/image/upload/v1590502488/Screenshot_2020-05-26_Forestal_i_Jardineria_Planas_Forestal_i_Jardineria_oacje7.png',
        alt: '',
        client: 'Planas Forestal Jardineria',
        tags: ['wordpress', 'php', 'woocommerce']
      },
      {
        name: 'Website',
        type: 'Wordpress',
        href: 'https://www.tutelardelripolles.cat/',
        img: 'https://res.cloudinary.com/dxk1jxscn/image/upload/v1590502647/Screenshot_2020-05-26_Tutelar_del_Ripoll%C3%A8s_Fundaci%C3%B3_Tutelar_del_Ripoll%C3%A8s_bq1sbe.png',
        alt: '',
        client: 'Fundació Tutelar del Ripollès',
        tags: ['wordpress']
      },
      {
        name: 'Website',
        type: 'Wordpress',
        href: 'https://fessrural.cat/',
        img: 'https://res.cloudinary.com/dxk1jxscn/image/upload/v1590502759/Screenshot_2020-05-26_FESS_Rural_Festival_de_l_Economia_Social_i_Solid%C3%A0ria_rural_op2hrl.png',
        alt: '',
        client: 'FESS Rural',
        tags: ['wordpress']
      },
      {
        name: 'Presentation',
        type: 'HTML, Javascript',
        href: 'https://anarfentbdt.cat/presentacio/',
        img: 'https://res.cloudinary.com/dxk1jxscn/image/upload/v1590514162/Screenshot_2020-05-26_Banc_del_temps_del_Ripoll%C3%A8s_fpqnwx.png',
        alt: '',
        client: 'XES Ripollès',
        tags: ['javascript', 'spa']
      },
      {
        name: 'Website',
        type: 'Wordpress',
        href: 'https://anarfentbdt.cat/',
        img: 'https://res.cloudinary.com/dxk1jxscn/image/upload/v1590505882/logo-fem-util-300x162_nknxlq.png',
        alt: '',
        client: 'XES Ripollès',
        tags: ['wordpress']
      }
    ]
    return { categories: cats, items1: items.filter((it, i) => i % 3 === 0), items2: items.filter((it, i) => i % 3 === 1), items3: items.filter((it, i) => i % 3 === 2) }
  }
}
</script>

<style>
.content {
  margin: 4rem 0.75rem;
}
.column {
  padding: 0;
}
a{
  color: #1e9e6b;
}
.portfolio .img-container {
  overflow: hidden;
  position: relative;
}
.portfolio .img-container:hover img {
  overflow: hidden;
  transform: scale(1);
}
.portfolio .gallery-hover {
  position: absolute;
  left: -30px;
  bottom: -100px;
  width: 351px;
  height: 351px;
  background: #1e9e6b;
  border-radius: 50%;
  transition: 0.3s;
  opacity: 0;
}
.portfolio .img-container:hover .gallery-hover {
  opacity: 0.95;
}
.portfolio .img-container .hover-inner {
  margin-top: 140px;
  margin-left: 50px;
}
.portfolio .img-container .hover-inner {
  color: #fff;
  font-size: 0.9rem;
}
.portfolio .img-container .hover-inner .name{
  font-size: 1.5rem;
  font-weight: 500;
  display: block;
}
.portfolio img {
  margin-bottom: -7px;
  transition: 0.3s;
  transform: scale(1.1);
  width: 100%;
}
.content p:last-child{
  margin-bottom:1rem;
}

@media only screen and (max-width: 769px) {
  .portfolio .img-container .gallery-hover {
  opacity: 0.85;
}
}

</style>

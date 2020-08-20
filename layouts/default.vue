<template>
  <section>
    <!-- <div> -->
        
            <b-navbar>
                <template slot="brand">
                    <b-navbar-item tag="router-link" :to="{ path: '/' }">
                        <img
                            src="~assets/ivt.png"
                            alt="Logo"
                        >
                        <p>- H A L O ~ P R O P E R T I -</p>
                    </b-navbar-item>
                </template>
                <template slot="end">
                    <b-navbar-dropdown label="Bahasa">
                        <b-navbar-item href="#">
                            Indonesia
                        </b-navbar-item>
                        <b-navbar-item href="#">
                            Bahasa Inggris
                        </b-navbar-item>
                    </b-navbar-dropdown>
                    <b-navbar-item href="#">
                        Masuk
                    </b-navbar-item>
                    <b-navbar-item href="#">
                        Gabung
                    </b-navbar-item>
                    
                </template>

                <template slot="start">
                    <b-navbar-item tag="div">
                        <p class="control ">
                        <input class="input" type="text" placeholder="Apa yang akan dicari">
                        <!-- <span class="icon is-left">
                            <ion-icon name="search-outline"></ion-icon>
                            <icon name="search" aria-hidden="true"></icon>
                        </span> -->
                        </p>
                    </b-navbar-item>
                </template>
            </b-navbar>
        
    <!-- </div> -->
    <div class="container">
    <b-carousel
        :autoplay="true"
        with-carousel-list
        :indicator="true"
        :overlay="gallery"
        @click="switchGallery(true)">
        <b-carousel-item v-for="(item, i) in items" :key="i">
            <figure class="image-u">
                <img :src="item.image">
            </figure>
        </b-carousel-item>
    </b-carousel>
    </div>

    <div class="container has-text-centered">
      <h1 class="title">Jelajahi Market Kami</h1>
    </div>

    <div class="container">
    <div class="columns is-multiline is-mobile is-variable has-text-centered">
        <div class="column-button is-one-third">
            <img class="img-b" src="~assets/banner/010-storefront.png">
            <p>Voucher Belanja</p>
        </div>
        <div class="column-button is-one-third">
            <img class="img-b" src="~assets/026-price.png">
            <p>Voucher Belanja</p>
        </div>
        <div class="column-button is-one-third">
            <img class="img-b" src="~assets/027-system.png">
            <p>Voucher Belanja</p>
        </div>
        <div class="column-button is-one-third">
            <img class="img-b" src="~assets/030-website.png">
            <p>Voucher Belanja</p>
        </div>
        <div class="column-button is-one-third">
            <img class="img-b" src="~assets/013-banking.png">
            <p>Voucher Belanja</p>
        </div>
        <div class="column-button is-one-third">
            <img class="img-b" src="~assets/017-voucher.png">
            <p>Voucher Belanja</p>
        </div>
    </div>
    </div>

    <div class="container">
    <b-carousel
        :autoplay="true"
        with-carousel-list
        :indicator="true"
        :overlay="gallery"
        @click="switchGallery(true)">
        <b-carousel-item v-for="(item, i) in items" :key="i">
            <figure class="image-u">
                <img :src="item.image">
            </figure>
        </b-carousel-item>
    </b-carousel>
    </div>

<div class="container">
      <h2 class="title">Lihat Karya Mereka</h2>
</div>

<div class="container is-mobile">
    <b-carousel-list v-model="test" :data="items" :items-to-show="4">
        <template slot="item" slot-scope="props">
            <figure class="image ">
                <a @click="info(props.index)"><img :src="props.list.image"></a>
            </figure>
        </template>
    </b-carousel-list>
</div>

<div class="container">
    <div class="columns is-multiline is-mobile is-variable">
        <div class="column is-one-third" v-for="(item, i) in items" :key="i">
        <div class="card" >
            <div class="columns is-half">
               <div class="column">
                    <figure class="image-figure">
                        <img :src="item.image">
                    </figure>  
                </div>
                <div class="column">
                    <p>Voucher Belanja</p>
                    <p class="control" v-if="items.rating">
                        <b-rate :value="items.rating" show-score="disabled"/>
                    </p>
                    <hr>
                    <b-rate
                        v-model="rate"
                        :icon-pack="packs"
                        :icon="icons"
                        :max="maxs"
                        :size="sizes"
                        :locale="locale"
                        :show-score="score"
                        :custom-text="custom"
                        :show-text="text"
                        :texts="texts"
                        :rtl="isRtl"
                        :spaced="isSpaced"
                        :disabled="isDisabled">
                    </b-rate>
                </div> 
            </div> 
        </div>
        </div>
    </div>
</div>
<div>
    <div class="column">

    </div>
</div>
    <div>
        <footer class="footer">
            <div class="content">
                <div class="columns">
                    <div class="column">
                        <h1>Halo Properti</h1>
                    </div>
                    <div class="column">
                        <div class="columns"><h2></h2></div>
                        <div class="columns"><h3>Tentang Kami</h3></div>
                        <div class="columns"><h3>Patner Kami</h3></div>
                        <div class="columns"><h3>Blog</h3></div>
                        <div class="columns"><h3>Layanan</h3></div>
                    </div>
                    <div class="column">
                        <div class="columns"><h2></h2></div>
                        <div class="columns"><h3>Pusat Bantuan</h3></div>
                        <div class="columns"><h3>Kontak Kami</h3></div>
                        <div class="columns"><h3>Syarat & Ketentuan</h3></div>
                        <div class="columns"><h3>Kebijakan Privasi</h3></div>
                    </div>
                    <div class="column">
                        <div class="columns"><h2></h2></div>
                        <div class="columns"><h3>Unduh Aplikasi</h3></div>
                        <div class="columns"><img class="image-0" src="~assets/ivt.png" alt="download"></div>
                        <div class="columns"><h3>Ikuti Kami</h3></div>
                        <div class="columns">
                            <div class="column"><a href="#">FB</a></div>
                            <div class="column"><a href="#">IG</a></div>
                            <div class="column"><a href="#">TW</a></div>
                            <div class="column"><a href="#">YT</a></div>
                        </div>
                    </div>
                </div>
                <!-- <p>
                    <strong>Bulma</strong> by <a href="https://jgthms.com">Jeremy Thomas</a>. The source code is licensed
                    <a href="http://opensource.org/licenses/mit-license.php">MIT</a>. The website content
                    is licensed <a href="http://creativecommons.org/licenses/by-nc-sa/4.0/">CC BY NC SA 4.0</a>.
                </p>
                <p>
                  Icons made by <a href="https://www.flaticon.com/authors/eucalyp" title="Eucalyp">Eucalyp</a> from <a href="https://www.flaticon.com/" title="Flaticon"> www.flaticon.com</a>
                </p> -->
            </div>
        </footer>
    </div>
  </section>
</template>


<script>
export default {
    data() {
        return {
            rate: 4.6,
            maxs: 5,
            sizes:'',
            packs:'mdi',
            icons:'star',
            score:false,
            custom:'',
            text:false,
            texts:['Very bad','Bad','Good','Very Good','Awesome'],
            isRtl:false,
            isSpaced:false,
            isDisabled:true,
            locale:undefined,
            
            animated: 'slide',
            drag: false,
            autoPlay: true,
            pauseHover: false,
            pauseInfo: false,
            repeat: true,
            pauseType: 'is-primary',
            carousel: 0,
            // interval: 3000,
            carousels: [
                { title: 'Slide 1', image: 'https://image.freepik.com/free-vector/wireframe-landscape-banner-design_1048-12316.jpg' },
                { title: 'Slide 2', image: 'https://image.freepik.com/free-vector/wireframe-landscape-banner-design_1048-12316.jpg' },
                { title: 'Slide 3', image: 'https://image.freepik.com/free-vector/wireframe-landscape-banner-design_1048-12316.jpg' },
                { title: 'Slide 4', image: 'https://image.freepik.com/free-vector/wireframe-landscape-banner-design_1048-12316.jpg' },
                { title: 'Slide 5', image: 'https://image.freepik.com/free-vector/wireframe-landscape-banner-design_1048-12316.jpg' },
                { title: 'Slide 6', image: 'https://image.freepik.com/free-vector/wireframe-landscape-banner-design_1048-12316.jpg' },
            ],
            test: 0,
            items: [
                {
                    title: 'Slide 1',
                    image: 'https://cdna.artstation.com/p/assets/images/images/010/098/130/large/sajal-kr-chand-flat-landscape.jpg?1522574693',
                    rating: 4.4
                },
                {
                    title: 'Slide 2',
                    image: 'https://mir-s3-cdn-cf.behance.net/project_modules/max_1200/7db5c985847371.5d8898692240d.jpg',
                    rating: 3.5
                },
                {
                    title: 'Slide 3',
                    image: 'https://mir-s3-cdn-cf.behance.net/project_modules/max_1200/49e7f485847371.5d8898692146c.jpg',
                    rating: 5
                },
                {
                    title: 'Slide 1',
                    image: 'https://cdna.artstation.com/p/assets/images/images/010/098/130/large/sajal-kr-chand-flat-landscape.jpg?1522574693',
                    rating: 4.4
                },
                {
                    title: 'Slide 2',
                    image: 'https://mir-s3-cdn-cf.behance.net/project_modules/max_1200/7db5c985847371.5d8898692240d.jpg',
                    rating: 3.5
                },
                {
                    title: 'Slide 3',
                    image: 'https://mir-s3-cdn-cf.behance.net/project_modules/max_1200/49e7f485847371.5d8898692146c.jpg',
                    rating: 5
                },
                // {
                //     title: 'Slide 7',
                //     image: 'https://buefy.org/static/img/placeholder-1280x960.png',
                //     rating: 2.7
                // },
                // {
                //     title: 'Slide 8',
                //     image: 'https://buefy.org/static/img/placeholder-1280x960.png',
                //     rating: 1.5
                // }
            ]
        }
    },
    // methods: {
    //     info(value) {
    //         this.carousel = value
    //         this.$buefy.toast.open({
    //             message: `This Slide ${value} !`,
    //             type: 'is-info'
    //         })
    //     }
    // }
}
</script>

<style>
.container{
    margin-bottom: 3rem;
}
.carousel-list .carousel-slides .carousel-slide {
    margin-right: 0rem !important;
    margin-bottom: 0rem !important;
    
}
.img-b{
    width: 35%;
    height: auto;
}

.carousel-list.has-shadow {
    -webkit-box-shadow: none;
    box-shadow: none;
}
.image img {
    /* display: block; */
    height: 16rem;
    width: 15rem;
    border-radius: 2rem;
}
/* .columns.is-mobile > .column.is-one-third {
    -webkit-box-flex: 0;
    -ms-flex: none;
    flex: none;
    width: 33.3%;
    padding: 5rem;
} */
.title{
    color: blue;
}
.columns.is-mobile .column.is-one-third {
    width: 30.3%;
    flex: 0 0 auto;
    padding: 0rem;
    margin-left: 1.5rem;
    margin-right: 0rem;
    margin-top: 0rem;
    margin-bottom: 2rem;
    column-gap: 1.5rem;
}
.column-button{
   width: 30.3%;
    flex: 0 0 auto;
    padding: 0rem;
    margin-left: 1.5rem;
    margin-right: 0rem;
    margin-top: 0rem;
    margin-bottom: 2rem;
    column-gap: 1.5rem;
}
.columns {
    margin-left: 0rem;
    margin-right: 0rem;
    margin-top: 0rem;
    margin-bottom: 0rem;
}
.card {
    background-color: white;
    -webkit-box-shadow: 0 2px 3px rgba(10, 10, 10, 0.1), 0 0 0 1px rgba(10, 10, 10, 0.1);
    box-shadow: 0 2px 3px rgba(10, 10, 10, 0.1), 0 0 0 1px rgba(10, 10, 10, 0.1);
    color: #4a4a4a;
    max-width: 100%;
    position: relative;
    border-radius: 8px;
}
.image-u img {
    display: block;
    width: 100%;
    max-height: 20rem;
    border-radius: 10px;
}
.image-figure img {
    display: block;
    width: 100%;
    max-height: 20rem;
    border-radius: 10px;
}
.footer {
    background-color: #000080;
    padding: 0rem 1.5rem 6rem;
}
.content h1,.content h2,.content h3 {
    color: azure;
    font-weight: 600;
    line-height: 1.125;
}
</style>

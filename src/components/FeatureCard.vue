<template>
    <div class="card"  @click="openPost(feature)">
        <div class="card-body">
          <h3>{{feature.title}}</h3>
          <p>{{ feature.description}}</p>
        </div>
    </div>
</template>

<script>
export default {
    props: ["feature"],
    methods: {
        openPost(post) {
        }
    }    
}
</script>

<style lang="scss" scoped>
    .card {
        height: auto;
        width: 100%;
        margin: 0 25px 50px;
        border-radius: 10px;
        overflow: hidden;
        padding-bottom: 30px;
        .image-wrapper {
            height: 180px;
            width: 100%;
            overflow: hidden;
            margin-bottom: 20px;
            .image {
                height: inherit;
                width: inherit;
                background-size: cover;
                background-position: center center;
                transition: all 300ms ease-in-out;
            }
        }
        .card-body {
            padding: 0;
            text-align: left;
            opacity: .8;
            transition: all 200ms ease-in-out;
            position: relative;
            h3 {
                font-size: 22px;
                margin-bottom: 15px;
                line-height: 1.35;
            }
            p {
                margin-bottom: 10px;
            }
            span.more {
                position: absolute;
                bottom: -50px;
                left: 0;
                opacity: 0;
                font-style: italic;
                transition: all 200ms ease-in-out;
            }
        }
        &:hover {
            .image {
                transform: scale(1.1);
            }
            .card-body {
                opacity: 1;
            }
            span.more {
                opacity: 1;
                bottom: -40px;
            }
        }
        
    }
   @media only screen and (max-width: 920px)  {
       .card {
           margin-bottom: 50px;
           width: calc(50% - 50px);
           .image-wrapper {
               height: 200px;
           }
       }
   }
   @media only screen and (max-width: 740px)  {
       .card {
           margin-bottom: 50px;
           width: 100%;
           .image-wrapper {
               height: 250px;
           }
       }
   }
</style>
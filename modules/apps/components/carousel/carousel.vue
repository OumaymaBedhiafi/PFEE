<template>
  <div>
    <a-carousel
      :autoplay="true"
      :dots="false"
      :infinite="true"
      :slides-to-scroll="1"
    >
      <a-carousel-slide
        v-for="(item, index) in carouselItems"
        :key="index"
      >
        <div class="item">
          <img
            :src="item.imageSrc"
            alt="carousel item"
          >
          <div class="item-details">
            <div class="item-title">
              {{ item.title }}
            </div>
            <div class="item-subtitle">
              {{ item.subtitle }}
            </div>
            <a-icon
              :type="item.iconType"
              :theme="item.iconTheme"
            />
          </div>
        </div>
      </a-carousel-slide>
    </a-carousel>
    <div class="see-all">
      <a-button
        type="primary"
        icon="search"
      >
        Voir tout
      </a-button>
    </div>
  </div>
</template>
  
  <script>
  export default {
    data() {
      return {
        carouselItems: [
          {
            imageSrc: 'https://example.com/image1.jpg',
            title: 'Titre de l\'item 1',
            subtitle: 'Sous-titre de l\'item 1',
            iconType: 'user',
            iconTheme: 'outlined',
          },
          {
            imageSrc: 'https://example.com/image2.jpg',
            title: 'Titre de l\'item 2',
            subtitle: 'Sous-titre de l\'item 2',
            iconType: 'star',
            iconTheme: 'filled',
          },
          {
            imageSrc: 'https://example.com/image3.jpg',
            title: 'Titre de l\'item 3',
            subtitle: 'Sous-titre de l\'item 3',
            iconType: 'heart',
            iconTheme: 'filled',
          },
        ],
      };
    },
  };
  </script>
  
  <style scoped>
  .item {
    position: relative;
    height: 200px;
  }
  
  .item img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
  
  .item-details {
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    background-color: rgba(0, 0, 0, 0.5);
    padding: 10px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    color: #fff;
  }
  
  .item-title {
    font-size: 24px;
    font-weight: bold;
  }
  
  .item-subtitle {
    font-size: 18px;
  }
  
  .see-all {
    display: flex;
    justify-content: flex-end;
    margin-top: 10px;
  }
  </style>
  
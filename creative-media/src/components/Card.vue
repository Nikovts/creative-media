<template>
  <div class="card">
    <img class="card-image" :src="imageUrl"/>
    <div class="card-data">
      <div class="card-details">
        <h3 class="card-title">{{item.title}}</h3>
        <ul>
          <li class="card-points" v-for="point,i in item.points" :key="i">
            {{point}}
          </li>
        </ul>
        <p class="card-description">{{ item.description }}</p>
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps(['item'])
const imageUrl = new URL(`../assets/${props.item.img}.jpg`, import.meta.url).href
</script>

<style lang="scss">
  .card {
    display: flex;
    flex-direction: row;
    align-items: flex-start;
    background: #FFFFFF;
    border-radius: 8px;
  }

  .card-image {
    width: 11.46rem;
    height: 21rem;
    border-radius: 8px 0px 0px 8px;
  }

  .card-data {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    padding: 2.5rem 1.875rem 2.125rem 2.125rem;
    gap: 1.875rem;

    width: 15.875rem;
    height: 21rem;
  }
  .card-details {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
    gap: 0.75rem;

    .card-title {
      font-family: 'Poppins';
      font-weight: 700;
      font-size: 1.5rem;
      line-height: 2rem;
      font-feature-settings: 'salt' on, 'liga' off;
      color: #353844;
    }

    ul {
      width: 11.81rem;
      list-style: none;
      margin-block-start: 0;
      padding-inline-start: 0;
    }

    li::before {
      content: "•";
      color: #D2AD81;
      margin-right: 0.5rem;
    }

    .card-points {
      width: 11.81rem;
      font-family: 'Nunito Sans';
      font-style: normal;
      font-weight: 700;
      font-size: 0.9375rem;
      line-height: 1.625rem;
      font-feature-settings: 'salt' on, 'liga' off;
      color: #353844;
    }

    .card-description {
      width: 11.81rem;
      font-family: 'Nunito Sans';
      font-style: normal;
      font-weight: 600;
      font-size: 0.9375rem;
      line-height: 1.5rem;
      font-feature-settings: 'salt' on, 'liga' off;
      color: #353844;
    }

  }

</style>
<template>
  <div class="container-fluid foods-container">
    <div class="row justify-content-center foods-row-container">
      <div class="col-lg-8 foods-column-container">
        <h1>Goodies you will surely</h1>
        <p class="rotatingText">
          <span class="rotatingText-adjective">love</span>
          <span class="rotatingText-adjective">crave</span>
          <span class="rotatingText-adjective">remember</span>
        </p>
      </div>
    </div>
    <div class="row justify-content-center foods-form-row">
      <div class="col-lg-8 foods-form-column"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Foods",
  components: {},
};
</script>

<style lang="scss">
.foods-container {
  background-color: #fafafa;
  height: 100vh;
  .foods-row-container {
    margin-top: 50px;
    padding-top: 30px;
    .foods-column-container {
      text-align: center;

      .rotatingText {
        .rotatingText-adjective {
          position: absolute;
          top: -5px;
          left: 230px;
          font-size: 40px;
          opacity: 0;
          &:nth-child(1) {
            left: 860px;
          }
          &:nth-child(2) {
            left: 860px;
          }
          &:nth-child(3) {
            left: 860px;
          }
        }
        .rotatingText-adjective:nth-of-type(1) {
          animation-name: rotate;
          animation-duration: 1.5s;
          animation-delay: 2s;
          animation: rotate 5s infinite;
        }

        .rotatingText-adjective:nth-of-type(2) {
          animation-name: rotate-second;
          animation-duration: 1.5s;
          animation-delay: 2s;
          animation: rotate-second 5s infinite;
        }

        .rotatingText-adjective:nth-of-type(3) {
          animation-name: rotate-three;
          animation-duration: 1.5s;
          animation-delay: 2s;
          animation: rotate-three 5s infinite;
        }
        @keyframes rotate {
          10% {
            opacity: 0;
            transform: translate3d(0, 50px, 0);
          }

          30% {
            opacity: 1;
            color: #007db6;
            transform: translate3d(0, 0, 0);
          }

          40% {
            opacity: 0;
            transform: translate3d(0, -25px, 0);
          }
        }

        @keyframes rotate-second {
          30% {
            opacity: 0;
            transform: translate3d(0, 50px, 0);
          }

          60% {
            opacity: 1;
            color: #ffe400;
            z-index: 111;
            transform: translate3d(0, 0, 0);
          }

          70% {
            opacity: 0;
            transform: translate3d(0, -25px, 0);
          }
        }

        @keyframes rotate-three {
          60% {
            opacity: 0;
            transform: translate3d(0, 50px, 0);
          }

          90% {
            opacity: 1;
            color: #ff4b4b;
            transform: translate3d(0, 0, 0);
          }

          100% {
            opacity: 0;
            transform: translate3d(0, -25px, 0);
          }
        }
      }
    }
  }

  .foods-form-row {
    padding-top: 30px;

    .foods-form-column {
      border-top: 1px solid black;
    }
  }
}
</style>

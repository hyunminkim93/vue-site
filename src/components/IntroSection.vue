<template>
  <section id="intro">
    <div class="intro__inner">
      <h2 class="intro__title">port developer</h2>
      <div class="intro__lines" aria-hidden="true">
        <span class="line"></span>
        <span class="line"></span>
        <span class="line"></span>
        <span class="line"></span>
        <span class="line"></span>
        <span class="line"></span>
        <span class="line"></span>
      </div>
      <div class="intro__text">
        <div class="text">
          <div>Turning challenges</div>
          <div>into opportunities through</div>
          <div>code.</div>
        </div>
        <div class="img">
          <img src="https://images.unsplash.com/photo-1595708615852-4dbfb63e19f7?w=800&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MzQzfHxmYWNlfGVufDB8fDB8fHww" alt="나" />
        </div>
      </div>
      <div class="intro__lines bottom" aria-hidden="true">
        <span class="line"></span>
        <span class="line"></span>
        <span class="line"></span>
        <span class="line"></span>
        <span class="line"></span>
        <span class="line"></span>
        <span class="line"></span>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
#intro {
  height: 100vh;
  background-color: #121212;
  color: #ffffff;

  .intro__inner {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    padding: 16px;

    .intro__title {
      font-size: 8.4vw;
      line-height: 1.4;
      font-weight: 800;
      white-space: nowrap;
      text-transform: uppercase;
      letter-spacing: -0.3vw;
      animation: fadeIn 1s ease-in-out;
    }

    .intro__lines {
      width: 100%;
      margin: 20px 0;

      .line {
        height: 1px;
        background-color: #ffffff;
        margin-bottom: 0.5vw;
        display: block;
        animation: grow 1s ease-in-out forwards;

        &:nth-child(2) {
          animation-delay: 0.2s;
        }
        &:nth-child(3) {
          animation-delay: 0.4s;
        }
        &:nth-child(4) {
          animation-delay: 0.6s;
        }
        &:nth-child(5) {
          animation-delay: 0.8s;
        }
        &:nth-child(6) {
          animation-delay: 1s;
        }
        &:nth-child(7) {
          animation-delay: 1.2s;
        }
      }
    }

    .intro__text {
      display: flex;
      width: 100%;
      height: 40vh;
      background-color: #1f1f1f;
      color: #ffffff;
      align-items: center;
      justify-content: center;
      flex-direction: column;
      position: relative;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);

      .text {
        font-size: 3vw;
        line-height: 1.2;
        font-weight: 900;
        text-transform: uppercase;
        text-align: center;
        position: relative;
        z-index: 100;
        transition: all 0.3s;
        cursor: pointer;
        text-decoration: none;
        color: #f0f0f0;

        &:hover {
          color: #ff4081;
          text-shadow: 0 0 10px #ff4081;
        }
      }

      .img {
        position: absolute;
        left: 50%;
        top: 50%;
        transform: translate(-50%, -50%);
        width: 30vh;
        height: 30vh;
        border-radius: 50%;
        overflow: hidden;
        filter: grayscale(100%);
        transition: all 0.3s;

        img {
          width: 100%;
          height: 100%;
          object-fit: cover;
        }

        &:hover {
          filter: grayscale(0%);
          transform: translate(-50%, -50%) scale(1.1);
        }
      }
    }
  }

  @keyframes fadeIn {
    from {
      opacity: 0;
    }
    to {
      opacity: 1;
    }
  }

  @keyframes grow {
    from {
      width: 0;
    }
    to {
      width: 100%;
    }
  }
}
</style>

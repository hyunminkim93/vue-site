<template>
  <header id="header" role="banner">
    <div class="header__inner">
      <h1 class="header__logo">
        <a href="#">Portfolio<em>vue.js</em></a>
      </h1>
      <nav class="header__nav" role="navigation" aria-label="메인 메뉴">
        <ul>
          <li><a href="#intro">intro</a></li>
          <li><a href="#skill">skill</a></li>
          <li><a href="#site">site</a></li>
          <li><a href="#portfolio">portfolio</a></li>
          <li><a href="#contact">contact</a></li>
        </ul>
      </nav>
      <div class="header__nav__mobile" id="headerToggle" aria-controls="primary-menu" aria-expanded="false">
        <span></span>
      </div>
    </div>
  </header>
</template>

<style lang="scss">
@import '@/assets/scss/mixin';
#header {
  @include position-fixed;
  z-index: 10000;

  .header__inner {
    @include flex-between;
    background-color: rgba(116, 99, 99, 0.1);
    backdrop-filter: blur(15px);
    padding: 1rem;

    .header__logo {
      font-size: 2rem;
      text-align: center;
      text-transform: uppercase;
      line-height: 1;

      em {
        font-size: 13px;
        display: block;
        color: var(--black200);
      }
    }
    .header__nav {
      display: none;
      li {
        display: inline;

        a {
          text-transform: uppercase;
          font-size: 1rem;
          padding: 14px;
          position: relative;
          font-weight: 400;

          &::before {
            content: '';
            height: 1px;
            width: calc(100% - 28px);
            background-color: var(--black);
            position: absolute;
            left: 14px;
            bottom: 10px;
            transform: scaleX(0);
            transition: all 0.3s;
          }

          &:hover::before {
            transform: scaleX(1);
          }
        }
      }
    }
    .header__nav__mobile {
      width: 40px;
      height: 40px;
      cursor: pointer;
      background-color: #ccc;

      span {
        display: block;
        width: 40px;
        height: 2px;
        background-color: var(--black);
        margin-top: 19px;
        position: relative;

        &::before {
          content: '';
          width: 40px;
          height: 2px;
          background-color: var(--black);
          position: absolute;
          right: 0;
          top: 6px;
          transition: width 0.3s;
        }
        &::after {
          content: '';
          width: 40px;
          height: 2px;
          background-color: var(--black);
          position: absolute;
          right: 0;
          bottom: 6px;
          transition: width 0.3s;
        }
      }
    }
  }
}
</style>

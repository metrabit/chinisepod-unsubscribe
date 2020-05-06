<template>
  <footer class="d-flex footer">
    <div class="d-flex footer__store">
      <div class="d-flex footer__store-btn">
        <svg viewBox="0 0 512 512" width="24">
          <g>
            <path
              d="M185.255,512c-76.201-0.439-139.233-155.991-139.233-235.21c0-129.404,97.075-157.734,134.487-157.734   c16.86,0,34.863,6.621,50.742,12.48c11.104,4.087,22.588,8.306,28.975,8.306c3.823,0,12.832-3.589,20.786-6.738   c16.963-6.753,38.071-15.146,62.651-15.146c0.044,0,0.103,0,0.146,0c18.354,0,74.004,4.028,107.461,54.272l7.837,11.777   l-11.279,8.511c-16.113,12.158-45.513,34.336-45.513,78.267c0,52.031,33.296,72.041,49.292,81.665   c7.061,4.248,14.37,8.628,14.37,18.208c0,6.255-49.922,140.566-122.417,140.566c-17.739,0-30.278-5.332-41.338-10.034   c-11.191-4.761-20.845-8.862-36.797-8.862c-8.086,0-18.311,3.823-29.136,7.881C221.496,505.73,204.752,512,185.753,512H185.255z"
            />
            <path
              d="M351.343,0c1.888,68.076-46.797,115.304-95.425,112.342C247.905,58.015,304.54,0,351.343,0z"
            />
          </g>
        </svg>
        <div class="footer__store-btn-text">
          <div>Download on the</div>
          <div class="footer__store-btn--big-text">App Store</div>
        </div>
      </div>
      <div class="d-flex footer__store-btn">
        <svg viewBox="0 0 511.995 511.995" width="24">
          <g>
            <path
              d="M98.102,6.525c-13.19-7.94-28.91-8.65-42.62-2.04l229.87,230.36l75.16-75.51L98.102,6.525z M34.362,25.805   c-2.9,6.14-4.46,12.97-4.46,20v421.38c0,7.06,1.57,13.79,4.5,19.8l229.78-230.87L34.362,25.805z M285.383,277.355l-229.5,230.59   c6.09,2.82,12.57,4.05,19.04,4.05c7.99,0,15.96-1.91,23.18-6.25l262.46-153.04L285.383,277.355z M460.453,217.535   c-0.09-0.06-0.19-0.12-0.28-0.17l-72.86-42.43l-80.77,81.15l80.82,80.99c0,0,73-42.56,73.09-42.61   c13.55-8.23,21.64-22.61,21.64-38.47S474.003,225.755,460.453,217.535z"
            />
          </g>
        </svg>
        <div class="footer__store-btn-text">
          <div>Got it on</div>
          <div class="footer__store-btn--big-text">Google play</div>
        </div>
      </div>
    </div>
    <div class="d-flex footer__navigation">
      <p>Copyright &copy; 2020 ChinesePod LLC</p>
      <ul class="d-flex footer__navigation-menu">
        <li v-for="(item, i) in navigationLinks" :key="i" class="footer__navigation-menu-item">
          <a :href="item.link">{{item.name}}</a>
        </li>
      </ul>
    </div>
    <div class="footer__social">
      <SocialMedia />
    </div>
  </footer>
</template>

<script>
import SocialMedia from "./SocialMedia";

export default {
  name: "Footer",
  components: {
    SocialMedia
  },
  data: () => ({
    navigationLinks: [
      { name: "Contact", link: "#" },
      { name: "Pricing", link: "#" },
      { name: "Careers", link: "#" },
      { name: "About Us", link: "#" },
      { name: "Affiliate", link: "#" },
      { name: "Resources", link: "#" },
      { name: "Privacy", link: "#" },
      { name: "Terms", link: "#" }
    ]
  })
};
</script>

<style lang="scss">
.footer {
  align-items: center;
  width: 95%;
  margin: 0 auto;

  &__store {
    flex: 1;
    align-items: center;
    justify-content: space-between;

    &-btn {
      width: 130px;
      border: 2px solid #000;
      justify-content: space-around;
      padding: 5px 12px;
      border-radius: 8px;
      cursor: pointer;

      &:first-child {
        margin-right: 8px;
      }

      &:last-child {
        margin-left: 8px;
      }

      &-text {
        font-size: 12px;
      }

      &--big-text {
        font-size: 20px;
        font-weight: 700;
      }
    }
  }

  &__navigation {
    flex: 4;
    justify-content: center;
    flex-direction: column;
    align-items: center;
    flex-wrap: wrap;
    margin-right: 100px;

    &-menu {
      justify-content: center;
      flex-wrap: wrap;
      width: 80%;
      padding-left: 0;

      &-item {
        width: 15%;
        display: flex;
        justify-content: center;
        margin-bottom: 10px;
      }

      &-item a {
        text-decoration: none;
        color: #d4170f;

        &:hover {
          text-decoration: underline;
        }
      }
    }
  }

  &__social {
    flex: 1;
  }
}
</style>
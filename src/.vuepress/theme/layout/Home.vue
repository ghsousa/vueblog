<template>
  <div class="home">
    <div class="hero">
      <img class="profile-pic" v-bind:src="data.pic" alt="A photo of Gabe Sousa looking b-e-a-utiful" />
      <h1 class="title">{{ data.heroText || $title || 'Hello' }}</h1>
      <h3 class="subtitle">{{ data.heroSubText }}</h3>
      <h2
        class="description"
      >{{ data.tagline || $description || 'These bespectacled eyes see things. These trap-beat loving ears hear things. This Brazilian born, Bay State raised soul feels things - and I turn it all into immersive digital art.' }}</h2>
    </div>

    <BlogPostList
      :pages="$site.pages"
      :page-size="$site.themeConfig.homePageSize"
      :start-page="$site.themeConfig.startPage"
    />
    <div class="social-icons" id="insta">
			<div class="icon-svg">
        <a href="https://instagram.com/onegroovydad">
					<img src="insta.svg" alt="Social Icon for Instagram">
        </a>
      </div>
      <div class="icon-svg" id="twitter">
        <a href="https://twitter.com/dev_gabe">
					<img src="tw-icon.svg" alt="Social Icon for Twitter">
        </a>
      </div>
      <div class="icon-svg" id="dev-icon">
        <a href="https://dev.to/gabe">
					<img src="dev-icon.svg" alt="Social Icon for www.DEV.to">
        </a>
      </div>
			 <div class="icon-svg" id="spotty">
				 <a href="https://open.spotify.com/user/gsous?si=y7QirTxRS5GE9_JghvO__w">
				 <img src="s-icon.svg" alt="Social Icon for Spotify">
				 </a>
				</div>
    </div>

    <div class="footer" v-if="data.footer">{{ data.footer }}</div>
  </div>
</template>

<script>
import NavLink from "../components/NavLink.vue";

export default {
  components: { NavLink },

  computed: {
    data() {
      return this.$page.frontmatter;
    },

    actionLink() {
      return {
        link: this.data.actionLink,
        text: this.data.actionText
      };
    }
  }
};
</script>

<style lang="stylus">
@import '../styles/config.styl';

.home {
  padding: 1rem 2rem 0;
  max-width: 600px;
  margin: 0px auto;
  opacity: 0;
  animation: fadein 0.3s ease-in-out 0.2s 1 forwards;

	.content.default {
		padding-bottom: 0;
	}

	.social-icons {
		padding-bottom: 1rem;
	}

  .icon-svg {
    display: inline-block;
    padding: 0.6rem 0.6rem 0 0.6rem;
		transition: transform ease-in-out .4s;
  }

	.icon-svg:hover {
		transform: scale(1.3);
	}

	.icon-svg img {
		width: 22px;
	}

	#twitter img {
		width: 22px;
		}

		#insta img {
			width: 22px;
		}

		#dev-icon img {
			width: 25px;
		}

	#spotty img {
		width: 22px;
	}

	.social-icons {
		text-align: center;
	}

  .title {
    font-weight: 600;
		font-family: 'Avenir Next';
		letter-spacing: -3px;
  }

  .subtitle {
    font-weight: 400;
		font-family: 'Avenir Next';
    letter-spacing: 4px;
    color: #555;
    background: linear-gradient(60deg, #ee0979, #ff6a00);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    padding-bottom: 0.2rem;
		padding-left: 9px;
  }

  ul.blog-list {
    max-width: 30rem;
    margin: auto !important;
  }

  time {
    font-size: 0.8rem;
    color: #888;
  }

  .blog-list__tags {
    display: none;
  }

  button.button--pagination {
    display: block;
  }

	.pagination {
		max-width: 30rem;
		margin: auto;
		display: none;
	}

	.see-all {
		max-width: 30rem;
		margin: auto;
	}

  .hero {
    text-align: center;
    padding-bottom: 1rem;

    .profile-pic {
      width: 130px;
      display: block;
      border-radius: 100%;
      margin: 3rem auto 0;
    }

    h1 {
      font-size: 3rem;
    }

    h1, h3 {
      margin: auto;
    }

    .description, .action {
      margin: 1.8rem auto;
    }

    .description {
			border: none;
			font-family: Avenir;
      color: #666;
      max-width: 30rem;
      font-size: 1.2rem;
      line-height: 1.4;
      margin: auto;
      text-align: left;
      padding: 0.6rem 0 0.5rem 0;
			font-weight: 400;
    }

    .action-button {
      display: inline-block;
      font-size: 1.2rem;
      color: #fff;
      background-color: $accentColor;
      padding: 0.8rem 1.6rem;
      border-radius: 4px;
      transition: background-color 0.1s ease;
      box-sizing: border-box;
      border-bottom: 1px solid darken($accentColor, 10%);

      &:hover {
        background-color: lighten($accentColor, 10%);
      }
    }
  }

  .features {
    border-top: 1px solid $borderColor;
    padding: 1.2rem 0;
    margin-top: 2.5rem;
    display: flex;
    flex-wrap: wrap;
    align-items: flex-start;
    align-content: stretch;
    justify-content: space-between;
  }

  .feature {
    flex-grow: 1;
    flex-basis: 30%;
    max-width: 30%;

    h2 {
      font-size: 1.4rem;
      font-weight: 500;
      border-bottom: none;
      padding-bottom: 0;
      color: lighten($textColor, 10%);
    }

    p {
      color: lighten($textColor, 25%);
    }
  }

  .footer {
    width: 100%;
    padding: 2% 0 5% 0%;
    text-align: center;
    letter-spacing: 4px;
    font-weight: 300;
    font-size: 0.6em;
    font-family: sans-serif;
    background: linear-gradient(60deg, #ee0979, #ff6a00);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
  }
}

@media (max-width: $MQMobile) {
  .home {
    .features {
      flex-direction: column;
    }

    .feature {
      max-width: 100%;
      padding: 0 2.5rem;
    }

		.subtitle {
			padding-right: 0;
			}
  }
}

@media (max-width: $MQMobileNarrow) {
  .home {
    padding-left: 1.5rem;
    padding-right: 1.5rem;

    .hero {
      img {
        max-height: 210px;
        margin: 2rem auto 1.2rem;
      }

      h1 {
        font-size: 2rem;
      }

      h1, .description, .action {
        margin: 0;
      }

      .description {
        font-size: 1.2rem;
        padding: 1rem 0;
      }

      .action-button {
        font-size: 1rem;
        padding: 0.6rem 1.2rem;
      }
    }

    .feature {
      h2 {
        font-size: 1.25rem;
      }
    }
  }
}

@keyframes fadein {
  0% {
    opacity: 0;
  }

  100% {
    opacity: 1;
  }
}
</style>

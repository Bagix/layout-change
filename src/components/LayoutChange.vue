<template>
  <div class="container">
    <button class="btn" type="button" @click="changeLayout('list')" :class="{'active': list}">List</button>
    <button class="btn" type="button" @click="changeLayout('grid')" :class="{'active': grid}">Grid</button>
    <div class="layout" :class="{'list': list, 'grid': grid}">
      <ul>
        <li v-for="article in articles" :key="article.title">
          <a :href="article.url">
            <div class="img-box">
              <img :src="article.image">
            </div>
            <h3 v-if="list">{{ article.title }}</h3>
          </a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'LayoutChange',
  data() {
    return {
      list: true,
      grid: false,
      articles: [
        {
          title: 'What You Need To Know About CSS Variables',
          url: 'https://tutorialzine.com/2016/03/what-you-need-to-know-about-css-variables/',
          image: 'https://tutorialzine.com/media/2016/03/css-variables.jpg'
        },
        {
          title: 'Freebie: 4 Great Looking Pricing Tables',
          url: 'https://tutorialzine.com/2016/02/freebie-4-great-looking-pricing-tables/',
          image: 'https://tutorialzine.com/media/2016/02/great-looking-pricing-tables.jpg'
        },
        {
          title: '20 Interesting JavaScript and CSS Libraries for February 2016',
          url: 'https://tutorialzine.com/2016/02/20-interesting-javascript-and-css-libraries-for-february-2016/',
          image: 'https://tutorialzine.com/media/2016/02/interesting-resources-february.jpg'
        },
        {
          title: 'Quick Tip: The Easiest Way To Make Responsive Headers',
          url: 'https://tutorialzine.com/2016/02/quick-tip-easiest-way-to-make-responsive-headers/',
          image: 'https://tutorialzine.com/media/2016/02/quick-tip-responsive-headers.png'
        },
        {
          title: 'Learn SQL In 20 Minutes',
          url: 'https://tutorialzine.com/2016/01/learn-sql-in-20-minutes/',
          image: 'https://tutorialzine.com/media/2016/01/learn-sql-20-minutes.png'
        },
        {
          title: 'Creating Your First Desktop App With HTML, JS and Electron',
          url: 'https://tutorialzine.com/2015/12/creating-your-first-desktop-app-with-html-js-and-electron/',
          image: 'https://tutorialzine.com/media/2015/12/creating-your-first-desktop-app-with-electron.png'
        }
      ]
    }
  },
  methods: {
    changeLayout: function(layout) {
      if(layout === 'list') {
        this.list = true
        this.grid = false
      } else {
        this.list = false
        this.grid = true
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style  lang="scss">

:root {
  --pink: #D83F87;
  --dark-purple: #2A1B3D;
  --purple: #44318D;
  --light-purple: #8264AA;
  --gray: #A4B3B6;
}

* {
  box-sizing: border-box;
}

body {
  background-color: var(--dark-purple);
  color: var(--gray);
}

img {
  display: block;
  width: 100%;
  height: auto;
}

ul {
  list-style: none;
  margin: 0;
  padding: 0;
}

.container {
  width: 100%;
  max-width: 1200px;
  padding: 1rem;
  margin: auto;
}

.btn {
  margin: 1rem;
  padding: .5rem 1.5rem;
  font-size: 1.5rem;
  border: none;
  border-radius: 3px;
  font-weight: bold;
  background-color: var(--light-purple);
  color: #fff;
  cursor: pointer;
  transition: all .2s linear;
  &:hover,
  &.active {
    background-color: var(--pink);
  }
  &.active {
    color: var(--purple);
  }
  &:focus {
    outline: none;
  }
}

.layout {
  &.list {
    ul {
      max-width: 900px;
      margin: auto;
      & > li {
        margin: 2rem 0;
      }
    }
    a {
      display: flex;
      align-items: center;
      color: var(--gray);
      text-decoration: none;
      transition: color .2s linear;
      .img-box {
        width: 40%;
        margin-right: 50px;
      }
      h3 {
        width: 60%;
      }
      &:hover {
        color: var(--pink);
      }
    }
  }

  &.grid {
    margin-top: 2rem;
    ul {
      display: grid;
      grid-template-rows: auto;
      grid-template-columns: 1fr 1fr;
    }
  }
}

</style>

<script>
import IconDefault from './icons/IconDefault.vue'
import IconOpenX from './icons/IconOpenX.vue'
import IconCloseX from './icons/IconCloseX.vue'

export default {
  components: {
    IconDefault,
    IconOpenX,
    IconCloseX
  },
  props: {
    cssTarget: {
      type: String,
      required: true
    }
  },
  computed: {
    cssProps() {
      return {
        'open-x': this.cssTarget + '-open-x',
        'close-x': this.cssTarget + '-close-x',
        'css-target': this.cssTarget + '',
        'css-placeholder': this.cssTarget + '-placeholder'
      }
    }
  },
  methods: {
    toggleVisibility() {
      this.hideElement(this.cssProps['css-target'])
      this.showElement(this.cssProps['open-x'])
      this.hideElement(this.cssProps['close-x'])
      this.showElement(this.cssProps['css-placeholder'])
    },
    hideElement(classTarget) {
      const div = document.querySelector(`.${classTarget}`)
      console.log('hidiing', div)
      div.style.display = div.style.display === 'block' ? 'none' : 'block'
    },
    showElement(classTarget) {
      const div = document.querySelector(`.${classTarget}`)
      console.log('Shoooowing', div)
      div.style.display = div.style.display === 'none' ? 'block' : 'none'
    }
  }
}
</script>

<template>
  <div class="item">
    <i>
      <slot name="icon">
        <IconOpenX
          :class="cssProps['open-x']"
          class="iconOpenX"
          @click.prevent="this.toggleVisibility()"
        />
        <IconCloseX
          :class="cssProps['close-x']"
          class="iconCloseX"
          @click.prevent="this.toggleVisibility()"
        />
      </slot>
    </i>
    <div class="details">
      <h3>
        <slot name="heading"></slot>
      </h3>

      <slot name="summary"></slot>
      <p :class="cssProps['css-placeholder']">.........</p>
      <div :class="cssProps['css-target']" class="startInvisible">
        <slot name="fullText"></slot>
      </div>
    </div>
  </div>
</template>

<style scoped>
.startInvisible {
  display: none;
}

.iconOpenX {
  display: block;
}

.iconCloseX {
  display: none;
}

li {
  color: aquamarine;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
}
.item {
  margin-top: 2rem;
  display: flex;
  position: relative;
}

.details {
  flex: 1;
  margin-left: 1rem;
}

i {
  display: flex;
  place-items: center;
  place-content: center;
  width: 32px;
  height: 32px;
  color: var(--color-text);
}

h3 {
  font-size: 1.2rem;
  font-weight: 500;
  margin-bottom: 0.4rem;
  color: var(--color-heading);
}

@media (min-width: 1024px) {
  .item {
    margin-top: 0;
    padding: 0.4rem 0 1rem calc(var(--section-gap) / 2);
  }

  i {
    top: calc(50% - 25px);
    left: -26px;
    position: absolute;
    border: 1px solid var(--color-border);
    background: var(--color-background);
    border-radius: 8px;
    width: 50px;
    height: 50px;
  }

  .item:before {
    content: ' ';
    border-left: 1px solid var(--color-border);
    position: absolute;
    left: 0;
    bottom: calc(50% + 25px);
    height: calc(50% - 25px);
  }

  .item:after {
    content: ' ';
    border-left: 1px solid var(--color-border);
    position: absolute;
    left: 0;
    top: calc(50% + 25px);
    height: calc(50% - 25px);
  }

  .item:first-of-type:before {
    display: none;
  }

  .item:last-of-type:after {
    display: none;
  }
}
</style>

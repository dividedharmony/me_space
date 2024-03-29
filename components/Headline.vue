<template>
  <h1 :is="`h${level}`" :class="cssClasses">
    <slot />
  </h1>
</template>

<script>
const SIZES = {
  0: 'size-zero',
  1: 'size-one',
  2: 'size-two',
  3: 'size-three',
  4: 'size-four',
  5: 'size-five',
  6: 'size-six',
}
export default {
  props: {
    level: {
      type: Number,
      default: 1,
      validator: (value) => {
        return value >= 1 && value <= 6
      },
    },
    size: {
      type: Number,
      default: 1,
      validator: (value) => {
        return !!SIZES[value]
      },
    },
    decorations: {
      type: Array,
      default() {
        return []
      },
      validator: (values) => {
        return values.every((value) => {
          return [null, 'italic', 'bold', 'underline'].includes(value)
        })
      },
    },
  },
  computed: {
    cssClasses() {
      const klasses = ['headline']
      klasses.push(SIZES[this.size])
      this.decorations.forEach((decoration) => {
        klasses.push(`h--${decoration}`)
      })
      return klasses
    },
  },
}
</script>

<style lang="scss" scoped>
.headline {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: normal;
  color: #35495e;
  letter-spacing: 1px;

  &.h--italic {
    font-style: italic;
  }

  &.h--underline {
    text-decoration: underline;
  }

  &.h--bold {
    font-weight: bold;
  }

  &.size-zero {
    font-size: 300px;
  }
  &.size-one {
    font-size: 100px;
  }
  &.size-two {
    font-size: 50px;
  }
  &.size-three {
    font-size: 26px;
  }
  &.size-four {
    font-size: 20px;
  }
  &.size-five {
    font-size: 16px;
  }
  &.size-six {
    font-size: 12px;
  }
}
</style>

<template>
  <styled-button :color="color" :outline="outline">
    <slot></slot>
  </styled-button>
</template>

<script>
import styled from 'vue-styled-components'

const propTypes = {
  color: {
    type: String,
    default: '#1678C2'
  },
  outline: {
    type: Boolean,
    default: false
  }
}

const StyledButton = styled('button', propTypes)`
  color: #ffffff;
  background-color: ${props => !props.outline ? props.color : 'transparent'};
  border-color: ${props => !props.outline ? props.color : '#ffffff'};
  &:hover {
    color: ${props => props.color};
    background-color: #ffffff;
    border-color: ${props => !props.outline ? props.color : '#ffffff'};
  }
`

export default {
  name: 'Button',
  components: {
    StyledButton
  },
  props: propTypes
}
</script>


<style lang="scss" scoped>
button {
  display: inline-block;
  text-align: center;
  vertical-align: middle;
  border-width: 1px;
  border-style: solid;
  padding: 0.375rem 0.75rem;
  font-size: 1rem;
  line-height: 1.5;
  border-radius: 0.25rem;
  transition: color 0.15s ease-in-out, background-color 0.15s ease-in-out, border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;
  &:hover {
    cursor: pointer;
  }
}
</style>

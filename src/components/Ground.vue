<script lang="ts" setup>
import image from '../assets/game.png'
import { BaseTexture, Rectangle, Texture } from 'pixi.js'
import { useScreen } from 'vue3-pixi'

defineProps<{
  x: number
}>()

const textureMain = BaseTexture.from(image)
const texture = new Texture(textureMain, new Rectangle(50, 100, 2300, 30))

const screen = useScreen()
</script>

<template>
  <TilingSprite :texture="texture" :width="screen.width" :y="screen.height - 50" :tile-position-x="x" :height="30" />
</template>

<style lang="scss" scoped></style>

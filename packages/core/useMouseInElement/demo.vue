<script setup lang="ts">
import { useMouseInElement } from '@vueuse/core'
import { stringify } from '@vueuse/docs-utils'
import { reactive, useTemplateRef } from 'vue'
import Area from './Area.vue'

const target = useTemplateRef<HTMLElement>('target')
const mouse = reactive(useMouseInElement(target))
const text = stringify(mouse)
</script>

<template>
  <div flex="~" gap="4">
    <Area ref="target" />
    <pre lang="yaml">{{ text }}</pre>
  </div>
</template>

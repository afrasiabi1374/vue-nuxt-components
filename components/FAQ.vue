<template>
  <div :class="['faq', open ? 'open' : '']" @click="$emit('toggleOpen', index)">
    <div class="question">{{faq.question}}</div>
    <div class="answer">{{faq.answer}}</div>
  </div>
</template>

<script>
export default {
    name: 'FAQ',
    props: ['faq', 'index', 'open']
}
</script>

<style>

</style>
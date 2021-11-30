<template>
  <div>
    <PageTitle :title="title" subTitle="(매출)" />
  </div>
</template>
<script>
import PageTitle from '@/components/PageTitle.vue'
export default {
  name: '',
  components: { PageTitle },
  data() {
    return {
      title: '2021년 4/4분기 매출 내역서'
    }
  },
  setup() {},
  created() {},
  mounted() {},
  unmounted() {},
  methods: {}
}
</script>

<template>
  <div class="tornado-body">
    <Icon name="tornado" />
    <div class="title">
      {{ $t('Welcome') }}{{ test }}{{ msg }}
    </div>
  </div>
</template>

<script>
import { mapState, mapActions } from 'vuex'
import { loadLanguageAsync } from 'utils/i18n'
export default {
  async created () {
    await sleep(2000)
    await loadLanguageAsync('tornado', 'zh-CN')
    await sleep(2000)
    await loadLanguageAsync('tornado', 'en-US')
  },
  data () {
    return {
      msg: 'tornado!',
    }
  },
  computed: {
    ...mapState([
      'test',
    ]),
  },
  methods: {
    ...mapActions([
      'getTest',
    ]),
  },
}
</script>

<template>
  <div style="padding-top: 16px;">
    <h2>布局</h2>
    <p>
      <strong>预览</strong>
    </p>


    <g-layout style="color: white; overflow:hidden; margin-bottom:50px;">
      <g-header style="height: 50px; background:lightskyblue;">
        header
      </g-header>
      <g-layout>
        <g-side style="height: 100px; background:#ddd; width:200px; color: black;">
          sider
        </g-side>
        <g-content style="height: 100px; background:deepskyblue;">
          content
        </g-content>
      </g-layout>
      <g-footer style="height: 50px; background:lightskyblue;">
        footer
      </g-footer>
    </g-layout>

    <p>
      <strong>代码</strong>
    </p>
    <pre><code>{{content}}</code></pre>
  </div>
</template>
<style scoped>
* {
  box-sizing: border-box;
}
</style>
<script>
import GLayout from '../../../src/layout/layout'
import GHeader from '../../../src/layout/header'
import GFooter from '../../../src/layout/footer'
import GContent from '../../../src/layout/content'
import GSide from '../../../src/layout/side'
export default {
  name: 'layout-demos-2',
  components: {GLayout, GHeader, GFooter, GContent, GSide},
  data () {
    return {
      content: `
          <g-layout style="color: white; overflow:hidden; margin-bottom:50px;">
            <g-header style="height: 50px; background:lightskyblue;">
              header
            </g-header>
            <g-layout>
              <g-side style="height: 100px; background:#ddd; width:200px; color: black;">
                sider
              </g-side>
              <g-content style="height: 100px; background:deepskyblue;">
                content
              </g-content>
            </g-layout>
            <g-footer style="height: 50px; background:lightskyblue;">
              footer
            </g-footer>
          </g-layout>
      `.replace(/^ {8}/gm, '').trim()
    }
  }
}
</script>

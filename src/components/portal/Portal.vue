<template>
  <div id="portal" class="content">
    <portal-header/>
    <portal-start/>
    <portal-solution/>
    <portal-contact/>
  </div>
</template>

<script>
import PortalHeader from './Portal.Header'
import PortalStart from './Portal.Start'
import PortalSolution from './Portal.Solution'
import PortalContact from './Portal.Contact'
export default {
  name: 'Portal',
  components: {
    PortalHeader,
    PortalStart,
    PortalSolution,
    PortalContact
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.content{
  height: 100%;
  width: 100%;
}
</style>

<template>
  <div class="DatatablePage">
    <DatatablePage/>
    <ChartPageUC/>
    <ChartPageAWT/>
  </div>
</template>

<script>
import DatatablePage from "@/components/DatatablePage";
import ChartPageUC from "@/components/ChartPageUC";
import ChartPageAWT from "@/components/ChartPageAWT";

export default {
  name: "App",
  components: {
    DatatablePage,
    ChartPageUC,
    ChartPageAWT,
  }
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
</style>

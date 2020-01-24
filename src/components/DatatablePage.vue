<template>
  <mdb-datatable
    :data="'https://magenta-json.herokuapp.com'"
    striped
    bordered
    :display="3"
    responsive
    reactive
    :time="5000"
    :searching="false"
    :pagination="false"
    :sorting="false"
    :tfoot="false"
  />
</template>

<script>
  import { mdbDatatable } from 'mdbvue';
  export default {
    name: 'DatatablePage',
    components: {
      mdbDatatable
    }
  }
</script>

<style>
</style>

<template>
  <mdb-datatable
    :data="'https://magenta-oauth.herokuapp.com'"
    striped
    bordered
    :display="3"
    responsive
    reactive
    :time="2000"
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

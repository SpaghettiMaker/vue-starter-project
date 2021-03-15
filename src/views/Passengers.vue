<template>
  <div class="about">
    <h1>This is an about page</h1>
  </div>
  <mdb-datatable
    id="example"
    :data="data"
    striped
    bordered
    data-page-length='25'
  />
</template>
<script>
import { mdbDatatable } from 'mdbvue'
export default {
  name: 'DatatablePage',
  components: {
    mdbDatatable
  },
  data () {
    return {
      passengers: [],
      data: {
        columns: [
          {
            label: 'Name',
            field: 'Name',
            sort: 'asc'
          },
          {
            label: 'Age',
            field: 'Age',
            sort: 'asc'
          },
          {
            label: 'Sex',
            field: 'Sex',
            sort: 'asc'
          },
          {
            label: 'class',
            field: 'class',
            sort: 'asc'
          },
          {
            label: 'Survived',
            field: 'Survived',
            sort: 'asc'
          },
          {
            label: 'Embarked',
            field: 'Embarked',
            sort: 'asc'
          },
          {
            label: 'Salary',
            field: 'salary',
            sort: 'asc'
          },
          {
            label: 'Siblings',
            field: 'Siblings',
            sort: 'asc'
          },
          {
            label: 'Parch',
            field: 'Parch',
            sort: 'asc'
          },
          {
            label: 'Ticket',
            field: 'Ticket',
            sort: 'asc'
          },
          {
            label: 'Fare',
            field: 'Fare',
            sort: 'asc'
          },
          {
            label: 'Cabin',
            field: 'Cabin',
            sort: 'asc'
          }
        ],
        rows: []
      }
    }
  },
  mounted () {
    fetch('http://coding-task.strakertranslations.com/passengers')
      .then(res => res.json())
      .then(data => { this.rows = data })
      .catch(err => console.log(err.message))
  }
}

</script>

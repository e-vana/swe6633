<template>
  <div>
    <b-row>
      <b-col lg="12" sm="12">
        <h2>Your Projects </h2>
        <b-button variant="primary" v-b-modal.add-project-requirement><b-icon icon="plus" scale="1.5"></b-icon> Create a new project</b-button>
        <b-table :items="projectList" :fields="fields" hover  @row-clicked="myRowClickHandler">
        </b-table>
      </b-col>
    </b-row>
    
    
  </div>
</template>

<script>
export default {
  data() {
    return {
      fields: [
        {
          key: 'name',
          sortable: true,
          label: "Project Name"
        },
      ],
      projectList: [
        {
          name: 'CS6070 PM1',
          description: 'Project module one for this springs semesters PM1 module.',
          id: '000',
        },
        {
          name: 'SWE6633 Group Project 1',
          description: 'Group project requirements and tasks for SWE6633.',
          id: '001',
        },
        {
          name: 'SWE6622 Semester Project ',
          description: 'Project module one for this springs semesters PM1 module.',
          id: '002',
        },
      ]
    }
  },
  methods: {
    myRowClickHandler: function(record, index){
      this.$router.push(`/projects/${record.id}`)
      console.log(record, index);
    }
  }
}
</script>

<style>
td:hover {
  cursor: pointer;
}
</style>
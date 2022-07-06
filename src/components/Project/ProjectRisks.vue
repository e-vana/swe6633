<template>
  <div id="project-risks">
    <h4>Project Risks</h4>
    <b-button variant="info" v-b-modal.add-project-risk><b-icon icon="plus" scale="1.5"></b-icon> Add a project risk</b-button>

    <b-table :items="projectRisks" :fields="projectRisksFields" hover responsive></b-table>
    <!-- <b-alert variant="info" show>There are no project risks yet.</b-alert> -->
    <b-modal id="add-project-risk" title="Add a project risk">
      <label>Describe the project risk</label>
      <b-input v-model="risk.description"></b-input>
      <label>What is the severity level?</label>
      <b-select :options="severityLevels"></b-select>
    </b-modal>
  </div>
</template>

<script>
export default {
  data(){
    return {
      severityLevels: ['Low', 'Medium', 'High'],
      risk: {
        description: null,
      },
      projectRisks: [
        {
          description: 'This is a project risk',
          severity: 'high',
          resolved: false 
        },
        {
          description: 'This is another project risk',
          severity: 'low',
          resolved: false 
        }
      ],
    }
  }
}
</script>

<style>

</style>
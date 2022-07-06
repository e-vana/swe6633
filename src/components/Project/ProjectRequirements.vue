<template>
  <div id="project-requirements">
    <h4>Project Requirements</h4>
    <b-button variant="success" v-b-modal.add-project-requirement><b-icon icon="plus" scale="1.5"></b-icon> Add a project requirement</b-button>
    
    <b-table :items="projectRequirements" :fields="projectRequirementsFields" hover responsive></b-table>
    <!-- <b-alert variant="success" show>There are no project requirements yet.</b-alert> -->
    <b-modal id="add-project-requirement" title="Add a project risk" content-class="my-modal">
      <label>What is the name of this project requirement?</label>
      <b-input v-model="requirement.name"></b-input>
      <label>Describe the project requirement</label>
      <b-input v-model="requirement.description"></b-input>
      <label>Is this a functional or non-functional requirement?</label>
      <b-select :options="functionalOrNonFunctional"></b-select>
      <label>What is the priority level?</label>
      <b-select :options="priorityLevels"></b-select>
    </b-modal>
  </div>
</template>

<script>
export default {
  data(){
    return {
      priorityLevels: ['Low', 'Medium', 'High'],
      functionalOrNonFunctional: ['Functional', 'Non-Functional'],
      requirement: {
        description: null,
      },
      projectRequirements: [
        {
          name: 'Create project view',
          type: 'Functional',
          description: 'Allow users to see what projects they have created.',
          priority: 'low' 
        },
        {
          name: 'Create users view',
          type: 'NonFunctional',
          description: 'Allow users to view existing users and create new users.',
          priority: 'low' 
        }
      ],
    }
  }
}
</script>

<style>
.my-modal {
  padding: 20px;
}
input {
  margin-bottom: 20px;
}
</style>
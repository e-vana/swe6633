<template>
  <div id="project-team-members">
    <h4>Project Team Members</h4>
    <b-button variant="primary" v-b-modal.add-project-team-member><b-icon icon="plus" scale="1.5"></b-icon> Add a team member</b-button>
    <b-table :items="projectMembers" :fields="projectMemberFields" hover responsive></b-table>
    <!-- <b-alert variant="primary" show>There are no team members added to this project yet.</b-alert> -->
    <b-modal id="add-project-team-member" title="Add a team member to this project">
      <label>Select a user</label>
      <b-select></b-select>
      <label>Select a role for this user on this project</label>
      <b-select :options="userRoles"></b-select>
    </b-modal>
  </div>
    
</template>

<script>
export default {
  data(){
    return {
    userRoles: ['Developer', 'QA', 'Project Management'],
    projectMemberFields: [
        {
          key: 'name',
          label: 'Name',
        },
        {
          key: 'role',
          label: 'Role',
        },
        {
          key: 'email',
          label: 'Email',
        },
      ],
      projectMembers: [
        {
          name: 'Evan',
          role: 'developer',
          email: 'test@test.com'
        },
        {
          name: 'Veera',
          role: 'developer',
          email: 'test@test.com'

        },
        {
          name: 'Navya',
          role: 'team lead',
          email: 'test@test.com'
        }
      ],
    }
  }
}
</script>

<style>


</style>
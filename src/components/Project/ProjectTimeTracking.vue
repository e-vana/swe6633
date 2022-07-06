<template>
  <div id="project-time-tracking">
    <h4>Project Time Tracking</h4>
    <b-button variant="warning" v-b-modal.add-project-requirement><b-icon icon="plus" scale="1.5"></b-icon> Add Project Hours</b-button>

    <b-progress show-value :max="getTotalHours" class="mb-3">
      <b-progress-bar variant="primary" :value="projectTimeTracking[0].hours"><span><strong>{{projectTimeTracking[0].taskName}}: {{projectTimeTracking[0].hours}}hours</strong></span></b-progress-bar>
      <b-progress-bar variant="success" :value="projectTimeTracking[1].hours"><span><strong>{{projectTimeTracking[1].taskName}}: {{projectTimeTracking[1].hours}}hours</strong></span></b-progress-bar>
      <b-progress-bar variant="info" :value="projectTimeTracking[2].hours"><span><strong>{{projectTimeTracking[2].taskName}}: {{projectTimeTracking[2].hours}}hours</strong></span></b-progress-bar>
    </b-progress>
    <b-table :items="projectTimeTracking" :fields="projectTimeTrackingFields" hover responsive></b-table>
    <!-- <b-alert variant="warning" show>There are no project requirements yet.</b-alert> -->
  </div>
</template>

<script>
export default {
  data(){
    return {
      projectTimeTracking: [
        {
          taskName: 'Requirements Gathering',
          hours: 30,
        },
        {
          taskName: 'Development',
          hours: 28,
        },
        {
          taskName: 'Testing',
          hours: 45,
        }
      ],
    }
  },
  computed: {
    getTotalHours: function(){
      let sum = 0;
      this.projectTimeTracking.forEach(time => {
        sum = sum +  time.hours;
      });
      return sum;
    }
  }
}
</script>

<style>

</style>
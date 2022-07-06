<template>
  <div>
    <b-row>
      <b-col lg="12" sm="12">
        <h2>Example Project  </h2>
        <p>As a group, create a software project that tracks project management and scheduling.</p>

        <div id="project-section-container">
          <!-- TEAM MEMBER SECTION -->
          <project-team-members></project-team-members>

          <!-- PROJECT REQUIREMENTS SECTION -->
          <project-requirements></project-requirements>

          <!-- PROJECT RISKS SECTION -->
          <project-risks></project-risks>

          <!-- PROJECT HOURS SECTION -->
          <project-time-tracking></project-time-tracking>
        </div>
      </b-col>
    </b-row>
  </div>
</template>

<script>
import ProjectRequirements from '../components/Project/ProjectRequirements.vue';
import ProjectRisks from '../components/Project/ProjectRisks.vue';
import ProjectTeamMembers from '../components/Project/ProjectTeamMembers.vue';
import ProjectTimeTracking from '../components/Project/ProjectTimeTracking.vue';
export default {
  components: { ProjectTeamMembers, ProjectRisks, ProjectRequirements, ProjectTimeTracking },
  data(){
    return {
    }
  },

}
</script>

<style>
/* .project-section {
  border: 1px solid rgb(233, 233, 233);
  border-radius: 5px;
  padding: 20px;
} */

#project-section-container > div{
  margin: 70px 0px;
}
</style>
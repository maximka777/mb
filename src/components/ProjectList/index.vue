<template>
  <div :class="'project-list project-list--grid-' + columns">
    <ProjectItem
      v-for="project in projects"
      :key="project.name"
      :project="project"
    />
  </div>
</template>

<script>
import ProjectItem from "./ProjectItem";

export default {
  components: {
    ProjectItem
  },
  props: {
    projects: Array,
    columns: {
      type: Number,
      default: 3
    }
  }
};
</script>

<style lang="scss">
.project-list {
  display: grid;
  grid-column-gap: 1rem;
  grid-row-gap: 1rem;
  grid-template-columns: repeat(3, 1fr);

  &.project-list--grid-3 {
    grid-template-columns: repeat(3, 1fr);
  }

  &.project-list--grid-4 {
    grid-template-columns: repeat(4, 1fr);
  }

  @media only screen and (max-width: 920px) {
    grid-template-columns: repeat(3, 1fr) !important;
  }

  @media only screen and (max-width: 720px) {
    grid-template-columns: repeat(2, 1fr) !important;
  }

  @media only screen and (max-width: 480px) {
    grid-template-columns: repeat(1, 1fr) !important;
  }

  .project-item {
    @media only screen and (max-width: 480px) {
      margin: 0 0 1rem 0;
    }
  }
}
</style>

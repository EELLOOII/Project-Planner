<template>
  <div class="project">
    <!-- <div class="actions" @click="toggleDetails"> -->
    <div class="actions">
        <h3  @click="showDetails = !showDetails">{{ project.title }}</h3>
        <div class="icons">            
            <span class="material-icons">edit</span>
            <span class="material-icons">delete</span>
            <span class="material-icons">done</span>
        </div>
    </div>
    <div v-if="showDetails" class="details">
        <p>{{ project.details }}</p>
    </div>
  </div>
</template>

<script>
export default {
    props: ['project'],
    data() {
        return {
            showDetails: false
        }
    },
    methods: {
        toggleDetails() {
            this.showDetails = !this.showDetails
        }
    }
}
</script>

<style>
    .project {
        margin: 20px auto;
        background: white;
        padding: 10px 20px;
        border-radius: 4px;
        box-shadow: 1px 2px 3px rgba(0, 0, 0, 0.5);
        border-left: 4px solid #e90074;
    } 
    h3 {
        cursor: pointer;
    }
    .actions {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 10px;
    }
    .material-icons {
        font-size: 24px;
        margin-left: 10px;
        color: #bbb;
        cursor: pointer;
    }
    .material-icons:hover {
        color: #777;
    }
</style>
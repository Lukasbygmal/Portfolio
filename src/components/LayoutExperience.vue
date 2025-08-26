<template>
    <div class="experience-title">
        Experience
    </div>
    <div class="experience-sub-title">
        SAAB Underwater Systems - Summer Internship as Developer - 2025
    </div>
    <div class="experience-description">
        Agent-based simulation in a maritime environment using LLM agents <br>
        Worked with C#, Python, Unity, Google ADK, MCP
    </div>
    
</template>

<script>
export default {
    name: 'LayoutExperience'
}
</script>

<style scoped>
.experience-title {
    font-size: 40px;
    font-weight: bold;
    color: black;
    margin-top: 15px;
    margin-bottom: 5px;
    background-color: transparent;
}

.experience-description {
    font-size: 24px;
    color: black;
    margin: 5px 10px;
    background-color: transparent;
}

.experience-sub-title {
    margin-top: auto;
    font-size: 28px;
    font-weight: bold;
    background-color: transparent;
    color: #BB4430;
}

@media (max-width: 768px) {
    .experience-title {
        font-size: 24px;
        margin: 4px;
    }

    .experience-description {
        font-size: 18px;
        color: black;
        margin: 15px;
    }

    .experience-sub-title {
        margin-top: auto;
        font-size: 1.2em;
        font-weight: bold;
        background-color: transparent;
        color: #BB4430;
    }
}
</style>
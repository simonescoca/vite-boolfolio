<template>
    <article class="single-project w-100">
        <h2>
            {{ project.title }}
        </h2>

        <div class="img-wrapper">
            <img v-if="project.image.startsWith('http')" :src="project.image" alt="">
            <img v-else :src="'http://127.0.0.1:8000/storage/' + project.image" alt="">
        </div>
        <h4 :style="'color:' + project.type.color + ';'">
            Type: {{ project.type.name }}
        </h4>
        <h5>
            {{ project.slug }}
        </h5>


        <h6>
            <span v-for="technology in project.technologies">
                {{ technology.name }}
            </span>
        </h6>
        <p>
            {{ project.content.substr(0, 200) }}
        </p>
    </article>
</template>

<script>
    export default {
        name: 'SingleProject',
        props : {
            'project' : Object
        }
    }
</script>

<style lang="scss" scoped>
    .single-project{
        width: calc((100% / 2) - 1rem);
        border-radius: 1rem;
        padding: 1rem;
        margin-right: 1rem;
        background-color: rgb(221, 221, 221);
        color: black;
        margin-bottom: 2rem;

        *{
            margin-bottom: 1rem;
        }

        img{
            width: 100%;
            height: 10rem;
            object-fit: cover;
        }

        h6 span{
            margin-right: 1rem;
        }

        &:hover{
            background-color: white;
        }
    }
</style>
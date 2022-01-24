<template>
   <div class="post">
       <div>
            <div><strong>Название:</strong>{{ post.title}}</div>
            <div><strong>Описание:</strong>{{ post.body}}</div>
       </div>
       <div class="post__btns">
           <my-button @click="$emit('remove', post)">Удалить</my-button>         
       </div>
        </div> 
</template>

<script>
    export default {
        props:{
            post:{
                type: Object,
                required: true,
            }
        }
    }
</script>

<style scoped>
 .post{
        padding: 15px;
        border: 2px solid red;
        margin-top: 15px;
        display: flex;
        align-items: center;
        justify-content: space-between;
        height: 100%;
    }
    .post .post__btns{
        display: flex;
        flex-direction: column;
        height: 100%;
        justify-content: space-around;
    }
   
</style>
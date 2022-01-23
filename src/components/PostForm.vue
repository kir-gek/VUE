<template>
    <form @submit.prevent class="form">
            <!-- @submit.prevent чтобы не обновлялась стр -->
            <h4>Создание поста</h4>
            <input 
            v-bind:value="post.title" 
            @input="post.title=$event.target.value"
            class="input" 
            type="text" 
            placeholder="Название"
            >
            <!-- @input="title=$event.target.value" cвязывание вписанного текста с переменной  -->
            <input 
            v-bind:value="post.body" 
             @input="post.body=$event.target.value"
            class="input" 
            type="text" 
            placeholder="Описание"
            >
            <button @click="createPost">Создать</button>
        </form>
</template>

<script>
export default{
    data(){
        return{
            post:{
                title:'',
                body:'',
            }
        }
    }
}
</script>

<style scoped>
.form{
    display: flex;
    flex-direction: column;
    justify-content: space-around;
}
.form button{
    margin-top: 15px;
    align-self: flex-end;
    padding: 10px 15px;
    background: none;
    color: teal;
    border: 1px solid teal;  
}

.input{
    width: 100%;
    padding: 10px 15px;
    border: 2px solid teal;
    margin-top: 15px;
}
</style>
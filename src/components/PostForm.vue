<template>
    <form @submit.prevent class="form">
            <!-- @submit.prevent чтобы не обновлялась стр -->
            <h4>Создание поста</h4>
            <my-input 
            v-model="post.title" 
            type="text" 
            placeholder="Название"
            >
            </my-input>

            <my-input 
            v-model="post.body"
            type="text" 
            placeholder="Описание"
            >         
            </my-input>
            <my-button class="form_btn" @click="createPost">Создать</my-button>
        </form>  
        
        
        <!-- @input="title=$event.target.value" cвязывание вписанного текста с переменной  -->
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
    },
    methods:{
        createPost(){
            this.post.id= Date.now();
            this.$emit('create', this.post);
            this.post={
                title:'',
                body:'',
            }
            
        },
    }
}
</script>

<style scoped>
.form{
    display: flex;
    flex-direction: column;
    justify-content: space-around;
}

.form .form_btn{
    align-self: flex-end;
    margin-top: 15px;
}

</style>
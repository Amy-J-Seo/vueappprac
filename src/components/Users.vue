<template>
    <div class="users">
      <h1>Users</h1>
      <form v-on:submit="addUser">
          <input type="text" v-model="newUser.name" placeholder="Entere name"><br>
          <input type="text" v-model="newUser.email" placeholder="Entere email"><br>
          <button>submit</button>
      </form>
      <ul>
          <li v-for="user in users" :key="user.name">{{user.name}}:{{user.email}}</li>
      </ul>
    </div>
</template>

<script>
export default {
    name:"Users",
    
data(){
    return{
       users:[
           {name:'John Doe',
           contacted: false,
           email:'hd@gmail.com'},
            {name:'aaa Doe',
           contacted: false,
           email:'aaaaa@gmail.com'},
            {name:'sssss Doe',
           contacted: false,
           email:'ssssss@gmail.com'},
       ],
       newUser:{name:"", email:""}
    }
},
methods:{
   addUser(e){
       e.preventDefault();
    console.log('submitted');
    this.users.push({
        name:this.newUser.name,
        email:this.newUser.email,
        contacted:false
    })
   }
},
computed:{

}
}
</script>
<style scoped>

</style>
<template>
    <div class="test">
        <input type="text" v-model="title"><br>


        <h1>{{title}}</h1>
        <p v-if="showName">{{user.firstName}}</p>
        <p v-else>Nobody</p>

        <ul>
            <li v-for="item in items" :key="item.title">{{item.title}}</li>
        </ul>

        <button v-on:click="greet('memee')">say greeting</button>

        <input type="text" v-on:keyup="pressKey" v-on:keyup.enter="enterHit" />
        <hr>
        <label for="firstName">First name</label>
        <input type="text" id=firstName v-model="user.firstName"><br>
            <label for="lastName">Last name</label>
        <input type="text" id=lastName v-model="user.lastName"><br>
        <h3>{{fullname}}</h3>
        <h2>{{msg}}</h2>
    </div>
</template>

<script>
export default {
    name:"Test",
    props:{
        msg:{
            type:"string",
            default:'Foobar'
        }
    },
data(){
    return{
        title:'Hambochi',
        user:{
            firstName:'John',
            lastName:'Doe'
        },
        showName:true,
        items:[
            {title:'item1'},
            {title:'item2'},
            {title:'item3'},
            {title:'item4'},
        ]
    }
},
methods:{
    greet(str){
        alert(str)
    },
    pressKey(e){
        console.log(e.target.value);
    },
    enterHit(){
        console.log('you hit enter');
    }
},
computed:{
    fullname(){
        return this.user.firstName+ " "+this.user.lastName;
    }
}
}
</script>
<style scoped>

</style>
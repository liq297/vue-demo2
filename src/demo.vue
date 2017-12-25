<template>
    <div id="demo">
        <fieldset>
            <legend>Add New Customer</legend>
            <form class="form-horizontal" onsubmit="return false;">
                <div class="form-group">
                    <label>Name:</label>
                    <input type="text" v-model="name">
                </div>
                <div>
                    <label>Age:</label>
                    <input type="text" v-model="age">
                </div>
                <div class="form-group">
                    <label for="inputEmail3" class="col-sm-2 control-label">Email</label>
                    <input type="email" v-model="email">
                </div>
                <div class="form-group">
                    <div class="col-sm-offset-2 col-sm-10">
                        <button class="btn btn-default" @click="addNewCustomer">Submit</button>
                    </div>
                </div>
            </form>
            <div>
                <table>
                    <thead>
                        <tr>
                            <th>Name</th>
                            <th>Age</th>
                            <th>Email</th>
                            <th>Delete</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr v-for="each_user,index in user_info_list">
                            <td>{{each_user.name}}</td>
                            <td>{{each_user.age}}</td>
                            <td>{{each_user.email}}</td>
                            <td><button @click="deleteOneCustomer(index)">Delete</button></td>
                        </tr>
                    </tbody>
                </table>            
            </div>
        </fieldset>
    </div>
</template>

<script>
    export default {
        name:'demo',
        data() {
            return {
                name:"liqian",
                age:"",
                email:"",
                user_info_list:[
                    {
                        name:"jack",
                        age:20,
                        email:"376459@qq.com"
                    },
                     {
                        name:"jack",
                        age:20,
                        email:"376459@qq.com"
                    },
                     {
                        name:"jack",
                        age:20,
                        email:"376459@qq.com"
                    }
                ]
            }
        },
        methods:{
            addNewCustomer:function(event){
                var new_customer = {};
                new_customer.name = this.name;
                new_customer.age = this.age;
                new_customer.email = this.email;
                this.user_info_list.push(new_customer);
            },
            deleteOneCustomer:function(index){
                this.user_info_list.splice(index,1);
            }
        }
    }
</script>
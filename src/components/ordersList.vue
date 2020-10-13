<template>
    <div>
        <div>
            <b-card no-body>
                <b-tabs card >
                <b-tab title="Orders Received" active  >
                    
                        
        <table class="table table-striped">
        
        
              <thead>
                
                <tr>
                <th>Order ID</th>
                <th>Customer Name</th>
                <th>No. items</th>
                <th>Amount</th>
                <th>Change Order status</th>
                </tr>
            </thead>
        
            <tbody v-for="(item,index) in orders" :key="index">

                    <tr v-if="item.status=='Order Received'">
                <td>{{ item.orderId}}</td>
                <td>{{ item.cName }}</td>
                <td>{{ item.items }}</td>
                <td>{{ item.amount }}</td>
                <td><b-button variant="primary" @click="changeStatus(item)"> Change status</b-button></td>
                </tr>
                
                <!-- </div> -->
            </tbody>
        </table>



                </b-tab>
        <b-tab title="Preparing">
                                     
        <table class="table table-striped">
        
        
              <thead>
                
                <tr>
                <th>Order ID</th>
                <th>Customer Name</th>
                <th>No. items</th>
                <th>Amount</th>
                <th>Change Order status</th>
                </tr>
            </thead>
        
            <tbody v-for="(item,index) in orders" :key="index">

                    <tr v-if="item.status=='preparing'">
                <td>{{ item.orderId}}</td>
                <td>{{ item.cName }}</td>
                <td>{{ item.items }}</td>
                <td>{{ item.amount }}</td>
                <td> 
                    <b-button variant="primary" @click="changeStatustoServe(item)"> Change status</b-button>
                    </td>
                </tr>
                
                <!-- </div> -->
            </tbody>
        </table>

                </b-tab>
                <b-tab title="Ready to serve">
                    <table class="table table-striped">
        
        
              <thead>
                
                <tr>
                <th>Order ID</th>
                <th>Customer Name</th>
                <th>No. items</th>
                <th>Amount</th>
                
                </tr>
            </thead>
        
            <tbody v-for="(item,index) in orders" :key="index">

                    <tr v-if="item.status=='Ready to serve'">
                <td>{{ item.orderId}}</td>
                <td>{{ item.cName }}</td>
                <td>{{ item.items }}</td>
                <td>{{ item.amount }}</td>
                
                </tr>
                
                <!-- </div> -->
            </tbody>
        </table>

                </b-tab>
                </b-tabs>
            </b-card>
            </div>
     
    </div>
</template>
<script>
import 'bootstrap-vue/dist/bootstrap-vue.css'

export default {
    
    data(){
        return{
            orders:[
                {"orderId":122,"cName":"Rajesh","items":1,"amount":"1000","status":"Order Received"},
                {"orderId":431,"cName":"Ram","items":1,"amount":"2000","status":"Order Received"},
                {"orderId":111,"cName":"Rahul","items":1,"amount":"3000","status":"Order Received"},
                {"orderId":221,"cName":"Rajib","items":1,"amount":"4000","status":"Ready to serve"},
                {"orderId":531,"cName":"Rakhee","items":1,"amount":"5000","status":"preparing"}]
        }
    },
    methods:{
        changeStatus(item){
            for(let i in this.orders){
                if(this.orders[i].orderId == item.orderId   ){
                    console.log(this.orderId)
                    this.orders[i].status="preparing"
                }
            }
        },
        changeStatustoServe(item){
            for(let i in this.orders){
                if(this.orders[i].orderId == item.orderId   ){
                    console.log(this.orderId)
                    this.orders[i].status="Ready to serve"
                }
            }
        }
    }
}
</script>
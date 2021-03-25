<template>
  <div>
    <h1>{{title}}</h1>
    <input type="text" v-model="input1" />
    <button type="button" @click="getData">get</button>
    <button type="button" @click="setData">set</button>
    <select class="form-control" v-model="region" @change="changeRegion">
        <option v-for="(item, index) in options" :key="index" :value="item.v">{{item.t}}</option>
    </select>
    <table class="table table-bordered" v-show="tableShow">
        <tr  v-for="(item, index) in options" :key="index">
            <td>{{item.v}}</td>
            <td>{{item.t}}</td>
        </tr>

    </table>
  </div>
</template>
<script>
export default {
    data(){
        return{
            title : "good",
            input1 : "abc",
            options :[
                {v:"S", t:"Seoul"},
                {v:"J", t:"Jeju"},
                {v:"B", t:"Busan"},
            ],
            region : "",
            tableShow : false,
        };
    },
    //watch 메소드는 객체의 이름과 동일한 이름을 함수로 만들어 실시간으로 변화 하는값을 출력한다
    watch:{
        input1(){
            console.log(""+this.input1)
        }
    },
    methods:{
        getData(){
            alert(this.input1)
        },
        setData(){
            this.input1 = "1234"
        },
        changeRegion(){
            alert(this.region)
        },
    },
    beforeCreate(){
        //console.log("beforeCreate");
    },
    created(){
        //console.log("created 시작과 동시에 동작 ex 디비에서 데이터를 미리 들고와서 바로 뿌려준다");
    },
    beforeMount(){
        //console.log("beforeMount");
    },
    mounted(){
        //console.log("mounted");
    },
    beforeUpdate(){
        //console.log(" beforeUpdate 데이터 변경시 동작");
    },
    updated(){ 
        //console.log(" updated 데이터 변경시 동작");
    },
    beforeDestroy(){
        //console.log("beforeDestroy");
    },
    destroyed(){
        //console.log("destroyed");
    },
   
};
</script>
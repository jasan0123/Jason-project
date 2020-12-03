<template>
  <div class="kanban">
      <div class="column" :style="{backgroundColor:column.color}" 
      v-for="(column , index) in data" 
      :key="index">

          <div class="column-header">
            {{column.name}}
          </div>

          <div class="column-body">  
            <div class="create-task" @click="create_task(index)"> Create Task </div>
          </div>
          

      </div>
      <b-model ref="create-task-model" title="Create Task">
          <p class="my-4">Hello from model!</p>
      </b-model>
  </div>
</template>

<script>
export default {
    props:{
        data:Array
    },
    methods:{
        create_task(index_column){
            console.log(index_column);
            this.$refs["create-task-model"].show()
        },
    },
}
</script>

<style>
.kanban{
    background-color: blueviolet;
    width: 100%;
    height: 100%;
}
.column{
    height: 600px;
    width: 300px;
    border-radius:10px ;
    display: inline-block;
    margin: 25px;
    padding: 10px;
    -webkit-box-shadow: 10px 10px 5px 0px rgba(0,0,0,0.75);
-moz-box-shadow: 10px 10px 5px 0px rgba(0,0,0,0.75);
box-shadow: 10px 10px 5px 0px rgba(0,0,0,0.75);
}
.column-header{
    display: flex;
    align-items: center;
    justify-content: center;
    height: 50px;
    font-size: 32px;
    font-weight: bold;
}
.column-body{
    height: calc(100% - 50px);
    border-radius: 10px;
    padding: 5px;
    background-color: rgba(255, 248, 220, 0.541);
}
.create-task{
    width: 100%;
    height: auto;
    padding: 10px;
    border-radius: 5px ;
    cursor: pointer;
}
.create-task:hover{
    background-color: crimson;
}
</style>
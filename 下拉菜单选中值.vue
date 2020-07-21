<template>
          <el-form>
              <el-form-item label="资源属性:">
                  <el-dropdown   @command="handleCommand($event,item,index,'attr')" trigger="click" v-for="(item,index) in resourceAttr" :key="index">
                      <span class="el-dropdown-link">
                        {{item.name}}<i class="el-icon-arrow-down el-icon&#45;&#45;right"></i>
                      </span>
                      <el-dropdown-menu slot="dropdown">
                          <el-dropdown-item v-for="(items,idx) in item.child" :key="idx"  :command="items">{{items.label}}</el-dropdown-item>
                      </el-dropdown-menu>
                  </el-dropdown>
              </el-form-item>
          </el-form>

 
</template>

<script>
    export default {
        name: "index",
        data(){
            return{
                resourceAttr:[
                    {
                        name:'数据来源',
                        child:[
                            {
                                label:'＃中'
                            }
                        ]
                    },
                    {
                        name:'阳江',
                        child:[
                            {
                                label:'阳江'
                            }
                        ]
                    },
                    {
                        name:'来源网域',
                        child:[
                            {
                                label:'＃中'
                            }
                        ]
                    },
                    {
                        name:'采集单位',
                        child:[
                            {
                                label:'＃中'
                            }
                        ]
                    },
                    {
                        name:'来源应用',
                        child:[
                            {
                                label:'＃中'
                            }
                        ]
                    },
                    {
                        name:'厂商',
                        child:[
                            {
                                label:'＃中'
                            }
                        ]
                    },
                    {
                        name:'资源状态',
                        child:[
                            {
                                label:'＃中'
                            }
                        ]
                    },
                ],
            }
        },
      
        methods:{
      
            handleCommand(val,item,index,types) {
                this.$set(item,"name",val.label) //用set更改item的值
               
            },
           
    }
</script>

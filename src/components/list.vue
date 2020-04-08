<template>
    <ul>
        <li class="list" v-for="item of items" v-bind:key="item.id" v-bind:class="{'active':item.active}" v-on:click="click(item)">
            {{item.text}}
        </li>
    </ul>
</template>
<script type="text/javascript">
  export default{
    name:'list',
    props:['items'],
    components:{

    },
    methods:{
      click(item){
      this.items.forEach( item => console.log(item));
      this.items.forEach( item => item.active = false );
      item.active = true;

      if(item.click)
        item.click(item);
      else if(item.both_events){
        item.click(item);
        this.$emit('item-clicked', item)
      }else
        this.$emit('item-clicked', item)

    }
    },
    created(){

    }

  }
</script>
<style media="screen" scoped>
    ul{
        display: flex;
        margin: 0;
        padding: 0;
    }
    li{
        flex: 1 0 auto;
        list-style-type: none;
        cursor: pointer;
        padding: 0;
    }

    ul.navbar{
        flex-direction: row;
    }
    ul.navbar li{
        flex: 1 0 0;
        text-align: center;
        border-bottom: solid 2pt transparent;
    }
    ul.navbar li.active{
        border-color: #42b983;
    }

    ul.sidebar{
        flex-direction: column;
    }
    ul.sidebar li{
        flex: 1 0 auto;
        text-align: left;
        background-color: white;
        color: #2c3e50;
    }
    ul.sidebar li.active{
        color: white;
        background-color: #42b983;
    }
</style>

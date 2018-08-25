<template>
  <div id="app">
    <div class="head">
      <h1>iview jsx 使用demo</h1>
      <h2>以table中使用select为例</h2>
    </div>
    <div class="before-select">
      <span>城市选择 官方写法:</span>
      <Select v-model="model1" style="width:200px">
        <Option v-for="item in cityList" :value="item.value" :key="item.value">{{ item.label }}</Option>
      </Select>
    </div>
    <Table :columns="columns1" :data="data1"></Table>
  </div>
</template>

<script>

export default {
  name: 'app',
  data() {
    return {
      columns1: [
        {
          title: 'Name',
          key: 'name'
        },
        {
          title: 'Age',
          key: 'age'
        },
        {
          title: 'Address',
          key: 'address'
        },
        {

          title: 'jsx 城市选择',
          key: 'city',
          render: (h, params) => {
            return (<div>jsx render</div>)
          }
        }

      ],
      data1: [
        {
          name: 'John Brown',
          age: 18,
          address: 'New York No. 1 Lake Park',
          date: '2016-10-03'
        },
        {
          name: 'Jim Green',
          age: 24,
          address: 'London No. 1 Lake Park',
          date: '2016-10-01'
        },
        {
          name: 'Joe Black',
          age: 30,
          address: 'Sydney No. 1 Lake Park',
          date: '2016-10-02'
        },
        {
          name: 'Jon Snow',
          age: 26,
          address: 'Ottawa No. 2 Lake Park',
          date: '2016-10-04'
        }
      ],
      cityList: [
        {
          value: 'New York',
          label: 'New York'
        },
        {
          value: 'London',
          label: 'London'
        },
        {
          value: 'Sydney',
          label: 'Sydney'
        },
        {
          value: 'Ottawa',
          label: 'Ottawa'
        },
        {
          value: 'Paris',
          label: 'Paris'
        },
        {
          value: 'Canberra',
          label: 'Canberra'
        }
      ],
      model1: ''
    }
  }
}
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  padding: 20px;
}
.head {
  margin-top: 60px;
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.before-select {
  height: 60px;
  display: flex;
  align-items: center;
}
.before-select span {
  margin-right: 20px;
}
</style>

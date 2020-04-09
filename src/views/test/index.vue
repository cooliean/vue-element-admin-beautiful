<template>
  <div class="test-container">
    <el-row :gutter="15">
      <el-col :xs="24" :sm="24" :md="12" :lg="12" :xl="12">
        <el-card shadow="never">
          <div slot="header">
            <svg-icon icon-class="heat_map" />
            <span>交流学习群(愿者上钩,童叟无欺)</span>
          </div>
          <img src="@/assets/ewm.png" />
        </el-card>
      </el-col>
      <el-col :xs="24" :sm="24" :md="12" :lg="12" :xl="12">
        <el-card
          shadow="never"
          style="height: 335px; line-height: 30px; font-weight: bold;"
        >
          在这里你能学到更多的知识,包括eslint自动的修复而不是手动--fix(千万不要去掉规范,规范是每个人必备的技能),
          包括组件的快速搭建与入手,你的所有问题都会第一时间得到解答,你同时还可以获得一手的学习资料,不要去相信网上好几年前的教程,对技术没有任何的提升,
          这里有更多的注册码与激活工具,保证你的开发坏境实时保持最新,当然一切都是你的自愿原则,你来或者不来,我都会在那里,开源还是会继续,你还是可以享受到最新的开源代码
        </el-card>
      </el-col>
    </el-row>

    <!--<div>
      <br />
      select哪个字段指的是与和或,与是0,或是1
      <br />
      这里会自动的根据你添加的节点生成json
      <br />
      {{ JSON.stringify(data) }}
    </div>
    <div class="block">
      <p>使用 scoped slot</p>
      <el-tree
        :data="data"
        node-key="id"
        default-expand-all
        :expand-on-click-node="false"
      >
        <span class="custom-tree-node" slot-scope="{ node, data }">
          <span>{{ node.label }}</span>
          <span>
            {{ node.select }}
            <el-select v-if="2 === node.level" v-model="data.select">
              <el-option
                v-for="item in options"
                :key="item.value"
                :label="item.label"
                :value="item.value"
              >
              </el-option>
            </el-select>
          </span>
          <span>
            <el-button
              v-if="1 === node.level"
              type="text"
              size="mini"
              @click="() => append(data, node.level)"
            >
              添加子级
            </el-button>
            &lt;!&ndash;<el-button
              v-if="2 === node.level"
              type="text"
              size="mini"
              @click="() => append(data, node.level)"
            >
              添加三级
            </el-button>&ndash;&gt;
            右边是后端反的<el-select
              v-if="2 === node.level"
              v-model="data.sjselect"
              @change="(value, label) => append(data, node.level, value, label)"
            >
              <el-option
                v-for="item in options2"
                :key="item.value"
                :value="item.value"
              >
              </el-option>
            </el-select>
            <el-button
              v-if="1 !== node.level"
              type="text"
              size="mini"
              @click="() => remove(node, data)"
            >
              删除
            </el-button>
          </span>
        </span>
      </el-tree>
      <el-button @click="handleGetAll" type="primary">打印到控制台</el-button>
    </div>-->
  </div>
</template>
<script>
let id = 0;
let id2 = 0;
export default {
  data() {
    let data = [
      {
        id: "0",
        label: "我的方案",
        children: [
          {
            id: "0",
            label: "方案0",
            select: 0,
            sjselect: "",
            children: [],
          },
        ],
      },
    ];
    return {
      data: JSON.parse(JSON.stringify(data)),
      options: [
        {
          value: 0,
          label: "与",
        },
        {
          value: 1,
          label: "或",
        },
      ],
      options2: [
        {
          value: "a",
          label: "a",
        },
        {
          value: "b",
          label: "b",
        },
      ],
    };
  },

  methods: {
    handleGetAll() {
      console.log(JSON.stringify(this.data));
    },
    append(data, level, value) {
      debugger;
      if (1 === level) {
        id++;
        const newChild = {
          id: id,
          label: "方案" + id,
          select: 0,
          children: [],
        };
        if (!data.children) {
          this.$set(data, "children", []);
        }
        data.children.push(newChild);
      }
      if (2 === level) {
        id2++;
        /*在这里调用后端反的数据*/
        const newChild = { id: id2, label: value, children: [] };

        if (!data.children) {
          this.$set(data, "children", []);
        }
        data.children.push(newChild);
      }
    },

    remove(node, data) {
      const parent = node.parent;
      const children = parent.data.children || parent.data;
      const index = children.findIndex((d) => d.id === data.id);
      children.splice(index, 1);
    },
  },
};
</script>
<style lang="scss" scoped>
::v-deep {
  .el-tree-node__content {
    height: 46px;
  }

  .el-select {
    margin-left: 10px;
  }
}
</style>

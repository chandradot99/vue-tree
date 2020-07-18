<template>
  <div>
    <div class="tree-header">
      <h2>Tree Demo</h2>
      <select v-model="treeView">
        <option value="file">File</option>
        <option value="map">Map</option>
        <option value="outline">Outline</option>
      </select>
    </div>
    <div v-if="data">
      <tree :treeData="data" :treeOptions="treeOptions" :treeView="treeView"></tree>
    </div>
  </div>
</template>

<script>
import tree from './../v-tree/index'

export default {
  components: {
    tree
  },
  data () {
    return {
      data: null,
      treeView: 'file',
      treeOptions: {
        childrenKey: 'children',
        selectable: false,
        showHoverOptions: false,
        singleSelect: false
      }
    }
  },
  methods: {
    initTreeData () {
      this.data = {
        id: 1,
        options: {
          label: 'First',
          classes: [],
          icon: '',
          hoverOptions: [],
          expanded: true,
          selected: false,
          visible: true,
          selectable: false,
          draggable: true
        },
        children: [
          {
            id: 11,
            options: {
              label: 'First First',
              classes: [],
              icon: '',
              hoverOptions: [],
              expanded: true,
              selected: false,
              visible: true,
              selectable: false,
              draggable: true
            },
            children: [
              {
                id: 11,
                options: {
                  label: 'First First',
                  classes: [],
                  icon: '',
                  hoverOptions: [],
                  expanded: true,
                  selected: false,
                  visible: true,
                  selectable: false,
                  draggable: true
                }
              },
              {
                id: 12,
                options: {
                  label: 'First Second',
                  classes: [],
                  icon: '',
                  hoverOptions: [],
                  expanded: true,
                  selected: false,
                  visible: true,
                  selectable: false,
                  draggable: true
                }
              }
            ]
          },
          {
            id: 12,
            options: {
              label: 'First Second',
              classes: [],
              icon: '',
              hoverOptions: [],
              expanded: true,
              selected: false,
              visible: true,
              selectable: false,
              draggable: true
            },
            children: [
              {
                id: 11,
                options: {
                  label: 'First First',
                  classes: [],
                  icon: '',
                  hoverOptions: [],
                  expanded: true,
                  selected: false,
                  visible: true,
                  selectable: false,
                  draggable: true
                }
              },
              {
                id: 12,
                options: {
                  label: 'First Second',
                  classes: [],
                  icon: '',
                  hoverOptions: [],
                  expanded: true,
                  selected: false,
                  visible: true,
                  selectable: false,
                  draggable: true
                }
              }
            ]
          }
        ]
      }
    }
  },
  mounted () {
    this.initTreeData()
  }
}
</script>

<style lang="scss" scoped>
  .tree-header {
    text-align: center;
  }
</style>

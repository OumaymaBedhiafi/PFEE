<template>
  <a-menu
    class="menu font-sf-regular margin-t-menu"
    mode="inline"
    theme="gray"
  >
    <a-row justify="space-around">
      <draggable
        :clone="clone"
        class="drag"
        :list="navTree"
        :sort="false"
        :group="{ name: 'oum', pull: 'clone', put: false }"
        item-key="id"
      >
        <template
          #item="{ element: nav }"
        >
          <a-col
            class="component rounded"
            :span="120"
          >
            <a-menu-item class="menu-item">
              <div
                v-if="nav.organismName!=='section'"
                class="icon-container"
              >
                <img :src="navIcons[nav.image]">
              
          
                <span class="label-class"> {{ $t(nav.organismName) }} </span>
              </div>

              <div v-if="nav.organismName ==='section'">
                <a-popover placement="right">
                  <template #content>
                    <div class="icon-container">
                      <div
                        class="my-icon-class"
                      >
                        <img :src="navIcons[nav.image]">
                      </div>
                    </div>
                  </template>
                  <template #title>
                    <span>Add New Section</span>
                  </template>
                  <span class="label-class">{{ $t(nav.organismName) }}</span>
                </a-popover>
              </div>
            </a-menu-item>
          </a-col>
        </template>
      </draggable>
    </a-row>
  </a-menu>
</template>




<script lang="ts" setup>
 import { v4 as uuidv4 } from 'uuid'
 import { cloneDeep } from 'lodash';
 import nav from '~~/assets/data/nav.json';


 

  defineProps({
    collapsed: {
      type: Boolean,
    },
    navTree: {
      type: Array,
      default: () => {
        return [];
      },
    },
  });

  const clone = (component) => {
            component.uuid = uuidv4()
                return cloneDeep(component)
            }

  function onDragOver(event): void {
    event.target.classList.add('dndPlaceholder');
  }


  
  

   function onDragStart(event: DragEvent) {

   // event.dataTransfer.dropEffect = 'move';
    //event.dataTransfer.effectAllowed = "move";


    //event.dataTransfer?.setData('component', JSON.stringify(component))
    //  this.$emit('onDragstart', 'bg-light');
    //},
    //onDragEnd(event: DragEvent) {
      //this.$emit('onDragEnd');
    }
  


</script>


<style lang="less">
@import 'ant-design-vue/lib/menu/style/index.less';
</style>

<style lang="scss" scoped>
@import '@UI/assets/scss/variable';

.icon-container {
  border: 1px solid rgb(255, 255, 225);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  background: rgb(255, 255, 255);
  padding: 20px 30px  20px  30px ;

}

.my-icon-class {
  color: #86898d;
  font-size:3px;
}

.label-class {
 
  font-size: 11px;
  color: #595c5f;
  line-height: 1;
}

.menu.ant-menu-gray {
  background-color: #f7f7f7;

  height: 100%;
 
}
.menu-item {
  display: inline-block;
  margin-right: 10px; /* vous pouvez ajuster ce nombre pour définir l'espace entre les éléments de menu */
}


.email-structure {
  min-height: 100%;
}

#components-popover-demo-placement .ant-btn {
      width: 70px;
      text-align: center;
      padding: 0;
      margin-right: 8px;
      margin-bottom: 8px;
    }

</style>

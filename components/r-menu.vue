<template>
    <div v-if="menuShow" class="rMenu" id='rMenu' @mouseleave="closeMenu" :style="{top:y+'px',left:x+'px'}">
        <ul>
            <li 
                v-for='(m,i) in data'
                :key='i'
                @click="liClick(m),closeMenu()" >
               {{ m.optionName }}
            </li>
        </ul>
    </div>
</template>

<script>
export default {
  data() {
    return {
      menuShow: false,
      top: 0,
      left: 0,
      data: []
    };
  },
  props: {
    liClick: {
      type: Function,
      default: function() {
        console.log();
      }
    }
  },
  methods: {
    closeMenu() {
      this.menuShow = false;
    },
    openMenu(obj) {
      this.menuShow = true;
      this.y = obj.y - 10;
      this.x = obj.x - 10;
      this.data = obj.data;
    }
  }
};
</script>
<style>
.rMenu {
  position: absolute;
  top: 0;
  background: #fdfdfd;
  border-radius: 3px;
  border: 1px solid #b1b1b1;
  box-shadow: 0 1px 5px #666;
  font-size: 12px;
}
.rMenu ul {
  padding: 0;
  list-style-type: none;
  margin: 0;
}
.rMenu ul li {
  border-bottom: 1px solid #dcdcdc;
  box-shadow: 0 1px 0 #fff;
  padding: 5px 10px;
  width: 100px;
}
.rMenu ul li:last-child {
  border-bottom: 0px;
  box-shadow: 0 1px 0 #fff;
  padding: 5px 10px;
  width: 100px;
}
.rMenu ul li:hover {
  background: #ececec;
  cursor: pointer;
}
</style>
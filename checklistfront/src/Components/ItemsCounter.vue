<template>
  <div class='ItemsCounter'>{{counter}}</div>
</template>

<script>
export default {
  name: 'count',

  props: ['allItems', 'singleCategory', 'itemsChecked'],

  computed: {
    counter () {
      const liste = this.allItems.filter(
        i => i.category_name === this.singleCategory
      )
      let countChecked = 0

      for (let it = 0; it < liste.length; it++) {
        if (this.itemsChecked.includes(liste[it].name)) {
          countChecked += 1
        }
      }
      return ` ${countChecked} / ${liste.length} `
    }
  }
}
</script>

<style>
.ItemsCounter {
  color: gray;
}
</style>

<template>
  <div>
    <AccordionMenu class="tagmodal-checklist_category" v-for="list in tag_lists" :key="list.id">
      <button slot="title" class="tagmodal-checklist_category_title">
        <p>{{ list.type }}</p>
      </button>
      <li class="tagmodal-checklist_category_column" slot="content">
        <ul v-for="tag in list.tags" :key="tag.id" >
          <li>
            <input type="checkbox" :id="tag.id" :value="tag" />
            <label :for="tag.id">
              <img :src="'https://ptera-publish.topaz.dev/' + tag.icon_path" :alt="tag.id" />
              {{ tag.id }}
            </label>
          </li>
        </ul>
      </li>
    </AccordionMenu>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import AccordionMenu from '~/components/VAccordionMenu.vue'

export default Vue.extend({
  data() {
    return {
      tag_lists: [
      {
        type: 'aaa',
        tags: [
          'aaa1', 'aaa2', 'aaa3'
        ]
      },
      {
        type: 'bbb',
        tags: [
          'bbb1', 'bbb2', 'bbb3'
        ]
      },
      {
        type: 'ccc',
        tags: [
          'ccc1', 'ccc2', 'ccc3'
        ]
      },
    ]
    }
  },
  components: {
    AccordionMenu
  }
})
</script>

<style lang="scss" scoped>
html {
  background: lightgrey;
}
</style>

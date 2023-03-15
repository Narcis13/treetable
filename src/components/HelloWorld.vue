<script setup>
import { ref ,computed} from 'vue'

const props=defineProps({
  data:Array,
  groupBy:String
})
const groupedData=computed(()=> {
      // group the data by the specified property
      const groups = {}
      props.data.forEach((item) => {
        const groupValue = item[props.groupBy]
        if (groups[groupValue]) {
          groups[groupValue].items.push(item)
        } else {
          groups[groupValue] = {
            groupName: groupValue,
            items: [item]
          }
        }
      })

      // convert the groups object to an array
      const result = []
      for (const groupName in groups) {
        result.push(groups[groupName])
      }

      return result
    })

</script>

<template>
   <table>
      <tbody>
        <template v-for="group in groupedData">
          <tr><td class="antet" colspan="3">{{ group.groupName }}</td></tr>
          <tr v-for="row in group.items">
            <td>{{ row.name }}</td>
            <td>{{ row.age }}</td>
            <td>{{ row.gender }}</td>
          </tr>
        </template>
      </tbody>
    </table>
</template>

<style scoped>
.antet {
  text-align: left;
  font-weight: 700;
}
</style>

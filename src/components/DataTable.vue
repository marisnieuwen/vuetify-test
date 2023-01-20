<template>
    <v-table
      fixed-header
      :hover=true
    >
      <thead>
        <tr sortable= true>
            <th class="text-left">
            
          </th>
          <th class="text-left">
            Name and type
          </th>
          <th class="text-left">
            Severity
          </th>
          <th class="text-left">
            Description
          </th>
          <th class="text-left">
            Reported
          </th>
        </tr>
      </thead>

      
      <tbody>
        <tr
          v-for="item in problems"
          :key="item.name"
          :style="`background:${getColorTable(item.severity)}`"
          class="table-row-dashboard"
        >

          <td>{{ item.image }}</td>
          <td>{{ item.name }} {{ item. type}}</td>
          <td><v-chip class="ma-2" :style="`background:${getColorChip(item.severity)}`" label>{{ item.severity }} <v-icon :icon="`${getIcon(item.severity)}`" :style="`padding-left: 7px`"></v-icon></v-chip></td>
          <td>{{ item.description }}</td>
          <td>{{ item.reported }}</td>
        </tr>
      </tbody>
    </v-table>
  </template>

<script>
export default {
  data () {
    return {
      problems: [
        {
          image: '',
          name: 'Frozen Yogurt',
          type: '',
          severity: 4,
          description: 'Lorem ipsum dolor sit amet, consec adipiscing elit. Ut et massa mi. Lorem ipsum dolor sit amet, consec adipiscing..',
          reported: '3 mintues ago',
        },
        {
          image: '',
          name: 'Frozen Yogurt',
          severity: 4,
          description: 'Loremipsum',
          reported: '0',
        },
        {
          image: '',
          name: 'Frozen Yogurt',
          severity: 4,
          description: 'Loremipsum',
          reported: '0',
        },
        {
          image: '',
          name: 'Frozen Yogurt',
          severity: 3,
          description: 'Loremipsum',
          reported: '0',
        },
        {
          image: '',
          name: 'Frozen Yogurt',
          severity: 3,
          description: 'Loremipsum',
          reported: '0',
        },
        {
          image: '',
          name: 'Frozen Yogurt',
          severity: 2,
          description: 'Loremipsum',
          reported: '0',
        },
        {
          image: '',
          name: 'Frozen Yogurt',
          severity: 2,
          description: 'Loremipsum',
          reported: '0',
        },
        {
          image: '',
          name: 'Frozen Yogurt',
          severity: 2,
          description: 'Loremipsum',
          reported: '0',
        },
        {
          image: '',
          name: 'Frozen Yogurt',
          severity: 1,
          description: 'Loremipsum',
          reported: '0',
        },
        {
          image: '',
          name: 'Frozen Yogurt',
          severity: 1,
          description: 'Loremipsum',
          reported: '0',
        },
      ],
    }
  },
  methods: {
      getColorTable (severity) {
        if (severity >= 4) return '#BE151F'
        else if (severity > 2) return '#CC7A1A'
        else if (severity > 1) return '#245A90'
        else return '#304352'
      },
      getColorChip (severity) {
        if (severity >= 4) return '#930A0A'
        else if (severity > 2) return '#B2650A'
        else if (severity > 1) return '#0A3D71'
        else return '#202C36'
      },
      getIcon (severity) {
        if (severity >= 4) return 'mdi-alert-circle'
        else if (severity > 2) return 'mdi-alert-circle-outline'
        else if (severity > 1) return 'mdi-timer-outline'
        else return 'mdi-timer-outline'
      },
    }
}
</script>

<style scoped>
  td {
    border: solid 1px transparent;
    border-style: solid none;
    padding: 20px;
    height: 60px !important;
  }

  td:first-child {
    border-left-style: solid;
    border-top-left-radius: 10px;
    border-bottom-left-radius: 10px;
  }

  td:last-child {
    border-right-style: solid;
    border-bottom-right-radius: 10px;
    border-top-right-radius: 10px;
  }
.v-table {
  border: solid 1px transparent;
  border-radius: 6px;
  margin-top: 35px;
}
  .v-table :deep() .v-table__wrapper > table {
    border-spacing: 0 0.7rem;
    border-color: transparent;
  }

  .v-table--fixed-header :deep() .v-table__wrapper > table > thead > tr > th{
    font-size: large;
  }

  .v-table--fixed-header :deep() .v-table__wrapper > table > tbody > tr > td{
    font-size: medium;
    color: #fff;
  }
</style>

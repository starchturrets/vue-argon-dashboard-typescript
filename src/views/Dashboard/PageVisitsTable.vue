<template>
  <div class="card">
    <div class="card-header border-0">
      <div class="row align-items-center">
        <div class="col">
          <h3 class="mb-0">Page visits</h3>
        </div>
        <div class="col text-right">
          <a href="#!" class="btn btn-sm btn-primary">See all</a>
        </div>
      </div>
    </div>

    <div class="table-responsive">
      <base-table thead-classes="thead-light" :data="tableData">
        <template slot="columns">
          <th>Page name</th>
          <th>Visitors</th>
          <th>Unique users</th>
          <th>Bounce rate</th>
        </template>

        <template slot-scope="{ row }">
          <th scope="row">
            {{ row.page }}
          </th>
          <td>
            {{ row.visitors }}
          </td>
          <td>
            {{ row.unique }}
          </td>
          <td>
            <i
              class="fas fa-arrow-up text-success mr-3"
              :class="
                row.bounceRateDirection === 'up'
                  ? 'text-success'
                  : 'text-danger'
              "
            />
            {{ row.bounceRate }}
          </td>
        </template>
      </base-table>
    </div>
  </div>
</template>
<script>
  export default {
    name: 'PageVisitsTable',
    data() {
      return {
        tableData: [
          {
            page: '/argon/',
            visitors: '4,569',
            unique: '340',
            bounceRate: '46,53%',
            bounceRateDirection: 'up',
          },
          {
            page: '/argon/index.html',
            visitors: '3,985',
            unique: '319',
            bounceRate: '46,53%',
            bounceRateDirection: 'down',
          },
          {
            page: '/argon/charts.html',
            visitors: '3,513',
            unique: '294',
            bounceRate: '36,49%',
            bounceRateDirection: 'down',
          },
          {
            page: '/argon/tables.html',
            visitors: '2,050',
            unique: '147',
            bounceRate: '50,87%',
            bounceRateDirection: 'up',
          },
          {
            page: '/argon/profile.html',
            visitors: '1,795',
            unique: '190',
            bounceRate: '46,53%',
            bounceRateDirection: 'down',
          },
        ],
      };
    },
  };
</script>
<style>
</style>

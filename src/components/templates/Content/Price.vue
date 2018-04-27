<template>
  <section id="services">
    <div class="container">

      <header class="section-header wow fadeInUp">
        <h3>Стоимость бухгалтерского обслуживания</h3>
        <!--<p>Задача удаленной бухгалтерии — качественно, эффективно и на удобных условиях предоставлять широкий спектр бухгалтерских услуг. Даже вновь открытой организации необходим бухгалтер, но штатного бухгалтера не всегда можно себе позволить, особенно, если бизнес только на стадии становления. Поэтому удаленная бухгалтерия — это наилучшее решение для экономии на содержании персональной бухгалтерии и качественно организованного учета.</p>-->
      </header>

      <div class="row">

        <table class="table table-hover">
          <tr>
            <th v-for="col in columnsData" :key="col.id">{{col.label}}</th>
          </tr>
          <tbody>
            <tr v-for="(row,index) in rowsData" :key="index">
              <td v-for="col in columnsData" :key="col.id">
                <span v-if="col.countPlus">{{ row[col.column] + Math.ceil((row[col.column] * col.countPlus) / 100)  }}</span>
                {{row[col.id]}} {{col.addString}}
              </td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Price',
  data: function () {
    return {
      asd: 'asd2',
      columnsData: [
        { id: 'name', label: 'Наименование', addString: 'в месяц' },
        { id: 'price1', label: 'Услуги', addString: 'руб.' },
        { id: 'price2', label: 'Оптовая торговля', addString: 'руб.' },
        { id: 'price3', label: 'Розничная торговля', addString: 'руб.', column: 'price2', countPlus: 25 },
        { id: 'price4', label: 'Производство и строительная деятельность', addString: 'руб.', column: 'price1', countPlus: 50 }
      ],
      rowsData: [
        { name: 'До 5 операций', price1: 3000, price2: 3500 },
        { name: 'До 10 операций', price1: 5750, price2: 6700 },
        { name: 'До 15 операций', price1: 8250, price2: 9600 },
        { name: 'До 20 операций', price1: 10500, price2: 2250 },
        { name: 'До 25 операций', price1: 12500, price2: 4600 },
        { name: 'До 30 операций', price1: 14250, price2: 8400 },
        { name: 'До 35 операций', price1: 15750, price2: 16650 },
        { name: 'До 40 операций', price1: 17000, price2: 18400 },
        { name: 'До 45 операций', price1: 18500, price2: 19800 },
        { name: 'От 50 операций', price1: 20000, price2: 23500 }
      ]
    }
  }
}
</script>

<style></style>

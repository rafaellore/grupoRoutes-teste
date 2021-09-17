<template>
  <div class="q-pa-md">
    <q-table
      title="Treats"
      :rows="rows"
      :columns="columns"
      row-key="name"
      :visible-columns="visibleColumns"
       style="height: 500px;"
    >
      <template v-slot:top>
        <div style="display:flex; flex-direction:column;">        
            <h5 style="margin:0; padding:0;">Exemplo 1</h5>
            <div style="display:flex; flex-direction: row;">
                <p style="color:#0349fc; padding-right:10px" >Dashboard</p>
                <p style="color:#9e9e9e;">/</p>
                <p style="color:#9e9e9e; padding-left:10px">Dashboard</p>
            </div>
        </div>
        <q-space />
        <q-input borderless dense debounce="600" outlined v-model="text" placeholder="Search" style="margin-right: 20px;">
          <template v-slot:append>
            <q-icon name="search" color="blue-10"/>
          </template>
        </q-input>
        <q-select
          v-model="visibleColumns"
          multiple
          outlined
          dense
          options-dense
          :display-value="$q.lang.table.columns"
          emit-value
          map-options
          :options="columns"
          option-value="name"
          options-cover
          style="min-width: 150px;"

        />
      <h5 style="color:#242de7; margin:0 20px; padding:0;">Novo Exemplo</h5>
      <q-icon name="fullscreen"  style="color: #77797d; font-size: 28px; padding: 0 20px; cursor: pointer;" />
      <p style=" flex-basis: 100%;height: 0;"></p>
      <q-icon name="filter_alt"  style="color: #77797d; font-size: 28px; padding: 0 20px; cursor: pointer;" />
      <h5 style="margin:0; padding:0;color: #77797d;">Filtro</h5>
      </template>
      
    </q-table>
  </div>
</template>

<script>

const columns = [
  {
    sit: 'sit',
    required: true,
    label: 'Situação',
    align: 'left',
    field: row => row.name,
    format: val => `${val}`,
    sortable: true
  },
  { name: 'cod', align: 'center', label: 'Cod Exemplo', field: 'cod', sortable: true },
  { name: 'nome', label: 'nome', field: 'nome', sortable: true },
  { name: 'descrição', label: 'descrição', field: 'descrição' },
  { name: 'tipo', label: 'tipo', field: 'tipo' },
  { name: 'origem', label: 'Origem', field: 'origem' },
  { name: 'contato', label: 'Contato', field: 'contato', sortable: true, sort: (a, b) => parseInt(a, 10) - parseInt(b, 10) },
  { name: 'email', label: 'Email', field: 'email', sortable: true, sort: (a, b) => parseInt(a, 10) - parseInt(b, 10) },
  { name: 'tel1', label: 'Telefone 1', field: 'tel1', sortable: true },
  { name: 'tel2', label: 'Telefone 2', field: 'tel2', sortable: true },
]

const rows = [
  {
    cod: '122',
    nome: 'nome 15',
    descrição: 'descriçao 15',
    tipo: 'tipo 15',
    origem: 'origem 15',
    contato: 'contato 15',
    email: 'email 15',
    tel1: 'Telefone 15',
    tel2: 'Telefone 15',
  },
  {
    cod: '121',
    nome: 'nome 14',
    descrição: 'descriçao 14',
    tipo: 'tipo 14',
    origem: 'origem 14',
    contato: 'contato 14',
    email: 'email 14',
    tel1: 'Telefone 14',
    tel2: 'Telefone 14',
  },
 {
    cod: '120',
    nome: 'nome 13',
    descrição: 'descriçao 13',
    tipo: 'tipo 13',
    origem: 'origem 13',
    contato: 'contato 13',
    email: 'email 13',
    tel1: 'Telefone 13',
    tel2: 'Telefone 13',
  },
  {
    cod: '138',
    nome: 'nome 38',
    descrição: 'descriçao 38',
    tipo: 'tipo 38',
    origem: 'origem 38',
    contato: 'contato 38',
    email: 'email 38',
    tel1: 'Telefone 38',
    tel2: 'Telefone 38',
  },
   {
    cod: '922',
    nome: 'nome 45',
    descrição: 'descriçao 45',
    tipo: 'tipo 45',
    origem: 'origem 45',
    contato: 'contato 45',
    email: 'email 45',
    tel1: 'Telefone 45',
    tel2: 'Telefone 45',
  },
  {
    cod: '154',
    nome: 'nome 15',
    descrição: 'descriçao 15',
    tipo: 'tipo 15',
    origem: 'origem 15',
    contato: 'contato 15',
    email: 'email 15',
    tel1: 'Telefone 15',
    tel2: 'Telefone 15',
  },
]

export default {
    name:"Table",
  setup () {
    return {
      columns,
      rows
    }
  }
}
</script>

<style lang="css">
thead tr:first-child{
    background: #b1d6fc;
    color: #915210;
}
tbody tr:nth-child(odd){
    background: #dcedff;
}
</style>
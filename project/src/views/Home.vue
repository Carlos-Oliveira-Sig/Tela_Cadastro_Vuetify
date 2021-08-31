<template>
        <div class="mx-8">

        <v-toolbar flat class="transparent">
          
          <v-toolbar-title class="light-blue--text">
            Lista de Alunos
          </v-toolbar-title>
          
          <v-spacer></v-spacer>
          
          <v-dialog v-model="dialog" width="500">
            <template v-slot:activator="{on, attrs}">
              <v-btn class="mb-2" color="blue" dark v-bind="attrs" v-on="on">
                Novo
              </v-btn>
            </template>
            
            <v-card>
              
              <v-card-title class="text-h6 grey lighten-3">
                Cadastrar novo aluno
              </v-card-title>
              
              <v-divider></v-divider>
              
              <v-card-text class="mt-4" align="center">
                <v-avatar color="grey" size="132" class="mb-6">
                  <v-icon dark size="72">
                     mdi-account-circle
                  </v-icon>
                </v-avatar>
                <v-row class="my-0">
                  <v-col cols="12" md="6" class="py-0">
                    <v-text-field label="Nome" outlined />
                  </v-col>
                  <v-col cols="12" md="6" class="py-0">
                    <v-text-field label="Email" outlined />
                  </v-col>
                </v-row>
                <v-row class="my-0">
                  <v-col cols="12" md="12" class="py-0">
                    <v-text-field label='Digite as skills separadas por ","' outlined />
                  </v-col>
                </v-row>
                <v-row class="my-0">
                  <v-col cols="12" md="12" class="py-0">
                    <v-text-field label="Digite a url da foto" outlined />
                  </v-col>
                </v-row>
              </v-card-text>
        
              <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn class="mb-4"
                  color="blue"
                  dark
                  @click="dialog = false"
                >
                Adicionar
                </v-btn>
              </v-card-actions>
            </v-card>
          </v-dialog>
        </v-toolbar>

        <v-data-table
          v-model="selected"
          :headers="headers"
          :items="students"
          item-key="name"
          show-select
          class="elevation-1"
        >
          <!-- <template -v-slot:item.name='{ item }'>
            <v-avatar size="32" class="mr-1">
            </v-avatar>
            {{item.name}}
          </template> -->

        </v-data-table>
      </div>
</template>

<script>
    export default {
    name: 'Home',
    
    
    data () {
      return {
        dialog: false,
        
        selected: [],
        headers: [
          {
            text: 'Nome',
            align: 'start',
            sortable: false,
            value: 'name',
          },
          { text: 'Email', value: 'email' },
          { text: 'Skills', value: 'skills' },
          { text: 'Adicionado em:', value: 'dataadd', align: 'end' },
        ],
        students: [
          {
            name: 'Lindsey Stroud',
            email: 'lindsey.stroud@gmail.com',
            skills: 'HTML, VUE, REACT, ANGULAR',
            dataadd: '5 minutes ago',
          },
          {
            name: 'Nicci Troiani',
            email: 'nicci.troiani@gmail.com',
            skills: 'HTML, VUE, REACT, ANGULAR',
            dataadd: '14 minutes ago',
          },
          {
            name: 'George Fields',
            email: 'george.fields@gmail.com',
            skills: 'HTML, VUE, REACT, ANGULAR',
            dataadd: '6 Hours ago',
          },
          {
            name: 'Rebecca Moore',
            email: 'rebecca.moore@gmail.com',
            skills: 'HTML, VUE, REACT, ANGULAR',
            dataadd: 'Dec 14, 2018',
          },
          {
            name: 'Jane Doe',
            email: 'jane.doe@gmail.com',
            skills: 'HTML, VUE, REACT, ANGULAR',
            dataadd: 'Dec 12, 2018',
          },
          {
            name: 'Jones Dermot',
            email: 'jones.dermot@gmail.com',
            skills: 'HTML, VUE, REACT, ANGULAR',
            dataadd: 'Dec 11, 2018',
          },
          {
            name: 'Martin Merces',
            email: 'martin.merces@gmail.com',
            skills: 'HTML, VUE, REACT, ANGULAR',
            dataadd: 'Dec 9, 2018',
          },
          {
            name: 'Franz Ferdinand',
            email: 'franz.ferdinand@gmail.com',
            skills: 'HTML, VUE, REACT, ANGULAR',
            dataadd: 'Dec 6, 2018',
          },
          {
            name: 'John Smith',
            email: 'john.smith@gmail.com',
            skills: '',
            dataadd: 'Nov 30, 2018',
          },
        ],
      }
    },
  }
</script>

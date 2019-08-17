<template>
  <div>
    <table>
      <tr>
        <th>Tubarão</th>
        <th>Lobo</th>
        <th>Águia</th>
        <th>Gato</th>
      </tr>
      <tr>
        <td>{{ respostas.i }}</td>
        <td>{{ respostas.c }}</td>
        <td>{{ respostas.o }}</td>
        <td>{{ respostas.a }}</td>
      </tr>
    </table>
    <div v-for="(item, index) in questoesEmbaralhadas" :key="index">
      <h1>{{ item.questao }}</h1>
      <ul>
        <li v-for="(item2, index) in item.alternativas" :key="index">
          <a class="alternativa" href @click.prevent="mark(item2.perfil)">{{ item2.alternativa }}</a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  props: ["questoes"],
  data() {
    return {
      questoesEmbaralhadas: [],
      respostas: {
        i: 0,
        c: 0,
        o: 0,
        a: 0
      }
    };
  },
  mounted() {
    this.questoesEmbaralhadas = this.shuffleArray(this.questoes);
  },
  methods: {
    shuffleArray(array) {
      var counter = array.length,
        temp,
        index;
      while (counter > 0) {
        index = Math.floor(Math.random() * counter);

        counter--;

        temp = array[counter];
        array[counter] = array[index];
        array[index] = temp;
      }
      return array;
    },
    mark(perfil) {
      switch (perfil) {
        case "i":
          this.respostas.i++;
          break;
        case "c":
          this.respostas.c++;
          break;
        case "o":
          this.respostas.o++;
          break;
        case "a":
          this.respostas.a++;
          break;
      }
    }
  }
};
</script>

<style>
</style>

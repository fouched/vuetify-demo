<template>
	<v-app>
		<v-main>
			<HelloWorld>
				<v-checkbox v-for="icdRow in icdRows" :key="icdRow.id" v-model="icdRow.checked" @click="icdSelection"></v-checkbox>
			</HelloWorld>
		</v-main>
	</v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld'

export default {
	name: 'App',
	components: {
		HelloWorld
	},
	data() {
		return {
			icdRows: [{id: '1', desc:'Check 1', checked: false}, {id: '2', desc:'Check 2', checked: true}]
		}
	},
  methods: {
    icdSelection: function() {
      this.icdRows.forEach(element => {
        console.log(element.id + ' ' + element.checked);
      });
    }

  }
}
</script>

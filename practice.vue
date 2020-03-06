 Vue.component('number-list',{
 props: ['number_list'], // props['var']  var should be all lower case like postgresql col name ex: numberlist or number_list
  
  template: `
  	<ul>
    	<li v-for="number in number_list">{{ number.sl }}</li>
    </ul>
  `
  
});

app = new Vue({
el: '#root',
component: [
	'cat-list'
],
data: {
greeting: 'Hello I world' ,
count: 5,
value: 5,
email: 'éghfgh',
animals: ['cat', 'dog', 'rat'],
numbers: [{sl : 'one'}, {sl : 'two'}, {sl : '3 / three'}],
newNumber: ''
},

methods: {
	addNumber: function() {
  	this.numbers.push({ sl : this.newNumber});
    this.newNumber = '';
  }
},

filters: {
	capitalize : function (value) {
  	return value.toUpperCase();
  },
  addA : function (value) {
  	return value + 'Á';
  }
},
computed: {
	addZ: function (value) {
  				if(this.newNumber.length > 3) {
          	return this.newNumber + 'z';
          }
  			}
},

created: function () {
	console.log('created')
},
mounted: function () {
	console.log('mounted')
},
updated: function () {
	console.log('updated')
},
distroyed: function () {
	console.log('distoryed')
}
})
setTimeout( function() {
app.$destroy();
}, 5000); 
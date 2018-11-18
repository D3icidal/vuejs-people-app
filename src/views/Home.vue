<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <h3>{{ subheading }}</h3>
    <br>
    <hr>
    <br>
    <p><h4>Current entries:</h4></p><br>
    <ol>
      <li v-for="person in people"> <h5>{{person.name}}</h5>{{person.bio}}<br><br></li>
    </ol>
    <br>
    <br>    
    <p><hr5> Add to this collection!</hr5></p>
    <p>Persons name: <input type="text" v-model="newPerson.name"> 
    <br>Biography: <input type="text" v-model="newPerson.bio">
    <br><button v-on:click="addPerson()">Add this person to enternal glory</button>
    </p>
    <p></p>
    <br>
    <br>
    <br>
    <br>
    <p></p>
  </div>
</template>

<style></style>

<script>
export default {
  data: function() {
    return {
      message: "1Welcome to Vue.js!",
      subheading: "A app about interesting people",
      people: [
        {name: "Name1", bio: "conquered name2", bioVisable: true},
        {name: "Name2", bio: "conquered name3", bioVisable: true},
        {name: "Name3", bio: "conquered name1", bioVisable: true}
      ],
      newPerson: {name:"John Smith", bio:"What they were known for, who have they conquered, who have they killed..."}
    };
  },
  created: function() {},
  methods: {
    addPerson: function() {
      console.log('inside AddPerson');
      if (this.newPerson.bio && this.newPerson.name) {
        console.log('if statement');
        this.people.push(this.newPerson);
        this.newPerson = {name:"John Smith", bio:"What they were known for, who have they conquered, who have they killed..."};
      }

    }
  },
  computed: {}
};
</script>

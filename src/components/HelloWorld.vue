<template>
  <div>
    <h1>{{ msg }}</h1>
    <p>
      <i>Hello There!</i>            
      Just click the "Add a Note!" button right below 
      <br>            
    </p>
    <button class="add" @click="createNote()">Add a Note!</button>

    <div class="notes">
      <div class="note" v-for="(row, index) in notes" :key=row>
        <p class="close" @click="removeNote(index)">
          X
        </p>
        <h1 contenteditable="true" @click="cleanT()">{{title}}</h1>
        <p contenteditable="true" @click="cleanD()">{{description}}</p>
      </div>
    </div>    
    
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }, 
  data (){
    return{
      notes:[],
      noteCounter: 0,
      title: 'Title',
      description: 'Description'   
    }
  },
  methods:{
    createNote(){
      this.noteCounter++
      this.notes.push(this.noteCounter)      
      
    },
    removeNote: function(index){
      this.notes.splice(index, 1)
     },
    // cleanT(){      
    //   this.title = ''
    // },
    // cleanD(){
    //   this.description = ''
    // }
    
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import url('https://fonts.googleapis.com/css?family=Roboto+Slab&display=swap');
        
    img {
      margin-bottom: 3rem;
    }

    h1{
      font-family: 'Roboto Slab', serif;
    }

    h1 > p{
      font-family: 'Roboto Slab', serif;
    }

    .add{
      background-color: rgb(245, 118, 72);
      color:rgb(16, 16, 128);
      padding: 0.8rem;
      border-radius: 1rem;
      font-family: 'Roboto Slab', serif;
      font-family: 2rem;
      border:none;
      width: 7rem;
      outline:darkred;
      font-weight: bold;      
    }

    .add:hover{
      cursor:pointer;
      box-shadow: 2px 3px 13px sandybrown;
    }

    .notes{
      display: flex;
      flex-wrap: wrap;
      flex-direction: row;
      justify-content: center;
      width: 85%;
      margin: auto;
      box-sizing: border-box;
      margin-top: 2.2rem;
    }

    .notes .note{
      font-family: 'Roboto Slab', serif;
      padding: 0.8rem;
      margin: 1rem;
      width: 18rem;
      height: auto;
      box-sizing: border-box;
      border-radius: 0.23rem;
      position: relative;
      top:0;
      left: 0;
      transition: box-shadow 2s, left 2s top 2s;
      box-shadow: 10px -10px 0 -3px white, 10px -10px 0 0 #ffaaa5;
      background-color: #a8e6cf;                  
    }

    .notes .note:hover{
      box-shadow: 0 0 0 -3px white, 0 0 0 0px #ffaaa5;
      top: -20px;
      left: 20px;
      cursor: pointer;                        
    }

    .note .note .close{
      text-align: right;
      margin-right: 0.5rem;
    }

    .note .note .close:hover{
      font-weight: bold;
    }

</style>

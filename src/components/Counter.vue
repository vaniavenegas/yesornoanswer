<template>
  <h2> {{ costumeTitle }} </h2>
  <p> {{ counter }} <sup>2</sup> = {{ squareCounter }}</p>
  <p data-testid="counter"> {{ counter }} </p>
 

  <div class="buttons-container" >
      <button @click="increase">+1</button>
      <button @click="dicrease">-1</button>
  </div>
</template>

<script>
export default {
    props: {
        title: String,
        start: {
            type: Number,
            default: 100,
            validator( value ) {
                return value > 100
            }

        } 
    },
    //name: 'Counter'}
    data () {
        return {
        counter: this.start
        }
    
    },

    methods : {
        
        getSquareValue() {
            console.log('getSquareValue')
            return this.counter*this.counter
        },

        increase() {
            this.counter++

        },

        dicrease() {
            this.counter--

        },
    },

    computed: {
        squareCounter() {
            console.log('computed squareCounter')
            return this.counter*this.counter

        },

        costumeTitle() {
            return this.title || 'Counter'

        }
    }

}
</script>

<style>

button {
    background-color: #64BB87;
    border-radius: 5px;
    border: 1px solid white;
    color: white;
    cursor: pointer;
    margin: 0 5px;
    padding: 5px 15px;
    transition: 0.3s ease-in-out;
}

button:hover {
    background-color: #5aa67b;
    transition: 0.3s ease-in-out;
}

</style>
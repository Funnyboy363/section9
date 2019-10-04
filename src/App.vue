<template>
<div>
<button @click="selectedComponent = 'appQuote'">Quote</button>
<button  @click="selectedComponent = 'appAuthor'">Author</button>
<button  @click="selectedComponent = 'appNew'">New</button>
<hr>
<p>{{ selectedComponent }} </p>

<keep-alive>
<component :is="selectedComponent"></component>
</keep-alive>
 <!-- <app-quote>
<h2 slot="title"> {{ quoteTitle }} </h2>
<p slot="subtitle"> {{ subtitle }} </p>
<p slot="content">A Wonderful Quote</p>
 </app-quote> -->
</div>
</template>

<script>
import Quote from './components/Quote';
import Author from './components/Author';
import New from './components/New';

export default {
    data: function() {
      return {
        quoteTitle: 'A beautiful quote',
        subtitle: 'This is a subtitle',
        selectedComponent: 'appQuote'
      }
    },
  
  components: {
    appQuote: Quote,
    appAuthor: Author,
    appNew: New
  }
}

</script>

<style>

</style>

<template>
  <div id="app">
    <div class="min-w-screen min-h-screen bg-gray-800 flex items-center justify-center px-5 py-5">
      <div class="w-full mx-auto rounded-xl bg-gray-100 shadow-lg p-10 text-gray-800 relative overflow-hidden min-w-80 max-w-3xl">
        <p class="text-gray-900 text-xl">
          <em>"</em>
        </p>

        <h1 class="text-gray-800 font-bold text-xl text-center">
          <div class="pre-formatted">
            {{ selectedComment }}
          </div>
        </h1>

        <p class="text-gray-900 text-xl text-right">
          <em>"</em>
        </p>

        <br />

        <p class="text-gray-900 font-light text-center">
          egy Telex kommentelő
        </p>
      </div>
    </div>
  </div>

  <footer class = 'px-50 bg-gray-800 text-gray-100'>
    <div class = 'max-w-7xl mx-auto py-12 px-4 sm:px-6 lg:py-6 lg:px-8 border-t border-gray-700'>
      <div class = 'mt-2 py-8 px-4 sm:px-6 lg:px-8 md:flex md:items-center md:justify-between'>
        <div class = 'flex space-x-2 md:order-2'>
          <p class="text-gray-500">
            <a href = 'https://facebook.com/sandorkiraly0' class = 'text-gray-500 hover:text-gray-400'>
              Facebook
            </a>
          </p>
        </div>

        <div class = 'mt-8 text-base md:mt-0 md:order-1'>
          <h1 class="font-semibold text-gray-100 sm:text-lg">
            napitelex
          </h1>
          
          <p class="text-gray-500">
            Telex legvállalhatatlanabb facebook <br /> kommentjeiből egy összeállítás naponta.
          </p>
        </div>
      </div> 
    </div>  
  </footer>
</template> 

<script>
export default {
  name: 'foo',
  data () {
    return {
      selectedComment: '',
      comments: [
          { v: "Vicc az egész még ujságjuk is van, borzasztó!\nBeteg világ de nagyon!"  },
          { v: "HÁ HA MÁR SZÓBA KERÜLT, ÉN IS KURVÁRA BÜSZKE VAGYOK,\nHOGY HETERÓ VAGYOK ÉS ARANYEREM IS VAN!" },
          { v: "Mikór amúgy is skizofrén vagy,\nés az egyetlen fiad meleg." },
          { v: "Lop ez, lop az,\nstílszerű a vendég." },
          { v: "Ha nem tetszik,\nmiért ment katonának." },
          { v: "" },
      ],
    }
  },

  mounted: function () {
    this.generate()
  },

  methods: {
    generate () {
      this.selectedComment = this.comments[Math.floor(Math.random() * this.comments.length)].v;
    }
  }
}
</script>

<style>
  @import url('https://cdnjs.cloudflare.com/ajax/libs/tailwindcss/2.0.4/tailwind.min.css');

  .pre-formatted {
    white-space: pre;
  }
</style>
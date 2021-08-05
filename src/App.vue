<template>
  <div id = "app">
    <div class = "min-w-screen min-h-screen bg-gray-800 flex items-center justify-center px-5 py-5">
      <div class = "w-full mx-auto rounded-xl bg-gray-100 shadow-lg p-10 text-gray-800 relative overflow-hidden min-w-80 max-w-3xl md:min-w-50 md:max-w-xl">
        <p class = "text-gray-900 text-xl">
          <em>"</em>
        </p>

        <h1 class = "text-gray-800 font-bold text-xl md:text-lg sm:text-sm text-center">
          <div class="pre-formatted">
            {{ selectedComment }}
          </div>
        </h1>

        <p class = "text-gray-900 text-xl text-right">
          <em>"</em>
        </p>

        <br />

        <p class = "text-gray-900 font-light text-center">
          egy Telex kommentelő
        </p>
      </div>
    </div>
  </div>

  <footer class = 'px-50 bg-gray-800 text-gray-100'>
    <div class = 'max-w-7xl md:max-w-3xl sm:max-w-xl mx-auto py-12 px-4 sm:px-6 lg:py-6 lg:px-8 border-t border-gray-700'>
      <div class = 'mt-2 py-8 px-4 sm:px-6 lg:px-8 md:flex md:items-center md:justify-between'>
        <div class = 'flex space-x-2 md:order-2'>
          <p class="text-gray-500 inline-flex space-x-1">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9.663 17h4.673M12 3v1m6.364 1.636l-.707.707M21 12h-1M4 12H3m3.343-5.657l-.707-.707m2.828 9.9a5 5 0 117.072 0l-.548.547A3.374 3.374 0 0014 18.469V19a2 2 0 11-4 0v-.531c0-.895-.356-1.754-.988-2.386l-.548-.547z" />
            </svg>

            <a href = 'https://facebook.com/sandorkiraly0' class = 'text-gray-500 hover:text-gray-400'>
                Facebook
            </a>
          </p>
        </div>

        <div class = 'mt-8 text-base md:mt-0 md:order-1'>
          <div class="inline-flex space-x-2">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 20H5a2 2 0 01-2-2V6a2 2 0 012-2h10a2 2 0 012 2v1m2 13a2 2 0 01-2-2V7m2 13a2 2 0 002-2V9a2 2 0 00-2-2h-2m-4-3H9M7 16h6M7 8h6v4H7V8z" />
            </svg>

            <h1 class="font-semibold text-gray-100 sm:text-lg"> 
              napitelex
            </h1>
          </div>
          
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
            lastSelectedComment: '',
            selectedComment: '',

            comments: [
                { value: "Vicc az egész még ujságjuk is van, borzasztó!\nBeteg világ de nagyon!" },
                { value: "Há ha már szóba került, én is kurvára büszke vagyok,\nhogy heteró vagyok és aranyerem is van!" },
                { value: "Mikór amúgy is skizofrén vagy,\nés az egyetlen fiad meleg." },
                { value: "Lop ez, lop az,\nstílszerű a vendég." },
                { value: "Ha nem tetszik,\nmiért ment katonának." },
                { value: "Fogam negyven, körmömsz húsz,\nha TikTokozol megb.zúlsz 😄😃" },
            ],
        }
    },

    mounted: function () {
        this.generate()
    },

    methods: {
        generate () {
            while (this.lastSelectedComment == this.selectedComment) {
                this.selectedComment = this.comments[Math.floor(Math.random() * this.comments.length)].value;
            }

            this.lastSelectedComment = this.selectedComment
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
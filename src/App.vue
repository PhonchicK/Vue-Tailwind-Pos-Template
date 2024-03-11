<script>
  import ShoppingCartItem from '/src/components/ShoppingCartItem.vue'
  import SearchProduct from '/src/components/SearchProduct.vue'

  export default {
  name: "app",
  components: {
    ShoppingCartItem,
    SearchProduct
  },
  data() {
    return {
      inShoppingCartItems: [
        {name: 'Örnek ürün', price: 40, quantity: 1, discount: 0, isOpen: false}
      ],
      openTab: 1,
      openMenu: false
    }
  },
  methods: {
    toggleTabs(tabNumber){
      this.openTab = tabNumber
    },
    toggleMenu() {
      this.openMenu = !this.openMenu
    }
  }
}
</script>
<template>
  <!--no print area-->
  <div class="hide-print flex flex-row h-screen antialiased text-blue-gray-800 bg-gray-200">
    <!--Left sidebar-->
    <div class="flex flex-row w-auto flex-shrink-0">
      <div class="flex flex-col items-center py-1 px-2 flex-shrink-0 bg-gray-50">
        <a v-on:click="toggleTabs(1)" v-bind:class="{'border-2 border-orange-400 bg-orange-100': openTab === 1}"
           class="flex items-center justify-center my-1 h-20 w-20 text-gray-400 rounded-md hover:bg-orange-200">
          <svg viewBox="0 0 20 20" class="p-5" v-bind:class="{'fill-orange-400': openTab === 1, 'fill-gray-400': openTab !== 1}">
            <path d="M10.862,6.47H3.968v6.032h6.894V6.47z M10,11.641H4.83V7.332H10V11.641z M12.585,11.641h-0.861v0.861h0.861V11.641z M7.415,14.226h0.862v-0.862H7.415V14.226z M8.707,17.673h2.586c0.237,0,0.431-0.193,0.431-0.432c0-0.237-0.193-0.431-0.431-0.431H8.707c-0.237,0-0.431,0.193-0.431,0.431C8.276,17.479,8.47,17.673,8.707,17.673 M5.691,14.226h0.861v-0.862H5.691V14.226z M4.83,13.363H3.968v0.862H4.83V13.363z M16.895,4.746h-3.017V3.023h1.292c0.476,0,0.862-0.386,0.862-0.862V1.299c0-0.476-0.387-0.862-0.862-0.862H10c-0.476,0-0.862,0.386-0.862,0.862v0.862c0,0.476,0.386,0.862,0.862,0.862h1.293v1.723H3.106c-0.476,0-0.862,0.386-0.862,0.862v12.926c0,0.476,0.386,0.862,0.862,0.862h13.789c0.475,0,0.861-0.387,0.861-0.862V5.608C17.756,5.132,17.369,4.746,16.895,4.746 M10.862,2.161H10V1.299h0.862V2.161zM11.724,1.299h3.446v0.862h-3.446V1.299z M13.016,4.746h-0.861V3.023h0.861V4.746z M16.895,18.534H3.106v-2.585h13.789V18.534zM16.895,15.088H3.106v-9.48h13.789V15.088z M15.17,12.502h0.862v-0.861H15.17V12.502z M13.447,12.502h0.861v-0.861h-0.861V12.502zM15.17,10.778h0.862V9.917H15.17V10.778z M15.17,9.055h0.862V8.193H15.17V9.055z M16.032,6.47h-4.309v0.862h4.309V6.47zM14.309,8.193h-0.861v0.862h0.861V8.193z M12.585,8.193h-0.861v0.862h0.861V8.193z M13.447,14.226h2.585v-0.862h-2.585V14.226zM13.447,10.778h0.861V9.917h-0.861V10.778z M12.585,9.917h-0.861v0.861h0.861V9.917z"/>
          </svg>
        </a>
        <a v-on:click="toggleTabs(2)" v-bind:class="{'border-2 border-orange-400 bg-orange-100': openTab === 2}"
           class="flex items-center justify-center my-1 h-20 w-20 text-gray-400 rounded-md hover:bg-orange-200">
          <svg viewBox="0 0 20 20" class="p-5" v-bind:class="{'fill-orange-400': openTab === 2, 'fill-gray-400': openTab !== 2}">
            <path d="M17.671,13.945l0.003,0.002l1.708-7.687l-0.008-0.002c0.008-0.033,0.021-0.065,0.021-0.102c0-0.236-0.191-0.428-0.427-0.428H5.276L4.67,3.472L4.665,3.473c-0.053-0.175-0.21-0.306-0.403-0.306H1.032c-0.236,0-0.427,0.191-0.427,0.427c0,0.236,0.191,0.428,0.427,0.428h2.902l2.667,9.945l0,0c0.037,0.119,0.125,0.217,0.239,0.268c-0.16,0.26-0.257,0.562-0.257,0.891c0,0.943,0.765,1.707,1.708,1.707S10,16.068,10,15.125c0-0.312-0.09-0.602-0.237-0.855h4.744c-0.146,0.254-0.237,0.543-0.237,0.855c0,0.943,0.766,1.707,1.708,1.707c0.944,0,1.709-0.764,1.709-1.707c0-0.328-0.097-0.631-0.257-0.891C17.55,14.182,17.639,14.074,17.671,13.945 M15.934,6.583h2.502l-0.38,1.709h-2.312L15.934,6.583zM5.505,6.583h2.832l0.189,1.709H5.963L5.505,6.583z M6.65,10.854L6.192,9.146h2.429l0.19,1.708H6.65z M6.879,11.707h2.027l0.189,1.709H7.338L6.879,11.707z M8.292,15.979c-0.472,0-0.854-0.383-0.854-0.854c0-0.473,0.382-0.855,0.854-0.855s0.854,0.383,0.854,0.855C9.146,15.596,8.763,15.979,8.292,15.979 M11.708,13.416H9.955l-0.189-1.709h1.943V13.416z M11.708,10.854H9.67L9.48,9.146h2.228V10.854z M11.708,8.292H9.386l-0.19-1.709h2.512V8.292z M14.315,13.416h-1.753v-1.709h1.942L14.315,13.416zM14.6,10.854h-2.037V9.146h2.227L14.6,10.854z M14.884,8.292h-2.321V6.583h2.512L14.884,8.292z M15.978,15.979c-0.471,0-0.854-0.383-0.854-0.854c0-0.473,0.383-0.855,0.854-0.855c0.473,0,0.854,0.383,0.854,0.855C16.832,15.596,16.45,15.979,15.978,15.979 M16.917,13.416h-1.743l0.189-1.709h1.934L16.917,13.416z M15.458,10.854l0.19-1.708h2.218l-0.38,1.708H15.458z"/>
          </svg>
        </a>
        <a v-on:click="toggleTabs(3)" v-bind:class="{'border-2 border-orange-400 bg-orange-100': openTab === 3}"
           class="flex items-center justify-center my-1 h-20 w-20 text-gray-400 rounded-md hover:bg-orange-200">
          <svg viewBox="0 0 24 24" class="p-5 fill-none" v-bind:class="{'stroke-orange-400': openTab === 3, 'stroke-gray-400': openTab !== 3}">
            <path d="M15 12C15 13.6569 13.6569 15 12 15C10.3431 15 9 13.6569 9 12C9 10.3431 10.3431 9 12 9C13.6569 9 15 10.3431 15 12Z" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"></path> 
            <path d="M12.9046 3.06005C12.6988 3 12.4659 3 12 3C11.5341 3 11.3012 3 11.0954 3.06005C10.7942 3.14794 10.5281 3.32808 10.3346 3.57511C10.2024 3.74388 10.1159 3.96016 9.94291 4.39272C9.69419 5.01452 9.00393 5.33471 8.36857 5.123L7.79779 4.93281C7.3929 4.79785 7.19045 4.73036 6.99196 4.7188C6.70039 4.70181 6.4102 4.77032 6.15701 4.9159C5.98465 5.01501 5.83376 5.16591 5.53197 5.4677C5.21122 5.78845 5.05084 5.94882 4.94896 6.13189C4.79927 6.40084 4.73595 6.70934 4.76759 7.01551C4.78912 7.2239 4.87335 7.43449 5.04182 7.85566C5.30565 8.51523 5.05184 9.26878 4.44272 9.63433L4.16521 9.80087C3.74031 10.0558 3.52786 10.1833 3.37354 10.3588C3.23698 10.5141 3.13401 10.696 3.07109 10.893C3 11.1156 3 11.3658 3 11.8663C3 12.4589 3 12.7551 3.09462 13.0088C3.17823 13.2329 3.31422 13.4337 3.49124 13.5946C3.69158 13.7766 3.96395 13.8856 4.50866 14.1035C5.06534 14.3261 5.35196 14.9441 5.16236 15.5129L4.94721 16.1584C4.79819 16.6054 4.72367 16.829 4.7169 17.0486C4.70875 17.3127 4.77049 17.5742 4.89587 17.8067C5.00015 18.0002 5.16678 18.1668 5.5 18.5C5.83323 18.8332 5.99985 18.9998 6.19325 19.1041C6.4258 19.2295 6.68733 19.2913 6.9514 19.2831C7.17102 19.2763 7.39456 19.2018 7.84164 19.0528L8.36862 18.8771C9.00393 18.6654 9.6942 18.9855 9.94291 19.6073C10.1159 20.0398 10.2024 20.2561 10.3346 20.4249C10.5281 20.6719 10.7942 20.8521 11.0954 20.94C11.3012 21 11.5341 21 12 21C12.4659 21 12.6988 21 12.9046 20.94C13.2058 20.8521 13.4719 20.6719 13.6654 20.4249C13.7976 20.2561 13.8841 20.0398 14.0571 19.6073C14.3058 18.9855 14.9961 18.6654 15.6313 18.8773L16.1579 19.0529C16.605 19.2019 16.8286 19.2764 17.0482 19.2832C17.3123 19.2913 17.5738 19.2296 17.8063 19.1042C17.9997 18.9999 18.1664 18.8333 18.4996 18.5001C18.8328 18.1669 18.9994 18.0002 19.1037 17.8068C19.2291 17.5743 19.2908 17.3127 19.2827 17.0487C19.2759 16.8291 19.2014 16.6055 19.0524 16.1584L18.8374 15.5134C18.6477 14.9444 18.9344 14.3262 19.4913 14.1035C20.036 13.8856 20.3084 13.7766 20.5088 13.5946C20.6858 13.4337 20.8218 13.2329 20.9054 13.0088C21 12.7551 21 12.4589 21 11.8663C21 11.3658 21 11.1156 20.9289 10.893C20.866 10.696 20.763 10.5141 20.6265 10.3588C20.4721 10.1833 20.2597 10.0558 19.8348 9.80087L19.5569 9.63416C18.9478 9.26867 18.6939 8.51514 18.9578 7.85558C19.1262 7.43443 19.2105 7.22383 19.232 7.01543C19.2636 6.70926 19.2003 6.40077 19.0506 6.13181C18.9487 5.94875 18.7884 5.78837 18.4676 5.46762C18.1658 5.16584 18.0149 5.01494 17.8426 4.91583C17.5894 4.77024 17.2992 4.70174 17.0076 4.71872C16.8091 4.73029 16.6067 4.79777 16.2018 4.93273L15.6314 5.12287C14.9961 5.33464 14.3058 5.0145 14.0571 4.39272C13.8841 3.96016 13.7976 3.74388 13.6654 3.57511C13.4719 3.32808 13.2058 3.14794 12.9046 3.06005Z" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"></path>
          </svg>
        </a>
      </div>
    </div>
    <!--left sidebar end-->
    <!--tab page content-->
    <div class="flex-grow flex w-full">
      <SearchProduct v-if="openTab === 1"/> <!--v-bind:class="{'hidden': openTab !== 1, 'block': openTab === 1}"-->
      <div class="flex flex-col h-full w-full p-4" v-if="openTab === 2">
        <h1>WAITING EMPLOYERS</h1>
      </div>
      <div class="flex flex-col h-full w-full p-4" v-if="openTab === 3">
        <h1>SETTINGS</h1>
      </div>
    </div>
    <!--tab page content end-->
    <!--shopping cart-->
    <div class="flex flex-col h-full w-5/12 bg-gray-50 border-l-2 border-gray-300">
      <div class="border-b-2 w-full h-24 border-gray-300 items-center flex p-4">
        <div class="border-2 rounded-lg flex-row flex items-center p-1 border-gray-200">
          <svg viewBox="-4 0 32 32" class="w-14">
            <path d="M0 25.281h0.781v-18.563h-0.781v18.563zM2.344 25.281h1.531v-18.563h-1.531v18.563zM5.406 25.281h1.563v-18.563h-1.563v18.563zM8.5 25.281h3.125v-18.563h-3.125v18.563zM13.156 25.281h2.344v-18.563h-2.344v18.563zM17.031 25.281h1.563v-18.563h-1.563v18.563zM20.125 25.281h0.781v-18.563h-0.781v18.563zM22.469 25.281h1.531v-18.563h-1.531v18.563z" class="fill-gray-500"/>
          </svg>
          <input class="text-2xl h-12 p-2 bg-gray-200 rounded-md"/>
        </div>
      </div>
      <!--items list area-->
      <div class="flex flex-grow w-full h-3/5 relative">
        <ul class="w-full overflow-y-scroll p-2 list-shoppingcart">
          <ShoppingCartItem :title="'dsadsa'"/>
          <ShoppingCartItem :title="'dsa'"/>
          <ShoppingCartItem :title="'dsadhgfdghfsa'"/>
          <ShoppingCartItem :title="'jghjgfjh'"/>
          <ShoppingCartItem :title="'dsa'"/>
          <ShoppingCartItem :title="'dsadhgfdghfsa'"/>
          <ShoppingCartItem :title="'jghjgfjh'"/>
          <ShoppingCartItem :title="'dsa'"/>
          <ShoppingCartItem :title="'dsadhgfdghfsa'"/>
          <ShoppingCartItem :title="'jghjgfjh'"/>
          <ShoppingCartItem :title="'dsa'"/> 
          <ShoppingCartItem :title="'dsadhgfdghfsa'"/>
          <ShoppingCartItem :title="'jghjgfjh'"/>
        </ul>
        <div v-if="openMenu" class="absolute top-3/5 w-full h-2/5 px-10">
          <div class="flex bg-orange-100 w-full h-full rounded-t-md p-10 border-x-2 border-t-2 border-gray-300" v-bind:class="{'border-b-2': openMenu}">
            <h1>For simple cart process</h1>
          </div>
        </div>
      </div>
        
      <!--items list area end-->
      <div class="flex flex-col w-full h-3/6 bg-gray-200">
        <div @click="toggleMenu" class="h-12 bg-orange-100 mx-10 rounded-b-md text-center border-x-2 border-b-2 border-gray-300">
          <span>OPEN THE MENU</span>
        </div>
        <div class="flex flex-row w-full h-full my-2">
          <div class="flex flex-col h-full w-1/2 border-r p-3 border-b-2 border-gray-300">
            <div class="flex h-full">
              <span class="w-36 text-center">Tax :</span>
              <span class="w-full">846$</span>
            </div>
            <div class="flex h-full">
              <span class="w-36 text-center">Sub Total :</span>
              <span class="w-full">158M$</span>
            </div>
          </div>
          <div class="flex flex-col h-full w-1/2 border-l p-3 border-b-2 border-gray-300">
            <div class="flex h-full">
              <span class="w-36 text-center">Discount :</span>
              <span class="w-full">-846K$</span>
            </div>
            <div class="flex h-full">
              <span class="w-36 text-center">Total :</span>
              <span class="w-full">198M$</span>
            </div>
          </div>
        </div>
        <div class="flex flex-row w-full h-auto p-2">
          <button class="w-20 h-20 bg-orange-500 rounded-md p-2 mx-2">
            <svg class="fill-gray-200" viewBox="0 0 16 16">
             <path d="M14.75 2.5H1.25A1.25 1.25 0 0 0 0 3.75v8.5a1.25 1.25 0 0 0 1.25 1.25h13.5A1.25 1.25 0 0 0 16 12.25v-8.5a1.25 1.25 0 0 0-1.25-1.25zM1.25 3.75h2a1.86 1.86 0 0 1-2 1.75zm0 8.5V10.5a1.86 1.86 0 0 1 2 1.75zm13.5 0H12.8a1.86 1.86 0 0 1 1.95-1.75zm0-3a3.1 3.1 0 0 0-3.2 3h-7.1a3.1 3.1 0 0 0-3.2-3v-2.5a3.1 3.1 0 0 0 3.2-3h7.1a3.1 3.1 0 0 0 3.2 3zm0-3.75a1.86 1.86 0 0 1-1.95-1.75h1.95z"></path>
             <path d="M8 5a3.1 3.1 0 0 0-3.2 3A3.1 3.1 0 0 0 8 11a3.1 3.1 0 0 0 3.2-3A3.1 3.1 0 0 0 8 5zm0 4.75A1.86 1.86 0 0 1 6.05 8 1.86 1.86 0 0 1 8 6.25 1.86 1.86 0 0 1 10 8a1.86 1.86 0 0 1-2 1.75z"></path>
            </svg>
          </button>
          <button class="w-20 h-20 bg-lime-600 rounded-md p-2 mx-2">
            <svg class="fill-gray-200" viewBox="0 0 24 24">
               <path d="M16,6 L20,6 C21.1045695,6 22,6.8954305 22,8 L22,16 C22,17.1045695 21.1045695,18 20,18 L16,18 L16,19.9411765 C16,21.0658573 15.1177541,22 14,22 L4,22 C2.88224586,22 2,21.0658573 2,19.9411765 L2,4.05882353 C2,2.93414267 2.88224586,2 4,2 L14,2 C15.1177541,2 16,2.93414267 16,4.05882353 L16,6 Z M20,11 L16,11 L16,16 L20,16 L20,11 Z M14,19.9411765 L14,4.05882353 C14,4.01396021 13.9868154,4 14,4 L4,4 C4.01318464,4 4,4.01396021 4,4.05882353 L4,19.9411765 C4,19.9860398 4.01318464,20 4,20 L14,20 C13.9868154,20 14,19.9860398 14,19.9411765 Z M5,19 L5,17 L7,17 L7,19 L5,19 Z M8,19 L8,17 L10,17 L10,19 L8,19 Z M11,19 L11,17 L13,17 L13,19 L11,19 Z M5,16 L5,14 L7,14 L7,16 L5,16 Z M8,16 L8,14 L10,14 L10,16 L8,16 Z M11,16 L11,14 L13,14 L13,16 L11,16 Z M13,5 L13,13 L5,13 L5,5 L13,5 Z M7,7 L7,11 L11,11 L11,7 L7,7 Z M20,9 L20,8 L16,8 L16,9 L20,9 Z"></path>
            </svg>
          </button>
          <button class="w-20 h-20 bg-sky-600 rounded-md p-2 mx-2">
            <svg viewBox="0 0 24 24" class="fill-none stroke-gray-200">
              <path d="M8 7.00003H4M8 12H4M8 17H4M12 3V21M9.2 21H16.8C17.9201 21 18.4802 21 18.908 20.782C19.2843 20.5903 19.5903 20.2843 19.782 19.908C20 19.4802 20 18.9201 20 17.8V6.20003C20 5.07993 20 4.51987 19.782 4.09205C19.5903 3.71573 19.2843 3.40977 18.908 3.21802C18.4802 3.00003 17.9201 3.00003 16.8 3.00003H9.2C8.07989 3.00003 7.51984 3.00003 7.09202 3.21802C6.71569 3.40977 6.40973 3.71573 6.21799 4.09205C6 4.51987 6 5.07993 6 6.20003V17.8C6 18.9201 6 19.4802 6.21799 19.908C6.40973 20.2843 6.71569 20.5903 7.09202 20.782C7.51984 21 8.07989 21 9.2 21Z" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"></path>
            </svg>
          </button>
        </div>
      </div>
    </div>
    <!--shopping cart end-->
  </div>
  <!--no print area end-->
</template>
<style scoped>
  .list-shoppingcart > li:nth-child(odd) {
    --tw-bg-opacity: 1;
    background-color: rgba(238, 238, 238, var(--tw-bg-opacity));
  }
  .top-3\/5 {
    top: 60%;
  }
  .h-2\/5 {
    height: 40%;
  }
</style>
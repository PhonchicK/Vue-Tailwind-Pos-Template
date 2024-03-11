<script>
    export default {
        name: 'SearchProduct',
        data() {
            return {
                location: [
                    "Products",
                    "Furnitures",
                    "Wardrobes"
                ],
                products: [
                    {
                        name: 'Rustic Comfort 6-Door Wardrobe',
                        price: '86M',
                        img: 'https://media.homecentre.com/i/homecentre/165438113-165438113-HC23052023_02-2100.jpg?fmt=auto&$quality-standard$&sm=c&$prodimg-m-sqr-pdp-2x$'
                    },
                    {
                        name: 'Olivos 3-Door Wardrobe with Mirror',
                        price: '35M',
                        img: 'https://media.homeboxstores.com/i/homebox/165368803-165368803-HMBX18022023Q_01-2100.jpg?fmt=auto&$quality-standard$&sm=c&$prodimg-m-sqr-pdp-2x$'
                    },
                    {
                        name: 'Wakefit Wardrobe',
                        price: '128Mr',
                        img: 'https://m.media-amazon.com/images/I/61TWbJDdLLL._AC_UF894,1000_QL80_.jpg'
                    }
                ]
            }
        },
        methods: {
        }
    }
</script>
<template>
    <!--product list-->
    <div class="flex flex-col h-full w-full p-7">
        <div class="bg-gray-50 w-full p-3 justify-center flex rounded-md">
            <div class="rounded-md bg-gray-200 relative flex justify-end items-center w-5/12">
                <input class="text-lg p-2 rounded-md bg-gray-200 w-full">
                <svg viewBox="0 0 24 24" class=" absolute fill-none w-7 stroke-orange-500 mr-2">
                    <path d="M11 6C13.7614 6 16 8.23858 16 11M16.6588 16.6549L21 21M19 11C19 15.4183 15.4183 19 11 19C6.58172 19 3 15.4183 3 11C3 6.58172 6.58172 3 11 3C15.4183 3 19 6.58172 19 11Z" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"></path> 
                </svg>
            </div>
        </div>
        <div class="w-full h-auto">
            <ul class="list-none flex flex-row p-1 px-5 bg-gray-50 rounded-md mt-3">
                <li v-for="item in location" class="flex">
                    <a href="#" class="text-orange-600">{{ item }}</a>
                    <svg viewBox="0 0 24 20" class="fill-none w-5 stroke-gray-400"> 
                        <path d="M4 12H20M20 12L16 8M20 12L16 16" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"></path>
                    </svg>
                </li>
            </ul>
        </div>
        <div class="flex flex-wrap flex-grow overflow-y-scroll content-start w-full h-5/6 mt-3 gap-5" >
            <div class="h-64 w-44 bg-gray-50 items-center justify-center flex flex-col rounded-md drop-shadow-md" v-for="item in products">
                <img class="rounded-full w-36 h-36 mb-4" v-bind:src = item.img>
                <a class="text-balance text-center mx-2 mb-2 h-10">{{ item.name }}</a>
                <a class="my-1 font-bold">{{ item.price }} TL</a>
            </div>
        </div>
    </div>
      <!--product list end-->
</template>
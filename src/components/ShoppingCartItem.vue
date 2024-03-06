<script setup>
    defineProps(['title'])
</script>
<script>
    export default {
        name: 'ShoppingCartItem',
        data() {
            return {
                isOpen: false
            }
        },
        methods: {
            toggleOpen() {
                if(event.target.tagName === "INPUT")
                {
                    return;
                }
                this.isOpen = !this.isOpen
            }

        }
    }
</script>
<template>
    <li @click="toggleOpen" class="list-none w-full flex flex-col rounded-xl pt-3 mb-3" v-bind:class="{'border-l-4 border-lime-500': isOpen}">
        <div class="flex flex-row w-full ">
            <svg viewBox="0 0 20 34" class="w-8 h-8 stroke-gray-400" v-if="!isOpen">
                <path d="M6 18M18 12L13 7M18 12L13 17" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"></path>
            </svg>
            <svg viewBox="0 0 20 34" class="w-8 h-8 stroke-gray-400" v-if="isOpen">
                 <path d="M12 18L7 13M12 18L17 13" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"></path> 
            </svg>
            <span class="pl-3 -mt-0.5">50</span>
            <div class="flex flex-col ml-3 -mt-0.5 w-full">
                <h2 class="text-slate-900">{{ title }}</h2>
                <h3 class="text-gray-400 text-sm">Renk</h3>
            </div>
            <div class="w-2/6 h-full text-center flex flex-col">
                <span class="text-center">5.00 TL</span>
            </div>
            <button class="w-10 mr-2">
                <svg viewBox="0 0 24 37">
                    <path fill="none" d="M12.0004 9.5L17.0004 14.5M17.0004 9.5L12.0004 14.5M4.50823 13.9546L7.43966 17.7546C7.79218 18.2115 7.96843 18.44 8.18975 18.6047C8.38579 18.7505 8.6069 18.8592 8.84212 18.9253C9.10766 19 9.39623 19 9.97336 19H17.8004C18.9205 19 19.4806 19 19.9084 18.782C20.2847 18.5903 20.5907 18.2843 20.7824 17.908C21.0004 17.4802 21.0004 16.9201 21.0004 15.8V8.2C21.0004 7.0799 21.0004 6.51984 20.7824 6.09202C20.5907 5.71569 20.2847 5.40973 19.9084 5.21799C19.4806 5 18.9205 5 17.8004 5H9.97336C9.39623 5 9.10766 5 8.84212 5.07467C8.6069 5.14081 8.38579 5.2495 8.18975 5.39534C7.96843 5.55998 7.79218 5.78846 7.43966 6.24543L4.50823 10.0454C3.96863 10.7449 3.69883 11.0947 3.59505 11.4804C3.50347 11.8207 3.50347 12.1793 3.59505 12.5196C3.69883 12.9053 3.96863 13.2551 4.50823 13.9546Z" stroke="#000000" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"></path>
                </svg>
            </button>
        </div>
        <div v-if="isOpen" class="w-full flex flex-row p-4">
            <div class="flex flex-col w-4/12">
                <span>Count</span>
                <input class="rounded-md border-2 border-gray-400 p-2 text-right w-32">
            </div>
            <div class="flex flex-col w-4/12">
                <span>Unit Price</span>
                <input class="rounded-md border-2 border-gray-400 p-2 text-right w-32">
            </div>
        </div>
    </li>
</template>
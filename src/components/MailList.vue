<script setup lang="ts">
</script>

<template>
    <div class="w-full h-full p-2 md:p-10 text-gray-700 dark:text-gray-200 dark:bg-gray-800">
         <div class="flex mb-6 items-center px-5 py-3 rounded-lg w-full border-2 border-gray-300 dark:border-gray-700">
            <label for="search" class="mr-4">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                <path stroke-linecap="round" stroke-linejoin="round" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" />
                </svg>
            </label>
            <input id="search" type="search" placeholder="Search here" class="outline-none w-full bg-transparent">
         </div>  
         <ul class="flex flex-col">
            <li v-for="(mail, index) in mails" :key="mail.title" class="flex  rounded-lg transition-shadow cursor-pointer hover:shadow-2xl hover:shadow-blue-300 dark:hover:shadow-gray-900 w-full p-5 bg-white dark:bg-gray-700 mb-4" >
                <div class="relative  w-10 h-10">
                    <img :src="mail.picture" class="  rounded-full bg-sky-300 w-full h-full object-cover" alt="">
                    <div class="absolute right-0 bottom-0 z-10 w-3 h-3 bg-green-600 rounded-full border-2 border-white">
                    </div>
                </div>
                <div class="w-full flex flex-col pl-4">
                    <h1 class="font-bold" >
                        {{mail.from}}
                    </h1>
                   <div class="flex my-2">
                     <p>{{mail.title}}</p>
                     <div v-if="mail.attachment" class="ml-2">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M15.172 7l-6.586 6.586a2 2 0 102.828 2.828l6.414-6.586a4 4 0 00-5.656-5.656l-6.415 6.585a6 6 0 108.486 8.486L20.5 13" />
                        </svg>
                     </div>
                   </div>
                   <p>
                        {{mail.body}}
                     </p>
                </div>
            </li>
         </ul>
    </div>
</template>

<script lang="ts">

export default {
    data(){
        return{
            mails:[
                {
                    from:"Filipe Lukebana",
                    title:"Some Random Title",
                    body:"Do laboris consequat ut aute. Dolor minim ea excepteur officia et anim nulla proident nisi non et eu culpa consequat.. ",
                    picture:"https://picsum.photos/200/300",
                    attachment:"https://picsum.photos/200/300"

                },
                {
                    from:"Rita Naomi",
                    title:"Some Random Title from Rita",
                    body:"Do laboris consequat ut aute. Dolor minim ea excepteur officia et anim nulla proident nisi non et eu culpa consequat.. ",
                    picture:"https://picsum.photos/201/300",
                    attachment:"https://picsum.photos/200/300"
                },
                {
                    from:"Alexandre",
                    title:"Some Random Title from Alexandre",
                    body:"Do laboris consequat ut aute. Dolor minim ea excepteur officia et anim nulla proident nisi non et eu culpa consequat.. ",
                    picture:"https://picsum.photos/202/300",
                    attachment:"https://picsum.photos/200/300"
                },
                {
                    from:"Daniel Tomás",
                    title:"Some Random Title from Daniel",
                    body:"Do laboris consequat ut aute. Dolor minim ea excepteur officia et anim nulla proident nisi non et eu culpa consequat.. ",
                    picture:"https://picsum.photos/203/300",
                    attachment:"https://picsum.photos/200/300"
                },
            ]
        }
    }
}

</script>

<script setup lang="ts">

</script>

<template>
    <div class="w-full h-screen flex-col py-10 overflow-y-auto">
            <ul class="w-full h-auto  flex flex-col px-5 text-gray-700 dark:text-gray-200">
                <li class=" w-full">
                    <button class=" justify-center sm:justify-start  px-2 sm:px-10 w-full py-3 mb-3 bg-gradient-2 flex items-center rounded-lg text-white font-bold">
                      <div class="mr-0 sm:mr-2">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M12 9v3m0 0v3m0-3h3m-3 0H9m12 0a9 9 0 11-18 0 9 9 0 0118 0z" />
                        </svg>
                      </div>  
                      <p class="hidden sm:block">
                        New message
                      </p>
                    </button>

                    
                </li>
                <li class=" w-full" v-for="(menu, index) in menus" :key="menu.label">
                    <button v-if="menu.link"  class="justify-center sm:justify-start relative px-2 sm:px-10 w-full py-3  my-2  flex items-center rounded-lg text-gray-700 dark:text-gray-200 font-bold dark:hover:bg-gray-600 dark:hover:text-gray-300 hover:bg-sky-100 hover:text-sky-700 transition-colors">
                      <div class="mr-2" v-html="menu.icon">
                      </div>  
                      <p class="hidden sm:block">
                        {{menu.label}}
                      </p>
                      <div v-show="menu.unread != null"  class="w-7 h-7 flex flex-col items-center justify-center bg-gray-200 dark:bg-gray-800 rounded-md absolute -right-4 sm:right-4 ">
                        {{menu.unread}}
                      </div>
                    </button>
                    <div v-else class=" uppercase text-gray-400 font-bold w-full border-t dark:border-gray-800  py-2 px-2 sm:px-10 w-full" >
                        <h1>{{menu.label}}</h1>
                    </div>
                </li>
            </ul>
    </div>
</template>

<script>

export default {
    data(){
        return{
            menus:[
                {
                    label:"Inbox",
                    icon:`<svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M4 16v1a3 3 0 003 3h10a3 3 0 003-3v-1m-4-4l-4 4m0 0l-4-4m4 4V4" />
                        </svg>`,
                    link:"#"
                },
                {
                    label:"Favorite",
                    icon:`<svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M5 3v4M3 5h4M6 17v4m-2-2h4m5-16l2.286 6.857L21 12l-5.714 2.143L13 21l-2.286-6.857L5 12l5.714-2.143L13 3z" />
                        </svg>`,
                    link:"#",
                    unread:"04"
                },
                {
                    label:"Sent",
                    icon:`<svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M8 10h.01M12 10h.01M16 10h.01M9 16H5a2 2 0 01-2-2V6a2 2 0 012-2h14a2 2 0 012 2v8a2 2 0 01-2 2h-5l-5 5v-5z" />
                        </svg>`,
                    link:"#",

                },
                {
                    label:"Trash",
                    icon:`<svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M19 7l-.867 12.142A2 2 0 0116.138 21H7.862a2 2 0 01-1.995-1.858L5 7m5 4v6m4-6v6m1-10V4a1 1 0 00-1-1h-4a1 1 0 00-1 1v3M4 7h16" />
                        </svg>`,
                    link:"#"
                },
                {
                    label:"Draft",
                    icon:`<svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                    <path stroke-linecap="round" stroke-linejoin="round" d="M11 5H6a2 2 0 00-2 2v11a2 2 0 002 2h11a2 2 0 002-2v-5m-1.414-9.414a2 2 0 112.828 2.828L11.828 15H9v-2.828l8.586-8.586z" />
                    </svg>`,
                    link:"#",
                     unread:"02"
                },
                {label:"Meets", },
                {
                    label:"Create Meeting",
                    icon:`<svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M15 10l4.553-2.276A1 1 0 0121 8.618v6.764a1 1 0 01-1.447.894L15 14M5 18h8a2 2 0 002-2V8a2 2 0 00-2-2H5a2 2 0 00-2 2v8a2 2 0 002 2z" />
                        </svg>`,
                    link:"#",
                },
                {
                    label:"Join Meeting",
                    icon:`<svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M17 16l4-4m0 0l-4-4m4 4H7m6 4v1a3 3 0 01-3 3H6a3 3 0 01-3-3V7a3 3 0 013-3h4a3 3 0 013 3v1" />
                        </svg>`,
                    link:"#",
                },
                {label:"Tools", },
                                {
                    label:"Chat",
                    icon:`<svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                    <path stroke-linecap="round" stroke-linejoin="round" d="M8 12h.01M12 12h.01M16 12h.01M21 12c0 4.418-4.03 8-9 8a9.863 9.863 0 01-4.255-.949L3 20l1.395-3.72C3.512 15.042 3 13.574 3 12c0-4.418 4.03-8 9-8s9 3.582 9 8z" />
                    </svg>`,
                    link:"#",
                    unread:"06"
                },
                                {
                    label:"Calendar",
                    icon:`<svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z" />
                        </svg>`,
                    link:"#",
                    unread:"01"
                },
            ]
        }
    }
}

</script>
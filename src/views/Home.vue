<script>
 // import {
 //   web3Accounts,
 //   web3Enable,
 //   // web3FromAddress,
 //   // web3ListRpcProviders,
 //   // web3UseRpcProvider
 // } from '@polkadot/extension-dapp'
 import { defineComponent, reactive } from 'vue'

 // Internal imports
 import ButtonRepo from '@/components/ButtonRepo.vue'


 export default defineComponent({
   components: {
     ButtonRepo
   },
   setup () {
     const user = reactive({
       accounts: {
         address: 'Not enabled yet...'
         // address: '',
         // meta: {
         //   genesisHash: null,
         //   name: undefined,
         //   source: '',
         // },
       },
       enabled: {
         name: 'Not enabled yet...',
         // name: '',
         // version: '',
       },
     })

     const enable = async () => {
       // returns an array of all the injected sources
       // (this needs to be called first, before other requests)
       // const allInjected = await web3Enable('my cool dapp');

       // user.enabled = allInjected
     }

     const getAccounts = async () => {
       // returns an array of { address, meta: { name, source } }
       // meta.source contains the name of the extension that provides this account
       // const allAccounts = await web3Accounts();
       //
       // user.accounts = allAccounts
     }

     return {
       enable,
       getAccounts,

       user,
     }
   }
 })
</script>

<template>
  <div class="bg-gray-50">
    <div
      class="max-w-screen-xl px-4 py-12 mx-auto sm:px-6 lg:py-16 lg:px-8 lg:flex lg:items-center lg:justify-between"
    >
      <h2
        class="text-3xl font-extrabold leading-9 tracking-tight text-gray-900 sm:text-4xl sm:leading-10"
      >
        Edgeware Crystal NFT: Geode
        <!-- <br />
             <span class="text-indigo-600">Vite 2.x + Vue 3.x + Tailwind 2.x</span> -->

      </h2>

      <div class="flex mt-8 lg:flex-shrink-0 lg:mt-0 space-x-3">
        <div class="rounded-md shadow">
          <div
            @click="enable"
            class="items-center justify-center px-5 py-3 text-base font-medium leading-6 text-white transition duration-150 ease-in-out bg-indigo-600 border border-transparent rounded-md hover:bg-indigo-500 focus:outline-none"
          >Enable Web3</div>
        </div>


        <div class="rounded-md shadow">
          <div
            @click="getAccounts"
            class="items-center justify-center px-5 py-3 text-base font-medium leading-6 text-white transition duration-150 ease-in-out bg-indigo-600 border border-transparent rounded-md hover:bg-indigo-500 focus:outline-none"
          >Show Web3 accounts</div>
        </div>

      </div>
      <div class="flex mt-8 lg:flex-shrink-0 lg:mt-0">
        <div class="rounded-md shadow">
          <router-link
            to="/about"
            class="items-center justify-center px-5 py-3 text-base font-medium leading-6 text-white transition duration-150 ease-in-out bg-indigo-600 border border-transparent rounded-md hover:bg-indigo-500 focus:outline-none"
          >About</router-link>
        </div>
      </div>

    </div>

    <div>
      <h3>Enabled</h3>
      <div>
        {{ user.enabled }}
      </div>
    </div>

    <div>
      <h3>Accounts</h3>
      <div>
        {{ user.accounts }}
      </div>
    </div>
  </div>

</template>

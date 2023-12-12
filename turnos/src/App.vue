<script setup>
// const placa = [{
//   plate: 'Bgo-908', done: 0
// },{
//   placa: 'Bgeb-77', done: 0
// },{
//   placa: 'juwfb', done: 0
// }]

const plateModule1 = [
  {
    plate: 'XDCHH',
    done: 0
  },
  {
    plate: 'HT550',
    done: 0
  },
  {
    plate: 'G3WQ',
    done: 0
  },
  {
    plate: 'PTWE',
    done: 0
  }
]

const plateModule2 = [
  {
    plate: 'XDCHH',
    done: 0
  },
  {
    plate: 'HT550',
    done: 0
  }
]

const plateModule3 = [
  {
    plate: 'XDCHH',
    done: 0
  },
  {
    plate: 'HT550',
    done: 0
  },
  {
    plate: 'G3WQ',
    done: 0
  }
]
</script>

<template>
  <div class="bg-slate-200 shadow-md border-2">
    <div class="text-center">
      <h1 class="mt-8 text-3xl font-semibold uppercase">Sistema de turnos</h1>
    </div>
    <div class="grid grid-cols-3 gap-4 mx-auto container text-center mt-5">
      <div class="bg-pink-50">
        <div class="bg-blue-500 text-white rounded rounded-b-none p-2 font-semibold">Módulo 1</div>
        <div class="mt-2">
          <h1 v-for="(p, index) in plateModule1" :key="index++" class="rounded m-2 w-[90%] bg-white font-semibold">
            <span>{{ index }}</span> -
            <span>{{ p.plate }}</span>
          </h1>
        </div>
      </div>

      <div class="bg-pink-50">
        <div class="bg-orange-500 text-white rounded rounded-b-none p-2 font-semibold">
          Módulo 2
        </div>
        <div class="mt-2">
          <h1 v-for="(p, index) in plateModule2" :key="index++" class="rounded m-2 w-[90%] bg-white font-semibold">
            <span>{{ index }}</span> -
            <span>{{ p.plate }}</span>
          </h1>
        </div>
      </div>

      <div class="bg-pink-50">
        <div class="bg-green-500 text-white rounded rounded-b-none p-2 font-semibold">Módulo 3</div>
        <div class="mt-2">
          <h1 v-for="(p, index) in plateModule3" :key="index++" class="rounded m-2 w-[90%] bg-white font-semibold">
            <span>{{ index }}</span> -
            <span>{{ p.plate }}</span>
          </h1>
        </div>
      </div>
    </div>

    <div class="bg-pink-50 h-20 mx-auto container mt-4 mb-4 rounded flex">
      <div class="w-[30%] text-center flex items-center px-4 uppercase">
        <h1 class="flex items-center"><span class="text-3xl font-semibold px-2">9</span> Turnos</h1>
      </div>
      <div class="flex space-x-4 w-[70%] p-4 justify-around items-center">
        <div>
          <input class="w-36 rounded p-1 border-2 border-black" type="text" placeholder="Código" />
        </div>
        <div>
          <input class="w-36 rounded p-1 border-2 border-black" type="number" />
        </div>
        <div>
          <button class="bg-purple-400 p-1 rounded px-4 text-white">Agregar Turno</button>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped></style>

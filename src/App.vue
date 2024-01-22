<script setup>
import { ref } from 'vue'
    const lebarBahan = ref(79);
    const panjangBahan = ref(109);
    const lebarPotongan = ref(21);
    const panjangPotongan = ref(29.2);
    const lebarMataPisau = ref(0.2);
    const totalKertas = ref(0);

    const hitungTotalKertas = () => {
      const Material = Math.floor(lebarBahan.value * panjangBahan.value);
      const Cutting = Math.floor(lebarPotongan.value * panjangPotongan.value);
      const x = Math.round(Material / Cutting);
      const xy = Math.round(x * lebarMataPisau.value);
      totalKertas.value = x-xy;

    //   const materialWidth = Math.floor((lebarBahan.value-lebarMataPisau.value) / lebarPotongan.value)
    //   const materialHeight = Math.floor((panjangBahan.value-lebarMataPisau.value) / panjangPotongan.value)
    //   totalKertas.value = materialWidth*materialHeight;
    //   console.log(materialWidth);
    //   console.log(materialHeight);
    //   console.log(x);
    //   console.log(xy);
      
      console.log(totalKertas.value);
    };

</script>

<template>
	<div
		class="py-10 lg:py-20 h-screen bg-sky-500/85 w-full flex flex-col gap-8 lg:gap-16 shrink-0 items-center section-wrapper"
	>
		<main class="flex gap-10 max-sm:flex-col px-10 lg:px-10 content-wrapper">
			<aside class="w-[30%] max-sm:w-full flex flex-col gap-4 lg:gap-10">
				<h3 class="text-[28px] font-bold">Kalkulator Kertas</h3>
				<p>
					This information will be displayed publicly so be careful what you
					share.
				</p>
			</aside>
			<div class="md:w-full flex flex-col gap-8 form-wrapper">
				<div class="w-full flex flex-col gap-y-3">
					<h4 class="text-[24px] font-bold material">Ukuran Bahan</h4>
					<div class="w-full">
						<label
							for="material-p-width"
							class="block text-sm font-medium leading-6 text-gray-900"
							>Lebar Kertas</label
						>
						<div
							class="mt-2 flex rounded-md shadow-sm ring-1 ring-inset ring-gray-300 focus-within:ring-2 focus-within:ring-inset focus-within:ring-indigo-600 px-3"
						>
							<input
                                class="block flex-1 border-0 bg-transparent py-1.5 pr-2 text-gray-900 placeholder:text-gray-400 focus:ring-0 sm:text-sm sm:leading-6 focus:outline-none focus:border-0"
								type="number"
								name="material-width"
								id="material-p-width"
                                v-model="lebarBahan"
							/>
							<span
								class="flex select-none items-center text-gray-500 sm:text-sm"
								>CM</span
							>
						</div>
					</div>

					<div class="w-full">
						<label
							for="material-p-height"
							class="block text-sm font-medium leading-6 text-gray-900"
							>Panjang Kertas</label
						>
						<div
							class="mt-2 flex rounded-md shadow-sm ring-1 ring-inset ring-gray-300 focus-within:ring-2 focus-within:ring-inset focus-within:ring-indigo-600 px-3"
						>
							<input
                                class="block flex-1 border-0 bg-transparent py-1.5 pr-2 text-gray-900 placeholder:text-gray-400 focus:ring-0 sm:text-sm sm:leading-6 focus:outline-none focus:border-0"
								type="number"
								name="material-height"
								id="material-p-height"
                                v-model="panjangBahan"
							/>
							<span
								class="flex select-none items-center text-gray-500 sm:text-sm"
								>CM</span
							>
						</div>
					</div>
				</div>

                <div class="w-full flex flex-col gap-y-3">
					<h4 class="text-[24px] font-bold">Ukuran Potong</h4>
					<div class="w-full">
						<label
							for="cutting-p-width"
							class="block text-sm font-medium leading-6 text-gray-900"
							>Lebar Kertas</label
						>
						<div
							class="mt-2 flex rounded-md shadow-sm ring-1 ring-inset ring-gray-300 focus-within:ring-2 focus-within:ring-inset focus-within:ring-indigo-600 px-3"
						>
							<input
                                class="block flex-1 border-0 bg-transparent py-1.5 pr-2 text-gray-900 placeholder:text-gray-400 focus:ring-0 sm:text-sm sm:leading-6 focus:outline-none focus:border-0"
								type="number"
								name="cutting-width"
								id="cutting-p-width"
                                v-model="lebarPotongan"
							/>
							<span
								class="flex select-none items-center text-gray-500 sm:text-sm"
								>CM</span
							>
						</div>
					</div>

					<div class="w-full">
						<label
							for="cutting-p-height"
							class="block text-sm font-medium leading-6 text-gray-900"
							>Tinggi Kertas</label
						>
						<div
							class="mt-2 flex rounded-md shadow-sm ring-1 ring-inset ring-gray-300 focus-within:ring-2 focus-within:ring-inset focus-within:ring-indigo-600 px-3"
						>
							<input
                            class="block flex-1 border-0 bg-transparent py-1.5 pr-2 text-gray-900 placeholder:text-gray-400 focus:ring-0 sm:text-sm sm:leading-6 focus:outline-none focus:border-0"
								type="number"
								name="cutting-height"
								id="cutting-p-height"
                                v-model="panjangPotongan"
							/>
							<span
								class="flex select-none items-center text-gray-500 sm:text-sm"
								>CM</span
							>
						</div>
					</div>

                    <div class="w-full">
						<label
							for="cutting-p-blade"
							class="block text-sm font-medium leading-6 text-gray-900"
							>Lebar Mata Pisau</label
						>
						<div
							class="mt-2 flex rounded-md shadow-sm ring-1 ring-inset ring-gray-300 focus-within:ring-2 focus-within:ring-inset focus-within:ring-indigo-600 px-3"
						>
							<input
                                class="block flex-1 border-0 bg-transparent py-1.5 pr-2 text-gray-900 placeholder:text-gray-400 focus:ring-0 sm:text-sm sm:leading-6 focus:outline-none focus:border-0"
								type="number"
								name="cutting-blade"
								id="cutting-p-blade"
                                v-model="lebarMataPisau"
							/>
							<span
								class="flex select-none items-center text-gray-500 sm:text-sm"
								>CM</span
							>
						</div>
					</div>
				</div>

                <div class="mt-6 flex items-center justify-end gap-x-6 form-action">
                    <button type="button" class="text-sm font-semibold leading-6 text-gray-900">Reset</button>
                    <button type="submit" class="rounded-md bg-indigo-600 px-3 py-2 text-sm font-semibold text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600"
                        @click="hitungTotalKertas">Save</button>
                </div>
			</div>
		</main>
	</div>
</template>

<style scoped>
</style>

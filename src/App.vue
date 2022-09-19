<template>
	<div class="container-md">
		<div class="row mt-5">
			<h1>河川監視</h1>
		</div>
		<div class="row mt-5">
			<div class="row">
				<div class="col-md-6"><img src="https://www.cgr.mlit.go.jp/cctv/ootagawa/61/cctv.jpg" /></div>
			</div>
			<div class="row">
				<div class="col-md-6"><img src="https://www.cgr.mlit.go.jp/cctv/ootagawa/62/cctv.jpg" /></div>
			</div>
			<div class="row">
				<div class="col-md-6"><img src="https://cam.river.go.jp/cam/now/122333161.jpg" /></div>
			</div>
			<div class="row">
				<div class="col-md-6"><img src="https://cam.river.go.jp/cam/now/122333113.jpg" /></div>
			</div>
		</div>
		<!-- <div class="row">
			<Chart :size="{ width: 500, height: 400 }" :data="data" :margin="margin" :direction="direction">
				<template #layers>
					<Grid strokeDasharray="2,2" />
					<Line :dataKeys="['name', 'pl']" />
				</template>
			</Chart>
		</div> -->
	</div>
</template>

<script>
import { defineComponent, ref } from 'vue'
import { Chart, Grid, Line } from 'vue3-charts'
import { plByMonth } from '@/data'

export default defineComponent({
	name: 'LineChart',
	components: { Chart, Grid, Line },
	setup() {
		const data = ref(plByMonth)
		const direction = ref('horizontal')
		const margin = ref({
			left: 0,
			top: 20,
			right: 20,
			bottom: 0
		})

		return { data, direction, margin }
	}
})
</script>
<template>
	<Table :tableData="tableDataSet" />
</template>

<script setup>
import router from '@/router';
import { computed, onMounted, ref } from 'vue';
import Table from '@/components/Table.vue';

const tableDataSet = ref({
	list: [
		{
			date: '2023.01.04 (수)',
			nameKr: '박민호',
			startDt: '09:58',
			endDt: '19:36',
		},
		{
			date: '2023.01.04 (수)',
			nameKr: '정연호',
			startDt: '08:33',
			endDt: '18:48',
		},
	], // 테이블에 들어갈 데이터 --> 더미 데이터는 여기에
	total: 0,
	isLoading: true,
	columnList: [
		// 테이블 컬럼정보 정의 및 커스텀
		{ name: 'date', align: 'center', label: '날짜', field: 'date', headerStyle: '', style: '', classes: 'app-fw-6', sortable: true },
		{ name: 'nameKr', align: 'center', label: '이름', field: 'nameKr', sortable: true },
		{ name: 'startDt', align: 'center', label: '출근시간', field: 'startDt', headerStyle: '', style: '', classes: '' },
		{ name: 'endDt', align: 'center', label: '퇴근시간', field: 'endDt', headerStyle: '', style: '', classes: '' },
	],
	sortKey: {
		nameKr: 'nameKr',
		rank: 'rank',
		joinDt: 'joinDt',
		stat: 'stat',
	},
});
</script>

<style scoped lang="scss"></style>

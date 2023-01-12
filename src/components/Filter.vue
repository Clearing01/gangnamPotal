<template>
	<div class="app-table-filter-wrapper">
		<div class="filter-wrapper">
			<div class="filter-container">
				<div class="flex items-center">
					<div class="filter-title mr-10">구분</div>
					<div>
						<q-select
							class="app-input input-medium input-select"
							outlined
							dropdown-icon="icon-keyboard-arrow-down"
							label="선택하세요"
							popup-content-class="select-popup"
						/>
						<!-- v-model="filterData.index"
							@update:model-value="handleIndexFilter"
							:options="propDataSet?.indexList" -->
					</div>
				</div>
			</div>
			<div class="filter-container">
				<div class="flex items-center">
					<div>
						<q-input class="app-input input-medium" outlined placeholder="입력하세요" />
						<!-- v-model="input.string"
					:disable="selectedFilter?.isDisable"
					@keydown="keyupEnter($event)" -->
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
const props = defineProps({ tableData: Object });
</script>

<style scoped lang="scss">
.app-table-filter-wrapper {
	background: rgba(240, 243, 249, 0.8);
	border-radius: 12px;
	margin-bottom: 20px;
}
.filter-wrapper {
	width: 100%;
	padding: 16px 24px;
	.filter-container {
		display: inline-block;
		vertical-align: top;
		margin-left: 20px;
		&:first-child {
			margin-left: 0;
		}
	}
	.filter-title {
		font-size: $font-02;
		line-height: $font-06;
		color: $blue-gray-10;
		font-weight: 500;
	}
	.app-input,
	.app-input-picker {
		width: 100%;
	}
}
.option-wrapper {
	width: 100%;
	border-top: 1px solid rgba(231, 235, 243, 0.8);
	padding: 16px 24px 8px;
}
.filter-chip-wrapper {
	width: calc(100% - 97px);
}
</style>

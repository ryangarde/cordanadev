<template>
	<q-layout view="lHh Lpr lFf">
		<MainHeader />
		<MainSideBar />
		<q-page-container>
			<q-page>
				<router-view />
			</q-page>
		</q-page-container>
	</q-layout>
</template>

<script>
import MainSideBar from '../components/MainSideBar.vue';
import MainHeader from '../components/MainHeader.vue';

export default {
	components: { MainSideBar, MainHeader },
};
</script>




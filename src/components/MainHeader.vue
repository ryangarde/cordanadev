<template>
	<q-header elevated>
		<q-toolbar class="bg-white text-black" style="height: 80px">
			<div class="search-bar">
				<q-icon name="mdi-magnify" />
				<input type="text" placeholder="Search for..." />
			</div>

			<div class="flex-grow"></div>

			<div class="profile" id="profile">
				<q-avatar>
					<img src="https://cdn.quasar.dev/logo/svg/quasar-logo.svg" />
				</q-avatar>

				<div class="profile-name">Ronald Hunter</div>

				<q-icon name="mdi-chevron-down" />

				<q-menu touch-position target="#profile">
					<q-list style="min-width: 100px">
						<q-item clickable v-close-popup>
							<q-item-section>My Profile</q-item-section>
						</q-item>
						<q-item clickable v-close-popup>
							<q-item-section>Logout</q-item-section>
						</q-item>
					</q-list>
				</q-menu>
			</div>

			<div class="notification">
				<q-icon name="mdi-bell-outline" />
			</div>

			<!-- <q-toolbar-title>Quasar Framework</q-toolbar-title> -->
		</q-toolbar>
	</q-header>
</template>

<style scoped>
.flex-grow {
	flex-grow: 1;
}

.profile {
	display: flex;
	column-gap: 10px;
	align-items: center;
	cursor: pointer;
	padding: 0 20px;
}

.profile-name {
	font-size: 14px;
}

.notification {
	display: grid;
	place-items: center;
	width: 80px;
	height: 80px;
	border-left: 1px solid #eeeeee;
}

.notification i {
	font-size: 30px;
	cursor: pointer;
}

.search-bar {
	display: flex;
	align-items: center;
	width: 350px;
	margin-left: 30px;
}

.search-bar i {
	font-size: 24px;
	color: #ababab;
}

.search-bar input {
	padding: 8px 13px;
	width: 100%;
	border: none;
	outline: none;
}
</style>
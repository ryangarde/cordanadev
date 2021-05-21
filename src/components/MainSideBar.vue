<template>
	<q-drawer v-model="leftDrawerOpen" show-if-above bordered content-class="drawer">
		<template v-for="group in navGroups">
			<q-list :key="group.name">
				<q-item-label header class="group-title">
					{{ group.name }}
				</q-item-label>

				<q-item clickable tag="a" target="_blank" v-for="link in group.links" :key="link.title" class="item">
					<q-item-section v-if="link.icon" avatar>
						<q-icon :name="link.icon" />
					</q-item-section>

					<q-item-section>
						<q-item-label>{{ link.title }}</q-item-label>
					</q-item-section>
				</q-item>
			</q-list>

			<br :key="group.name + 'br'" />
			<q-separator :key="group.name + 'separator'" />
			<br :key="group.name + 'br2'" />

			<q-tab
				:key="group.name + 'asdf'"
				label="Settings <i class='fas fa-caret-down' />"
				name="settings"
				slot="title"
				icon="fas fa-cogs faa-pulse"
				class="faa-parent animated-hover"
				@click="displaySettingsMenu = !displaySettingsMenu"
			>
				<q-popover v-model="displaySettingsMenu">
					<q-list item-separator link>
						<q-item to="settings-system" replace v-close-overlay>
							<q-item-side left class="faa-parent animated-hover">
								<q-item-tile icon="fas fa-cog faa-pulse" />
							</q-item-side>
							System
						</q-item>

						<q-item to="settings-users" replace v-close-overlay>
							<q-item-side left class="faa-parent animated-hover">
								<q-item-tile icon="fas fa-user faa-pulse" />
							</q-item-side>
							Users
						</q-item>
					</q-list>
				</q-popover>
			</q-tab>
		</template>
	</q-drawer>
</template>

<script>
export default {
	name: 'MainLayout',
	data: () => ({
		displaySettingsMenu: true,
		leftDrawerOpen: false,
		navGroups: [
			{
				name: 'Main',
				links: [{ title: 'Dashboard', icon: 'mdi-cog-outline' }],
			},
			{
				name: 'Manage Listings',
				links: [
					{ title: 'Add new', icon: 'holiday_village' },
					{ title: 'My Properties', icon: 'home' },
					{ title: 'My Favorites', icon: 'favorite_border' },
					{ title: 'Save Search', icon: 'mdi-home-search' },
					{ title: 'Reviews', icon: 'mdi-chat-processing-outline' },
					{ title: 'Invoice', icon: 'mdi-note-text-outline' },
				],
			},
			{
				name: 'Manage Account',
				links: [
					{ title: 'My Package', icon: 'mdi-package-variant-closed' },
					{ title: 'My Profile', icon: 'mdi-account' },
					{ title: 'Logout', icon: 'mdi-logout' },
				],
			},
		],
	}),
};
</script>

<style scoped>
.q-item__label {
	color: #333;
}

.group-title.q-item__label {
	color: #ababab;
	text-transform: uppercase;
}

.q-icon {
	color: #ababab;
}

.q-icon {
	transition: 0.3s;
}

.q-item:hover .q-icon {
	color: #0ec6d5;
}
</style>

<style >
.drawer {
	padding: 20px;
}

body.desktop .q-hoverable:hover > .q-focus-helper {
	background: #f8f8f8;
	/* opacity: 1; */
}
</style>
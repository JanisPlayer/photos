<!--
 - @copyright Copyright (c) 2020 Corentin Mors
 -
 - @license AGPL-3.0-or-later
 -
 - @author Corentin Mors <medias@pixelswap.fr>
 -
 - This program is free software: you can redistribute it and/or modify
 - it under the terms of the GNU Affero General Public License as
 - published by the Free Software Foundation, either version 3 of the
 - License, or (at your option) any later version.
 -
 - This program is distributed in the hope that it will be useful,
 - but WITHOUT ANY WARRANTY; without even the implied warranty of
 - MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
 - GNU Affero General Public License for more details.
 -
 - You should have received a copy of the GNU Affero General Public License
 - along with this program. If not, see <http://www.gnu.org/licenses/>.
 -
 -->

<template>
	<h2 v-if="item.injected.onThisDay" class="grid-title" :style="{height: item.height + 'px'}">
		{{ n('photos', '{years} year ago', '{years} years ago', item.injected.onThisDay, {years: item.injected.onThisDay}) }}<span>  ·  {{ item.injected.month }} {{ item.injected.year }}</span>
	</h2>
	<h2 v-else class="grid-title" :style="{height: item.height + 'px'}">
		{{ item.injected.month }}
		<span>{{ item.injected.year }}</span>
	</h2>
</template>

<script>
export default {
	name: 'SeparatorVirtualGrid',

	inheritAttrs: false,

	props: {
		item: {
			type: Object,
			required: true,
		},
	},
}
</script>

<style lang="scss" scoped>
.grid-title {
	grid-column: 1/8;
	padding: 48px 0 12px 0;
	margin: 0;
	span {
		font-weight: normal;
	}
	&.first-title {
		padding: 0 0 12px 0;
	}
}
</style>

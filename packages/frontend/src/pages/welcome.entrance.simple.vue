<!--
SPDX-FileCopyrightText: syuilo and misskey-project
SPDX-License-Identifier: AGPL-3.0-only
-->

<template>
<div v-if="meta" :class="$style.root">
	<div :class="$style.contents">
		<MkVisitorDashboard/>
	</div>
	<footer :class="$style.footer">
		&copy; {{ instanceName }} | <a :href="meta.repositoryUrl || 'https://github.com/misskey-dev/misskey'" target="_blank">Source Code</a>
	</footer>
</div>
</template>

<script lang="ts" setup>
import { instanceName } from '@@/js/config.js';
import MkVisitorDashboard from '@/components/MkVisitorDashboard.vue';
import { instance as meta } from '@/instance.js';
</script>

<style lang="scss" module>
.root {
	height: 100cqh;
	overflow: auto;
	overscroll-behavior: contain;
	background: #ffffff !important;
	color: #000000 !important;
}

.footer {
	position: fixed;
	bottom: 16px;
	left: 0;
	right: 0;
	text-align: center;
	font-size: 0.8em;
	opacity: 0.7;
	z-index: 10;
}

.contents {
	position: relative;
	width: min(430px, calc(100% - 32px));
	margin: auto;
	padding: 100px 0 100px 0;
}
</style>


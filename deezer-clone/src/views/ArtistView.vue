<script setup>
import Magnify from 'vue-material-design-icons/Magnify.vue'
import Play from 'vue-material-design-icons/Play.vue'
import Pause from 'vue-material-design-icons/Pause.vue'
import DotsHorizontal from 'vue-material-design-icons/DotsHorizontal.vue'
import HeartOutline from 'vue-material-design-icons/HeartOutline.vue'
import ClockTimeFiveOutLine from 'vue-material-design-icons/ClockTimeFiveOutLine.vue'
import artist from '@/artist.json'

import { useSongStore } from '@/stores/song'
import { storeToRefs } from 'pinia'
const useSong = useSongStore()
const { isPlaying, currentTrack, currentArtist } = storeToRefs(useSong)
</script>

<template>
	<div id="HeaderSection" class="max-w-[1500px] mx-auto">
		<div
			class="flex items-center w-full relative h-full px-8 mt-6 min-w-[650px]"
		></div>
	</div>
</template>

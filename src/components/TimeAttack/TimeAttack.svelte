<script lang="ts">
	import type { TrackData } from '$lib/TrackData/TrackData'
	import CommonGamePlay from '../CommonGamePlay/CommonGamePlay.svelte'
	import TimeAttackFinished from './UI/TimeAttackFinished.svelte'
	import TimeAttackIntro from './UI/TimeAttackIntro.svelte'
	import TimeAttackPaused from './UI/TimeAttackPaused.svelte'

	export let trackData: TrackData
</script>

<CommonGamePlay {trackData} let:proceed let:time let:restart let:trackRecord>
	<TimeAttackPaused {time} {trackData} slot="ui-paused" {proceed} {restart} />
	<TimeAttackIntro slot="ui-intro" {proceed} {trackData} {trackRecord} />
	<TimeAttackFinished {time} slot="ui-finished" {restart} {trackRecord} {trackData} />
</CommonGamePlay>

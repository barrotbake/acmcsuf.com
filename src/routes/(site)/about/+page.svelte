<script lang="ts">
  import Spacing from '$lib/public/legacy/spacing.svelte';
  import type { Officer } from '$lib/public/board/types';
  import { getPositionByTermIndex, termIndex } from '$lib/public/board/utils';
  import AboutUs from './about-us.svelte';
  import OfficerProfileList from './officer-profile-list.svelte';

  function filterOfficers(officer: Officer): boolean {
    const isCurrentTerm = getPositionByTermIndex(officer, $termIndex) !== undefined;
    return isCurrentTerm;
  }
</script>

<svelte:head>
  <title>About | ACM at CSUF</title>
</svelte:head>

<Spacing --min="175px" --med="200px" --max="200px" />

<AboutUs />

<Spacing --min="120px" --med="150px" --max="200px" />

<h1 class="size-lg acm-heavier">Board members</h1>

<Spacing --min="16px" --med="16px" --max="16px" />

<OfficerProfileList filter={filterOfficers} placeholderPicture="placeholder.png" />

<Spacing --min="40px" --med="95px" --max="120px" />

<style>
  h1 {
    display: flex;
    justify-content: center;
  }
</style>

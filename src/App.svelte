<script>
  import Navbar from "./Navbar.svelte";
  import Player from "./Player.svelte";
  import AddPlayer from "./AddPlayer.svelte";

  let players = [
    { name: "Mohamed", points: 55 },
    { name: "Sam", points: 44 },
    { name: "Sara", points: 30 }
  ];

  const addPlayer = e => {
    const newPlayer = e.detail;
    players = [...players, newPlayer];
  };
</script>

<Navbar />
<div class="container">
  <AddPlayer on:addplayer={addPlayer} />

  {#if players.length === 0}
    <p>No players</p>
  {:else}
    {#each players as player}
      <Player name={player.name} points={player.points} />
    {/each}
  {/if}
</div>

<script setup lang="ts">
import { onMounted, ref } from "vue";
import type { Ref } from "vue";

const playerInfo: Ref<Player[]> = ref([]);

interface Player {
  name: string;
  origin: string;
  FIDE_ID: string;
  birth_date: string;
  totem?: string;
}

const getPlayerInfo = async (): Promise<Player[]> => {
  let res = await fetch("https://api.npoint.io/9a8a6bda604bb0813b9c");
  return (await res.json()).members;
};

onMounted(async () => {
  playerInfo.value = await getPlayerInfo();
});
</script>
<template>
  <table>
    <thead>
      <th>Nom</th>
      <th>Origine</th>
      <th>ID</th>
      <th>birth</th>
      <th>totem</th>
    </thead>
    <tbody>
      <tr v-for="player in playerInfo">
        <td>{{ player.name }}</td>
        <td>{{ player.origin }}</td>
        <td>{{ player.FIDE_ID }}</td>
        <td>{{ player.birth_date }}</td>
        <td>{{ player.totem }}</td>
      </tr>
    </tbody>
  </table>
</template>

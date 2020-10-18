<template>
  <main class="team-page">
    <KNavigationBar title="Team"/>
    <div class="content formatted">
      <div id="java">
        <TeamMember
          v-for="member in members"
          :key="member.name"
          :product="member"
        />
      </div>
    </div>
  </main>
</template>

<style lang="scss" scoped>
div.content {
  display: flex;
  flex-direction: column;
  margin-bottom: 5rem;

  /*div.group {
    display: flex;
    flex-direction: column;
  }*/
}
</style>

<script>
  import KNavigationBar from "@/components/KNavigationBar";
  import TeamMember from "../components/TeamMember";

  export default {
    name: "TeamPage",
    components: {
      TeamMember,
      KNavigationBar
    },
    async fetch() {
      this.members = await fetch(
        "https://admin-panel.cryptic.rubidium.ml/api/team/member/list"
      ).then(res => res.json());
    },
    data() {
      return {
        members: []
      };
    },
    head() {
      return {
        titleTemplate: "Team - %s"
      };
    }
  };
</script>

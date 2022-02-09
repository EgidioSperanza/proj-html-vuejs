<template>
  <section class="section-team">
    <div class="team" v-for="member in relevanceTeamMembers()" :key="member.id">
      <div class="member">
        <img :src="`/img/team/${member.picture}.jpg`" :alt="member.name" />
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'SectionTeam',
  data() {
    return {
      teamMembersSorted: [],
    }
  },
  props: {
    teamMembers: Array,
  },
  methods: {
    relevanceTeamMembers() {
      let vote = []
      vote = this.sortRelevance(vote)
      if (this.teamMembers.length > 4) {
        let membersRelevance = []

        this.teamMembers.forEach((member) => {
          if (vote.includes(member.vote_relevance)) {
            membersRelevance.push(member)
          }
        })
        this.teamMembersSorted = membersRelevance
        return this.teamMembersSorted
      } else {
        return this.teamMembers
      }
    },
    sortRelevance(vote) {
      this.teamMembers.forEach((member) => {
        if (member.vote_relevance) {
          vote.push(member.vote_relevance)
        }
      })
      vote = vote.slice(vote.length - 4, vote.length).sort()
      return vote
    },
  },
}
</script>

<style scoped lang="scss">
@import '@/style/variables.scss';

.section-team {
  width: 100%;
  display: flex;
  justify-content: space-between;
  .team {
    width: calc(100% / 4);
    .member {
      width: 100%;
      img {
        width: 100%;
        height: 100%;
        object-fit: contain;
      }
    }
  }
}
</style>

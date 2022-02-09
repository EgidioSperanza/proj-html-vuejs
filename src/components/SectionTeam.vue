<template>
  <section class="section-team">
    <div class="team" v-for="member in relevanceTeamMembers()" :key="member.id">
      <img :src="`/img/team/${member.picture}.jpg`" :alt="member.name" />
      <div class="member">
        <h2>{{ member.name }}</h2>
        <div class="mansions">
          <p v-for="(mansion, index) in member.mansions" :key="index">
            {{ mansion }}
          </p>
        </div>
        <div class="socials">
          <span v-for="(social, index) in member.socials" :key="index">
            <span v-if="social.instagram !== null">
              <a :href="social.instagram" target="blank">
                <i class="fab fa-instagram"></i>
              </a>
            </span>
            <span v-if="social.twitter !== null">
              <a :href="social.instagram" target="blank">
                <i class="fab fa-twitter"></i>
              </a>
            </span>
            <span v-if="social.facebook !== null">
              <a :href="social.instagram" target="blank">
                <i class="fab fa-facebook"></i>
              </a>
            </span>
            <span v-if="social.linkedin !== null">
              <a :href="social.instagram" target="blank">
                <i class="fab fa-linkedin"></i>
              </a>
            </span>
            <!-- <span v-for="(linkSocial, index) in social" :key="index">{{linkSocial}}</span> -->
          </span>
        </div>
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
@import '@/style/team.scss';

</style>

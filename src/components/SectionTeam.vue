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
@import '@/style/variables.scss';

.section-team {
  width: 100%;
  margin-bottom: 10px;
  display: flex;
  justify-content: space-between;
  .team {
    width: calc(100% / 4);
    &:hover {
      background: url('/img/pixel-bkg/bkg-pixel-news.png');
      padding: 30px;
    }
    &:hover img {
      display: none;
    }
    &:hover .member {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }
    img {
      width: 100%;
      height: 100%;
      object-fit: contain;
    }
    .member {
      display: none;
      width: 100%;
      height: 100%;
      background-color: $bkg-orange-red;
      color: $text-white;

      h2 {
        text-transform: uppercase;
      }
      .mansions {
        display: flex;

        p {
          padding: 5px;
          color: $text-no-pure-white;
        }
      }
      .socials i {
        padding: 5px;
        font-size: 20px;
      }
    }
  }
}
</style>

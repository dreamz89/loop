<template>
  <div id="team">
    <div class="header">
      <h2>UNSER TEAM</h2>
      <h4>SUBTITLES VON UNSEREM TEAM</h4>
    </div>
    <div class="toggle">
      <h5
        v-for="(state, index) in toggleStates"
        :key="index"
        @click="toggleList(state)"
        :class="{ active: currentState === state }"
      >
        {{ state }}
      </h5>
    </div>
    <div class="sailors">
      <div
        class="sailor"
        v-for="(member, index) in paginatedFilteredList"
        :key="index"
      >
        <img
          :src="require(`@/assets/${member.image}`)"
          :style="{ zIndex: index + 1 }"
        />
        <div class="info" :style="{ zIndex: index }">
          <h4>{{ member.name }}</h4>
          <p>{{ member.duties }}</p>
        </div>
      </div>
    </div>
    <div class="load-more">
      <button
        v-if="filteredTeamDataToShow < filteredTeamData.length"
        @click="filteredTeamDataToShow += 10"
      >
        LOAD MORE
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      teamData: [],
      filteredTeamData: [],
      filteredTeamDataToShow: 10,
      toggleStates: ["Show all", "trim", "tactic", "helmsman"],
      currentState: "Show all",
    };
  },
  mounted() {
    fetch("sailor_team.json")
      .then((response) => response.json())
      .then((data) => {
        this.teamData = data
        this.filteredTeamData = data
      });
  },
  computed: {
    paginatedFilteredList() {
      return this.filteredTeamData.slice(0, this.filteredTeamDataToShow)
    },
  },
  methods: {
    toggleList(state) {
      this.currentState = state
      this.filteredTeamDataToShow = 10

      if (state === "Show all") {
        this.filteredTeamData = this.teamData
      } else {
        this.filteredTeamData = this.teamData.filter((sailor) =>
          sailor.duty_slugs.includes(state)
        )
      }
    },
  },
};
</script>

<style lang="scss" scoped>
#team {
  background-color: $black;
  padding-top: 80px;
  display: flex;
  flex-direction: column;
  align-items: center;

  .header {
    color: $white;
    margin-bottom: 80px;
    max-width: 350px;
    text-align: center;

    h2 {
      line-height: 1;
      margin: 0;
    }

    h4 {
      border-bottom: 1px solid $white;
      margin: 0;
      padding: 18px 12px;
    }
  }

  .toggle {
    display: flex;
    color: $white;
    margin-bottom: 24px;

    h5 {
      cursor: pointer;
      margin: 0 15px;
      padding-bottom: 8px;
      text-transform: capitalize;

      &.active {
        border-bottom: 2px solid $white;
      }
    }
  }

  .sailors {
    display: flex;
    flex-wrap: wrap;
    width: 100%;

    .sailor {
      position: relative;
      cursor: pointer;
      height: 280px;
      width: 280px;

      &:hover {
        & + .sailor {
          visibility: hidden;
        }
        img {
          filter: grayscale(0);
        }
        .info {
          transition: all 0.1s;
          transform: translateX(100%);
        }
      }

      @media (min-width: 901px) and (max-width: $desktop) {
        height: 20vw;
        width: 20vw;
      }

      @media (min-width: 901px) {
        &:nth-child(5n + 5) {
          &:hover {
            & + .sailor {
              visibility: visible;
            }
            img {
              filter: grayscale(0);
            }
            .info {
              transition: all 0.1s;
              transform: translateX(-100%);
            }
          }
        }
      }

      @media (min-width: 751px) and (max-width: 900px) {
        height: 25vw;
        width: 25vw;

        &:nth-child(4n + 4) {
          &:hover {
            & + .sailor {
              visibility: visible;
            }
            img {
              filter: grayscale(0);
            }
            .info {
              transition: all 0.1s;
              transform: translateX(-100%);
            }
          }
        }
      }

      @media (min-width: 551px) and (max-width: 750px) {
        height: 33.3vw;
        width: 33.3vw;

        &:nth-child(3n + 3) {
          &:hover {
            & + .sailor {
              visibility: visible;
            }
            img {
              filter: grayscale(0);
            }
            .info {
              transition: all 0.1s;
              transform: translateX(-100%);
            }
          }
        }
      }

      @media (max-width: 550px) {
        height: 50vw;
        width: 50vw;

        &:nth-child(2n + 2) {
          &:hover {
            & + .sailor {
              visibility: visible;
            }
            img {
              filter: grayscale(0);
            }
            .info {
              transition: all 0.1s;
              transform: translateX(-100%);
            }
          }
        }
      }

      img {
        position: relative;
        height: 100%;
        width: 100%;
        filter: grayscale(1);
        z-index: 1;
      }

      .info {
        background-color: $off-white;
        color: $black;
        padding: 30px;
        height: 100%;
        width: 100%;
        position: absolute;
        top: 0;
        left: 0;
        display: flex;
        flex-direction: column;
        justify-content: flex-end;

        h4 {
          margin: 0 0 16px;
          text-transform: uppercase;

          @media (max-width: 360px) {
            font-size: 0.94rem;
          }
        }

        p {
          margin: 0;
        }
      }
    }
  }

  .load-more {
    @include center;

    background-color: $black;
    height: 160px;

    button {
      background-color: $black;
      border: 2px solid $white;
      color: $white;
      font-weight: bold;
      cursor: pointer;
      padding: 12px 30px;

      &:hover {
        background-color: $white;
        color: $black;
      }
    }
  }
}
</style>
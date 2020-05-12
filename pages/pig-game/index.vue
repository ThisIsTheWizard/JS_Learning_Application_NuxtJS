<template>
  <section id="pig-game">
    <div class="container text-center">
      <b-modal ref="my-modal" hide-footer hide-header>
        <div class="my-flex">
          <h4 class="m-0">There is a winner. Play a new game!!!!</h4>
        </div>
      </b-modal>
      <div class="row wrapper-box">
        <div
          class="col-6 first-player-box"
          :class="{ active: currentPlayer === 0 }"
        >
          <div class="player-name">
            <h1 class="my-flex">
              {{ player_one_points > 100 ? "Winner!!!" : "Player 1" }}
              <div v-if="currentPlayer === 0"></div>
            </h1>
          </div>
          <div class="player-points pb-5">
            <h1 class="display-1">{{ player_one_points }}</h1>
          </div>
          <div class="current-points-box bg-danger w-25 mx-auto">
            <div class="current-points-name"><h4>Current</h4></div>
            <div class="current-points">
              <h1>{{ currentPlayer === 0 ? currentPoints : 0 }}</h1>
            </div>
          </div>
        </div>
        <div
          class="col-6 second-player-box"
          :class="{ active: currentPlayer === 1 }"
        >
          <div class="player-name">
            <h1 class="my-flex">
              {{ player_two_points > 100 ? "Winner!!!" : "Player 2" }}
              <div v-if="currentPlayer === 1"></div>
            </h1>
          </div>
          <div class="player-points pb-5">
            <h1 class="display-1">{{ player_two_points }}</h1>
          </div>
          <div class="current-points-box bg-danger w-25 mx-auto">
            <div class="current-points-name"><h4>Current</h4></div>
            <div class="current-points">
              <h1>{{ currentPlayer === 1 ? currentPoints : 0 }}</h1>
            </div>
          </div>
        </div>
        <div class="new-game-btn">
          <button class="my-btn" @click="makeNewGame">+ New Game</button>
        </div>
        <div class="playing-btns my-flex flex-column">
          <button class="my-btn" @click="rollDice">Roll Dice</button>
          <button class="my-btn" @click="holdDice">Hold</button>
        </div>
        <img
          :src="require(`~/assets/pig-game/${dice}`)"
          alt="Dice"
          class="dice"
          width="120px"
          height="120px"
        />
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      currentPlayer: 0,
      dice: "dice-4.png",
      currentPoints: 0,
      player_one_points: 0,
      player_two_points: 0
    };
  },
  methods: {
    rollDice() {
      if (this.player_one_points < 100 && this.player_two_points < 100) {
        let count = Math.floor(Math.random() * 6) + 1;
        this.dice = "dice-" + count + ".png";
        if (count !== 1) {
          this.currentPoints += count;
        } else {
          this.currentPoints = 0;
          this.currentPlayer === 0
            ? (this.currentPlayer = 1)
            : (this.currentPlayer = 0);
        }
      } else {
        this.$refs["my-modal"].show();
      }
    },
    holdDice() {
      if (this.player_one_points < 100 && this.player_two_points < 100) {
        if (this.currentPlayer === 0) {
          this.player_one_points += this.currentPoints;
          this.currentPoints = 0;
          this.currentPlayer = 1;
        } else {
          this.player_two_points += this.currentPoints;
          this.currentPoints = 0;
          this.currentPlayer = 0;
        }
      } else {
        this.$refs["my-modal"].show();
      }
    },
    makeNewGame() {
      this.currentPlayer = 0;
      this.currentPoints = 0;
      this.player_one_points = 0;
      this.player_two_points = 0;
    }
  }
};
</script>

<style scoped>
.wrapper-box {
  position: relative;
}
.first-player-box,
.second-player-box {
  padding: 8% 0;
  background-color: rgba(0, 255, 255, 1);
}
.active {
  background-color: rgba(0, 190, 190, 1);
}
.player-name div {
  width: 20px;
  height: 20px;
  margin-left: 20px;
  border-radius: 50%;
  background-color: red;
  border: 2px solid #fff;
}
.new-game-btn {
  position: absolute;
  top: 10%;
  left: 50%;
  transform: translate(-50%, -50%);
}
.playing-btns {
  position: absolute;
  bottom: -10%;
  left: 50%;
  transform: translate(-50%, -50%);
}
.dice {
  position: absolute;
  top: 40%;
  left: 50%;
  transform: translate(-50%, -50%);
}
</style>

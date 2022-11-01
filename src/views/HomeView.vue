<template>
  <section>
    <h1>
      SPLI <br />
      TTER
    </h1>
    <div class="container">
      <div class="left">
        <label for="">
          <p>Bill</p>
          <input type="text" placeholder="0" v-model="bill" :maxlength="4" pattern="\d*"/>
        </label>
        <label for="">
          <p>Select Tip %</p>
          <div class="radio-buttons">
            <div class="radiodiv">
              <button
                class="radio-btn"
                value="5"
                @click="(isChecked = true), (tip = 5), totalTip()"
                :class="{ checked: tip === 5 }"
              >
                5%
              </button>
              <button
                class="radio-btn"
                value="10"
                @click="(isChecked = true), (tip = 10)"
                :class="{ checked: tip === 10 }"
              >
                10%
              </button>
              <button
                class="radio-btn"
                value="15"
                @click="(isChecked = true), (tip = 15)"
                :class="{ checked: tip === 15 }"
              >
                15%
              </button>
            </div>

            <div class="radiodiv">
              <button
                class="radio-btn"
                value="25"
                @click="(isChecked = true), (tip = 25)"
                :class="{ checked: tip === 25 }"
              >
                25%
              </button>
              <button
                class="radio-btn"
                value="50"
                @click="(isChecked = true), (tip = 50)"
                :class="{ checked: tip === 50 }"
              >
                50%
              </button>
              <input
                class="radio-btn custom"
                type="text"
                placeholder="Custom"
                v-model="tip"
                :maxlength="3"
                pattern="\d*"
              />
            </div>
          </div>
        </label>
        <label for="">
          <p>Number of People</p>
          <input type="text" placeholder="0" v-model="noOfPeople" @focusin="isDisabled = false" :maxlength="2" pattern="\d*"/>
        </label>
      </div>
      <div class="right">
        <div class="inputs">
          <div class="tippp totals">
            <div class="col">
              <h3>Tip Amount</h3>
              <span>/ person</span>
            </div>
            <p type="text" id="totalinputs">
              ${{ ((bill * tip) / 100 / noOfPeople).toFixed(2) }}
            </p>
          </div>
          <div class="totalpp totals">
            <div class="col">
              <h3>Total</h3>
              <span>/ person</span>
            </div>
            <p type="text" id="totalinputs" @focus="isDisabled = false">
              ${{
                (bill / noOfPeople + (bill * tip) / 100 / noOfPeople).toFixed(2)
              }}
            </p>
          </div>
        </div>
        <button class="reset-btn" :disabled="isDisabled" @click="reset()">
          RESET
        </button>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return this.initialState();
  },
  methods: {
    initialState() {
      return {
        isChecked: false,
        isDisabled: true,
        tip: null,
        bill: null,
        noOfPeople: null,
        
      };
    },
    reset() {
      Object.assign(this.$data, this.initialState());
    },
  },
};
</script>

<style>
section {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  height: 100vh;
  background: var(--lgcyan);
  flex-direction: column;
  gap: 2.5rem;
  font-family: "Space Mono", monospace;
}
h1 {
  letter-spacing: 6px;
  color: var(--dgcyan);
  font-size: 28px;
}
.container {
  background: var(--white);
  border-radius: 26px;
  width: 63rem;
  height: 30rem;
  box-shadow: 0px 0px 30px 0px rgba(0, 0, 0, 0.13);
  display: flex;
  flex-direction: row;
  padding: 2rem;
  justify-content: space-between;
  padding-left: 3rem;
  column-gap: 2rem;
}
.left {
  width: 50%;
  height: 100%;
  display: flex;
  flex-direction: column;
  color: var(--dgcyan);
  font-weight: 700;
  justify-content: space-between;
  padding-bottom: 1rem;
  padding-top: 1rem;
}

.radio-buttons {
  display: flex;
  flex-direction: column;
  row-gap: 1rem;
  
}
.radio-btn {
  font-size: 24px;
  font-weight: 700;
  color: var(--vlgcyan);
  background: var(--vdcyan);
  border: none;
  outline: none;
  border-radius: 5px;
  width: 30%;
  padding-block: 0.4rem;
  transition: .2s cubic-bezier(0.65, 0.05, 0.36, 1) all;
  cursor: pointer;
}
.radiodiv {
  display: flex;
  column-gap: 1rem;
}
.left label {
  display: flex;
  flex-direction: column;
  row-gap: 0.5rem;
}
.left input {
  font-size: 24px;
  border: none;
  outline: none;
  width: 100%;
  background: var(--vlgcyan);
  border-radius: 5px;
  padding: 0.4rem;
  padding-left: 1rem;
  padding-right: 1rem;
  border: 2px solid transparent;
  transition: .2s ease-in-out all;
  text-align: right;
}
.left input:focus{
  border: 2px solid var(--scyan);
}
.checked {
  color: var(--vdcyan);
  background: var(--scyan);
}
.right {
  width: 50%;
  height: 100%;
  background: var(--vdcyan);
  border-radius: 20px;
  padding: 2rem;
  display: flex;
  flex-direction: column;
  row-gap: 2rem;
  justify-content: space-between;
}
.inputs {
  display: flex;
  flex-direction: column;
  row-gap: 2rem;
}
.reset-btn {
  width: 100%;
  border-radius: 6px;
  font-size: 24px;
  font-weight: 700;
  border: none;
  outline: none;
  padding-block: 0.3rem;
}
.reset-btn:enabled {
  color: var(--vdcyan);
  background: var(--scyan);
   cursor: pointer;
}
.reset-btn:disabled {
  filter: opacity(1);
  cursor: not-allowed;
}
.reset-btn:enabled:hover {
  background: var(--lgcyan);
}
.col {
  display: flex;
  flex-direction: column;
}
.col h3 {
  color: var(--white);
}
.col span {
  color: var(--gcyan);
  font-weight: 600;
}
.totals {
  display: flex;
  width: 100%;
  justify-content: space-between;
}
#totalinputs {
  background: var(--vdcyan);
  border: none;
  outline: none;
  color: var(--scyan);
  font-weight: 700;
  font-size: 3rem;
  min-width: 13rem;
  width: fit-content;
  height: fit-content;
  text-align: right;
}
.right input::placeholder {
  color: var(--scyan);
}
.radiodiv input {
  width: 30%;
  color: var(--vdcyan);
}
.custom::placeholder {
  text-align: center;
}
.custom{
  cursor: text;
}

@media only screen and (max-width: 1200px){
    /*Tablets [601px -> 1200px]*/
}
@media only screen and (max-width: 600px){
	/*Big smartphones [426px -> 600px]*/
  section{
    height: fit-content;
    padding-right: 2rem;
    padding-left: 2rem;
    row-gap: 1rem;
    padding-top: 2rem;
    padding-bottom: 3rem;
  }
  .container{
    display: flex;
    flex-direction: column;
    height: fit-content;
    min-width: fit-content;
    width: fit-content;
    padding: 1rem;
    row-gap: 2rem;
  }
  .right{
    width: fit-content;
    padding: 1rem;
  }
  .left{
    width: fit-content;
    padding-top: 0;
    row-gap: 1rem;
    padding: 0.4rem;
  }
  .left label{

  }
  .totals h3{
font-size: 1rem;
white-space: nowrap;
  }
  .totals span{

  }
  #totalinputs{
    font-size: 2rem;
  }
}
@media only screen and (max-width: 425px){
	/*Small smartphones [325px -> 425px]*/
}
</style>

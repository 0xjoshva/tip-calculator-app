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
          <input type="text" placeholder="0" />
        </label>
        <label for="">
          <p>Select Tip%</p>
          <div class="radio-buttons">
            <div class="radiodiv">
              <button
                class="radio-btn"
                value="5"
                @click="(isChecked = true), (tip = 5)"
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
              <button class="radio-btn custom">Custom</button>
            </div>
          </div>
        </label>
        <label for="">
          <p>Number of People</p>
          <input type="text" placeholder="0" />
        </label>
      </div>
      <div class="right">
        <div class="inputs">
        <div class="tippp totals">
          <div class="col">
            <h3>Tip Amount</h3>
            <span>/ person</span>
          </div>
          <input type="text" placeholder="$0.00"/>
        </div>
        <div class="totalpp totals">
          <div class="col">
            <h3>Total</h3>
            <span>/ person</span>
          </div>
          <input type="text" placeholder="$0.00"/>
        </div>
        </div>
        <button class="reset-btn" :disabled="isDisabled">RESET</button>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      tip: 0,
      isChecked: false,
      isDisabled: true,
    };
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
  gap: 4rem;
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
  width: 60rem;
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
  padding: 0.2rem;
  padding-left: 1rem;
  padding-right: 1rem;
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
.inputs{
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
  padding-block: .3rem;
}
.reset-btn:enabled {
  color: var(--vdcyan);
  background: var(--scyan);
}
.reset-btn:disabled {
  filter: opacity(0.4);
}
.reset-btn:enabled:hover {
  background: var(--lgcyan);
}
.col{
  display: flex;
  flex-direction: column;
}
.col h3{
  color: var(--white);
}
.col span{
  color: var(--gcyan);
  font-weight: 600;
}
.totals{
  display: flex; 
  width: 100%;
  justify-content: space-between;
  
}
.right input{
  background: var(--vdcyan);
  border: none;
  outline: none;
color: var(--scyan);
 font-weight: 700;
 font-size: 3rem;
 width: 10rem;
 height: fit-content;
}
.right input::placeholder{
  color: var(--scyan);
 

}
</style>

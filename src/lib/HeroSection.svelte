<script>
  const excercises = [
    {
      src: "https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fmedia1.popsugar-assets.com%2Ffiles%2Fthumbor%2FFdPuG8MoN3_6fMdBocPWsOE2G9I%2Ffit-in%2F1024x1024%2Ffilters%3Aformat_auto-!!-%3Astrip_icc-!!-%2F2016%2F10%2F31%2F575%2Fn%2F1922729%2F9e74794a58173dbd288a92.94471248_Push-Up%2Fi%2FPush-Ups.jpg&f=1&nofb=1",
      name: "push ups",
      check: false,
    },
    {
      src: "https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Ffthmb.tqn.com%2FMC79jiV0M-zVvbIXV3SGmxmmINQ%3D%2F2122x1415%2Ffilters%3Afill(FFDB5D%2C1)%2FGettyImages-534699027-5707ff223df78c7d9ea73de0.jpg&f=1&nofb=1",
      name: "abs",
      check: false,
    },
    {
      src: "https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fbloximages.chicago2.vip.townnews.com%2Fcolumbustelegram.com%2Fcontent%2Ftncms%2Fassets%2Fv3%2Feditorial%2F4%2Fde%2F4de6180d-3f57-5468-99d0-702367596464%2F598e95a4e1fc1.image.jpg%3Fresize%3D1200%252C1200&f=1&nofb=1",
      name: "squats",
      check: false,
    },
    {
      src: "https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fi0.wp.com%2Fwww.getfitwithcedar.com%2Fwp-content%2Fuploads%2F2020%2F01%2FGoblet-squat-2.png%3Fw%3D940%26ssl%3D1&f=1&nofb=1",
      name: "legs",
      check: false,
    },
  ];
  let started = false;
  let currentExcercise = 0;
  let counterSet = 0;
  let setComplete = false;
  let numberReps = 3;

  // functions
  function setFinish() {
    counterSet++;
    if (counterSet >= numberReps) {
      counterSet = 0;
      setComplete = true;
    }
  }

  $: if (setComplete) {
    currentExcercise++;
    setComplete = false;
    if (currentExcercise >= excercises.length) {
      started = false;
    }
  }
</script>

<div>
  {#if !started && currentExcercise > 0}
    <div class="center normal">
      <h1>Good Job</h1>
    </div>
  {:else if !started}
    <div class="center normal">
      <button on:click={() => (started = !started)}>Start workout</button>
    </div>
  {:else}
    <div class="card normal">
      <p class="title">{excercises[currentExcercise].name}</p>
      <img src={excercises[currentExcercise].src} alt="" width="250px" />
      <div class="buttons">
        <button on:click={setFinish}>{counterSet} of {numberReps}</button>
      </div>
    </div>
  {/if}
</div>

<style scoped>
  @import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300&display=swap");
  .normal {
    font-family: "Poppins", sans-serif;
  }
  div {
    display: flex;
    flex-wrap: wrap;
  }
  .card {
    display: grid;
    margin: 1rem;
    padding: 1rem;
    border: 1px solid #928374;
    border-radius: 10px;
    justify-content: center;
    align-items: center;
    justify-items: center;
    height: 70vh;
    width: 100vw;
    font-family: "Open Sans", sans-serif;
  }
  button {
    outline: none;
    background-color: white;
    font-size: 17px;
    border: 1px solid #928374;
    padding: 1rem;
    border-radius: 10px;
    margin: 0.5rem;
    cursor: pointer;
  }
  .buttons {
    display: grid;
  }
  p {
    text-transform: capitalize;
    font-size: 27px;
  }
  .center {
    width: 100vw;
    height: 70vh;
    display: flex;
    justify-content: center;
    align-items: center;
  }
</style>

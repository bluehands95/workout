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

  function check(obj) {
    obj.check = !obj.check;
  }
</script>

<div>
  {#each excercises as ex}
    <div class="card">
      <p>{ex.name}</p>
      <img src={ex.src} alt="a" width="200px" />
      <div class="buttons">
        <button on:click={() => (ex.check = !ex.check)}>First set</button>
        <button on:click={() => (ex.check = !ex.check)}>Second set</button>
        <button on:click={() => (ex.check = !ex.check)}>Third set</button>
      </div>
    </div>
  {/each}
</div>

<style scoped>
  @import url("https://fonts.googleapis.com/css2?family=Roboto&display=swap");
  p {
    font-size: 20px;
    text-transform: capitalize;
    font-family: "Roboto", sans-serif;
    font-weight: 100;
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
</style>

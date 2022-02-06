<template>
  <div class="info">
    <div>
      <div class="title">Lore</div>
      <p>
        Nel infinità del multiverso, c'è una piccola realtà in una manciata di
        pixel in cui <strong>Simone Massaro</strong> deve correre per il resto
        della sua vita.
      </p>
      <p>
        Perché? Non lo so, non ci ho ancora pensato, ma presto ci inventeremo un
        motivo più o meno plausibile.
      </p>
    </div>
    <div>
      <div class="title">Comandi</div>
      <p>È un gioco per scimmie, non ci sono molti tasti da poter premere...</p>
      <p>
        Usa la <strong>barra spaziatrice</strong> per <strong>saltare</strong>!
      </p>
      <div class="spacebar">SPACE</div>
    </div>
    <div>
      <div class="title">Credits</div>
      <p>
        Questo incredibile giochino è stato realizzato da
        <a href="https://github.com/MilanStojko" target="_blank"
          >Milan Stojkovic</a
        >
        e
        <a href="https://github.com/matteopompei" target="_blank"
          >Matteo Pompei</a
        >.
      </p>
      <p>
        Il progetto è open source e potete trovarlo
        <a href="https://github.com/MilanStojko/massaro-runner" target="_blank"
          >qui</a
        >.
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Info",
};
</script>

<style lang="scss" scoped>
.info {
  display: flex;
  margin: 300px 10px 10px 10px;
  padding: 50px;
  font-size: 1.5rem;
  letter-spacing: 1px;

  & > div {
    padding: 50px 100px;
    min-height: 300px;
    width: 50%;
    border-right: 3px solid #fff;
  }

  & > div:last-child {
    border: none;
  }

  .title {
    margin-bottom: 30px;
    padding: 0 50px 5px 0;
    width: fit-content;
    border-bottom: 3px solid #fff;
    font-size: 3rem;
    font-weight: bold;
    letter-spacing: 10px;
  }

  .spacebar {
    margin: 50px auto;
    padding: 10px 100px;
    width: fit-content;
    border: 3px solid #fff;
    border-radius: 10px;
    text-align: center;
    letter-spacing: 10px;
  }

  p {
    margin: 10px 0;
  }

  a {
    font-weight: bold;
    color: inherit;

    &:hover {
      text-decoration: none;
    }
  }
}
</style>

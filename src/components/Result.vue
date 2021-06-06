<template>
  <div>
        <h3>Your score is {{score}}ms</h3>
        <div class="card">
            <div v-if="score<30">
                <h4>You are god.No one can act like You!!! &#128525;</h4>
            </div>
            <div v-else-if="score>=30 && score<=100">
                <h4>Hey NOOB!!!You are slow man!!! &#128517;</h4>
            </div>
            <div v-else>
                <h4>Extra NOOB!!!<br>You are <b>SLOWEST</b> human in the world &#128514;</h4>
            </div>
        </div>
  </div>
</template>

<script>
export default {
    props:['score'],
}
</script>

<style>
.card {
/* Add shadows to create the "card" effect */
    width: 350px;
    /* height: 70px; */
    box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
    transition: 0.3s;
    margin: 0 auto;
    background-color: white;
    border-radius: 10px;
    padding: 10px;
}

/* On mouse-over, add a deeper shadow */
.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2);
}

</style>
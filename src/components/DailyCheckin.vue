<template>
    <div class="vue-tempalte">
        <form>
            <h3>Daily Check-In</h3>

            <div class="form-group">
                <label>Hey, how are ya feeling?</label>
                <div>
                  <textarea v-model="feels_entry" id="feel_input" placeholder="Write down some of your thoughts and emotions...">
                  </textarea>
                </div>
            </div>

            <div class="form group">
              <label>Rate your mood on a scale of 1-10</label>
              <div class="slider-container">
                <vue-range-slider v-model="checkin_rating" :min="min" :max="max" :formatter="formatter"></vue-range-slider>
              </div>
            </div>

            <div class="form-group">
                <label>Any goals for today?</label>
                <textarea  v-model="goals_entry" id="goal_input" name="dc_goals" placeholder="Write down anything you want to achieve today, big or small...">
                </textarea>
            </div>

            <div class="form-group">
                <label>Any thing else you want to mention?</label>
                <textarea v-model="misc_entry" id="misc_input" name="dc_misc" placeholder="Write down whatever else you want to make not of...">
                </textarea>
            </div>

            <div class="form-group">
              <router-link :to="{name: 'success'}"><button v-on:click="submitCheckin" type="submit" class="btn btn-dark btn-lg btn-block" id= "dc_submit">Submit</button></router-link>
            </div>

        </form>
        <div>
          <p>{{ checkin_rating }}</p>
          <p>{{ feels_entry }}</p>
          <p>{{ goals_entry }}</p>
          <p>{{ misc_entry }}</p>
        </div>

        <footer class="text-center text-lg-start bg-light text-muted">
          <div class="btn-group" role="group" id="dc_footer">
            <button type="button" class="btn btn-secondary" disabled>
              <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-heart" viewBox="0 0 16 16">
  <path d="m8 2.748-.717-.737C5.6.281 2.514.878 1.4 3.053c-.523 1.023-.641 2.5.314 4.385.92 1.815 2.834 3.989 6.286 6.357 3.452-2.368 5.365-4.542 6.286-6.357.955-1.886.838-3.362.314-4.385C13.486.878 10.4.28 8.717 2.01L8 2.748zM8 15C-7.333 4.868 3.279-3.04 7.824 1.143c.06.055.119.112.176.171a3.12 3.12 0 0 1 .176-.17C12.72-3.042 23.333 4.867 8 15z"/>
</svg>
              <div>Wellness</div>
            </button>
            <button type="button" class="btn btn-secondary">
              <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-journal-bookmark" viewBox="0 0 16 16">
  <path fill-rule="evenodd" d="M6 8V1h1v6.117L8.743 6.07a.5.5 0 0 1 .514 0L11 7.117V1h1v7a.5.5 0 0 1-.757.429L9 7.083 6.757 8.43A.5.5 0 0 1 6 8z"/>
  <path d="M3 0h10a2 2 0 0 1 2 2v12a2 2 0 0 1-2 2H3a2 2 0 0 1-2-2v-1h1v1a1 1 0 0 0 1 1h10a1 1 0 0 0 1-1V2a1 1 0 0 0-1-1H3a1 1 0 0 0-1 1v1H1V2a2 2 0 0 1 2-2z"/>
  <path d="M1 5v-.5a.5.5 0 0 1 1 0V5h.5a.5.5 0 0 1 0 1h-2a.5.5 0 0 1 0-1H1zm0 3v-.5a.5.5 0 0 1 1 0V8h.5a.5.5 0 0 1 0 1h-2a.5.5 0 0 1 0-1H1zm0 3v-.5a.5.5 0 0 1 1 0v.5h.5a.5.5 0 0 1 0 1h-2a.5.5 0 0 1 0-1H1z"/>
</svg>
              <div>Diary</div>
            </button>
          </div>
        </footer>
    </div>
</template>

<script>
import 'vue-range-component/dist/vue-range-slider.css'
import VueRangeSlider from 'vue-range-component'

export default {
  data() {
    return {
      feels_entry: '',
      goals_entry: '',
      misc_entry:  '',
      checkin_rating: 5,
    }
  },
  components: {
    VueRangeSlider,
  },
  methods: {
    submitCheckin(){
        console.log("PENIS");
    },
  },
  created() {
    this.min = 1
    this.max = 10
    this.formatter = checkin_rating => `${checkin_rating}`
  }
}
</script>

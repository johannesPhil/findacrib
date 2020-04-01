<template>
  <b-container fluid>
    <b-row class="text-center" id="hero">
      <Navigation />
      <b-row no-gutters align-h="center" id="frost-wrap">
        <b-col cols="10" id="frost">
          <b-row>
            <b-col class="hero-content">
              <h1>Looking for somewhere to stay?</h1>
            </b-col>
          </b-row>
          <b-row>
            <b-col class="hero-content">
              <b-row no-gutters align-h="center">
                <b-form-row>
                  <b-col sm class="search-item">
                    <b-form-select>
                      <option value>Apartment Type</option>
                      <option value>1 Bedroom</option>
                      <option value>2 Bedroom</option>
                      <option value>3 Bedroom</option>
                    </b-form-select>
                  </b-col>
                  <b-col sm class="search-item">
                    <b-form-select v-model="apartment" :options="type">
                      <option value>Apartment Type</option>
                      <option value>1 Bedroom</option>
                      <option value>2 Bedroom</option>
                      <option value>3 Bedroom</option>
                    </b-form-select>
                  </b-col>
                  <b-col sm class="search-item">
                    <b-button variant="info">Find</b-button>
                  </b-col>
                </b-form-row>
              </b-row>
            </b-col>
          </b-row>
        </b-col>
      </b-row>
    </b-row>
    <b-row align-h="center" class="property-container">
      <b-col cols="12">
        <h2>Top Apartment Listings</h2>
        <hr />
      </b-col>
      <b-col cols="11">
        <b-row class="flex-row-container">
          <!-- <b-col cols="none" sm="" offset="1" class="card-container">
            <b-row>
             <b-col cols="12" class="front-card no-padding">
              <b-col cols="12" class="card-image-container no-padding">
                <img src="../static/hero.jpg" alt class="card-image" />
              </b-col>
              <b-col class="card-desc no-padding">
                <b-col cols="12" class="card-desc-title no-padding">
                  <p class="card-p">Bunk Space</p>
                </b-col>
                <hr />
                <b-col cols="12" class="card-desc-location no-padding">
                  <p class="card-p">Location: Agbowo</p>
                </b-col>
                <b-col cols="12" class="card-desc-cost no-padding">
                  <p class="card-p">&#x20a6;95,000</p>
                </b-col>
                <b-col cols="12" class="card-desc-space no-padding">
                  <p class="card-p">Available Space</p>
                </b-col>
              </b-col>
            </b-col>
            </b-row>
            <b-row class="card-back no-padding">
              <b-col cols="12" class="desc-container">
                <b-row>
                  <b-col cols="12">
                    <p class="card-p">Bunk Space</p>
                    <hr>
                  </b-col>
                </b-row>
                <b-row>
                <b-col cols="12" class="full-desc">
                  <p class="card-p">
                    Lorem ipsum dolor, sit amet consectetur adipisicing elit.Ut consequatur itaque corrupti nesciunt, provident explicabo maiores reprehenderitbeatae ducimus fugiat corporis accusamus dolore quaerat neque inventore odit quidem facere. Suscipit?
                  </p>
                </b-col>
                <b-col class="infra flex-column-container">
                <span>Toilet</span>
                <span>Running Water</span>
              </b-col>
              </b-row>
              </b-col>
              <hr>
            </b-row>
          </b-col>
          <b-col cols="none" sm="" offset="1" class="card-container">
            <b-row>
             <b-col cols="12" class="front-card no-padding">
              <b-col cols="12" class="card-image-container no-padding">
                <img src="../static/hero.jpg" alt class="card-image" />
              </b-col>
              <b-col class="card-desc no-padding">
                <b-col cols="12" class="card-desc-title no-padding">
                  <p class="card-p">Bunk Space</p>
                </b-col>
                <hr />
                <b-col cols="12" class="card-desc-location no-padding">
                  <p class="card-p">Location: Agbowo</p>
                </b-col>
                <b-col cols="12" class="card-desc-cost no-padding">
                  <p class="card-p">&#x20a6;95,000</p>
                </b-col>
                <b-col cols="12" class="card-desc-space no-padding">
                  <p class="card-p">Available Space</p>
                </b-col>
              </b-col>
            </b-col>
            </b-row>
            <b-row class="card-back no-padding">
              <b-col cols="12" class="desc-container">
                <b-row>
                  <b-col cols="12">
                    <p class="card-p">Bunk Space</p>
                    <hr>
                  </b-col>
                </b-row>
                <b-row>
                <b-col cols="12" sm="" class="full-desc">
                  <p class="card-p">
                    Lorem ipsum dolor, sit amet consectetur adipisicing elit.Ut consequatur itaque corrupti nesciunt, provident explicabo maiores reprehenderitbeatae ducimus fugiat corporis accusamus dolore quaerat neque inventore odit quidem facere. Suscipit?
                  </p>
                </b-col>
                <b-col class="infra flex-column-container">
                <span>Toilet</span>
                <span>Running Water</span>
              </b-col>
              </b-row>
              </b-col>
              <hr>
            </b-row>
          </b-col>
          <b-col cols="none" sm="" offset="1" class="card-container">
            <b-row>
             <b-col cols="12" class="front-card no-padding">
              <b-col cols="12" class="card-image-container no-padding">
                <img src="../static/hero.jpg" alt class="card-image" />
              </b-col>
              <b-col class="card-desc no-padding">
                <b-col cols="12" class="card-desc-title no-padding">
                  <p class="card-p">Bunk Space</p>
                </b-col>
                <hr />
                <b-col cols="12" class="card-desc-location no-padding">
                  <p class="card-p">Location: Agbowo</p>
                </b-col>
                <b-col cols="12" class="card-desc-cost no-padding">
                  <p class="card-p">&#x20a6;95,000</p>
                </b-col>
                <b-col cols="12" class="card-desc-space no-padding">
                  <p class="card-p">Available Space</p>
                </b-col>
              </b-col>
            </b-col>
            </b-row>
            <b-row class="card-back no-padding">
              <b-col cols="12" class="desc-container">
                <b-row>
                  <b-col cols="12">
                    <p class="card-p">Bunk Space</p>
                    <hr>
                  </b-col>
                </b-row>
                <b-row>
                <b-col cols="12" class="full-desc">
                  <p class="card-p">
                    Lorem ipsum dolor, sit amet consectetur adipisicing elit.Ut consequatur itaque corrupti nesciunt, provident explicabo maiores reprehenderitbeatae ducimus fugiat corporis accusamus dolore quaerat neque inventore odit quidem facere. Suscipit?
                  </p>
                </b-col>
                <b-col class="infra flex-column-container">
                <span>Toilet</span>
                <span>Running Water</span>
              </b-col>
              </b-row>
              </b-col>
              <hr>
            </b-row>
          </b-col>
          <b-col cols="none" sm="" offset="1" class="card-container">
            <b-row>
             <b-col cols="12" class="front-card no-padding">
              <b-col cols="12" class="card-image-container no-padding">
                <img src="../static/hero.jpg" alt class="card-image" />
              </b-col>
              <b-col class="card-desc no-padding">
                <b-col cols="12" class="card-desc-title no-padding">
                  <p class="card-p">Bunk Space</p>
                </b-col>
                <hr />
                <b-col cols="12" class="card-desc-location no-padding">
                  <p class="card-p">Location: Agbowo</p>
                </b-col>
                <b-col cols="12" class="card-desc-cost no-padding">
                  <p class="card-p">&#x20a6;95,000</p>
                </b-col>
                <b-col cols="12" class="card-desc-space no-padding">
                  <p class="card-p">Available Space</p>
                </b-col>
              </b-col>
            </b-col>
            </b-row>
            <b-row class="card-back no-padding">
              <b-col cols="12" class="desc-container">
                <b-row>
                  <b-col cols="12">
                    <p class="card-p">Bunk Space</p>
                    <hr>
                  </b-col>
                </b-row>
                <b-row>
                <b-col cols="12" class="full-desc">
                  <p class="card-p">
                    Lorem ipsum dolor, sit amet consectetur adipisicing elit.Ut consequatur itaque corrupti nesciunt, provident explicabo maiores reprehenderitbeatae ducimus fugiat corporis accusamus dolore quaerat neque inventore odit quidem facere. Suscipit?
                  </p>
                </b-col>
                <b-col class="infra flex-column-container">
                <span>Toilet</span>
                <span>Running Water</span>
              </b-col>
              </b-row>
              </b-col>
              <hr>
            </b-row>
          </b-col>-->
          <div class="card-container">
            <div class="card-inner">
              <div class="card-front">
                <div class="card-image-container">
                  <img src="../static/hero.jpg" alt class="card-image" />
                </div>
                <div class="card-desc">
                  <div class="card-desc-title">
                    <p class="card-p">Bunk Space</p>
                  </div>
                  <hr />
                  <div class="desc-detail">
                    <div class="card-desc-location inline-desc">
                      <fa :icon="['fas', 'map-marker-alt']" />&nbsp;&nbsp;&nbsp;Agbowo
                    </div>
                    <div class="card-desc-cost inline-desc">&#x20A6;95,000/year</div>
                    <div class="card-desc-cost inline-desc" title>
                      <fa :icon="['fas', 'calendar-alt']" />&nbsp;&nbsp;&nbsp;12/3/20
                    </div>
                  </div>
                  <div class="card-action">
                    <button type="submit" class="card-button">View Details</button>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="card-container">
            <div class="card-inner">
              <div class="card-front">
                <div class="card-image-container">
                  <img src="../static/hero.jpg" alt class="card-image" />
                </div>
                <div class="card-desc">
                  <div class="card-desc-title">
                    <p class="card-p">Bunk Space</p>
                  </div>
                  <hr />
                  <div class="desc-detail">
                    <div class="card-desc-location inline-desc">
                      <fa :icon="['fas', 'map-marker-alt']" />&nbsp;&nbsp;&nbsp;Agbowo
                    </div>
                    <div class="card-desc-cost inline-desc">&#x20A6;95,000/year</div>
                    <div class="card-desc-cost inline-desc">
                      <fa :icon="['fas', 'calendar-alt']" />&nbsp;&nbsp;&nbsp;12/3/20
                    </div>
                  </div>
                  <div class="card-action">
                    <button type="submit" class="card-button">View Details</button>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="card-container">
            <div class="card-inner">
              <div class="card-front">
                <div class="card-image-container">
                  <img src="../static/hero.jpg" alt class="card-image" />
                </div>
                <div class="card-desc">
                  <div class="card-desc-title">
                    <p class="card-p">Bunk Space</p>
                  </div>
                  <hr />
                  <div class="desc-detail">
                    <div class="card-desc-location inline-desc">
                      <fa :icon="['fas', 'map-marker-alt']" />&nbsp;&nbsp;&nbsp;Agbowo
                    </div>
                    <div class="card-desc-cost inline-desc">&#x20A6;95,000/year</div>
                    <div class="card-desc-cost inline-desc">
                      <fa :icon="['fas', 'calendar-alt']" />&nbsp;&nbsp;&nbsp;12/3/20
                    </div>
                  </div>
                  <div class="card-action">
                    <button type="submit" class="card-button">View Details</button>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="card-container">
            <div class="card-inner">
              <div class="card-front">
                <div class="card-image-container">
                  <img src="../static/hero.jpg" alt class="card-image" />
                </div>
                <div class="card-desc">
                  <div class="card-desc-title">
                    <p class="card-p">Bunk Space</p>
                  </div>
                  <hr />
                  <div class="desc-detail">
                    <div class="card-desc-location inline-desc">
                      <fa :icon="['fas', 'map-marker-alt']" />&nbsp;&nbsp;&nbsp;Agbowo
                    </div>
                    <div class="card-desc-cost inline-desc">&#x20A6;95,000/year</div>
                    <div class="card-desc-cost inline-desc">
                      <fa :icon="['fas', 'calendar-alt']" />&nbsp;&nbsp;&nbsp;12/3/20
                    </div>
                  </div>
                  <div class="card-action">
                    <button type="submit" class="card-button">View Details</button>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </b-row>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
import Navigation from '../components/Navigation'
export default {
  components: {
    Navigation
  }
}
</script>

<style scoped>
body {
  /* font-family: "Rubik", sans-serif;
  font-family: 'Oswald', sans-serif; */
  font-family: "Fira Sans", sans-serif;
  background-color: #f5f9fc;
}
.no-padding {
  padding: 0;
}
.col {
  padding: 0;
}
#hero {
  position: relative;
  min-height: 600px;
  background-image: url("../static/hero.jpg");
  background-position: center;
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-size: cover;
  color: #ffffff;
}
#frost-wrap{
  width: 100%;
}
#frost {
  position: relative;
  height: fit-content;
  padding: 20px;
  height: fit-content;
  width: 100%;
  background: inherit;
  overflow: hidden;
}
#frost::before {
  content: "";
  background: inherit;
  position: absolute;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
  box-shadow: inset 0 0 0 3000px rgba(255, 255, 255, 0.3);
  filter: blur(8px);
}
.hero-content {
  height: fit-content;
}

.form-row{
  width: 100%;
}
.custom-select,
.btn {
  height: 3rem;
  margin: 1rem 0;
}
.custom-select {
  color: rgba(24, 40, 72, 0.5);
}
.btn {
  width: 100%;
  background-color: #3b2461;
  border: transparent;
  color: #ffffff;
}
.btn:hover {
  color: #3b2461;
  background: #fff;
}
#full-col-width .col-12 {
  margin: 0;
  padding: 15px;
}

.property-container {
  padding: 3rem 1rem;
}

.flex-row-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  /* font-family: 'Rubik', sans-serif;
  font-family: 'Fira Sans', sans-serif;
  font-family: 'Oswald', sans-serif; */
}
.card-container {
  flex: 2 0 250px;
  height: auto;
  overflow: auto;
  margin: 1rem;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  border-radius: 8px;
  border: 1px solid #f1f1f1;
  background-color: #fff;
  text-align: left;
}
.card-container:hover {
  box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
}
.card-image-container {
  width: 100%;
  height: 300px;
}
.card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  text-align: center;
  transition: transform 0.8s;
  transform-style: preserve-3d;
}
/* .card-container:hover .card-inner {
  transform: rotateY(180deg);
} */
.card-front,
.card-back {
  width: 100%;
  height: 100%;
  -webkit-backface-visibility: hidden; /* Safari */
  -moz-backface-visibility: hidden;
  -o-backface-visibility: hidden;
  backface-visibility: hidden;
}
.card-back {
  background-color: white;
  transform: rotateY(180deg);
}
.card-image {
  width: 100%;
  height: 100%;
  border-top-left-radius: 6px;
  border-top-right-radius: 6px;
}
.card-desc {
  padding: 0.5rem;
  text-align: left;
}
.card-p {
  margin: 0;
}
hr {
  margin: 0;
}
.desc-detail {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-between;
}
.inline-desc {
  min-width: 40%;
  padding: 0.3rem;
  margin: 0.5rem 0;
  display: block;
  background-color: rgb(28, 197, 223);
  border-radius: 20px;
  text-align: center;
  color: #fff;
}
.card-action {
  width: 100%;
  text-align: center;
}
.card-button {
  border: transparent;
  background-color: #44c482;
  color: #fff;
  border-radius: 40px;
  margin-top: 1rem;
  padding: 0.5rem 1rem;
}
</style>

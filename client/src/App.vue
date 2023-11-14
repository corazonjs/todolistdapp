<template>
  <div v-if="isDrizzleInitialized" id="app">
    <div>
      <b-navbar type="info" variant="info" sticky>
        <div class="container">
        
          <b-navbar-brand href="#">
            ToDo List DApp
          </b-navbar-brand>

          <!-- <b-navbar-nav>
            <b-nav-item href="#">Home</b-nav-item>
          </b-navbar-nav> -->

          <b-navbar-nav>
            <b-nav-item href="#" disabled>
                Your account:<br>: 
            </b-nav-item>
            <b-nav-item href="#" disabled>
                <drizzle-contract contractName="Todos" method="PUNISHMENT_TIME" />
            </b-nav-item>
            <b-nav-item href="#" disabled>
              <drizzle-account units="Ether" :precision="3" />
            </b-nav-item>
          </b-navbar-nav>

        </div>
      </b-navbar>
    </div>

    <div class="container py-3 my-4">

      <div class="row">
        <div class="col-lg-8 col-md-12">
          <h3>Add a Task</h3>
          <AddTaskForm />
        </div>
        <div class="col-lg-1 col-md-12"></div>
        <div class="col-lg-3 col-md-12 bg-info bg-gradient text-light rounded-3 p-2">
          <h3>Claim Prize </h3>
          <Prizes />
        </div>
      </div>

      <div class="row">
        <div class="col-sm-12">
          <h3>Todos</h3>
          <Tasks />
        </div>
      </div>

    </div>

  </div>

  <div v-else>
    <p>Loading...</p>
    <p>Is <a href="https://metamask.io/" target="_blank">MetaMask</a> extension installed on your browser?</p>
    <p>Is proper network selected in MetaMask? (Localhost on port 8545)</p>
  </div>
</template>

<script>
import Tasks from './Tasks'
import Prizes from './Prizes'
import AddTaskForm from './AddTaskForm'
import { mapGetters } from 'vuex'

export default {
  name: 'app',
  components: {
    Tasks,
    Prizes,
    AddTaskForm,
  },

  computed: mapGetters('drizzle', ['isDrizzleInitialized'])
}
</script>

<style>
/* #app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */
.b-divider {
  height: 3rem;
  background-color: rgba(255, 255, 255, 0.1);
  border: solid rgba(0, 0, 0, .15);
  border-width: 1px 0;
  box-shadow: inset 0 .5em 1.5em rgba(0, 0, 0, .1), inset 0 .125em .5em rgba(0, 0, 0, .15);
}
</style>
<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link> |
      <router-link to="/list">List</router-link> |
      <router-link to="/drawer">Drawer</router-link> |
      <router-link to="/cards">Cards</router-link> |
      <router-link to="/simple">Simple</router-link> |
      <router-link to="/stagger">Stagger</router-link> |
      <router-link to="/state">State</router-link> |
      <router-link to="/timeline">Timeline</router-link> |
      <router-link to="/master">Master</router-link>
    </div>
    <transition name="slide-fade" mode="out-in">
      <router-view />
    </transition>  
  </div>
</template>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

button {
  width: 8em;
  height: 2em;
  margin: 0.5em;
  border-radius: 5px;
  background: linear-gradient(to right, #16c0b0, #84cf6a);
  font-size: 1em;
  color: white;
  border: none;
  outline: none;
  cursor: pointer;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}

.modal {
  width: 250px;
  height: 200px;
  padding: 10px;
  margin: 0 auto;
  margin-top: 20px;
  border-radius: 2%;
  background-color: #e0e0e0;
}

/* TRANSITIONS */
.fade-enter { 
  /* starting-style */
  opacity: 0;
}

.fade-enter-active, .fade-leave-active { 
  /* entering-style and leaving-style */
  transition: opacity 0.5s ease-out;
}

.fade-leave-to {
  /* ending-style */
  opacity: 0;
}

/* TRANSITIONS: SLIDE-FADE */
.slide-fade-enter { 
  transform: translateX(10px);
  opacity: 0;
}

.slide-fade-enter-active, .slide-fade-leave-active { 
  /* entering-style and leaving-style */
  transition: all 0.5s ease;
}

.slide-fade-leave-to {
  transform: translateX(-10px);
  opacity: 0;
}

/* TRANSITION-GROUP: SLIDE-UP */
.slide-up-enter { 
  transform: translateY(10px); 
  opacity: 0;
}

.slide-up-enter-active { 
  /* entering-style and leaving-style */
  transition: all 0.5s ease;
}

.slide-up-move { 
  /* v-move */
  transition: transform 0.8s ease-in;
}
</style>

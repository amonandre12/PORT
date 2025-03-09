
<script setup>
import { ref } from "vue";
import NavBar from './NavBar.vue';

const menuOpen = ref(false); 
const toggleMenu = () => {
  menuOpen.value = !menuOpen.value;
};
const closeMenu = () => {
  menuOpen.value = !menuOpen.value;
}
</script>

<template>
  <NavBar class="heard-link">

    <NavBar class="logo">
      <img src="@/assets/logo.jpg" alt="Logo" />
    </NavBar>

    <button class="btn-menu" @click="toggleMenu">
      <box-icon name='menu'></box-icon>
    </button>

    <nav :class="{ 'menu-open': menuOpen }" class="nav">
      <img src="@/assets/logo.jpg" alt="Logo" />
      <box-icon name='x' class="croix" @click="closeMenu"></box-icon>
      <NavBar><a href="#">Accueil</a></NavBar>
      <NavBar><a href="#"> À propos</a></NavBar>
      <NavBar><a href="#">Projets</a></NavBar>
      <NavBar><a href="#">Contact</a></NavBar>
    </nav>
</NavBar>
</template>

<style scoped>

.heard-link {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px 20px;
  color: #fff;
  width: 100%;
  align-items: center;
  justify-content: space-between;
  padding: 10px 20px;
  box-shadow: 0 4px 6px rgba(7, 3, 3, 0.1);
  background-color: #fff;
}
.nav img {
  display:none;
}
.croix {
  display:none;
}
.logo img {
  margin-left: 30px;
  width:100%;
  border-radius: 50%;
  height: 50px;
  cursor: pointer;
}
.logo img:hover {
  transform: scale(1.1);
  transition: transform 0.3s ease-in-out;
}
.btn-menu {
  font-size: 20px;
  background: none;
  border: none;
  cursor: pointer;
  display: none;
  color: white;
}
box-icon {
  position:relative;
  top:5px;
}

.nav a {
  color: black;
  text-decoration: none;
  font-size: 18px;
  transition: color 0.3s;

}

.nav a:hover {
  color: #00bcd4;
}
.nav {
  display: flex;
  gap: 25px;
  position: absolute;
  right: 15%;
}

.nav a {
  text-decoration: none;
  font-weight: bold;
  color: black;
}

/* .nav a:hover { */
  /* background-color: #D4D3DC; */
  /* opacity: 0.7; */
/* } */

/* Styles spécifiques pour mobile */
@media (max-width: 769px) {
  .btn-menu {
    display: block;
    position: relative;
    left: 1%;
  }
  
  button {
    position:relative;
    bottom:3px;
  }
  .nav {
    display: none;
    flex-direction: column;
    position: absolute;
    gap: 50px;
    top: 0px;
    text-align: center;
    width: 100%;
    background: white;
    padding: 15px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    padding-bottom: 130px;
    z-index: 1000;
    right: 0px;
    max-width: 100%;
  }
  
.nav img {
  display:block;
  position:relative;
  
  /* max-height: 70px; */
  width: 150px;
  border-radius: 50%;
  height: 100px;
  cursor: pointer;
  /* left:10px; */
  /* bottom:10px; */
}
.croix {
  display:block;
  position: absolute;
  right: 10px;
  top:  60px;
}

.nav a {
  font-size: 1.4rem;
  padding: 6px 130px 6px 130px ;
  border: 1px solid #0d9488;
  text-align: center;
  position: relative;
  top: 5px;
}
  .menu-open {
    display: flex;
  }

}
</style>
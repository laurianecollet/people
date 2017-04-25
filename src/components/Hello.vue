<template>
  <div>
    <!--Il doit y avoir un element parent pour tous les autres sinon erreur, on est pas obligé de renseigner la class-->
    <navbar :title="title"></navbar>
    <breadscrumbs></breadscrumbs>
    <div class="container">
      <liste></liste>
    </div>
    <footerapp :titleFooter="titleFooter"></footerapp>
  </div>
</template>

<script>
  import Navbar from './Navbar' // j'importe le composant qui s'appelle Nav par défaut depuis le fichier Nav.vue
  import FooterApp from './FooterApp' // Si on met @/ ca part de src
  import Breadscrumbs from './Breadscrumbs'
  import Liste from './Liste.vue'
  export default { // Ca sera toujours export default et un objet 
    name: 'hello', // identifiant au composant 
    components: { navbar: Navbar, footerapp: FooterApp, breadscrumbs: Breadscrumbs, liste: Liste },// je charge le composant dans Hello , nav est la balise
    data() { // Si je charge des données la dedans et qu'elles ont le même nom dans d'autres composant cela n'ecrase pas celle là 
      return {
        title: 'GOT App',
        titleFooter: 'Game Of Throne App',
      }
    },
  }

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h1,
  h2 {
    font-weight: normal;
  }
  
  ul {
    list-style-type: none;
    padding: 0;
  }
  
  li {
    display: inline-block;
    margin: 0 10px;
  }
  
  a {
    color: #42b983;
  }
</style>
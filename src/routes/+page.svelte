
<script>
    import Boite from "../lib/components/boite.svelte";

    class tache
    {
        title;
        description;
        priorite;

        constructor(p_title, p_description, p_priorite)
        {
            this.title = p_title;
            this.description = p_description;
            this.priorite = p_priorite;
        };
    }

    let list = [];

    function ajouter()
    {
        let f_titre = document.getElementById('titre').value;
        let f_description = document.getElementById('desc').value;
        let f_priorite = Number(document.getElementById('priorite').value);
        let newTask = new tache(f_titre, f_description, f_priorite);
        list = [...list, newTask];
    };
</script>
<div class="columns is-centered">
    <div class="column is-half">
<h1 class="title">TODO</h1>
<div class="field">
    <label class="label">Titre</label>
    <div class="control">
      <input class="input" type="text" id="titre">
    </div>
  </div>
  
  <div class="field">
    <label class="label">Description</label>
    <div class="control">
      <textarea name="desc" id="desc" class="textarea"></textarea>
    </div>
  </div>
  <div class="field">
    <label class="label">Priorite</label>
    <div class="control">
      <input type="number" class="input" id="priorite">
    </div>
  </div>  
  <div class="control">
    <button class="button is-primary" on:click={ajouter}>Ajouter</button>
  </div>
    {#each list as task}
        <Boite titre={task.title} description={task.description} priorite={task.priorite}/>
    {/each}
    </div>
    </div>
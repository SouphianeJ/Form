# Formulaire

<script>
window.addEventListener("load", function () {
  function sendData() {
    var XHR = new XMLHttpRequest();

    // Liez l'objet FormData et l'élément form
    var FD = new FormData(form);

    // Définissez ce qui se passe si la soumission s'est opérée avec succès
    XHR.addEventListener("load", function(event) {
      alert(event.target.responseText);
    });

    // Definissez ce qui se passe en cas d'erreur
    XHR.addEventListener("error", function(event) {
      alert('Oups! Quelque chose s\'est mal passé.');
    });

    // Configurez la requête
    XHR.open("POST", "https://example.com/cors.php");

    // Les données envoyées sont ce que l'utilisateur a mis dans le formulaire
    XHR.send(FD);
  }

  // Accédez à l'élément form …
  var form = document.getElementById("myForm");

  // … et prenez en charge l'événement submit.
  form.addEventListener("submit", function (event) {
    event.preventDefault();

    sendData();
  });
});
</script>
  
  
<div class="formulaireAlex">
<p>Répondez aux questions</p>

  <form>
    
<div>
<label for="nom">Votre nom</label>
<input type="text" id="nom" name="nom" placeholder="Martin" required>
</div>

<div>
<label for="email">Votre e-mail</label>
<input type="email" id="email" name="email" placeholder="monadresse@mail.com" required>
</div>

<div>
  <label for="bienetre">Comment vous sentez-vous ?</label>
  <select name="bienetre" id="bienetre" required>
    <option value="low">Non</option>
    <option value="medium">bof</option>
    <option value="high">Tres bien</option>
  </select>
</div>

<div>

<input type="submit" value="Envoyer !">
  
 </div>

</form>

</div>

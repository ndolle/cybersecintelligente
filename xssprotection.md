```
<!DOCTYPE html>
<html>
<head>
  <title>Cybersecurite Intelligence - XSS</title>
  <script>
    function sanitizeInput(input) {
      // Remplace les caractères spéciaux par leur équivalent HTML
      return input.replace(/&/g, '&amp;')
                  .replace(/</g, '&lt;')
                  .replace(/>/g, '&gt;')
                  .replace(/"/g, '&quot;')
                  .replace(/'/g, '&#x27;')
                  .replace(/`/g, '&#x60;');
    }

    function processInput() {
      var userInput = document.getElementById('userInput').value;
      var sanitizedInput = sanitizeInput(userInput);
      document.getElementById('output').innerHTML = sanitizedInput;
    }
  </script>
</head>
<body>
  <h1>Protection contre XSS Réfléchi</h1>
  <input type="text" id="userInput" placeholder="Entrez votre texte" />
  <button onclick="processInput()">Soumettre</button>
  <div id="output"></div>
</body>
</html>
```

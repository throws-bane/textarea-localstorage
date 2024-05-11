# textarea-localstorage
## This is just a simple example of how to implement textarea autosave using JavaScript and LocalStorage.

````
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Autosave Textarea</title>
</head>
<body>
<textarea id="myTextarea" rows="4" cols="50"></textarea>

<script>
// Get the textarea element
const textarea = document.querySelector("#myTextarea");

// This function saves the textarea value to LocalStorage using the localStorage.setItem() method.
function saveText() {
  // Save the textarea value to LocalStorage
  localStorage.setItem("textarea-value", textarea.value);
}

// Load saved text when the page loads
window.onload = function() {
// If the textarea value exists in LocalStorage, it is set as the initial value of the textarea element.
  const savedText = localStorage.getItem('textarea-value');
  if (savedText) {
    textarea.value = savedText;
  }
};

// Autosave on input event
textarea.addEventListener('input', saveText);
</script>

</body>
</html>
````

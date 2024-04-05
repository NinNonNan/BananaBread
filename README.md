# veganfruitbread

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ingredients List</title>
</head>
<body>
    <h1>Ingredients List</h1>
    <ul id="ingredient-list"></ul>

    <script>
        fetch('ingredients.json')
            .then(response => response.json())
            .then(data => {
                const ingredientList = document.getElementById('ingredient-list');
                data.ingredients.forEach(ingredient => {
                    const listItem = document.createElement('li');
                    listItem.textContent = `${ingredient.quantity} of ${ingredient.name}`;
                    ingredientList.appendChild(listItem);
                });
            })
            .catch(error => console.error('Error fetching JSON:', error));
    </script>
</body>
</html>

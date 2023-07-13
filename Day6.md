### The day 5 task in [this link](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week1-day5-task/task.md)

```javascript
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Day5</title>
    <style>
        #characterList {
            height: 700px;
            display: flex;
            flex-direction: column;
            flex-wrap: wrap;
            justify-content: flex-start;
            list-style-type: none;
            padding: 0;
        }
        
        .item {
            margin-bottom: 10px;
            display: flex;
            flex-direction: row;
        }
        
        .img {
            width: 100px;
            margin-right: 15px;
        }
        
        h3 {
            display: flex;
            flex-direction: column;
        }
        
        .character-details {
            display: flex;
            flex-direction: column;
            justify-content: center;
        }
        
        p {
            margin: 0;
            margin-bottom: 10px;
        }
    </style>
    <ul id="characterList"></ul>

    <script>
        fetch("https://rickandmortyapi.com/api/character")
            .then((response) => response.json())
            .then((data) => {
                const aliveChatacters = data.results.filter((item) => item.status === "Alive");
                const characterList = document.getElementById("characterList");

                aliveChatacters.forEach((character) => {
                    const listItem = document.createElement("li");
                    listItem.classList.add("item"); // css class item

                    const image = document.createElement("img");
                    image.classList.add("img");
                    image.src = character.image;
                    image.alt = character.name;

                    const detailsContainer = document.createElement('div');
                    detailsContainer.classList.add('character-details');


                    const name = document.createElement('h3');
                    name.textContent = character.name;

                    const location = document.createElement('p');
                    location.textContent = `Location: ${character.location.name}`;

                    const species = document.createElement('p');
                    species.textContent = `Species: ${character.species}`;

                    const gender = document.createElement('p');
                    gender.textContent = `Gender: ${character.gender}`;

                    detailsContainer.append(name, location, species, gender)

                    listItem.appendChild(image);
                    listItem.appendChild(detailsContainer);
                    characterList.appendChild(listItem);




                });
            })
            .catch((error) => {
                console.log("Error:", error);
            });
    </script>
</head>

<body>
    <div class="div"></div>
</body>

</html>
```

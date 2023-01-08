## FRQ 1

***

## FRQ 2

### - People Table -

<table>

  <tr id="nameRows">
  </tr>

  <tr id="ageRows">
  </tr>

  <tr id="emailRows">
  </tr>

</table>


<script>
    function getPeople() {

        // Fetch data from API
        fetch('https://akhilcodingsociety.tk/api/person/')
        .then(response => response.json())
        .then(data => {
    
            peopleData = data;
            console.log(peopleData);
            
            // get row elements
            let nameRow = document.getElementById("nameRows");
            let ageRow = document.getElementById("ageRows");
            let emailRow = document.getElementById("emailRows");
            
            // clear table contents
            for (let j = 0; j < peopleData.length; j++){    

                nameRow.innerHTML = " ";
                ageRow.innerHTML = " ";
                emailRow.innerHTML = " ";

            }

            // add table contents
            for (let i = 0; i < peopleData.length; i++){  

                let header = document.createElement("th");
                header.setAttribute("id", i);
                header.innerHTML = peopleData[i].name;
                nameRow.appendChild(header);

                let newAgeRow = document.createElement("td");
                newAgeRow.setAttribute("id", i);
                newAgeRow.innerHTML = peopleData[i].age;
                ageRow.appendChild(newAgeRow);


                let newEmailRow = document.createElement("td");
                newEmailRow.setAttribute("id", i);
                newEmailRow.innerHTML = peopleData[i].email;
                emailRow.appendChild(newEmailRow);  
            }

        });

        

        }

</script>

<button onclick="getPeople()">Click To Update People Table</button>

***


## FRQ 3

***

## FRQ 4




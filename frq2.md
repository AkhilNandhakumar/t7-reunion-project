
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
                newAgeRow.innerHTML = peopleData[i].age + " Years Old";
                ageRow.appendChild(newAgeRow);


                let newEmailRow = document.createElement("td");
                newEmailRow.setAttribute("id", i);
                newEmailRow.innerHTML = peopleData[i].email;
                emailRow.appendChild(newEmailRow);  
            }

        });

}

function getInputId(){
    let input = document.getElementById("inputId").value;
    return input;
}

function getInputEmail(){
    let input = document.getElementById("inputEmail").value;
    return input;
}

function getInputPassword(){
    let input = document.getElementById("inputPassword").value;
    return input;
}

function getInputName(){
    let input = document.getElementById("inputName").value;
    return input;
}

function getInputDob(){
    let input = document.getElementById("inputDob").value;
    return input;
}

function getInputHeight(){
    let input = document.getElementById("inputHeight").value;
    return input;
}

function getInputWeight(){
    let input = document.getElementById("inputWeight").value;
    return input;
}


function addPeople(){
    

    const params = {
        email: getInputEmail(),
        password: getInputPassword(), 
        name: getInputName(),
        dob: getInputDob(),
        height: getInputHeight(),
        weight: getInputWeight(),
    };

    const options = {
        method: 'POST',
        body: JSON.stringify( params )  
    };

    fetch( 'https://akhilcodingsociety.tk/api/person/post', options )
        .then(response => response.json())
        .then(data => {console.log(data);});

    }

function getId(id) {
    idResult = document.getElementById("idResult");

    if(id < 19){
        idResult.innerHTML = "Invalid ID. Person 0 has an ID of 19.";
    }
    // Fetch data from API
    fetch('https://akhilcodingsociety.tk/api/person/' + id)
    .then(response => response.json())
    .then(data => {
        console.log(data);
        idResult.innerHTML = "Person: " + data.name;
    })
}

</script>

<button onclick="getPeople()">Click To Update People Table</button>

<br>

### Get Person by ID

<p id="idResult"></p>

<input id="inputId" placeholder="Input Id">
    <button onclick="getId(getInputId())">Get Person by ID</button>

<br>

### Create New Person

<input id="inputEmail" placeholder="Input Email">
    <button onclick="getInputEmail()">Submit</button>

<input id="inputPassword" placeholder="Input Password">
    <button onclick="getInputPassword()">Submit</button>

<input id="inputName" placeholder="Input Name">
    <button onclick="getInputName()">Submit</button>

<input id="inputDob" placeholder="MM-dd-yyyy">
    <button onclick="getInputDob()">Submit</button>

<input id="inputHeight" placeholder="Input Height">
    <button onclick="getInputHeight()">Submit</button>

<input id="inputWeight" placeholder="Input Weight">
    <button onclick="getInputWeight()">Submit</button>

<button onclick="addPeople()">Submit New Person</button>

    
    



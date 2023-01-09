## FRQ 3

<script> 
function getInput(){
let inputbox = document.getElementByID("inputext").value
return inputbox

}

function calculate(ex) {
    
    result = document.getElementById("resultbox");

    // Fetch data from API
    fetch('https://akhilcodingsociety.tk/api/calendar/api/calculator/' + ex)
    .then(response => response.json())
    .then(data => {

        console.log(data);

        result.innerHTML = data.Result;

    })
}
</script>

<p id="resultbox">

</p>

<input id="inputext" placeholder="Input Equation">

<button onclick="calculate(getInput())">Submit</button> 
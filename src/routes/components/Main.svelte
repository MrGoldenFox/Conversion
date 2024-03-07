<script>
import { onMount } from "svelte";

let inputValue = '';
let warning = '';

function handleInput(event){
    inputValue = event.target.value;
}

let messageLength = '';
let messageVolume = '';
let messageMass = '';

function btnConvert(){
    if(isNaN(inputValue)){
        warning = 'Please write a number'
    }
    else{
    warning = '';
    messageLength = `${inputValue} meters = ${(inputValue * 3.281).toFixed(2)} feet | ${inputValue} feet = ${(inputValue / 3.281).toFixed(2)} meters`
    messageVolume = `${inputValue} liters = ${(inputValue * 0.264).toFixed(2)} gallons | ${inputValue} gallons = ${(inputValue / 0.264).toFixed(2)} liters`
    messageMass = `${inputValue} kilos = ${(inputValue * 2.204).toFixed(2)} pounds | ${inputValue} pounds = ${(inputValue / 2.204).toFixed(2)} kilos`
    }
}

</script>

<section>
    <main>
        <div class="titleContent">
            <h1>Metric/Imperial Unit Conversion</h1>
            <h5>{warning}</h5>
            <input type="text" bind:value={inputValue} on:input={handleInput} maxlength="7"><br>
            <button on:click={btnConvert}>Convert</button>
        </div>
        <div class="mainContent">
            <div class="container">
                <h4>Length (Meter/Feet)</h4>
                <p>{messageLength}</p>
            </div>
            <div class="container">
                <h4>Volume (Liters/Gallons)</h4>
                <p>{messageVolume}</p>
            </div>
            <div class="container">
                <h4>Mass (Kilograms/Pounds)</h4>
                <p>{messageMass}</p>
            </div>
        </div>
    </main>
</section>

<style>
    section {
        text-align: center;
        background-color: #1C1C1C;
        width: 100%;
        height: 100vh;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }

    main {
        display: flex;
        flex-direction: column;
        justify-content: center;
        width: 550px;
    }

    .titleContent {
        min-height: 40vh;
        background-color: #6943FF;
    }

    .mainContent {
        background-color: #F4F4F4;
        height: 55vh;
        display: flex;
        flex-direction: column;
        justify-content: center;
    }

    .container {
        background-color: #FFFFFF;
        width: 90%;
        margin: 0px auto;
        height: 108px;
        margin-top: 10px;
        display: flex;
        flex-direction: column;
        justify-content: center;
    }

    h1 {
        font-weight: 800;
        font-size: 28px;
        line-height: 38px;
        letter-spacing: -3%;
        color: #FFFFFF;
        margin-top: 33px;
        font-family: "Inter", sans-serif;
    }

    h4 {
        margin: 0;
        color: #5A537B;
        font-weight: 600;
        font-size: 1.2rem;
        line-height: 20px;
        font-family: "Inter", sans-serif;
    }

    h5 {
        height: 20px;
        margin-block: 5px;
        color: #FFFF00;
        font-weight: 800;
        font-size: 1.2em;
        letter-spacing: 1.2px;
    }

    p {
        font-family: "Inter", sans-serif;
        color: #353535;
        font-weight: 400;
        font-size: 0.9rem;
        line-height: 20px;
    }

    input {
        width: 117px;
        height: 83px;
        border: 2px solid #B295FF;
        background-color: transparent;
        border-radius: 5px;
        margin-bottom: 30px;
        font-family: "Inter", sans-serif;
        font-size: 58px;
        line-height: 24.39px;
        font-weight: 800;
        color: white;
        outline: none;
        text-align: center;
    }

    button {
        width: 117px;
        height: 42px;
        border-radius: 5px;
        font-weight: 500;
        font-size: 1em;
        line-height: 24px;
        border: none;
        font-family: "Inter", sans-serif;
        margin-bottom: 10px;
    }

    button:active {
        background-color: #CCCCCC;
    }

    @media only screen and (max-width: 555px){
        main {
            width: 90%;
        }

        h1{
            margin-top: 10px;
            font-size: 1.3rem;
        }
    }

    @media only screen and (min-width: 1100px){
        button:hover{
            background-color: #CCCCCC;
        }
        button:active {
        background-color: #F0F0F0;
    }
    }

</style>
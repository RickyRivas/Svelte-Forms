<script>
	import Toggle from './Toggle.svelte';
    import CustomInput from './CustomInput.svelte';
    let val = 'Ricky';
    let selectedOption = 1;
    let price = 0;
    let agreed = false;
    let favColor = 'pink'
    let singleFavColor = 'red'
    let usernameInput;
    let customInput;

    $: console.log(singleFavColor)
    $: console.log(val);
    $: console.log(selectedOption)
    $: console.log(price)
    $: console.log(agreed)
    $: console.log(favColor)
    $: console.log(customInput)

    function setValue(e){
        val = e.target.value 
    }
    function saveData(){
        console.log(usernameInput.value)
        customInput.empty()
    }
</script>

<!-- <input type="text" bind:value={value} on:input={setValue}> -->
<CustomInput bind:val={val} bind:this={customInput}/>
<p>{val}</p>

<Toggle bind:chosenOption={selectedOption}/>

<input type="number" bind:value={price} >


<label for="">
<input type="checkbox" bind:checked={agreed}>
Agree to terms
</label>


<h1>Fav color</h1>
<label for="">
    red
    <input type="radio" value='red' name='color' bind:group={favColor}>
</label>
<label for="">
    blue
    <input type="radio" value='blue' name='color' bind:group={favColor}>
</label>
<label for="">
    pink
    <input type="radio" value='pink' name='color' bind:group={favColor}>
</label>


<select name="" id="" bind:value={singleFavColor}>
    <option value="green">green</option>
    <option value="red">red</option>
    <option value="blue">blue</option>
</select>

<input type="text" bind:this={usernameInput}>
<button on:click={saveData}></button>
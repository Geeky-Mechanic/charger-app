<script>
export let items;
export let style;
</script>

<form action="" style={style}>
    
    {#each items as item}
        <label for={item.name} id={item.name}>{item.label}</label>
        {#if item.type === "text" || item.type === "number" || item.type === "email"}
            <input type={item.type} name={item.name} id={item.name} placeholder={item.placeholder}/>
        {:else if item.type === "textarea"}
            <textarea name={item.name} id={item.name} cols={item.cols} rows={item.rows} placeholder={item.placeholder}></textarea>
        {:else if item.type === "select"}
            <select name={item.name} id={item.name}>
                {#each item.options as option}
                    <option>{option}</option>
                {/each}
            </select>
        {/if}
    {/each}
</form>

<style>
form {
    display: flex;
    flex-direction: column;
    justify-content: center;
    width: 80%;
}

label {
    font-size: 1.2rem;
    color: #6B6969;
    margin: 1rem 0;
}

input {
    padding: 0.6rem 0.4rem;
    width: 60%;
}

textarea {
    padding: 0.6rem 0.4rem;
    width: 60%;
}

select {
    padding: 0.6rem 0.4rem;
    width: 60%;   
}


</style>
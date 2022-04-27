<script>
import Card from '../components/Card.svelte';
import Form from '../components/Form.svelte';

import { slide } from 'svelte/transition';

const days = ["1", "2", "3", "4", "5", "6", "7", "8"];

const hours = ["1", "2", "3", "4", "5", "6", "7", "8"];

let items = [
    {
        label: "Name",
        type: "text",
        name: "services-name",
        placeholder: "John",
    },
    {
        label: "Last Name",
        type: "text",
        name: "services-lname",
        placeholder: "Doe",
    },
    {
        label: "email",
        type: "email",
        name: "services-email",
        placeholder: "johndoe@gmail.com",
    },
    {
        label: "Phone Number",
        type: "text",
        name: "services-number",
        placeholder: "819-856-1234",
    },
    {
        label: "Address",
        type: "text",
        name: "services-address",
        placeholder: "123 Rue des Pins, Val-d'Or",
    },
    {
        label: "Year",
        type: "select",
        name: "services-year",
        options: ["2022"],
    },
    {
        label: "Month",
        type: "select",
        name: "services-month",
        options: ["May", "June", "July"],
    },
    {
        label: "Day",
        type: "select",
        name: "services-day",
        options: days,
    },
    {
        label: "Hour",
        type: "select",
        name: "services-hours",
        options: hours,
    },
];

</script>

<div out:slide>
<Card hoverable>
<div class="services-container">
    <h2 class="services-title">Our Services</h2>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. 
        Quo, alias? Atque, alias aut recusandae nobis cumque deleniti doloremque eaque eum asperiores odit id. 
        Quas, itaque earum. Hic, labore fugit! Aliquam!
    </p>
    <Form {items} />
</div>
</Card>
</div>


<style>

</style>
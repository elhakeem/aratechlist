<script>
	import { createEventDispatcher } from 'svelte';
	const dispatch = createEventDispatcher();

	const change = e => {
		dispatch('change', {value: e.target.value});
	}
</script>

<input type="text" on:input={change} placeholder="إبحث بالإسم أو بالموضوع أو بأي كلمات دلالية"/>

<style lang="scss">
    input {
        display: block;
        width: 100%;
        outline: none;
        background-color: rgba(255, 255, 255, 0.1);
        border-radius: 5px;
        border: 1px solid #333;
        padding: 20px;
        font-size: 18px;
        color: white;
        font-weight: 300;
        margin: 0 0 50px;
    }

</style>

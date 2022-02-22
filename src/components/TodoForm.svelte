<script>
    import {addTodo} from '../stores/todoStore.js';
    import {user} from '../stores/authStore.js';
    let todo = '';
    const handleSubmit = () => {
        console.log($user);
        addTodo(todo, $user.id)
        todo = '';
    }
</script>

<form class="form my-6" on:submit|preventDefault={handleSubmit}>
    <div class="flex flex-col text-sm mb-2">
        <label for="todo" class="font-bold mb-2 text-gray-800 ">
            Todo
        </label>
        <input
            type="text"
            name="todo"
            bind:value={todo}
            placeholder="ex. Clean Your Room"
            class="appearance-none shadow-sm border border-gray-200 p-2 focus:outline-none focus:border-gray-500 rounded-lg "
            
        />
    </div>
    <button
        type="submit"
        class=" w-full shadow-sm rounded bg-pink-500 hover:bg-red-600 text-white py-2 px-4"
    >
        Submit
    </button>
</form>
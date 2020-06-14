<script>
    let todos = [];
    let input = "";

    function addTodo() {
        if (input) {
            todos = [
                ...todos,
                {
                    text: input,
                    id: Math.random()
                        .toString(36)
                        .substr(2, 9)
                }
            ];
        }
        input = "";
    }

    function removeTodo(id) {
        const index = todos.findIndex(todo => todo.id === id);
        todos.splice(index, 1);
        todos = todos;
    }
</script>

<style>
    .todolist {
        text-align: center;
        
    }
    h3 {
        margin-bottom: 1em;
    }
    form {
        justify-content: center;
        margin-bottom: 1em;
    }
    li {
        text-align: center;
        margin: 0 auto
    }
</style>

<section class="todolist">
    <div class="container">
        <h3>TO DO LIst</h3>
        <form class="form-inline"
            on:submit|preventDefault = "{addTodo}">
            <div class="input-group inline">
                <input bind:value="{input}" type="text" class="form-control" placeholder="What need to be done?">
            </div>
            <div class="input-group">
                <button class="btn btn-primary" value="Add">Submit</button>
            </div>
        </form>
        <ul>
            <li></li>
        </ul>
    </div>
</section>


<ul class="list-group" class:list={todos.length > 0}>
	{#each todos as todo (todo.id)}
		<li class="list-group-item" transition:slide="{{duration: 300, easing: elasticInOut}}">
			<div class="is-flex" style="align-items: center">
				<span class="is-pulled-left">{todo.text}</span>
				<div style="flex: 1"></div>
				<button class="button is-text is-pulled-right is-small" on:click={()=> removeTodo(todo.id)}>
					<span class="icon">
						<i class="fas fa-check"></i>
					</span>
				</button>
			</div>
		</li>
	{:else}
		<li class="has-text-centered" transition:slide="{{delay: 600, duration: 300, easing: elasticInOut}}">
			Nothing here!
		</li>
	{/each}
</ul> 


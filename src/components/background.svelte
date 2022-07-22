<script>
  import Header from "./Header.svelte"
  import Input from "./Input.svelte";
  import Todos from "./Todos.svelte";
</script>

<div class="background">
    <Header />
    <Input />
    <Todos />
</div>

<style>
    .background{
        width: 100%;
        height: 100vh;
        background-color: #66CCCC;
        display: flex;
        flex-direction: column;
        align-items: center;
    }
</style>
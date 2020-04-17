<template>
    <header>
        <h1>TodoList</h1>
        <div id="nav">
            <router-link to="/">Home</router-link> |
            <router-link to="/about">About</router-link>
        </div>
    </header>
</template>

<script>
export default {
    name:"Header"
}
</script>

<style>
    header {
        background: #333;
        color: #fff;
        text-align: center;
        padding: 10px;
    }
    header a{
        color: #fff;
        padding-right: 5px;
    }
    #nav {
        background: #333;
        text-align: center;
        padding: 0px;
    }

    #nav a {
        text-decoration: none;
        font-weight: bold;
        color: #fff;
    }

    #nav a.router-link-exact-active {
        color: #42b983;
    }

</style>
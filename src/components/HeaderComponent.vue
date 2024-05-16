<template>
    <div class="header" id="home">
        <div class="title">
            <h1>The Aryan Hotel</h1>
        </div>
        <nav class="navbar">
            <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </div>
</template>

<style>
.header {
    position: fixed;
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    height: 5em;
    background-color: #3a3935;
    color: white;
    border-bottom: 2px solid #ffd000;
}

.title {
    flex: 1;
    text-align: center;
    margin-left: 10%;
    font-size: 1.1em;
    letter-spacing: 4px;
    text-transform: uppercase;
    text-shadow: 1px 1px 2px rgb(180, 180, 180);
}

.navbar ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
}

.navbar ul li {
    display: inline;
    margin-right: 20px;
}

.navbar ul li a {
    color: white;
    text-decoration: none;
}

.navbar ul li a:hover {
    text-decoration: underline;
}
</style>
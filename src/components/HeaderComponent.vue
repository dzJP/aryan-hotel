<template>
    <div class="header">
        <div class="title">
            <h1>The Aryan Hotel</h1>
        </div>
        <nav class="navbar">
            <ul>
                <li><a href="#">Home</a></li>
                <li><a href="#">About</a></li>
                <li><a href="#">Rooms</a></li>
                <li><a href="#">Contact</a></li>
            </ul>
        </nav>
    </div>
</template>

<style>
.header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 5em;
    background-color: #333;
    color: white;
}

.title {
    flex: 1;
    text-align: center;
    margin-left: 10%;
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

<template>
    <section class="about" id="about">
        <h2 class="heading">
            <span>Facility Information</span>
        </h2>
        <div class="about-container">
            <div class="about-box">
                <div class="about-box1">
                    <p>24 Hour Reception | Room service | Terrace | Daily Cleaning | Smoking Area | Air conditioning |<br>
                        Internet Connection - Wireless | Internet Connection (Lobby) - Free | Baby bed
                    </p>
                </div>
            </div>
        </div>
    </section>
</template>

<style>
.heading {
    text-align: center;
    font-size: 3rem;
    margin: 10%;
    text-transform: uppercase;
    letter-spacing: 3px;
}

.about {
    border-top: solid 2px #868686;
}

.about-container {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
    gap: 2rem;
}

.about-container .about-box {
    color: var(--white);
    flex: 1 1 30rem;
    background-color: var(--testcolor);
    padding: 8rem 2rem 8rem;
    border-radius: 1rem;
    text-align: center;
    border: .2rem solid #868686;
    transition: .5s ease;
}

.about-box p {
    font-family: 'Futura', sans-serif;
    font-size: 2em;
    justify-content: center;
}

section {
    min-height: 100vh;
    padding: 2rem 10% 1rem;
}

</style>
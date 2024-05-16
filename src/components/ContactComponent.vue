<template>
    <section class="contact" id="contact">
        <h2 class="heading">
            <span>Contact</span>
        </h2>

        <div class="contact-container">
            <div class="contact-box">
                <div class="contact-icon1">
                    <a href="https://www.google.com">Clickable link</a>
                    <p>123456789</p>
                    <p>aryanhotel@aryanhotel.com</p>
                </div>
            </div>
        </div>
    </section>
</template>
<style>
.heading {
    text-align: center;
    font-size: 4rem;
    margin: 10%;
}

.contact {
    border-top: solid 2px #868686;
}

.contact-container {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
    gap: 2rem;
}

.contact-container .contact-box {
    color: var(--white);
    flex: 1 1 30rem;
    background-color: var(--testcolor);
    padding: 6rem 4rem 4rem;
    border-radius: 1rem;
    text-align: center;
    border: .2rem solid #868686;
    transition: .5s ease;
}

section {
    min-height: 100vh;
    padding: 2rem 10% 1rem;
}

.contact-box h3,
.contact-box p,
.contact-box a {
    color: var(--white);
    display: flex;
    flex-direction: row;
    justify-content: center;
    font-size: 2em;
    letter-spacing: 5px;
    font-weight: 400;
    text-shadow: 1px 1px 2px var(--orange);
}

.contact-box p {
    margin: 50px;
}

.contact-box a:hover {
    color: var(--orange);
}

@media (max-width: 1366px) {
    .contact-container .contact-box {
        color: var(--white);
        flex: 1 1 30rem;
        background: var(--light-gray);
        padding: 3rem 2rem 2rem;
        border-radius: 0.1rem;
        text-align: center;
        border: .2rem solid var(--lightest-gray);
        transition: .5s ease;
    }

    .contact-box h3,
    p,
    a {
        display: flex;
        flex-direction: row;
        justify-content: center;
        font-size: 1.5em;
        letter-spacing: 5px;
        font-weight: 400;
        text-shadow: 1px 1px 2px var(--orange);
    }
}

@media (max-width: 768px) {
    .contact-container .contact-box {
        color: var(--white);
        flex: 1 1 30rem;
        background: var(--light-gray);
        padding: 3rem 2rem 2rem;
        border-radius: 0.1rem;
        text-align: center;
        border: .2rem solid var(--lightest-gray);
        transition: .5s ease;
    }

    .contact-box h3,
    p,
    a {
        display: flex;
        flex-direction: row;
        justify-content: center;
        font-size: 1.5em;
        letter-spacing: 5px;
        font-weight: 400;
        text-shadow: 1px 1px 2px var(--orange);
    }
}

@media (max-width: 360px) {
    .heading {
        text-align: center;
        font-size: 2em;
        margin-top: 7em !important;
    }
    .contact h2.heading {
        padding-bottom: 5em !important;
    }
    .contact {
        border-top: solid 1px var(--lightest-gray);
    }

    .contact-box p {
        margin-right: 35px;
        font-size: 1em !important;
    }
}
@media (max-width: 414px) {
    .contact-box p {
        font-size: 1.2em;
    }
    .contact h2.heading {
        margin-top: 2.5em !important;
        padding-bottom: 1.5em !important;
    }
}
</style>
<template>
    <div>
        <Navbar/>
        <section>
            <h1 style="margin-bottom:2em">VISION, MISSION AND CORE VALUES</h1>
            <h3>OUR VISION</h3>
            <p>TO BECOME THE LEADING REAL ESTATE COMPANY IN BICOL REGION PROVIDING WORLD CLASS REAL ESTATE SERVICES THAT MEET OUR CLIENTS NEEDS AT ALL TIMES.</p>
            <h3>OUR MISSION</h3>
            <p>We exist to provide world- class services in the area of our core competences that leave our clients happy and thoroughly satisfied.</p>
            <h3>OUR CORE VALUES</h3>
            <p>We exist to:
            Keep our clients satisfied; our colleagues/ collaborators happy; our staffs fulfilled and motivated; our management proud and celebrated; our brand competitive and progressive.
            To achieve the above, we pride ourselves on these Values:
            </p>

            <h4>Integrity</h4>
            <ul>
                <li>We keep our promises – we walk the talk.</li>
                <li>We are honest, trustworthy and ethical in our all actions.</li>
            </ul>
            <h4>Competence</h4>
            <ul>
                <li>We are research driven.</li>
                <li>We give reliable information that help our clients make the right decisions</li>
            </ul>
            <h4>Quality Client/ Customer service</h4>
            <ul>
                <li>Our clients are the driving force of our existence; keeping them satisfied is the fundamental reason for our existence</li>
                <li>We focus on opportunities where we can establish competitive advantage and deliver outstanding results.</li>
            </ul>

            <h4>Team Work</h4>
            <ul>
                <li>We work together to achieve more.</li>
                <li>We commit to achieving common goals.</li>
                <li>We support one another.</li>
            </ul>

            <h4>Prompt Delivery</h4>
            <ul>
                <li>We are quick to act and respond to clients’ needs</li>
                <li>We perform our duties without delay</li>
            </ul>
            <h4>Versatility</h4>
            <ul>
                <li>We are professional and adaptable to the varied needs of our clients</li>
                <li>We leverage on our collective strength to provide exceptional service</li>
            </ul>
        </section>
        <Footer/>
    </div>
</template>

<script>
import Navbar from '../custom/Navbar.vue'
import Footer from '../custom/Footer'
export default {
    components: {Navbar,Footer}
}
</script>


<style>
    section{
        padding:5%;
        margin-top: 3%;
    }
</style>
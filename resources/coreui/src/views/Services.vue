<template>
    <div>
        <Navbar/>

        <section class="services">
            <h1>SERVICES</h1>

            <h4>Property Staging</h4>
            <p>Selling a property quickly and at a higher price often requires staging the property. This can make your home more aesthetically and visually appealing.
                Prospective buyers will feel welcome, can easily picture living there, and entertaining friends and family. Some real estate agents offer these services for
                free while some may charge extra. Often times the agent will stage the property themselves. If it’s not possible for them to do it on their own, they will 
                hire a professional property staging company. 
            </p>

            <h4>Selling Real Estate</h4>
            <p>        
                When selling a property, hiring an experienced real estate agent is critical. It is particularly important for first time sellers. Many agents hold open houses to 
                generate additional interest in a property and make it easy for prospective buyers to stop by. Weekends are prime time for an open house. Good agents get feedback 
                on your home after an open house using a broker open house questionnaire.  The feedback sometimes reveals issues with the property or price you may not be aware of.
                Passing this feedback along to the seller can be more accurate when it is formally documented in a questionnaire versus trying to relay a conversation with the buyer’s agent.
            </p>
            <h4>  Buying Real Estate </h4>
            <p>       
                The real estate agents are not only efficient in selling; they are equally skilled helping their clients find the right home. Purchasing property is complicated particularly 
                for first-time buyers. Small mistakes can be costly. If you are moving from out of town, you need to hire an agent with local expertise to help you identify the best neighborhood 
                for you. They are also skilled at negotiating and can ensure you to find a property that meets all your requirements with the lowest price possible.  The seller typically pays the
                buyer’s commission as well so there is no reason to not use an agent.
            </p>

            <h4>New Construction </h4>
            <p> Many real estate investors hire agents when they want to build a house. Agents can help them locate lots for sale. They can also help identify homes that are candidates to tear 
                down and start over with new construction. Agents are deadline-oriented and realistic and can help you establish a timeline for your project.
            </p>
        
            <h4>Rental and Investment Properties</h4>
            <p>  A number of real estate’s agents are rental property owners. If you want to buy an investment property to rent out, they can help with this type of transaction as well. Managing a 
                property once you own it is important. Many real estate agents will be able to point you to a good property management firm if their company does not do that too.
            </p>
        </section>
        <Footer/>

    </div>
</template>

<script>
import Navbar from '../custom/Navbar'
import Footer from '../custom/Footer'
export default {
    components : {Navbar,Footer}
}
</script>

<style>
    section{
        padding: 5%;
        margin-top:2%
    }
</style>


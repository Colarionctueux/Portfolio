<aside>
    <div>
        <p>Présentation <br>
            générale</p>
    </div>
    <div class="bar"/>
    <div>
        <p> GTI - Site web </p>
        <p> Réalisé avec SvelteKit </p>
        <p> Projet pour un client </p>
    </div>
    <div class="bar"/>
    <div>
        <p> VM - Réseau </p>
        <p> Config poste de travail </p>
        <p> Projet d'école </p>
    </div>
    <div class="bar"/>
    <div>
        <p> Ilyva - jeu </p>
        <p> Réalisé avec godot </p>
        <p> Projet d'école </p>
    </div>
    <div class="bar"/>
    <div>
        <p> BDD J.O. - SQL </p>
        <p> Requêtage et gestion </p>
        <p> Projet d'école </p>
    </div>
</aside>
<img src="/main.jpg" alt="Montagnes blanches refletées sur un lac">
<div class="shadow" />
<section>
    <h1>ECKMAN Nicolas</h1>
    <div>
        <h2>Mes projets</h2>
        <p>Ce site est la liste des projets que j’ai réalisés jusqu’à aujourd’hui que vous pouvez également retrouver sur <a href="https://github.com/Colarionctueux" target="_blank">mon GitHub</a>.<br>
            <br>
            Si vous êtes un professionnel interessé par mes projets vous serez surement également interessé par <a href="https://cv-svelte-ruby.vercel.app/">mon CV</a> réalisé avec SvelteKit.</p>
    </div>
</section>

<style>
    :global(*){
        font-family: "Karla", sans-serif;
    }

    :global(body){
        background-color: black;
        margin: 0;
        overflow-y: hidden;
        height: 100vh;
    }

    img{
        width: 100%;
        height: 100vh;
        z-index: -1;
        object-fit: cover;
        position: absolute;
    }

    aside{
        display: flex;
        flex-direction: column;
        align-items: end;
        background-color: white;
        border-radius: 15px 0 0 0;
        width: 355px;
        height: 100vh;
        position: fixed;
        top: 0;
        right: 0;
        z-index: 10;
    }

    aside div{
        width: 229px;
        height: 142px;
        text-align: end;
        display: flex;
        justify-content: center;
        flex-direction: column;
        padding-right: 50px;
    }

    aside p{
        font-size: 1.375em;
        margin: 0;
    }

    .bar{
        background-color: rgb(122, 122, 122);
        height: 2px;
        width: 75px;
        margin: 0;
        padding: 0;
        margin-right: 50px;
    }

    section {
        height: 100%;
    }
    
    .shadow{
        background-color: rgba(0, 0, 0, 0.39);
        position: absolute;
        top: 0;
        left: 0;
        height: 100%;
        width: 100%;
        z-index: 0;
    }

    section{
        position: relative;
        z-index: 1;
        display: flex;
        flex-direction: column;
        height: 100%;
    }

    h1 {
        color: white;
        font-weight: 700;
        font-size: 3.25em;
        position: absolute;
        top: 100px;
        left: 10%;
    }

    h2 {
        color: white;
        font-size: 2.37em;
        margin: 0;
        margin-bottom: 20px;
        font-weight: 300;
    }
    
    section p {
        color: white;
        font-size: 1.81em;
        margin: 0;
        font-weight: 300;
    }

    section div {
        position: absolute;
        top: 230px;
        left: 10%;
        width: 700px;
        padding: 20px;
        background-color: rgba(129, 129, 129, 0.29);
        backdrop-filter: blur(35px);
    }

    a{
        color: white;
        text-decoration: underline;
        text-decoration-thickness: 1px;
    }
</style>
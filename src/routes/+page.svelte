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
<section>
    <img src="/main.jpg" alt="Montagnes blanches refletées sur un lac">
</section>

<style>
    :global(*){
        font-family: "Karla", sans-serif;
    }

    :global(body){
        background-color: black;
        margin: 0;
    }

    img{
        width: 100%;
        height: 100vh;
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
</style>
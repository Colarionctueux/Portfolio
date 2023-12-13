<script lang="ts">
    import { onDestroy, onMount } from "svelte";
    import Projets from "../components/Projets.svelte";
    import initIO from "$lib/initIO";
    import { browser } from "$app/environment";
    import { fade, blur, fly, slide, scale } from "svelte/transition";
    
    let selectedProject = -1;
    let observer: IntersectionObserver | undefined;

  
  let show = false;

    const projets = [
        {
            bgImg:"/bgGti.png",
            alt:"site GTI",
            schoolProject:false,
            date:"démarré le 03/11/2023",
            title:"GTI",
            logo:true,
            logoImg:"/logo-gti.svg",
            text:"Ce projet est un site web réalisé pour un client avec SvelteKit. Site vitrine mais également utilitaire pour le les clients aillent chercher les fiches techniques. Actuellement en développement, la partie BackEnd sera réalisée avec Node.js.",
            usedSkills:"/logo-svelte.png",
            unusedSkills:"/logo-jsnb.png",
            link:"https://gti-mu.vercel.app/"
        },
        {
            bgImg:"/reseau.png",
            alt:"VM ubuntu",
            schoolProject:true,
            date:"démarré le 04/10/2022 terminé le 26/03/2023",
            title:"Installation et configuration d’un poste de travail",
            logo:false,
            logoImg:"/logo-gti.svg",
            text:"Nous avons créé une machine virtuelle fonctionnant sous Debian 11 puis nous l’avons configuré en installant des logiciels et en préparant un fichier de pré-configuration pour les fois d’apres, nous avons ensuite installé Gitea.",
            usedSkills:"/bash.png",
        },
        {
            bgImg:"/bgIlyva.png",
            alt:"affiche ilyva",
            schoolProject:true,
            date:"démarré le 01/01/2023 terminé le 30/05/2023",
            title:"ILYVA",
            logo:true,
            logoImg:"/ilyvalogo.png",
            text:"Ilyva est un escape game réalisé avec godot engine ayant pour but de faire réviser Bash. Pour le site nous avons utilisé SvelteKit et stylisé avec SCSS. Nous avons également utilisé l’api Discord pour récuperer les photos de profil.",
            usedSkills:"/logo-svelte.png,/logo-godot.svg",
            link:"https://ilyva.sciencesky.fr/"
        },
        {
            bgImg:"/bgJo.jpg",
            alt:"paysage de nuit avec une statue des anneaux des jeux olympiques",
            schoolProject:true,
            date:"démarré le 01/03/2023 terminé le 14/04/2023",
            title:"Base de donnée SQL Statistiques",
            logo:false,
            text:"Dans ce projet nous avons du réaliser une base de donnée PostgreSQL conforme a partir d’un fichier CSV regroupant les athlètes de tous les J.O. Nous avons ensuite réalisé du requêtage pour ensuite faire des statistiques mathématiques.",
            usedSkills:"/postgresql.png",
            link:"https://github.com/Colarionctueux/sae-bdd"
        },
    ]

    onMount(() => {show = true;});

    onMount(() => {
        observer = initIO(document.body, 0.8);
    })

    onDestroy(() => {
        if (browser) {
            observer?.disconnect();
        }
    })
</script>


    <aside>
        <button class="reveal-1" on:click={() => selectedProject = -1}>
            <p>Présentation<br>
                générale</p>
        </button>
        <div  class="reveal-15" />
        <button class="reveal-2" on:click={() => selectedProject = 0}>
            <p> GTI - Site web </p>
            <p> Réalisé avec SvelteKit </p>
            <p> Projet pour un client </p>
        </button>
        <div  class="reveal-25"/>
        <button class="reveal-3" on:click={() => selectedProject = 1}>
            <p> VM - Réseau </p>
            <p> Config poste de travail </p>
            <p> Projet d'école </p>
        </button>
        <div  class="reveal-35"/>
        <button class="reveal-4" on:click={() => selectedProject = 2}>
            <p> Ilyva - jeu </p>
            <p> Réalisé avec godot </p>
            <p> Projet d'école </p>
        </button>
        <div  class="reveal-45"/>
        <button class="reveal-5" on:click={() => selectedProject = 3}>
            <p> BDD J.O. - SQL </p>
            <p> Requêtage et gestion </p>
            <p> Projet d'école </p>
        </button>
    </aside>
    <img src="/main.jpg" alt="Montagnes blanches refletées sur un lac">
    <div class="shadow" />
    {#if selectedProject === -1}
    {#if show}
        <section class="main">
            <h1 transition:fade={{ delay:100, duration:500}}>ECKMAN Nicolas</h1>
            <div transition:fade={{ delay:500, duration:500 }}>
                <h2>Mes projets</h2>
                <p>Ce site est la liste des projets que j’ai réalisés jusqu’à aujourd’hui que vous pouvez également retrouver sur <a href="https://github.com/Colarionctueux" target="_blank">mon GitHub</a>.<br>
                    <br>
                    Si vous êtes un professionnel interessé par mes projets vous serez surement également interessé par <a href="https://cv-svelte-ruby.vercel.app/">mon CV</a> réalisé avec SvelteKit.</p>
            </div>
        </section>
        {/if}
    {:else}
        <Projets {...projets[selectedProject]} /> 
    {/if}


<style>
    :global(*){
        font-family: "Karla", sans-serif;
    }

    :global(body){
        background-color: black;
        margin: 0;
        overflow-y: hidden;
        overflow-x: hidden;
        height: 100vh;
    }

    img{
        width: 100%;
        height: 100%;
        z-index: -1;
        object-fit: cover;
        position: absolute;
    }

    aside{
        display: flex;
        flex-direction: column;
        align-items: flex-end;
        background-color: white;
        border-radius: 15px 0 0 0;
        width: 25%;
        height: 100vh;
        position: fixed;
        top: 0;
        right: 0;
        z-index: 10;
    }

    aside button{
        width: 90%;
        height: 100%;
        text-align: right;
        background-color: transparent;
        border: none;
        padding: 0;
        padding-right: 20%;
    }

    aside p{
        font-size: 1.37em;
        margin: 0;
    }

    aside div{
        background-color: rgb(122, 122, 122);
        height: 2px;
        width: 75px;
        margin: 0;
        padding: 0;
        margin-right: 50px;
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

    section:first-of-type {
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
    
    section:first-of-type p {
        color: white;
        font-size: 1.81em;
        margin: 0;
        font-weight: 300;
    }

    section:first-of-type div {
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

    section:last-of-type {
        position: absolute;
        z-index: 9;
        top: 0;
        left: 0;
    }

    .main{
        width: 80%;
        padding-left: 10%;
    }

    [class*="reveal-"]{
        opacity: 0;
        transform: translateX(30px);
        transition-property: opacity, transform;
        transition-timing-function: ease;
        transition-duration: 1000ms;
    }

    .reveal-1{
        transition-delay: 300ms;
    }

    .reveal-15{
        transition-delay: 350ms;
    }

    .reveal-2{
        transition-delay: 400ms;
    }

    .reveal-25{
        transition-delay: 450ms;
    }

    
    .reveal-3{
        transition-delay: 500ms;
    }

    .reveal-35{
        transition-delay: 550ms;
    }

    
    .reveal-4{
        transition-delay: 600ms;
    }

    .reveal-45{
        transition-delay: 650ms;
    }

    .reveal-5{
        transition-delay: 700ms;
    }

    :global(.reveal-visible){
        transform: translateX(0)!important;
        opacity: 1!important;
    }
</style>
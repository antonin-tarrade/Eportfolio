<script>
  import { base } from '$app/paths';
  // ----Nav---- 
  import Nav from './Nav.svelte';
  export let navLinks = {
      'About': base + '/',
      'Projects': base + '/projects',
      'Experiences' : base + '/experiences',
      'Contact': base + '/contact'
  };

  // ----Project----
  import Project from './Project.svelte';
  import { Category } from './Project.svelte';  
  export let projects = [
    {
      name: 'Penguin Survivors',
      description: 'This game project originated from a <i>"Pass the game"</i> Game Jam organized by my school game dev club.\n The goal of the game is to survive each wave of enemy penguins, by shooting snowballs at them.',
      link: 'https://github.com/antonin-tarrade/ProjectPenguin',
      video : base + '/video/project-penguin.mp4',
      tag: ['Unity2D', 'C#', 'Game Jam', 'WIP'],
      category: Category.GAME
    },
    {
      name: 'Satellite Graph Visualization Project',
      description: 'This project is made for the <i>Graph theory</i> course of my school. The goal is to visualize and annalyse the graph representing a cluster of satellites. For this project, the choice of the tools was free. I chose to use Unity3D in the goal of better representing the situation as well as to learn more about Unity3D.',
      link: 'https://github.com/antonin-tarrade/Projet-Graphe',
      video: base + '/video/graph-project.mp4',
      tag: ['Unity3D', 'C#', 'Graph Theory'],
      category: Category.SCHOOL
    },

    {
      name: 'Space Travelers',
      description: 'In this game, two players play against each others, as the aliens vs the astronauts, competiting for the holy chicken. Each player chan choose X different character to play and will play turn by turn. Each round the replays of the previous ones are played and you can interact with them. The goal of the game is to be the players with most chicken captured at the end of the game.',
      link: 'https://github.com/antonin-tarrade/Project-ChristmasTravelers',
      video : base + '/video/Space-Travelers.mp4',
      tag: ['Unity2D', 'C#', 'Game Jam', 'WIP'],
      category: Category.GAME
    },
    {
      name: 'Sausage Serenity',
      description: 'This game was made as a participation of the Global Game Jam 2024. The theme of this yeear was <i>Make me laugh</i>. In this game you play as a sausage dog and wonder in a ciy filled with depression. As you make your way through the city, you\'ll meet various characters and have to respond to their requests to restore their laughter. The goal of the game is to make the city a better place.',
      link: 'https://github.com/antonin-tarrade/SausageSerenity',
      video : base + '/video/Sausage-serenity.mp4',
      tag: ['Godot','GDScript','Global Game Jam'],
      category: Category.GAME
    },
    {
      name: 'Eportfolio',
      description: 'This eportfolio was made using the <i>Svelte</i> framework. After looking at the different options, I decided to use svelte because it is a open source framework and also for its Component-Based Architecture and performance. The goal of this eportfolio is to showcase my projects and experiences.',
      link: 'https://github.com/antonin-tarrade/Eportfolio',
      img: base + '/img/svelte.png',
      tag: ['Svelte', 'HTML', 'CSS', 'Javascript'],
      category: Category.PERSONAL
    },
    {
      name: 'RaffIDE',
      description: 'This project was made for the <i>Java POO Programming</i> course of my school. The goal was to apply POO concepts in Java as well as work in a large team (8-9 people) using the Agile method. This project is an IDE for the <i>Refinning method</i> of constructing an aplication. This project is completly in french.',
      link: 'https://github.com/newtondotcom/RaffIDE',
      img: base + '/img/raffIde.png',
      tag: ['Java', 'JavaSwing','Scrum'],
      category: Category.SCHOOL
    }
  ];

  // ----Filter----
  import Filter from './Filter.svelte';
  import {createFilter} from './Filter.svelte';

  let filters = [
    createFilter('category', Category.GAME),
    createFilter('category', Category.SCHOOL),
    createFilter('category', Category.PERSONAL),
    createFilter('category', Category.OTHER)
  ];

  let objectsToFilter = projects;
  let ObjectComponent = Project;
  let filterName = 'My Projects';

  // ----Experience----
  import Experience from './Experience.svelte';
  let experiences = [
    {
      role: 'App Developer',
      company: {
        name: 'AIRBUS',
        logo: base + '/img/airbus.png',
        site: 'https://www.airbus.com/en'
      },
      year: '2023',
      description: 'This internship focused on developing the initial version of an application using a low-code tool, ensuring a rapid and secure deployment for potential approval.My responsibilities included data extraction and processing, creating a mobile/web application through the AppSheet platform but also conducting tool presentations for potential end-users.',
      country: 'France',
      city: 'Toulouse',
      tags: ['Data Bases', 'AppSheet', 'Excel', 'SAFe'],
      document: {
        name: 'Internship report',
        confidential: true,
      }
    },
    {
      role: 'Software Developer',
      company: {
        name: 'IRIT',
        logo: base + '/img/irit.png',
        site: 'https://www.irit.fr'
      },
      year: '2022',
      description: 'During this internship, my goal was to create a Python program in order to generate multiple choice quizzes automatically. I had to generate multiple quizzes related to several teaching platforms, such as Moodle and AMC, from a single description.',
      country: 'France',
      city: 'Toulouse',
      tags: ['Python', 'Mako', 'LateX'],
      document: {
        name: 'Internship report',
        confidential: false,
        link: base + '/document/Report-IRIT.pdf'
      }
    },
  ]

  // ----Resume----
  import Resume from './Resume.svelte';
  let resumes = [
    {
      language: 'English',
      icon: base + '/icons/united-kingdom.svg',
      link: base + '/document/Cv-English.pdf'
    },
    {
      language: 'French',
      icon: base + '/icons/france.svg',
      link: base + '/document/Cv-Francais.pdf'
    }
  ]


  // ----CoverLetter----
  import CoverLetter from './CoverLetter.svelte';
  let coverLetters = [
    {
      company: 'Nintendo',
      language: 'EN',
      link: base + '/document/Nintendo-Cover-Letter.pdf'
    },
    {
      company: 'Riot Games',
      language: 'EN',
      link: base + '/document/Riot-Games-Cover-Letter.pdf'
    },
    {
      company: 'Ubisoft',
      language: 'FR',
      link:   base + '/document/Ubisoft-Cover-Letter.pdf'
    },
  ]


  // ----Social----
  import Social from './Social.svelte';
  let socials = [
    {
      name: 'LinkedIn',
      link: 'https://www.linkedin.com/in/antonin-tarrade-5700a8252/',
      svgPath: base + '/icons/linkedin.svg'
    },
    {
      name: 'Github',
      link: 'https://github.com/antonin-tarrade',
      svgPath: base + '/icons/github.svg'
    },
    //{
     // name: 'CV',
     // link: '',
      //svgPath: base + '/icons/profile.svg'
    //},
    {
      name: 'Mail',
      link: 'mailto:antonin.tarrade@etu.inp-toulouse.fr',
      svgPath: base + '/icons/email.svg'
    }
  ]

</script>

<div class="background" style="--background-image:url({base}/img/pattern5.png)"> 
  <main class="main-content" >
    <Nav links={navLinks} />
    <div class="name">
      <h1 class="name-title">ANTONIN TARRADE</h1>
      <h2 class="name-subtitle">Student in Computer Science, Aspiring Game developer & Software developer</h2>
    </div>
    <div class = "about" id="about">
      <h1 class="about-title"> About me </h1>
      <p class="about-text"> I am a student in Computer Science at ENSEEIHT, France. I am currently in my second year of Engineer's degree.
        <br>
        <br>
        Passionate about video games since childhood and president of the video game development club of my school, I have been learning how to develop games for almost 2 years (and playing for more than 15 &#x1F604).
        I am also particularly interested in software and web development.
        <br>
        <br>
        I am currently looking for a 4-to-6 months internship in the field of video games or software development to explore their respective professional world, as well as gain more experience.</p>
      </div>
      
    <div class="projects" id="projects">
      <Filter {filterName} {filters} {objectsToFilter} {ObjectComponent}/>
    </div>
  
    <div class="experiences" id="experiences">
      <h1>Professional Project - PPP</h1>
      <h2>Experiences</h2>
      {#each experiences as experience (experience.role)}
      <Experience {experience}/>
      {/each}
    </div>
  
    <div class="job-application">
      <h1>Job (Internship) Applications</h1>
      <h2>Resumes</h2>
      <div class="resume-buttons">
        {#each resumes as resume (resume.language)}
        <Resume {resume}/>
        {/each}
      </div>
      <h2>Cover Letters</h2>
      <div class="cover-letters">
        {#each coverLetters as letter (letter.company)}
        <CoverLetter {letter}/>
        {/each}
      </div> 
    </div>
  
    <div class = "contacts">
      <h1>Contacts</h1>
      <h2> Let's get in touch !</h2>
      <div class = "socials" id="contact">
        {#each socials as social (social.name)}
        <Social {social}/>
        {/each}
      </div>
    </div>
  </main>
</div>

<style>
    :global(html, body) {
      margin: 0;
      padding: 0;
      height: 100%;
      font: 16px 'Roboto', sans-serif;
      background-color: var(--background-color, #19112C);
      color: var(--text-color, #ffffff);
      scroll-behavior: smooth;
    }

    .background::before {
      content: "";
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      background-image: var(--background-image);
      opacity: 0.03;
      filter : invert(1);
      pointer-events: none;
      z-index: 0;
    }


    .main-content {
        text-align: center;
        padding: 1em;
        max-width: 1200px;
        margin: 0 auto;
    }

    .name-title,
    .name-subtitle {
        font-weight: 100;
    }

    .name-title {
        font-size: 4em;
        margin-bottom: 0.1em;
    }

    .name-subtitle {
        font-size: 1em;
        margin-top: 0.1em;
    }

	.about{
		text-align: justify;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;

	}

	.about-title{
		font-size: 2em;
		max-width: 5em;
	}

	.about-text{
		font-size: 1em;
		max-width: 50em;
	}


  .projects{
    margin-top: 5em;
  }

  .experiences h1{
    font-size: 2.5em;
    text-align: left;
  }

  .experiences h2{
    font-size: 2em;
    text-align: center;
  }

  .job-application h1{
    font-size: 2.5em;
    text-align: left;
  }

  .job-application h2{
    font-size: 2em;
    text-align: center;
    margin-bottom: 0.5em;
  }

  .resume-buttons{
    display: flex;
    justify-content: center;
    align-items: center;
  }


  .cover-letters{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  .contacts{
    margin-top: 5em;
  }

  .contacts h1{
    font-size: 2.5em;
    text-align: left;
  }

  .socials{
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
  }


  /* Media Queries */
  


</style>

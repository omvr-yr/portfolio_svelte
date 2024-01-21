<script lang="ts">
	import { tooltip } from '$lib/tooltip/tooltip'
	import {
		IconBrandSvelte,
		IconBrandJavascript,
		IconBrandTypescript,
		IconBrandHtml5,
		IconBrandCss3,
		IconBrandSass,
		IconBrandTailwind,
		IconBrandGit,
		IconBrandPython,
		IconBrandMongodb,
		IconBrandSupabase,
		IconBrandFirebase,
		IconBrandAngular,
		IconBrandLinkedin,
		IconBrandThreejs,
		IconMail,
		IconSql,
		IconBrandGithub,
		IconBrandPhp,
		IconBrandCSharp,
		IconBrandCpp,
		IconBrandReactNative,
		IconExternalLink
	} from '@tabler/icons-svelte'
	import Project from './Project.svelte'
	import { colorHover } from '$lib/colorHover'

	const technos = {
		proficient: [
			{ name: 'Javascript', comp: IconBrandJavascript, color: '#f7df1e' },
			{ name: 'Python', comp: IconBrandPython, color: '#3776ab' },
			{ name: 'Php', comp: IconBrandPhp, color: '#dd0031' },
			{ name: 'HTML5', comp: IconBrandHtml5, color: '#e34f26' },
			{ name: 'CSS3', comp: IconBrandCss3, color: '#264de4' },
			{ name: 'Git', comp: IconBrandGit, color: '#f05032' },
		],
		experienced: [
			{ name: 'C#', comp: IconBrandCSharp, color: '#184e12' },
			{ name: 'C++', comp: IconBrandCpp, color: '#dd0aa7' },
			{ name: 'Typescript', comp: IconBrandTypescript, color: '#007acc' },
			{ name: 'SQL', comp: IconSql, color: '#f29111' }
		],
		familiar: [
			{ name: 'React Native', comp: IconBrandReactNative, color: '#6309f6' },
			{ name: 'Svelte', comp: IconBrandSvelte, color: '#ff3e00' },
			{ name: 'Mongodb', comp: IconBrandMongodb, color: '#4db33d' },
			{ name: 'Firebase', comp: IconBrandFirebase, color: '#ffca28' },
			{ name: 'Angular', comp: IconBrandAngular, color: '#dd0031' },
		]
	}

	const projects = [
		{
			title: 'Tower Defense',
			href: 'https://youtu.be/aCwHLZKfbY0',
			src: 'image/logo-tower-defense.png',
			desc: 'Full game with 6 different game modes. All the explanations are in the attached GitHub Compte Rendu.pdf.',
			gitUrl: 'https://github.com/omvr-yr/tower_defense_swing',
			tags: ['Swing', 'GUI']
		},
		{
			title: 'FITSHARE Social Network',
			href: 'https://github.com/omvr-yr/FITSHARE_social_network',
			src: 'image/logo-fitshare.png',
			desc: 'Quick 3 days work functionnal sport-oriented social network (not responsive) to train on MySQL / PHP connection.',
			gitUrl: 'https://github.com/omvr-yr/FITSHARE_social_network',
			tags: ['PHP', 'MySQL', 'HTML5']
		},
		{
			title: 'Pacman',
			href: 'https://youtu.be/TsEL8npsvBc',
			src: 'image/logo-pacman.png',
			desc: 'An entire Pacman game coded in Java using Gradle. The game features 3 different levels, a scoring system, music and a skin store. Even better than the original game :)',
			gitUrl: 'https://github.com/omvr-yr/java_pacman',
			tags: ['Java', 'Gradle']
		},
		{
			title: 'Fuel Cell Dashboard',
			href: 'https://youtu.be/8Rq0tiOuxWE',
			src: 'image/logo-rt.png',
			desc: 'A responsive dashboard to monitor a hydrogen fuel cell with on-board Raspberry PI. An AI powered chatbot is intergrated, and also a Google Maps map to find an advisor next to us.',
			gitUrl: 'https://youtu.be/8R2xeAa5KsE',
			tags: ['Javascript', 'React', 'AI Chatbot']
		},
		{
			title: 'Java Image Editor',
			href: 'https://github.com/omvr-yr/Quick_Image_Editor_Using_Swing',
			src: 'image/logo-editor.png',
			desc: 'A simple select, cut, undo/redo picture editor.',
			gitUrl: 'https://github.com/omvr-yr/Quick_Image_Editor_Using_Swing',
			tags: ['Java', 'Swing']
		}
	]

	const copyEmail = () => {
		const email = 'omar@konate.pro'
		navigator.clipboard.writeText(email)
		alert(`Copied ${email} to clipboard`)
	}
</script>

<div class="grid max-w-screen-xl min-h-screen px-4 pt-10 mx-auto lg:grid-cols-2 md:px-24">
	<header
		class="mb-16 lg:col-start-1 lg:fixed lg:top-0 lg:max-h-screen lg:justify-between lg:py-24"
	>
		<a href="/">
			<h1 class="text-4xl font-bold tracking-wider font-bauhaus text-slate-200 sm:text-5xl">
				Omar KONATE
			</h1>
		</a>
		<h2 class="mt-3 text-lg font-medium tracking-tight colliding text-slate-200 sm:text-xl">
			Developper
		</h2>
		<p class="max-w-xs mt-4 mb-12 leading-normal text-slate-400">
			A French coder for more than 5 years, I'm particularly interested in cloud computing and increasingly in cybersecurity.<br><br> I recently fouded <a href="https://scio-edu.com">SCIO</a> an EdTech startup !
		</p>

		<button class="w-48 h-12 px-4 py-2 font-medium uppercase colliding" on:click={copyEmail}
			>Copy Email</button
		>

		<ul class="flex items-center mt-8 ml-1" aria-label="Social media">
			<li class="mr-5">
				<a
					class="block hover:text-blue-400"
					href="https://github.com/omvr-yr/"
					target="_blank"
					rel="noreferrer"
					><span class="sr-only">GitHub</span>
					<IconBrandGithub size={36} stroke={1} color={'currentColor'} />
				</a>
			</li>
			<li class="mr-5">
				<a
					class="block hover:text-blue-400"
					href="https://www.linkedin.com/in/omar-konate-87b686267/"
					target="_blank"
					rel="noreferrer"
					><span class="sr-only">LinkedIn</span>
					<IconBrandLinkedin size={36} stroke={1} color={'currentColor'} />
				</a>
			</li>
			<li class="mr-5">
				<a
					class="block hover:text-blue-400"
					href="mailto:omar@konate.pro"
					target="_blank"
					rel="noreferrer"
					><span class="sr-only">LinkedIn</span>
					<IconMail size={36} stroke={1} color={'currentColor'} />
				</a>
			</li>
		</ul>
		<span class="mt-2 font-thin">Email: omar@konate.pro</span>
	</header>

	<main class="lg:col-start-2">
		<section class="mb-12">
			<h2 class="flex mb-2 text-2xl title"><span>Certifications</span></h2>
			<ul class="mt-2">
				<li>Baccalaureate - Specialization Mathematics and Physics-chemistry <span class="text-slate-400">2022</span></li>
				<li>Bachelor Computer Science – Univeristy Paris Cité <span class="text-slate-400">2022-2024</span></li>
				<li>Google Cybersecurity - 6 months Certification <span class="text-slate-400">2023</span></li>
				<li>Blue Team Level 1 – Junior SOC Certification (4 months) <span class="text-slate-400">2023</span></li>
				<li>AWS Solution Architect – Assosiate Level <span class="text-slate-400">2023</span></li>
			</ul>
		</section>

		<!---------- TECHNOLOGIES ---------->
		<section class="mb-12">
			<h2 class="flex mb-2 text-2xl title"><span>Technologies</span></h2>

			<div class="mb-2">
				<h3 class="text-slate-200">Proficient</h3>
				<ul class="flex flex-wrap">
					{#each technos.proficient as { name, comp, color }}
						<li data-tooltip={name} data-color={color} use:tooltip use:colorHover>
							<div class="pointer-events-none">
								<svelte:component this={comp} size={64} stroke={1} color={'currentColor'} />
							</div>
						</li>
					{/each}
				</ul>
			</div>
			<div class="mb-2 text-slate-400">
				<h3 class="text-slate-200">Experienced</h3>
				<ul class="flex">
					{#each technos.experienced as { name, comp, color }}
						<li data-tooltip={name} data-color={color} use:tooltip use:colorHover>
							<div class="pointer-events-none">
								<svelte:component this={comp} size={64} stroke={1} color={'currentColor'} />
							</div>
						</li>
					{/each}
				</ul>
			</div>
			<div class="mb-2 text-slate-600">
				<h3 class="text-slate-200">Familiar</h3>
				<ul class="flex">
					{#each technos.familiar as { name, comp, color }}
						<li data-tooltip={name} data-color={color} use:tooltip use:colorHover>
							<div class="pointer-events-none">
								<svelte:component this={comp} size={64} stroke={1} color={'currentColor'} />
							</div>
						</li>
					{/each}
				</ul>
			</div>
		</section>

		<!---------- PROJECTS ---------->
		<section class="mb-12">
			<h2 class="flex mb-2 text-2xl title">
				<span class="whitespace-nowrap">Some Cool Projects ...</span>
			</h2>

			<div class="flex flex-col gap-8">
				{#each projects as project}
					<Project {project} />
				{/each}
			</div>
		</section>
	</main>
</div>

<style>
	/* Lines through titles */
	.title::before {
		content: '';
		margin: 1rem 0.5rem 0 0;
		width: 100%;
		height: 0.1rem;
		background: var(--delft-blue);
		width: 4rem;
	}
	.title::after {
		content: '';
		margin: 1rem 0 0 0.5rem;
		width: 100%;
		height: 0.1rem;
		background: var(--delft-blue);
	}

	button {
		box-shadow: 0.3em 0.3em 0 0 rgb(30 58 138), inset 6em 3.5em 0 0 rgb(37 99 235);

		transition: box-shadow 0.2s ease-in-out;
	}

	button:hover,
	button:focus {
		outline: none;
		box-shadow: 0.3em 0.3em 0 0 rgb(37 99 235), inset 0.3em 0.3em 0 0 rgb(37 99 235);
	}
</style>

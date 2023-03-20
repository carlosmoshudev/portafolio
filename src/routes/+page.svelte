<script lang="ts">
	import Enterprises from '../enterprises.json';
</script>

<article>
	<!-- Two columns with info -->
	<div class="columns">
		<!-- Left column will get my work experience -->
		<div class="column work-experience">
			{#each Enterprises as enterprise}
				<div class="enterprise">
					<h3>{enterprise.enterprise}</h3>
					<p>{enterprise.description.join(', ')}</p>
					<ul>
						{#each enterprise.tasks as task}
							<li>{task}</li>
						{/each}
					</ul>
					<h4>Skills</h4>
					<ul>
						{#each enterprise.skills as skill}
							<li class="tag">{skill}</li>
						{/each}
					</ul>
					<h4>Technologies</h4>
					{#each Object.keys(enterprise.technologies) as category}
						<h5>{category}</h5>
						<ul>
							{#each enterprise.technologies[category] as technology}
								<li class="tag">{technology}</li>
							{/each}
						</ul>
					{/each}
				</div>
			{/each}
		</div>
		<!-- Right column will get my education and courses -->
		<div class="column education-courses">
			<!-- Education and courses content will go here -->
		</div>
	</div>
</article>

<style lang="css" scoped>
	:root {
		--primary-color: #6200ee;
		--secondary-color: #03dac6;
		--main-font-family: 'Montserrat', sans-serif;
		--mono-font-family: 'Cascadia Code', monospace;
		--title-font-size: 1.5rem;
		--description-font-size: 1.2rem;
		--list-font-size: 1rem;
	}

	.columns {
		display: flex;
		flex-wrap: wrap;
		gap: 2rem;
	}

	.column {
		flex: 1;
		min-width: 300px;
		padding: 1rem;
		background-color: rgba(255, 255, 255, 0.1);
		border-radius: 4px;
		backdrop-filter: blur(10px);
		box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
	}

	.enterprise {
		margin-bottom: 2rem;
	}

	h3,
	h4,
	h5 {
		margin-bottom: 1rem;
		color: white;
		font-family: var(--main-font-family);
	}

	h3 {
		font-size: var(--title-font-size);
	}

	h4,
	h5 {
		font-size: var(--description-font-size);
	}

	p {
		margin-bottom: 1rem;
		color: white;
		font-size: var(--description-font-size);
		font-family: var(--mono-font-family);
	}

	.tag {
		display: inline-block;
		padding: 0.25rem 0.5rem;
		margin: 0 0.25rem 0.25rem 0;
		border-radius: 4px;
		background-image: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
		color: white;
		font-size: var(--list-font-size);
		font-family: var(--main-font-family);
	}

	/* Phone view: single column */
	@media (max-width: 767px) {
		.columns {
			flex-direction: column;
		}
	}
</style>

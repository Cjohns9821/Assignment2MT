1. What triggers this workflow to run?
The workflow is triggered by a push to the main branch.
In the deploy.yml file, the on: section specifies that any commit pushed to main will automatically start the deployment workflow.

2. What are the four main steps this workflow performs?
It uses these steps:

Checkout code – Pulls the repository code into the workflow runner.

Setup environment – Configures the correct version of Node.js or other tools needed.

Run validation tests – Checks HTML, links, or other project requirements before deployment.

Deploy to GitHub Pages – Uploads the built site to the GitHub Pages hosting environment.

3. What does the “Checkout code” step do and why is it necessary?

The Checkout code step downloads your repository’s files into the GitHub Actions runner.
It is necessary because:

The workflow cannot test, build, or deploy your site unless it has access to the actual code.
It ensures the runner is working with the exact version of your project that was pushed to main.
Without this step, the workflow would have nothing to validate or deploy.

4. What is the purpose of the environment configuration?
The environment configuration ensures the workflow uses the correct tools and versions needed to run your project.
This may include:

Setting up Node.js

Installing dependencies

Preparing the build environment

It guarantees that the workflow runs consistently, regardless of the machine GitHub uses behind the scenes.

5. How does automated deployment improve reliability compared to manual deployment?
Automated deployment improves reliability because:

It removes human error — no forgotten files or incorrect uploads.

It ensures tests run every time before deployment.

It guarantees consistent deployment steps.

It deploys immediately after a successful push, keeping the live site up to date.

This makes the process predictable, repeatable, and far less prone to mistakes.

6. What would happen if you pushed code to a different branch (not main)?
If you push to a different branch:

The workflow will not run, because it is only triggered by pushes to main.

Nothing will actually happen.

No tests will run.

No deployment will occur.

GitHub Pages will remain unchanged.

Only merging into main triggers the deployment pipeline.

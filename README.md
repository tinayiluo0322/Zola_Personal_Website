[![pipeline status](https://gitlab.com/ly178/tinayiluo_ids721_week1/badges/main/pipeline.svg)](https://gitlab.com/ly178/tinayiluo_ids721_week1/-/commits/main)

# Luopeiwen (Tina) Yi's Personal Website

## Objective

The primary goal is to create a sophisticated and user-friendly personal website. Utilizing Zola for streamlined content generation, hosted on Vercel to ensure blazing-fast performance, and leveraging a GitLab CI/CD workflow for efficient build and deployment processes, this project aims to showcase my professional journey and achievements in a compelling digital format.

## Web App Delivery 

![Screen_Shot_2024-03-06_at_10.37.41_PM](/uploads/1da75db83d6bd1ae88cecc4b3d26580f/Screen_Shot_2024-03-06_at_10.37.41_PM.png)

[Luopeiwen (Tina) Yi's Personal Webiste](https://tinaportfolio.vercel.app/)

## Description
### 1. Content Creation using Zola

#### a. Installing Zola and Initializing the Website:
1. Download and install Zola from its official website or use a package manager relevant to the operating system.
2. Open the terminal, navigate to the directory where I want the website to reside, and run `zola init <site_name>`. Follow the prompts to complete initialization.

#### b. Adding and Configuring the Theme:
1. Navigate to the site's root directory, then to the `themes` directory with `cd themes`.
2. Add a theme using Git submodules by executing `git submodule add <theme_repository_url>`. For the Kita theme, replace `<theme_repository_url>` with the actual URL of the Kita theme repository.
3. In the site's root, open the `config.toml` file to set `theme = "kita"` to apply the theme.

#### c. Customizing Site Configuration:
1. In the `config.toml` file, configure the base URL, enable Sass compilation and search index building as detailed earlier to tailor the site setup to my needs.
2. Add custom variables under `[extra]` and `[extra.profile]` for personalized information like name, bio, and social links.

#### d. Developing Content:
1. Create markdown files within the `content` folder for different sections of my website, such as `project1.md`, `project2.md`, `project3.md`, etc.
2. Add images and other static assets in my content within the `static/icons` directory. 
3. Utilize Zola's content management features to organize the content effectively.

#### e. Local Testing:
1. Run `zola serve` from the site's root directory to test my website locally. This command starts a local web server, allowing me to preview my website.

### 2. Hosting using Vercel

#### a. Installing the Vercel CLI:
1. Install the Vercel CLI globally using npm with the command `npm i -g vercel`.

#### b. Setting Up Vercel:
1. Run `vercel login` and follow the prompts to log in to my Vercel account.
2. In my site's root directory, execute `vercel link` to connect my local project with a Vercel project. Follow the CLI prompts to either link to an existing project or create a new one.
3. Configure my project settings as prompted, including the assignment of environment variables.
4. Prepare my project for deployment on Vercel by creating and configuring a `vercel.json` file in the project's root directory. This configuration file is essential for deploying a Zola-powered static site on Vercel. It includes a custom installation command for Zola, fetching its latest release directly from GitHub, and specifies the build command and output directory. The `vercel.json` ensures that Zola is installed and configured correctly, allowing Vercel to build and serve my site efficiently.

### 3. Deployment

#### a. Preparing for Continuous Deployment:
1. Ensure that the project is a Git repository if it's not already. Initialize a new Git repository with `git init` if necessary, and commit the changes.

#### b. Linking to GitLab and Setting Up CI/CD:
1. Push the repository to GitLab. Create a new project on GitLab and follow the instructions to push the local repository to GitLab.
2. In the GitLab project, navigate to "Settings" > "CI / CD" > "Variables" to add the Vercel token, team ID, and organization ID as secrets.

#### c. Configuring the `.gitlab-ci.yml` File

1. **Create a `.gitlab-ci.yml` file** at the root of the project. This YAML file will define the CI/CD pipeline's configuration.
2. **Define jobs** within this file to install the Vercel CLI, authenticate using the Vercel token, and deploy the project to Vercel. Below is an example configuration:

```yaml
# Use the Node.js Docker image for the CI/CD environment
image: node:18.12.1

# Global variables configuration
variables:
  GIT_SUBMODULE_STRATEGY: "recursive" # Strategy for checking out Git submodules
  ZOLA_VERSION: "" # Optionally specify the Zola version used for building the site

# Job for deploying to a preview environment
deploy_preview:
  stage: deploy
  except:
    - main # Do not run this job on the main branch
  script:
    - npm install --global vercel # Install Vercel CLI globally
    - vercel pull --yes --environment=preview --token=$VERCEL_TOKEN # Pull project settings for the preview environment
    - vercel build --token=$VERCEL_TOKEN # Build the project
    - vercel deploy --prebuilt --token=$VERCEL_TOKEN # Deploy the prebuilt project

# Job for deploying to production
deploy_production:
  stage: deploy
  only:
    - main # Only run this job on the main branch
  script:
    - npm install --global vercel # Install Vercel CLI globally
    - vercel pull --yes --environment=production --token=$VERCEL_TOKEN # Pull project settings for the production environment
    - vercel build --prod --token=$VERCEL_TOKEN # Build the project for production
    - vercel deploy --prebuilt --prod --token=$VERCEL_TOKEN # Deploy the prebuilt project to production
```

#### d. Deploying My Site:
1. After configuring CI/CD, any push to the `main` branch in the GitLab repository triggers the deployment process. GitLab CI/CD uses the settings in `.gitlab-ci.yml` to deploy my site to Vercel.

## Website Content Structure

1. **Introduction:** A warm welcome and a brief overview of what visitors can expect to find.
2. **About Me:** An engaging narrative that provides insights into my personal and professional background.
3. **Main Content:**
   - **Awards:** A showcase of my achievements and recognitions.
   - **Skills:** A detailed list of my technical and soft skills.
   - **Professional Experience:** An overview of my career journey, highlighting key roles and contributions.
   - **Projects:** A portfolio of my work, including descriptions and outcomes of significant projects.
   - **Research:** An exposition of my research endeavors and their impact.
   - **Education:** A rundown of my academic background, including degrees and certifications.

## Launching the Web App

Discover the culmination of my professional and personal endeavors by visiting [Luopeiwen (Tina) Yi's Personal Website](https://tinaportfolio.vercel.app/). This website not only serves as a digital portfolio but also as a testament to my commitment to quality, innovation, and continuous learning.
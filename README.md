# Learn how to make a blog using Quarto with Virsual Studio Code
[Quarto Overview](https://quarto.org/)
## Get started
1. Download and install `Quarto` from https://quarto.org/docs/get-started/
2. Install `Quarto` extension on `VS code`
## Create a basic blog
1. Create and open a working folder in `VS code`.
2. `Ctrl+shift+P` and select `Quarto:Create Project` and then `Blog Project`. Name the working folder (project). The following files and folders will automatically created.
    - `posts` folder which contains `_metadata.yml` file and the following folders: `post-with-code` and `welcome`. 
        - The `post-with-code` folder contains the following files:
            - `image.jpg`
            - `index.jpg`
        - The `welcome` folder contains the following files:
            - `index.qmd`
            - `thumbnail.jpg`
    - `_quarto.yml`
    - `about.qmd`
    - `index.qmd`
    - `profile.jpg`
    - `styles.css`
3. (optional) Create a `README.md` file.
## Initialize emty `Git` respository
1. Open `Terminal` in `VS code` (`Ctrl+` `).
2. In the root of the working project, type:
    > `git init`
## Render
In `terminal`, type:
> `quarto render`

After rendering, the following file and folders will be added:
    - `.gitignore` which has `/.quarto/` inside (i.e. `.quarto` folder will not be tracked).
    - `_site` folder
    - `.quarto` folder

## Change project configuration
1. In `_quarto.yml`, use `docs`as the `output-dir`:
> `Project:`
>
>>   `Type: Website`
>
>>  `output-dir: docs`

Note: By default, `quarto` uses `.quarto` as the `output-dir`

2. In `terminal`, type:
> `quarto render`

After rendering and changing the config, `docs` will be created and used as the new `output-dir`.

3. Delete `.quarto` folder.

## Publish to GitHub
1. Add `nojekyll` to the root of your repository that tells GitHub Pages not to do additional processing of your published site using Jekyll (the GitHub default site generation tool):

    > **`Bash`**

    > `touch .nojekyll`

    > **`Windows Command Prompt`**

    > `copy NUL .nojekyll`

2. `git add .`
3. `git commit -m <message in quotes> `
4. Log in `GitHub` and create a new repository from `dashboard`. Give a name to the repository.
5. In `terminal`, type:

> git remote add origin https://github.com/your-github-username/your-repository-name.git

> git branch -M main

> git push -u origin main

6. Configure your GitHub repository to publish from the `docs` directory of your `main` branch. 
    - From `settings` in `GitHub`, go to `pages`.
    - Under `Build and deployment`, select `deploy from a branch` under `source`
    - Under `Branch`, select `main` and then `/docs`. 
    - click `Save`.


## Resources:
- [Quick guide from Quarto website](https://quarto.org/docs/websites/website-blog.html)
- [`markdown` guide](https://www.markdownguide.org/)
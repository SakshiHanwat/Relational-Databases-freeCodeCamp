# How to Use GitHub Pages to Deploy a Project

## Introduction

GitHub Pages is a very useful and free service provided by GitHub that allows developers to deploy **static websites** and **client-side applications** directly from a GitHub repository. It is mainly used for projects that do not require a back-end server. This means the application should run completely in the user's browser using HTML, CSS, and JavaScript.

GitHub Pages is especially popular for open-source projects because it is completely free and easy to use. It is commonly used for portfolios, documentation sites, learning projects, and simple web applications.

---

## What Kind of Projects Can Be Deployed?

GitHub Pages can deploy:

* Static websites
* Client-side applications
* Projects made with HTML, CSS, and JavaScript

GitHub Pages **cannot** deploy:

* Applications that require server-side logic
* Database-driven applications
* Backend frameworks like Node.js, Django, or Spring Boot (without static build)

In simple words, if your project runs fully in the browser, GitHub Pages is a good option.

---

## Example: Basic HTML Page

To deploy a project, you need at least an HTML file in your repository. Below is an example of a simple HTML page:

```
<!DOCTYPE html>
<html>
  <head>
    <title>freeCodeCamp</title>
    <link rel="stylesheet" href="./style.css" />
  </head>
  <body>
    <h1>Welcome to freeCodeCamp's Lessons!</h1>
    <p>Let's have some fun learning about Git and GitHub!</p>
  </body>
</html>
```

This file can be placed in the root folder of your GitHub repository.

---

## Steps to Deploy Using GitHub Pages

### Step 1: Open Repository Settings

* Go to your GitHub repository
* Click on the **Settings** tab
* From the left sidebar, select **Pages**

---

### Step 2: Choose Deployment Source

* Under the **Source** section, select **Deploy from a branch**
* This option is used when you are not using frameworks or GitHub Actions

---

### Step 3: Select Branch

* Choose the branch you want to deploy from
* Usually, this is the **main** branch

---

### Step 4: Select Folder

* Choose where your files are located:

  * Root folder (`/`)
  * Docs folder (`/docs`)

For beginners, the **root folder** is recommended. After selecting, click the **Save** button.

---

### Step 5: Custom Domain (Optional)

* After saving, you will see an option to add a custom domain
* If you own a domain, you can configure it using GitHub documentation
* For learning purposes, this field can be left empty

---

## GitHub Pages URL Structure

Once deployed, GitHub automatically provides a URL.

* Default format:

  * `username.github.io/repository-name`

### Example:

If:

* Username: `johndoe`
* Repository name: `my-portfolio`

Then the deployed URL will be:

`johndoe.github.io/my-portfolio`

Visiting this URL will show your live website.

---

## Automatic Updates

Whenever you push new changes to the deployed branch (usually `main`):

* GitHub Pages automatically updates the live site
* Deployment may take a few minutes
* Sometimes a hard refresh is needed to clear the browser cache

---

## Additional Features

* You can include CSS and JavaScript files
* You can build interactive and styled websites
* Front-end frameworks like React or Angular can also be deployed after building static files

---

## Conclusion

GitHub Pages is an excellent platform for beginners and professionals to deploy static websites easily. It is free, simple, and integrates perfectly with GitHub repositories. It is ideal for portfolios, documentation, and front-end learning projects.

---

## Practice Questions

### Question 1

**What type of applications can be deployed on GitHub Pages?**

* Static sites and client-side applications ✅

---

### Question 2

**If your GitHub username is `johndoe` and repository name is `my-portfolio`, what is the deployed URL?**

* `johndoe.github.io/my-portfolio` ✅

---

### Question 3

**When configuring GitHub Pages, what options must be specified?**

* The branch to deploy from and the folder location ✅

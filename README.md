## PublishWell: A Streamlined Journal Publishing Platform

[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]
[![LinkedIn][linkedin-shield]][linkedin-url]

**PublishWell** is an open-source platform designed to streamline the journal publishing process for both editors and authors. This project provides a user-friendly interface for:

* **Manuscript Submission:** Authors can easily submit their manuscripts for review, including relevant metadata.
* **Peer Review:** Editors can manage the peer-review process efficiently, assigning reviewers and managing feedback.
* **Publication Management:** Once articles are accepted, editors can handle the publication process, including formatting and dissemination.

**Features:**

* **Intuitive UI/UX:** Designed for ease of use by both editors and authors.
* **Streamlined Workflow:** Simplifies manuscript submission, review, and publication.
* **Scalability:** Built to accommodate a growing number of journals and submissions.
* **Open Source:** Accessible for developers to contribute and enhance.

**Getting Started:**

1. **Prerequisites:**
   - **.NET 8:** Ensure you have .NET 8 installed on your development machine. You can download it from the official Microsoft website: [https://dotnet.microsoft.com/en-us/download](https://dotnet.microsoft.com/en-us/download)
   - **Git:** Install Git for version control. You can download it from: [https://git-scm.com/downloads](https://git-scm.com/downloads)

2. **Clone the repository:**

```bash
git clone https://github.com/Smx27/PublishWell.git
```

3. **Install dependencies:**

```bash
cd PublishWell
dotnet restore
```

4. **Run the application:**

```bash
dotnet run
```

The application will start on `https://localhost:7094` (HTTPS) or `http://localhost:5254` (HTTP). You can access the Swagger UI at `/swagger`.

## Deployment to Railway

This application is configured for deployment to Railway. Follow these steps:

### Prerequisites

- A [Railway](https://railway.app/) account
- GitHub repository connected to Railway

### Deploy Steps

1. **Push your code to GitHub:**

```bash
git add .
git commit -m "Add Railway configuration"
git push origin master
```

2. **Create a new project on Railway:**
   - Go to [Railway](https://railway.app/)
   - Click "New Project"
   - Select "Deploy from GitHub repo"
   - Choose your repository

3. **Railway will automatically:**
   - Detect the Dockerfile
   - Build your application
   - Deploy it to a public URL

4. **Access your API:**
   - Railway will provide a public URL (e.g., `https://your-app.railway.app`)
   - Access Swagger at `https://your-app.railway.app/swagger`

### Environment Variables

Currently, the application uses default configuration. When you need to add environment variables (for databases, API keys, etc.), add them in Railway:

1. Go to your project in Railway
2. Click on "Variables"
3. Add your environment variables

**Common environment variables you might need:**

- `ASPNETCORE_ENVIRONMENT`: Set to `Production` for production deployments
- `ConnectionStrings__DefaultConnection`: Database connection string (when you add a database)
- Any API keys or secrets your application needs

### Adding a Database

When you're ready to add a database (PostgreSQL, MySQL, etc.):

1. **In Railway:**
   - Click "New" in your project
   - Select "Database" (e.g., PostgreSQL)
   - Railway will provision the database and provide connection details

2. **Update your application:**
   - Install the appropriate NuGet package (e.g., `Npgsql.EntityFrameworkCore.PostgreSQL`)
   - Configure your DbContext in `Program.cs`
   - Add the connection string to Railway's environment variables

3. **Example for PostgreSQL:**

```bash
dotnet add package Npgsql.EntityFrameworkCore.PostgreSQL
```

Then in `Program.cs`:

```csharp
builder.Services.AddDbContext<ApplicationDbContext>(options =>
    options.UseNpgsql(builder.Configuration.GetConnectionString("DefaultConnection")));
```

And set the `ConnectionStrings__DefaultConnection` variable in Railway to the database URL provided by Railway.

### Monitoring

- View logs in the Railway dashboard under "Deployments"
- Set up health checks and monitoring as needed

**Developing**

1. **Code Style:** We follow a consistent code style to improve readability and maintainability. Specific guidelines will be added in a separate document (e.g., `.editorconfig` or a dedicated style guide document).
2. **Testing:** Write unit tests for your code to ensure quality and prevent regressions. Consider using a testing framework like xUnit or NUnit.

**Contributing**

We welcome contributions from the academic publishing community! Please refer to the separate [`CONTRIBUTING.md`](./CONTRIBUTING.md) file for detailed guidelines on contributing your code and ideas.

**Additional Notes**

* This project is under active development. The provided instructions will be updated as features and functionality evolve.
* We encourage contributions of new features and bug fixes. Feel free to create pull requests!
* We strive to use the latest stable versions of dependencies whenever possible. Undocumented or non-officially supported features should be avoided.
* We recommend following best practices for secure development. This includes avoiding the use of deprecated packages or practices.

**License:**

PublishWell is licensed under the [**MIT**][license-url]. By contributing to this project, you agree to the terms of the license.

**Stay Updated**

* Watch this repository for updates.
* Feel free to create issues or discussions on GitHub.

<!-- ACKNOWLEDGMENTS -->
## Acknowledgments

Use this space to list resources you find helpful and would like to give credit to. I've included a few of my favorites to kick things off!

* [Choose an Open Source License](https://choosealicense.com)
* [GitHub Emoji Cheat Sheet](https://www.webpagefx.com/tools/emoji-cheat-sheet)
* [Malven's Flexbox Cheatsheet](https://flexbox.malven.co/)
* [Malven's Grid Cheatsheet](https://grid.malven.co/)
* [Img Shields](https://shields.io)
* [GitHub Pages](https://pages.github.com)
* [Font Awesome](https://fontawesome.com)
* [React Icons](https://react-icons.github.io/react-icons/search)
* [Readme Template](https://github.com/othneildrew/Best-README-Template)
<p align="right">(<a href="#readme-top">back to top</a>)</p>




<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/othneildrew/Best-README-Template.svg?style=for-the-badge
[contributors-url]: https://github.com/Smx27/PublishWell/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/othneildrew/Best-README-Template.svg?style=for-the-badge
[forks-url]: https://github.com/othneildrew/Best-README-Template/network/members
[stars-shield]: https://img.shields.io/github/stars/othneildrew/Best-README-Template.svg?style=for-the-badge
[stars-url]: https://github.com/othneildrew/Best-README-Template/stargazers
[issues-shield]: https://img.shields.io/github/issues/othneildrew/Best-README-Template.svg?style=for-the-badge
[issues-url]: https://github.com/othneildrew/Best-README-Template/issues
[license-shield]: https://img.shields.io/github/license/othneildrew/Best-README-Template.svg?style=for-the-badge
[license-url]: https://github.com/Smx27/PublishWell/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/othneildrew
[product-screenshot]: images/screenshot.png
[Next.js]: https://img.shields.io/badge/next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white
[Next-url]: https://nextjs.org/
[React.js]: https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB
[React-url]: https://reactjs.org/
[Vue.js]: https://img.shields.io/badge/Vue.js-35495E?style=for-the-badge&logo=vuedotjs&logoColor=4FC08D
[Vue-url]: https://vuejs.org/
[Angular.io]: https://img.shields.io/badge/Angular-DD0031?style=for-the-badge&logo=angular&logoColor=white
[Angular-url]: https://angular.io/
[Svelte.dev]: https://img.shields.io/badge/Svelte-4A4A55?style=for-the-badge&logo=svelte&logoColor=FF3E00
[Svelte-url]: https://svelte.dev/
[Laravel.com]: https://img.shields.io/badge/Laravel-FF2D20?style=for-the-badge&logo=laravel&logoColor=white
[Laravel-url]: https://laravel.com
[Bootstrap.com]: https://img.shields.io/badge/Bootstrap-563D7C?style=for-the-badge&logo=bootstrap&logoColor=white
[Bootstrap-url]: https://getbootstrap.com
[JQuery.com]: https://img.shields.io/badge/jQuery-0769AD?style=for-the-badge&logo=jquery&logoColor=white
[JQuery-url]: https://jquery.com 
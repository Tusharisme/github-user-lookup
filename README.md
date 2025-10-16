# GitHub User Lookup

This repository hosts a simple, client-side web application designed to quickly retrieve and display the account creation date of any GitHub user. Built with plain HTML, CSS, and JavaScript, it offers a straightforward interface to query the GitHub API.

## Overview

The **GitHub User Lookup** is a minimalist web tool that allows users to input a GitHub username and instantly view when that account was created. It's a fully client-side application, meaning all logic runs directly in your web browser without the need for a backend server. This project demonstrates basic web development principles, including form handling, asynchronous API calls, and dynamic DOM manipulation.

## How It Works

Upon entering a GitHub username into the designated input field and submitting the form, the application performs the following steps:

1.  **API Request:** It makes an asynchronous `GET` request to the GitHub REST API (`https://api.github.com/users/{username}`).
2.  **Token Support:** If a `?token=YOUR_API_TOKEN` parameter is present in the URL, this token is used to authenticate the API request, increasing rate limits and ensuring more reliable lookups for frequent users.
3.  **Data Processing:** Once the API response is received, the application parses the JSON data, specifically extracting the `created_at` field.
4.  **Display Result:** The extracted creation date is then formatted as `YYYY-MM-DD` (UTC) and displayed on the web page, typically within 5 seconds of submission, providing quick feedback to the user.
5.  **Error Handling:** Basic error handling is in place to inform the user if the username is not found or if there's an issue with the API request.

The entire process is managed client-side using standard web technologies (HTML, CSS, JavaScript) without any server-side dependencies.

## Project Structure

The repository maintains a clean and intuitive structure:

*   `index.html`: The main entry point of the web application. It defines the page's structure, including the input form and the area where results will be displayed.
*   `style.css`: Contains all the cascading style sheets responsible for the visual presentation and layout of the application.
*   `script.js`: Houses the core JavaScript logic. This includes handling form submissions, making API requests, processing responses, and updating the DOM to display results.
*   `/input/`: While this directory is present for potential use cases involving static data files (e.g., CSVs for local parsing with libraries like PapaParse or JSON for pre-loaded configurations), it is **not actively used for dynamic data loading** in this specific project, as the application primarily relies on live data fetched from the GitHub API.

## How to Use / Run

To get the application up and running:

1.  **Clone the Repository:**
    ```bash
    git clone https://github.com/your-github-username/github-user-lookup.git
    cd github-user-lookup
    ```
2.  **Open `index.html`:** Simply open the `index.html` file directly in your preferred web browser. You can do this by double-clicking the file or by navigating to it via your browser's file menu.
3.  **Enter a GitHub Username:** In the input field, type the GitHub username you wish to look up.
4.  **Submit:** Click the "Submit" button or press Enter. The creation date will appear below the form.

### Using an API Token (Optional)

For authenticated requests or to increase your GitHub API rate limits, you can append a `token` query parameter to your URL:

```
file:///path/to/github-user-lookup/index.html?token=YOUR_PERSONAL_ACCESS_TOKEN
```

Replace `YOUR_PERSONAL_ACCESS_TOKEN` with a valid GitHub Personal Access Token that has at least the `public_repo` scope.

## Technologies Used

*   **HTML5:** For structuring the web page content.
*   **CSS3:** For styling the user interface.
*   **JavaScript (ES6+):** For all client-side logic, including DOM manipulation and API calls (using the Fetch API).
*   **GitHub REST API:** The external service used to fetch user data.

## Deployment Notes

This application is designed for easy deployment to static hosting services like **GitHub Pages**.

To deploy to GitHub Pages:

1.  Push your code to the `main` branch of your repository.
2.  In your repository settings on GitHub, navigate to the "Pages" section.
3.  Select the `main` branch as the source for GitHub Pages and save.
4.  Your application will be live at `https://your-github-username.github.io/github-user-lookup/`.

Since it's a fully client-side application, no special server configuration or build process is required.

## License Notice

This project is open-source and available under the [MIT License](LICENSE).
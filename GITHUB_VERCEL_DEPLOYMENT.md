# Publish CommerceLens

CommerceLens is a static website. Its `index.html` is at the repository root, so it needs no framework build step, backend, or environment variables.

## Publish with GitHub Pages

1. Upload the project files to the root of the GitHub repository and commit them to `main`. Confirm that `index.html` is at the top level.
2. Open the repository's **Settings** and choose **Pages**.
3. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
4. Select branch **`main`** and folder **`/(root)`**, then click **Save**.
5. Wait for the Pages build to finish, then use **Visit site** in the Pages settings. The first publish can take several minutes.

For this repository, the expected project-site address is:

`https://shubhamsrivastavaofficials.github.io/CommerceLens-Online-Shopping-Analytics/`

GitHub's [publishing-source guide](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site) describes the branch and folder settings.

## Publish with Vercel (optional)

1. In Vercel, choose **New Project** and import the GitHub repository.
2. Keep the project root at the repository root. If asked for a framework, choose **Other**; leave the build command empty and serve the root folder.
3. Deploy, then open the assigned Vercel URL and confirm that the dashboard loads.

Before publishing publicly, review the repository contents. The bundled dataset is generated demonstration data; do not add private customer data, passwords, or API keys.

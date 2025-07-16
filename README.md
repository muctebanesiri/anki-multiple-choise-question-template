# hugo-papermod-farsi-template

To use this template Just change the url and then go to Settings > Pages > Build and Deployment > Source > Github Action. 

Also, remember to enable github actions from actions tab. 

For now, Hugo has some problems with Github Actions for example, the font doesn't render well ([+](https://dev.to/github/how-to-host-a-static-nextjs-site-on-github-pages-4pe0)). You should set your base url like this:
`<your-username>.github.io` not `<you-username>github.io/repo_path`. 

You should also name your repository with `<your-username>.github.io`.

If you want to use this with netlify. You do not need any configuration. Just remember to set publishdir to `public`. 

If you want to clone this repo:
```
git clone <repo_url>
git submodule update --init --recursive # clone submodules
```
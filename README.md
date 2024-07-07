* Step 1:<br>
_ Created fullstack-repo repository<br>
_ Changed setting of repo to include PAT for authentication<br>
_ Added github workflow action(.github/workflows/update_from_submodules.yml)(The workflow is set to trigger on a repository_dispatch event which is a custom event i used to notify the fullstack-repo that an update has occurred in one of its submodules)<br>
* Step 2:<br>
_ Created frontend-repo repository<br>
_ Added PAT to secrets in repo settings<br>
_ Added a webhook to send an HTTP POST request to the fullstack-repo when a push event occurs in this repo(POST request triggers the repository_dispatch event in the fullstack-repo which in turn triggers the GitHub Actions workflow defined in .github/workflows/update_from_submodules.yml)<br>
_ Added github workflow action(.github/workflows/trigger)(it is to trigger the webhook when changes are pushed to this repo and to ensure continuous integration)<br>
* Step 3:<br>
_ Created backend-repo repository<br>
_ Added PAT to secrets in repo settings<br>
_ Added a webhook to send an HTTP POST request to the fullstack-repo when a push event occurs in this repo(POST request triggers the repository_dispatch event in the fullstack-repo which in turn triggers the GitHub Actions workflow defined in .github/workflows/update_from_submodules.yml)<br>
_ Added github workflow action(.github/workflows/trigger)(it is to trigger the webhook when changes are pushed to this repo and to ensure continuous integration)<br>

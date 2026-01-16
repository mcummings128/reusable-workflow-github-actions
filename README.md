# reusable-workflow-github-actions
This repo relates to the Medium article [Github Actions: Creating, Calling, and Testing a Reusable Workflow](https://blog.devops.dev/github-actions-creating-calling-and-testing-a-reusable-workflow-08684d697609)

This repo contains a reusable workflow `reusable-workflow-2-teams.yml` that should be referencable by other workflows. In the article, we discuss how the repository `org-mushroom-kingdom/bash-git-script` uses its caller workflow `XXXX` to call upon this reusable workflow. `reusable-workflow-2-teams.yml` doesn't do anything too fancy--it pretty much does an API call to print the members of a provided team line by line. 
<br>
<br>
The important things to grasp here:
- The caller workflow is able to call the reusable workflow due the presence of the `workflow_call` event in the reusable workflow
- The reusable workflow receives input from the caller workflow, using the `inputs` and `secrets` context to access that input and perform logic.

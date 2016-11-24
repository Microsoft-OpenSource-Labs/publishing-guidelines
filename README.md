# Microsoft Open Source Labs Publishing Guidelines


## Minimum Requirements

Each laboratory needs to include the following files as a minimum to be deployed:

1. A *LICENSE* file with an MIT License template.
2. A *README.md* Markdown file with the description of the laboratory. You can find a description of the Markdown syntax [here](https://guides.github.com/features/mastering-markdown/).
    * You can use [Pandoc](http://pandoc.org/index.html) to convert your *docx* file to Markdown.
3. A *Word* file with the description of the laboratory.
4. A *PDF* file with the description of the laboratory. 
5. Any other supporting documents, file, source code, etc.


## Content

In order to maintain a standardized repository of laboratories, there is some content that needs to be included in every laboratory. This sections are required:

<dl>

  <dt>Overview and Pre-Requisites</dt>
  <dd>An Overview of the scope of the lab, any pre-requisites and topics covered on the lab should be clearly explained here.</dd>

  <dt>Laboratory section(s)</dt>
  <dd>Here is where the content of the lab is added. Several sections and/or subsections can be added.</dd>

  <dt>Conclusion</dt>
  <dd>A conclusion detailing what was done and any follow-up steps.</dd>

  <dt>End your Lab</dt>
  <dd>Here it should be explained how to clear, delete and release any used resources so the user doesn't get billed after the lab.</dd>

  <dt>Additional Resources and References</dt>
  <dd>Any additional resource, links, references should be added here.</dd>

  <dt>License</dt>
  <dd>The licensing and copyright information</dd>

</dl>


## How to create a lab repository?

Please send an email to [emeaosslabs@microsoft.com](mailto:emeaosslabs@microsoft.com) with the repository name, the tile for the lab, a short description of the lab and your GitHub personal username.
We will create the repository and it will be initialized with an initial skeleton and you will be added to the list of GitHub contributors for the repo.

The initial skeleton of the lab will include a License file, an empty template Word document, a template Markdown Readme file and a gitignore file.
 

## Git repository best practices 

> Some of the best practices and recommendations described in this guide in terms of *Git Branching Strategy* are based from this model: [http://nvie.com/posts/a-successful-git-branching-model/](http://nvie.com/posts/a-successful-git-branching-model/)

The branching strategy recommended to maintain your Lab follows a three-stages and tagging approach.

In order to create a new branch, you can run the following command:

     # git branch -b NAME_OF_BRANCH

In order to jump into your new branch, you can run the command:

     # git checkout NAME_OF_BRANCH


### Development Branch

The `development` branch is the current *working* branch, current changes and updates will be done here.


### Staging Branch

The `staging` branch will give us a *preview* of a new release of the lab.

In order to commit your development changes from `development` to `staging`, you can use:

     # git checkout staging
     # git merge --no-ff development


### Master Branch

The `master` branch is the latest stable release of the lab.


### Tags / Deployments

Each `master` branch commit needs to be `tagged`, so users can easily browse previous versions of the lab content.


#### Deploy script

The publishing guideline contains a script that will help you automate the steps mentioned above to commit to the `master` branch and create a new tag/deployment.

Please copy `scripts/deploy.sh` script to the root of your lab repository, the script can be executed using the command:

     # ./deploy.sh -v "NEW_VERSION" -m "COMMENT"

Where `NEW_VERSION` is the name of the version or tag to be used and  `COMMENT` is a note for the commit.

## Contributing

If you want to contribute to a laboratory, you can follow the GitHub guidelines in how to contribute to a project: [https://guides.github.com/activities/contributing-to-open-source/#contributing](https://guides.github.com/activities/contributing-to-open-source/#contributing).

Also, is possible to report a bug or issue on the lab trough the [GitHub Issues](https://github.com/Microsoft-OpenSource-Labs/publishing-guidelines/issues) page.

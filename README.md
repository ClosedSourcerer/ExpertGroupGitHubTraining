# ExpertGroupGitHubTraining

https://docs.github.com/en

https://docs.github.com/en/get-started/learning-about-github/github-glossary

https://www.eclipse.org/projects/training/

## Training Tasks:

- Basic Setup
  - Create a GitHub Account --> MUST be done in advance
  - Setup Two Factor Authentication --> SHOULD be done in advance
  - Add name, company and a picture to your account
- Basic GitHub Navigation
  - Find ClosedSourcerer, go to the Expert Group Training Repository, Star the repository,
  - Find catenax-ev and follow it
  - Find stephanbcbauer and have him inite you to catenax-ev, accept the invite
- Basic Process within the training repo:
  - Go to the training Repo via your profile and "Your stars"
  - Start a discussion, participate in another users discussion, create an issue from your discussion (or decide that it is unworthy and close the discussion)
  - Add Assignees to the Issue, add the issue to the project and fill the custom properties
  - Goto the correct project flip through the different views, plan your issue ()
  - Go back to the issue and create a branch from the issue
- Actually Working on a file
  - Select your branch and navigate to one of the MD files that is not README.md
  - Edit the file and commit the change to the branch
  - Create  Pull requests to merge this branch back into main and add ClosedSourcerer as a Reviewer
  - `Wait for ClosedSourcer to Review and Merge`
  - Delete the feature branch
- Creating Issues / Discussion directly from an existing file
  - Open one of the md files
  - go to either code or blame view 
  - click on a line number and choose "reference in new discussion" or "reference in new issue"

## History

![Version Control Why](src/VersionControl_Why.svg)

## Process

```mermaid
graph TD;
classDef main fill:#BF7100
    Z:::main
    A:::main
    B:::main
    D:::main
    E:::main
    F:::main
    G:::main
    I:::main
    J:::main
    Z[Start] -->|Create Discussion directly| A
    Z[Start] -->|Create Discussion from FileView| A
    Z[Start] -->|Create Issue directly| D
    Z[Start] -->|Create Issue from FileView| D
    A[Discussions]-->|Discuss|B{Decide};
    B-->|Close Discussion|C[END];
    B-->|Create issue from discussion and close discussion|D[Issues];
    D-->|Create a branch for this issue|E[Feature Branch];
    E-->|Create a Pull Request|F[Pull requests]
    F-->|Review Pull Request|G{Decide}
    G-->|Close pull requests|H[END]
    G-->|Merge pull requests|I[Main Branch]
    I-->J[SUCCESS]
```

- Setup a team
- Setup a repository
  - Wiki
  - Discussions
- Setup a project and link it to the repository
  - Setup your views:
    - board
    - roadmap
    - table
- Plan your project by starting discussions, creating issues and setting them up within the project
- Get yourself a team of people and set them up as commiters, reviewers etc.
- Start: Loop
  - Have your team pull issues
  - Have your team create feature-branches per issue
  - Have your team work on the issues
  - Have your team pull-requests the feature-branch back into the main-branch
  - Do reviews
  - Solve merge conflicts
  - Merge
  - Delete feature-branch
- End: Loop

### Feature Branches

![Version Control Process](src/VersionControl_Why_2.svg)

```mermaid
    %%{init: { 'logLevel': 'debug', 'theme': 'default' , 'themeVariables': {
              'git0': '#b3cb2d',
              'git1': '#ffa600',
              'git2': '#dd8200',
              'git3': '#bf7100',
            'gitBranchLabel0': '#000000',
            'gitBranchLabel1': '#000000',
            'gitBranchLabel2': '#000000',
            'gitBranchLabel3': '#000000',
            'commitLabelColor': '#f4f2f3',
            'commitLabelBackground': '#219dd4',
            'commitLabelFontSize': '14px'
       } } }%%
gitGraph
    commit id: "24.03"
    branch "Feature A"
    commit id: "Added Feature"
    commit id: "Create Pull Request"
    commit id: "Review"
    commit id: "Changes after Review"
    checkout main
    branch "Feature B"
    commit
    commit
    commit
    commit
    checkout main
    merge "Feature B" id: "Merged Feature B"
    commit id: "24.05"
    branch "Feature C"
    commit
    commit
    commit
    commit
    checkout main
    commit id: "Technical Maintenance"
    merge "Feature A" id: "Merged Feature A"
    merge "Feature C" id: "Merged Feature C"
    commit id: "24.08"

```


## Main View

![Repo Main View](src/Repo_Main_View.jpg)

- star a repository
  - mark it as a favorite
- watch a repository
  - request email notification
- fork a repository
  - create a copy that is still linked to the original
    - used to make pseudo backups
    - used to start your own thing based on someon elses work

## Branches

- Repositories start with the main branch
  - used to be called master
    - used to be called trunk
- If you create a new branch you must choose an existing branch as the basis for the new one.
- Better to only create branches from main and also merge them back only into main
- Never merge main into another branch
- You can branch a branch
  - We could use this to create a "ReleaseCandidate" branch and then create "Feature" branches from the "ReleaseCandidate" branch 
- A branch is a parallel version of a repository. It is contained within the repository, but does not affect the primary or main branch allowing you to work freely without disrupting the "live" version. When you've made the changes you want to make, you can merge your branch back into the main branch to publish your changes. 

## Commits

- Make changes to a file and commit them into the branch.
- The commit represents the changes to the file
- Commits be be tracked and commented
- A commit, or "revision", is an individual change to a file (or set of files). When you make a commit to save your work, Git creates a unique ID (a.k.a. the "SHA" or "hash") that allows you to keep record of the specific changes committed along with who made them and when. Commits usually contain a commit message which is a brief description of what changes were made.

## Merge

- Merges apply changes from one branch into another branch
- We merge via pull requests
- Never merge main into another branch
- We merge our multiple feature branches into our release candidate branch and than that branch finally back into main
- Merging takes the changes from one branch (in the same repository or from a fork), and applies them into another. This often happens as a "pull request" (which can be thought of as a request to merge), or via the command line. A merge can be done through a pull request via the GitHub.com web interface if there are no conflicting changes, or can always be done via the command line.

## Merge conflict
- Can appear when making a pull requests
- Can appear when multiple feature branches edit the same file and then try merging back into the main branch
- Some merge conflicts can be solved automatically
- A difference that occurs between merged branches. Merge conflicts happen when people make different changes to the same line of the same file, or when one person edits a file and another person deletes the same file. The merge conflict must be resolved before you can merge the branches.

## Pull Requests

- Used to requests that a branch gets merged into another branch
- Can be combined with a review process
- Develop your feature in a feature branch and then request to have it merged back into the main branch
- Merge conflicts have to be resolved before the merge can be executed
- Pull requests are proposed changes to a repository submitted by a user and accepted or rejected by a repository's collaborators. Like issues, pull requests each have their own discussion forum.

## Forks

- A copy of antoher repository, that still knows its source
- You can sync with the source and pull requests into the source
- A fork is a personal copy of another user's repository that lives on your account. Forks allow you to freely make changes to a project without affecting the original upstream repository. You can also open a pull request in the upstream repository and keep your fork synced with the latest changes since both repositories are still connected.

## Issues

![Issue_Overview](src/Issue_Overview.jpg)

![Issue_Single](src/Issue_Single.jpg)

- Create Issues
  - Assign them to projects
  - Assign them to users
  - Create a Branch directly from an issue


## Projects

![Project Overview](src/Project_Overview.jpg)

- You only need one project
- Projects support multiple views
- Projects support workflows

### Table

![Project Table](src/Project_Table.jpg)

- Have a detailed view of multiple items at once, including custom fields

### Board

![Project Board](src/Project_Board.jpg)

- Transiton items through status, akin to Kanban

### Roadmap

![Project Roadmap](src/Project_Roadmap.jpg)

- Plan items on a timeline, using Start/End Dates or predefined Iterations

## Discussions

![Discussions](src/Discussions.jpg)

- Announcements
- General
- Ideas
- Polls
- Q&A
- Show and Tell

- Ability to create Issues from the Discussion!

## View a File

### Preview

![File_Preview](src/File_Preview.jpg)

- Have a look at how GitHub is going to render this file
  - Image support
  - Latex support
  - Markdown support

**The Cauchy-Schwarz Inequality**

https://latex.codecogs.com/eqneditor/editor.php

```math
\left( \sum_{k=1}^n a_k b_k \right)^2 \leq \left( \sum_{k=1}^n a_k^2 \right) \left( \sum_{k=1}^n b_k^2 \right)
```

**Polygons**

```stl
 solid TEATEST 
facet normal  0.986544E+00  0.100166E+00  0.129220E+00
 outer loop
  vertex  0.167500E+02  0.505000E+02  0.000000E+00
  vertex  0.164599E+02  0.505000E+02  0.221480E+01
  vertex  0.166819E+02  0.483135E+02  0.221480E+01
 endloop
endfacet
facet normal  0.986495E+00  0.100374E+00  0.129434E+00
 outer loop
  vertex  0.166819E+02  0.483134E+02  0.221470E+01
  vertex  0.169653E+02  0.483840E+02  0.000000E+00
  vertex  0.167500E+02  0.505000E+02  0.000000E+00
 endloop
endfacet
facet normal  0.896653E+00  0.906029E-01  0.433363E+00
 outer loop
  vertex  0.164599E+02  0.505000E+02  0.221480E+01
  vertex  0.156953E+02  0.505000E+02  0.379680E+01
  vertex  0.159350E+02  0.481278E+02  0.379680E+01
 endloop
endfacet
facet normal  0.896343E+00  0.910681E-01  0.433908E+00
 outer loop
  vertex  0.159350E+02  0.481277E+02  0.379670E+01
  vertex  0.166819E+02  0.483135E+02  0.221480E+01
  vertex  0.164598E+02  0.505000E+02  0.221470E+01
 endloop
endfacet
facet normal  0.658333E+00  0.661382E-01  0.749815E+00
 outer loop
  vertex  0.156953E+02  0.505000E+02  0.379680E+01
  vertex  0.146142E+02  0.505000E+02  0.474600E+01
  vertex  0.148789E+02  0.478652E+02  0.474600E+01
 endloop
endfacet
facet normal  0.657713E+00  0.664906E-01  0.750328E+00
 outer loop
  vertex  0.148788E+02  0.478652E+02  0.474590E+01
  vertex  0.159350E+02  0.481278E+02  0.379680E+01
  vertex  0.156953E+02  0.505000E+02  0.379670E+01
 endloop
endfacet
facet normal  0.247314E+00  0.247069E-01  0.968620E+00
 outer loop
  vertex  0.146142E+02  0.505000E+02  0.474600E+01
  vertex  0.133750E+02  0.505000E+02  0.506240E+01
  vertex  0.136683E+02  0.475641E+02  0.506240E+01
 endloop
endfacet
facet normal  0.246900E+00  0.248503E-01  0.968722E+00
 outer loop
  vertex  0.136682E+02  0.475640E+02  0.506230E+01
  vertex  0.148789E+02  0.478652E+02  0.474600E+01
  vertex  0.146141E+02  0.505000E+02  0.474590E+01
 endloop
endfacet
facet normal -0.247296E+00 -0.246004E-01  0.968628E+00
 outer loop
  vertex  0.133750E+02  0.505000E+02  0.506240E+01
  vertex  0.121357E+02  0.505000E+02  0.474600E+01
  vertex  0.124577E+02  0.472631E+02  0.474600E+01
 endloop
endfacet
facet normal -0.247099E+00 -0.246526E-01  0.968677E+00
 outer loop
  vertex  0.124576E+02  0.472630E+02  0.474590E+01
  vertex  0.136683E+02  0.475641E+02  0.506240E+01
  vertex  0.133750E+02  0.505000E+02  0.506230E+01
 endloop
endfacet
facet normal -0.658371E+00 -0.652821E-01  0.749858E+00
 outer loop
  vertex  0.121357E+02  0.505000E+02  0.474600E+01
  vertex  0.110546E+02  0.505000E+02  0.379680E+01
  vertex  0.114016E+02  0.470005E+02  0.379680E+01
 endloop
endfacet
facet normal -0.657983E+00 -0.654316E-01  0.750185E+00
 outer loop
  vertex  0.114015E+02  0.470004E+02  0.379670E+01
  vertex  0.124577E+02  0.472631E+02  0.474600E+01
  vertex  0.121357E+02  0.505000E+02  0.474590E+01
 endloop
endfacet
facet normal -0.896806E+00 -0.887243E-01  0.433437E+00
 outer loop
  vertex  0.110546E+02  0.505000E+02  0.379680E+01
  vertex  0.102900E+02  0.505000E+02  0.221480E+01
  vertex  0.106546E+02  0.468147E+02  0.221480E+01
 endloop
endfacet
facet normal -0.896617E+00 -0.889192E-01  0.433787E+00
 outer loop
  vertex  0.106546E+02  0.468147E+02  0.221470E+01
  vertex  0.114016E+02  0.470005E+02  0.379680E+01
  vertex  0.110545E+02  0.505000E+02  0.379670E+01
 endloop
endfacet
facet normal -0.986807E+00 -0.975587E-01  0.129210E+00
 outer loop
  vertex  0.102900E+02  0.505000E+02  0.221480E+01
  vertex  0.100000E+02  0.505000E+02  0.000000E+00
  vertex  0.103713E+02  0.467443E+02  0.000000E+00
 endloop
endfacet
facet normal -0.986777E+00 -0.976488E-01  0.129369E+00
 outer loop
  vertex  0.103712E+02  0.467443E+02  0.000000E+00
  vertex  0.106546E+02  0.468147E+02  0.221480E+01
  vertex  0.102899E+02  0.505000E+02  0.221470E+01
 endloop
endfacet
facet normal  0.956944E+00  0.259185E+00  0.130698E+00
 outer loop
  vertex  0.169653E+02  0.483840E+02  0.000000E+00
  vertex  0.166819E+02  0.483135E+02  0.221480E+01
  vertex  0.173653E+02  0.457903E+02  0.221480E+01
 endloop
endfacet
facet normal  0.957821E+00  0.257184E+00  0.128202E+00
 outer loop
  vertex  0.173652E+02  0.457902E+02  0.221470E+01
  vertex  0.176289E+02  0.459121E+02  0.000000E+00
  vertex  0.169652E+02  0.483839E+02  0.000000E+00
 endloop
endfacet
facet normal  0.866751E+00  0.239721E+00  0.437353E+00
 outer loop
  vertex  0.166819E+02  0.483135E+02  0.221480E+01
  vertex  0.159350E+02  0.481278E+02  0.379680E+01
  vertex  0.166703E+02  0.454692E+02  0.379680E+01
 endloop
endfacet
facet normal  0.871116E+00  0.235965E+00  0.430672E+00
 outer loop
  vertex  0.166702E+02  0.454692E+02  0.379670E+01
  vertex  0.173653E+02  0.457903E+02  0.221480E+01
  vertex  0.166819E+02  0.483134E+02  0.221470E+01
 endloop
endfacet
facet normal  0.632534E+00  0.179529E+00  0.753439E+00
 outer loop
  vertex  0.159350E+02  0.481278E+02  0.379680E+01
  vertex  0.148789E+02  0.478652E+02  0.474600E+01
  vertex  0.156878E+02  0.450152E+02  0.474600E+01
 endloop
endfacet
facet normal  0.640235E+00  0.177107E+00  0.747484E+00
 outer loop
  vertex  0.156878E+02  0.450152E+02  0.474590E+01
  vertex  0.166703E+02  0.454692E+02  0.379680E+01
  vertex  0.159350E+02  0.481277E+02  0.379670E+01
 endloop
endfacet
facet normal  0.236227E+00  0.687446E-01  0.969263E+00
 outer loop
  vertex  0.148789E+02  0.478652E+02  0.474600E+01
  vertex  0.136683E+02  0.475641E+02  0.506240E+01
  vertex  0.145615E+02  0.444948E+02  0.506240E+01
 endloop
endfacet
facet normal  0.240362E+00  0.682629E-01  0.968280E+00
 outer loop
  vertex  0.145614E+02  0.444948E+02  0.506230E+01
  vertex  0.156878E+02  0.450152E+02  0.474600E+01
  vertex  0.148788E+02  0.478652E+02  0.474590E+01
 endloop
endfacet
facet normal -0.235888E+00 -0.701130E-01  0.969248E+00
 outer loop
  vertex  0.136683E+02  0.475641E+02  0.506240E+01
  vertex  0.124577E+02  0.472631E+02  0.474600E+01
  vertex  0.134352E+02  0.439744E+02  0.474600E+01
 endloop
endfacet
facet normal -0.239835E+00 -0.697734E-01  0.968303E+00
 outer loop
  vertex  0.134351E+02  0.439743E+02  0.474590E+01
  vertex  0.145615E+02  0.444948E+02  0.506240E+01
  vertex  0.136682E+02  0.475640E+02  0.506230E+01
 endloop
endfacet
facet normal -0.629686E+00 -0.190172E+00  0.753213E+00
 outer loop
  vertex  0.124577E+02  0.472631E+02  0.474600E+01
  vertex  0.114016E+02  0.470005E+02  0.379680E+01
  vertex  0.124526E+02  0.435205E+02  0.379680E+01
 endloop
endfacet
facet normal -0.635720E+00 -0.188957E+00  0.748435E+00
 outer loop
  vertex  0.124525E+02  0.435205E+02  0.379670E+01
  vertex  0.134352E+02  0.439744E+02  0.474600E+01
  vertex  0.124576E+02  0.472630E+02  0.474590E+01
 endloop
endfacet
facet normal -0.860286E+00 -0.262490E+00  0.437044E+00
 outer loop
  vertex  0.114016E+02  0.470005E+02  0.379680E+01
  vertex  0.106546E+02  0.468147E+02  0.221480E+01
  vertex  0.117577E+02  0.431994E+02  0.221480E+01
 endloop
endfacet
facet normal -0.863284E+00 -0.260742E+00  0.432151E+00
 outer loop
  vertex  0.117576E+02  0.431994E+02  0.221470E+01
  vertex  0.124526E+02  0.435205E+02  0.379680E+01
  vertex  0.114015E+02  0.470004E+02  0.379670E+01
 endloop
endfacet
facet normal -0.948000E+00 -0.290292E+00  0.130488E+00
 outer loop
  vertex  0.106546E+02  0.468147E+02  0.221480E+01
  vertex  0.103713E+02  0.467443E+02  0.000000E+00
  vertex  0.114941E+02  0.430776E+02  0.000000E+00
 endloop
endfacet
facet normal -0.948495E+00 -0.289401E+00  0.128859E+00
 outer loop
  vertex  0.114940E+02  0.430775E+02  0.000000E+00
  vertex  0.117577E+02  0.431994E+02  0.221480E+01
  vertex  0.106546E+02  0.468147E+02  0.221470E+01
 endloop
endfacet
facet normal  0.912149E+00  0.388716E+00  0.129940E+00
 outer loop
  vertex  0.176289E+02  0.459121E+02  0.000000E+00
  vertex  0.173653E+02  0.457903E+02  0.221480E+01
  vertex  0.185356E+02  0.430441E+02  0.221480E+01
 endloop
endfacet
facet normal  0.914942E+00  0.384341E+00  0.123137E+00
 outer loop
  vertex  0.185356E+02  0.430441E+02  0.221470E+01
  vertex  0.187670E+02  0.432028E+02  0.000000E+00
  vertex  0.176289E+02  0.459121E+02  0.000000E+00
 endloop
endfacet
facet normal  0.823481E+00  0.363549E+00  0.435559E+00
 outer loop
  vertex  0.173653E+02  0.457903E+02  0.221480E+01
  vertex  0.166703E+02  0.454692E+02  0.379680E+01
  vertex  0.179256E+02  0.426258E+02  0.379680E+01
 endloop
endfacet
facet normal  0.836246E+00  0.356427E+00  0.416717E+00
 outer loop
  vertex  0.179256E+02  0.426258E+02  0.379670E+01
  vertex  0.185356E+02  0.430441E+02  0.221480E+01
  vertex  0.173652E+02  0.457902E+02  0.221470E+01
 endloop
endfacet
facet normal  0.598716E+00  0.276210E+00  0.751830E+00
 outer loop
  vertex  0.166703E+02  0.454692E+02  0.379680E+01
  vertex  0.156878E+02  0.450152E+02  0.474600E+01
  vertex  0.170630E+02  0.420343E+02  0.474600E+01
 endloop
endfacet
facet normal  0.620509E+00  0.273989E+00  0.734778E+00
 outer loop
  vertex  0.170629E+02  0.420343E+02  0.474590E+01
  vertex  0.179256E+02  0.426258E+02  0.379680E+01
  vertex  0.166702E+02  0.454692E+02  0.379670E+01
 endloop
endfacet
facet normal  0.222625E+00  0.107308E+00  0.968981E+00
 outer loop
  vertex  0.156878E+02  0.450152E+02  0.474600E+01
  vertex  0.145615E+02  0.444948E+02  0.506240E+01
  vertex  0.160743E+02  0.413563E+02  0.506240E+01
 endloop
endfacet
facet normal  0.234750E+00  0.108331E+00  0.966000E+00
 outer loop
  vertex  0.160743E+02  0.413563E+02  0.506230E+01
  vertex  0.170630E+02  0.420343E+02  0.474600E+01
  vertex  0.156878E+02  0.450152E+02  0.474590E+01
 endloop
endfacet
facet normal -0.221060E+00 -0.110681E+00  0.968959E+00
 outer loop
  vertex  0.145615E+02  0.444948E+02  0.506240E+01
  vertex  0.134352E+02  0.439744E+02  0.474600E+01
  vertex  0.150855E+02  0.406783E+02  0.474600E+01
 endloop
endfacet
facet normal -0.232415E+00 -0.112004E+00  0.966146E+00
 outer loop
  vertex  0.150854E+02  0.406782E+02  0.474590E+01
  vertex  0.160743E+02  0.413563E+02  0.506240E+01
  vertex  0.145614E+02  0.444948E+02  0.506230E+01
 endloop
endfacet
facet normal -0.586341E+00 -0.302315E+00  0.751538E+00
 outer loop
  vertex  0.134352E+02  0.439744E+02  0.474600E+01
  vertex  0.124526E+02  0.435205E+02  0.379680E+01
  vertex  0.142230E+02  0.400868E+02  0.379680E+01
 endloop
endfacet
facet normal -0.604035E+00 -0.302435E+00  0.737343E+00
 outer loop
  vertex  0.142229E+02  0.400867E+02  0.379670E+01
  vertex  0.150855E+02  0.406783E+02  0.474600E+01
  vertex  0.134351E+02  0.439743E+02  0.474590E+01
 endloop
endfacet
facet normal -0.797046E+00 -0.418805E+00  0.435110E+00
 outer loop
  vertex  0.124526E+02  0.435205E+02  0.379680E+01
  vertex  0.117577E+02  0.431994E+02  0.221480E+01
  vertex  0.136130E+02  0.396685E+02  0.221480E+01
 endloop
endfacet
facet normal -0.806263E+00 -0.415716E+00  0.420856E+00
 outer loop
  vertex  0.136129E+02  0.396684E+02  0.221470E+01
  vertex  0.142230E+02  0.400868E+02  0.379680E+01
  vertex  0.124525E+02  0.435205E+02  0.379670E+01
 endloop
endfacet
facet normal -0.876455E+00 -0.463654E+00  0.129812E+00
 outer loop
  vertex  0.117577E+02  0.431994E+02  0.221480E+01
  vertex  0.114941E+02  0.430776E+02  0.000000E+00
  vertex  0.133815E+02  0.395098E+02  0.000000E+00
 endloop
endfacet
facet normal -0.878295E+00 -0.461518E+00  0.124893E+00
 outer loop
  vertex  0.133815E+02  0.395097E+02  0.000000E+00
  vertex  0.136130E+02  0.396685E+02  0.221480E+01
  vertex  0.117576E+02  0.431994E+02  0.221470E+01
 endloop
endfacet
facet normal  0.854622E+00  0.503882E+00  0.125395E+00
 outer loop
  vertex  0.187670E+02  0.432028E+02  0.000000E+00
  vertex  0.185356E+02  0.430441E+02  0.221480E+01
  vertex  0.202189E+02  0.401891E+02  0.221480E+01
 endloop
endfacet
facet normal  0.859461E+00  0.498207E+00  0.114527E+00
 outer loop
  vertex  0.202189E+02  0.401890E+02  0.221470E+01
  vertex  0.204062E+02  0.403750E+02  0.000000E+00
  vertex  0.187670E+02  0.432028E+02  0.000000E+00
 endloop
endfacet
facet normal  0.771851E+00  0.474584E+00  0.423103E+00
 outer loop
  vertex  0.185356E+02  0.430441E+02  0.221480E+01
  vertex  0.179256E+02  0.426258E+02  0.379680E+01
  vertex  0.197250E+02  0.396993E+02  0.379680E+01
 endloop
endfacet
facet normal  0.792432E+00  0.467229E+00  0.392109E+00
 outer loop
  vertex  0.197250E+02  0.396992E+02  0.379670E+01
  vertex  0.202189E+02  0.401891E+02  0.221480E+01
  vertex  0.185356E+02  0.430441E+02  0.221470E+01
 endloop
endfacet
facet normal  0.563911E+00  0.365789E+00  0.740407E+00
 outer loop
  vertex  0.179256E+02  0.426258E+02  0.379680E+01
  vertex  0.170630E+02  0.420343E+02  0.474600E+01
  vertex  0.190269E+02  0.390067E+02  0.474600E+01
 endloop
endfacet
facet normal  0.599654E+00  0.368730E+00  0.710249E+00
 outer loop
  vertex  0.190268E+02  0.390066E+02  0.474590E+01
  vertex  0.197250E+02  0.396993E+02  0.379680E+01
  vertex  0.179256E+02  0.426258E+02  0.379670E+01
 endloop
endfacet
facet normal  0.210563E+00  0.144162E+00  0.966892E+00
 outer loop
  vertex  0.170630E+02  0.420343E+02  0.474600E+01
  vertex  0.160743E+02  0.413563E+02  0.506240E+01
  vertex  0.182265E+02  0.382128E+02  0.506240E+01
 endloop
endfacet
facet normal  0.231107E+00  0.149950E+00  0.961304E+00
 outer loop
  vertex  0.182264E+02  0.382127E+02  0.506230E+01
  vertex  0.190269E+02  0.390067E+02  0.474600E+01
  vertex  0.170629E+02  0.420343E+02  0.474590E+01
 endloop
endfacet
facet normal -0.207306E+00 -0.148874E+00  0.966882E+00
 outer loop
  vertex  0.160743E+02  0.413563E+02  0.506240E+01
  vertex  0.150855E+02  0.406783E+02  0.474600E+01
  vertex  0.174262E+02  0.374189E+02  0.474600E+01
 endloop
endfacet
facet normal -0.226481E+00 -0.155030E+00  0.961599E+00
 outer loop
  vertex  0.174262E+02  0.374188E+02  0.474590E+01
  vertex  0.182265E+02  0.382128E+02  0.506240E+01
  vertex  0.160743E+02  0.413563E+02  0.506230E+01
 endloop
endfacet
facet normal -0.539059E+00 -0.401840E+00  0.740230E+00
 outer loop
  vertex  0.150855E+02  0.406783E+02  0.474600E+01
  vertex  0.142230E+02  0.400868E+02  0.379680E+01
  vertex  0.167280E+02  0.367264E+02  0.379680E+01
 endloop
endfacet
facet normal -0.567783E+00 -0.407755E+00  0.715093E+00
 outer loop
  vertex  0.167280E+02  0.367263E+02  0.379670E+01
  vertex  0.174262E+02  0.374189E+02  0.474600E+01
  vertex  0.150854E+02  0.406782E+02  0.474590E+01
 endloop
endfacet
facet normal -0.720103E+00 -0.549960E+00  0.423079E+00
 outer loop
  vertex  0.142230E+02  0.400868E+02  0.379680E+01
  vertex  0.136130E+02  0.396685E+02  0.221480E+01
  vertex  0.162341E+02  0.362365E+02  0.221480E+01
 endloop
endfacet
facet normal -0.735083E+00 -0.547991E+00  0.399199E+00
 outer loop
  vertex  0.162341E+02  0.362364E+02  0.221470E+01
  vertex  0.167280E+02  0.367264E+02  0.379680E+01
  vertex  0.142229E+02  0.400867E+02  0.379670E+01
 endloop
endfacet
facet normal -0.785865E+00 -0.605524E+00  0.125530E+00
 outer loop
  vertex  0.136130E+02  0.396685E+02  0.221480E+01
  vertex  0.133815E+02  0.395098E+02  0.000000E+00
  vertex  0.160468E+02  0.360507E+02  0.000000E+00
 endloop
endfacet
facet normal -0.789229E+00 -0.602790E+00  0.117311E+00
 outer loop
  vertex  0.160468E+02  0.360507E+02  0.000000E+00
  vertex  0.162341E+02  0.362365E+02  0.221480E+01
  vertex  0.136129E+02  0.396684E+02  0.221470E+01
 endloop
endfacet
facet normal  0.783178E+00  0.610598E+00  0.117482E+00
 outer loop
  vertex  0.204062E+02  0.403750E+02  0.000000E+00
  vertex  0.202189E+02  0.401891E+02  0.221480E+01
  vertex  0.224408E+02  0.373392E+02  0.221480E+01
 endloop
endfacet
facet normal  0.789524E+00  0.604867E+00  0.103865E+00
 outer loop
  vertex  0.224407E+02  0.373391E+02  0.221470E+01
  vertex  0.225727E+02  0.375471E+02  0.000000E+00
  vertex  0.204062E+02  0.403750E+02  0.000000E+00
 endloop
endfacet
facet normal  0.710380E+00  0.578491E+00  0.400886E+00
 outer loop
  vertex  0.202189E+02  0.401891E+02  0.221480E+01
  vertex  0.197250E+02  0.396993E+02  0.379680E+01
  vertex  0.220931E+02  0.367913E+02  0.379680E+01
 endloop
endfacet
facet normal  0.735628E+00  0.573559E+00  0.360391E+00
 outer loop
  vertex  0.220930E+02  0.367913E+02  0.379670E+01
  vertex  0.224408E+02  0.373392E+02  0.221480E+01
  vertex  0.202189E+02  0.401890E+02  0.221470E+01
 endloop
endfacet
facet normal  0.526953E+00  0.453744E+00  0.718636E+00
 outer loop
  vertex  0.197250E+02  0.396993E+02  0.379680E+01
  vertex  0.190269E+02  0.390067E+02  0.474600E+01
  vertex  0.216015E+02  0.360167E+02  0.474600E+01
 endloop
endfacet
facet normal  0.571462E+00  0.465404E+00  0.675892E+00
 outer loop
  vertex  0.216014E+02  0.360167E+02  0.474590E+01
  vertex  0.220931E+02  0.367913E+02  0.379680E+01
  vertex  0.197250E+02  0.396992E+02  0.379670E+01
 endloop
endfacet
facet normal  0.199862E+00  0.182190E+00  0.962737E+00
 outer loop
  vertex  0.190269E+02  0.390067E+02  0.474600E+01
  vertex  0.182265E+02  0.382128E+02  0.506240E+01
  vertex  0.210379E+02  0.351287E+02  0.506240E+01
 endloop
endfacet
facet normal  0.227153E+00  0.195641E+00  0.954005E+00
 outer loop
  vertex  0.210379E+02  0.351287E+02  0.506230E+01
  vertex  0.216015E+02  0.360167E+02  0.474600E+01
  vertex  0.190268E+02  0.390066E+02  0.474590E+01
 endloop
endfacet
facet normal -0.195057E+00 -0.187078E+00  0.962785E+00
 outer loop
  vertex  0.182265E+02  0.382128E+02  0.506240E+01
  vertex  0.174262E+02  0.374189E+02  0.474600E+01
  vertex  0.204744E+02  0.342407E+02  0.474600E+01
 endloop
endfacet
facet normal -0.220046E+00 -0.200572E+00  0.954647E+00
 outer loop
  vertex  0.204743E+02  0.342406E+02  0.474590E+01
  vertex  0.210379E+02  0.351287E+02  0.506240E+01
  vertex  0.182264E+02  0.382127E+02  0.506230E+01
 endloop
endfacet
facet normal -0.491503E+00 -0.490658E+00  0.719499E+00
 outer loop
  vertex  0.174262E+02  0.374189E+02  0.474600E+01
  vertex  0.167280E+02  0.367264E+02  0.379680E+01
  vertex  0.199827E+02  0.334661E+02  0.379680E+01
 endloop
endfacet
facet normal -0.526205E+00 -0.504675E+00  0.684406E+00
 outer loop
  vertex  0.199827E+02  0.334660E+02  0.379670E+01
  vertex  0.204744E+02  0.342407E+02  0.474600E+01
  vertex  0.174262E+02  0.374188E+02  0.474590E+01
 endloop
endfacet
facet normal -0.639297E+00 -0.655211E+00  0.402488E+00
 outer loop
  vertex  0.167280E+02  0.367264E+02  0.379680E+01
  vertex  0.162341E+02  0.362365E+02  0.221480E+01
  vertex  0.196350E+02  0.329182E+02  0.221480E+01
 endloop
endfacet
facet normal -0.657046E+00 -0.655926E+00  0.371554E+00
 outer loop
  vertex  0.196350E+02  0.329182E+02  0.221470E+01
  vertex  0.199827E+02  0.334661E+02  0.379680E+01
  vertex  0.167280E+02  0.367263E+02  0.379670E+01
 endloop
endfacet
facet normal -0.690072E+00 -0.714014E+00  0.118256E+00
 outer loop
  vertex  0.162341E+02  0.362365E+02  0.221480E+01
  vertex  0.160468E+02  0.360507E+02  0.000000E+00
  vertex  0.195031E+02  0.327103E+02  0.000000E+00
 endloop
endfacet
facet normal -0.694255E+00 -0.711555E+00  0.108170E+00
 outer loop
  vertex  0.195030E+02  0.327103E+02  0.000000E+00
  vertex  0.196350E+02  0.329182E+02  0.221480E+01
  vertex  0.162341E+02  0.362364E+02  0.221470E+01
 endloop
endfacet
facet normal  0.695845E+00  0.710012E+00  0.108089E+00
 outer loop
  vertex  0.225727E+02  0.375471E+02  0.000000E+00
  vertex  0.224408E+02  0.373392E+02  0.221480E+01
  vertex  0.252272E+02  0.346084E+02  0.221480E+01
 endloop
endfacet
facet normal  0.702563E+00  0.705389E+00  0.939699E-01
 outer loop
  vertex  0.252271E+02  0.346083E+02  0.221470E+01
  vertex  0.252929E+02  0.348378E+02  0.000000E+00
  vertex  0.225727E+02  0.375471E+02  0.000000E+00
 endloop
endfacet
facet normal  0.635843E+00  0.675348E+00  0.373643E+00
 outer loop
  vertex  0.224408E+02  0.373392E+02  0.221480E+01
  vertex  0.220931E+02  0.367913E+02  0.379680E+01
  vertex  0.250540E+02  0.340036E+02  0.379680E+01
 endloop
endfacet
facet normal  0.660681E+00  0.674193E+00  0.330096E+00
 outer loop
  vertex  0.250540E+02  0.340036E+02  0.379670E+01
  vertex  0.252272E+02  0.346084E+02  0.221480E+01
  vertex  0.224407E+02  0.373391E+02  0.221470E+01
 endloop
endfacet
facet normal  0.482425E+00  0.539476E+00  0.690096E+00
 outer loop
  vertex  0.220931E+02  0.367913E+02  0.379680E+01
  vertex  0.216015E+02  0.360167E+02  0.474600E+01
  vertex  0.248090E+02  0.331484E+02  0.474600E+01
 endloop
endfacet
facet normal  0.526650E+00  0.559413E+00  0.640076E+00
 outer loop
  vertex  0.248090E+02  0.331483E+02  0.474590E+01
  vertex  0.250540E+02  0.340036E+02  0.379680E+01
  vertex  0.220930E+02  0.367913E+02  0.379670E+01
 endloop
endfacet
facet normal  0.187977E+00  0.221623E+00  0.956843E+00
 outer loop
  vertex  0.216015E+02  0.360167E+02  0.474600E+01
  vertex  0.210379E+02  0.351287E+02  0.506240E+01
  vertex  0.245283E+02  0.321682E+02  0.506240E+01
 endloop
endfacet
facet normal  0.217155E+00  0.242875E+00  0.945439E+00
 outer loop
  vertex  0.245282E+02  0.321682E+02  0.506230E+01
  vertex  0.248090E+02  0.331484E+02  0.474600E+01
  vertex  0.216014E+02  0.360167E+02  0.474590E+01
 endloop
endfacet
facet normal -0.182308E+00 -0.225324E+00  0.957075E+00
 outer loop
  vertex  0.210379E+02  0.351287E+02  0.506240E+01
  vertex  0.204744E+02  0.342407E+02  0.474600E+01
  vertex  0.242475E+02  0.311879E+02  0.474600E+01
 endloop
endfacet
facet normal -0.208560E+00 -0.245858E+00  0.946603E+00
 outer loop
  vertex  0.242474E+02  0.311879E+02  0.474590E+01
  vertex  0.245283E+02  0.321682E+02  0.506240E+01
  vertex  0.210379E+02  0.351287E+02  0.506230E+01
 endloop
endfacet
facet normal -0.443018E+00 -0.568374E+00  0.693315E+00
 outer loop
  vertex  0.204744E+02  0.342407E+02  0.474600E+01
  vertex  0.199827E+02  0.334661E+02  0.379680E+01
  vertex  0.240026E+02  0.303328E+02  0.379680E+01
 endloop
endfacet
facet normal -0.476257E+00 -0.588642E+00  0.653207E+00
 outer loop
  vertex  0.240025E+02  0.303327E+02  0.379670E+01
  vertex  0.242475E+02  0.311879E+02  0.474600E+01
  vertex  0.204743E+02  0.342406E+02  0.474590E+01
 endloop
endfacet
facet normal -0.560401E+00 -0.736761E+00  0.378332E+00
 outer loop
  vertex  0.199827E+02  0.334661E+02  0.379680E+01
  vertex  0.196350E+02  0.329182E+02  0.221480E+01
  vertex  0.238293E+02  0.297279E+02  0.221480E+01
 endloop
endfacet
facet normal -0.576745E+00 -0.739953E+00  0.346172E+00
 outer loop
  vertex  0.238292E+02  0.297278E+02  0.221470E+01
  vertex  0.240026E+02  0.303328E+02  0.379680E+01
  vertex  0.199827E+02  0.334660E+02  0.379670E+01
 endloop
endfacet
facet normal -0.598307E+00 -0.793663E+00  0.110132E+00
 outer loop
  vertex  0.196350E+02  0.329182E+02  0.221480E+01
  vertex  0.195031E+02  0.327103E+02  0.000000E+00
  vertex  0.237636E+02  0.294985E+02  0.000000E+00
 endloop
endfacet
facet normal -0.602372E+00 -0.791937E+00  0.999211E-01
 outer loop
  vertex  0.237635E+02  0.294985E+02  0.000000E+00
  vertex  0.238293E+02  0.297279E+02  0.221480E+01
  vertex  0.196350E+02  0.329182E+02  0.221470E+01
 endloop
endfacet
facet normal  0.591690E+00  0.799889E+00  0.100402E+00
 outer loop
  vertex  0.252929E+02  0.348378E+02  0.000000E+00
  vertex  0.252272E+02  0.346084E+02  0.221480E+01
  vertex  0.286039E+02  0.321106E+02  0.221480E+01
 endloop
endfacet
facet normal  0.597087E+00  0.797219E+00  0.890499E-01
 outer loop
  vertex  0.286039E+02  0.321105E+02  0.221470E+01
  vertex  0.285932E+02  0.323659E+02  0.000000E+00
  vertex  0.252929E+02  0.348377E+02  0.000000E+00
 endloop
endfacet
facet normal  0.545758E+00  0.761028E+00  0.350691E+00
 outer loop
  vertex  0.252272E+02  0.346084E+02  0.221480E+01
  vertex  0.250540E+02  0.340036E+02  0.379680E+01
  vertex  0.286320E+02  0.314377E+02  0.379680E+01
 endloop
endfacet
facet normal  0.564462E+00  0.763145E+00  0.314631E+00
 outer loop
  vertex  0.286319E+02  0.314377E+02  0.379670E+01
  vertex  0.286039E+02  0.321106E+02  0.221480E+01
  vertex  0.252271E+02  0.346083E+02  0.221470E+01
 endloop
endfacet
facet normal  0.424253E+00  0.615583E+00  0.664128E+00
 outer loop
  vertex  0.250540E+02  0.340036E+02  0.379680E+01
  vertex  0.248090E+02  0.331484E+02  0.474600E+01
  vertex  0.286718E+02  0.304862E+02  0.474600E+01
 endloop
endfacet
facet normal  0.457218E+00  0.637588E+00  0.620027E+00
 outer loop
  vertex  0.286718E+02  0.304862E+02  0.474590E+01
  vertex  0.286320E+02  0.314377E+02  0.379680E+01
  vertex  0.250540E+02  0.340036E+02  0.379670E+01
 endloop
endfacet
facet normal  0.170792E+00  0.258039E+00  0.950918E+00
 outer loop
  vertex  0.248090E+02  0.331484E+02  0.474600E+01
  vertex  0.245283E+02  0.321682E+02  0.506240E+01
  vertex  0.287174E+02  0.293955E+02  0.506240E+01
 endloop
endfacet
facet normal  0.193422E+00  0.280697E+00  0.940105E+00
 outer loop
  vertex  0.287173E+02  0.293955E+02  0.506230E+01
  vertex  0.286718E+02  0.304862E+02  0.474600E+01
  vertex  0.248090E+02  0.331483E+02  0.474590E+01
 endloop
endfacet
facet normal -0.165750E+00 -0.259591E+00  0.951388E+00
 outer loop
  vertex  0.245283E+02  0.321682E+02  0.506240E+01
  vertex  0.242475E+02  0.311879E+02  0.474600E+01
  vertex  0.287629E+02  0.283048E+02  0.474600E+01
 endloop
endfacet
facet normal -0.185977E+00 -0.280955E+00  0.941529E+00
 outer loop
  vertex  0.287628E+02  0.283048E+02  0.474590E+01
  vertex  0.287174E+02  0.293955E+02  0.506240E+01
  vertex  0.245282E+02  0.321682E+02  0.506230E+01
 endloop
endfacet
facet normal -0.391712E+00 -0.631064E+00  0.669567E+00
 outer loop
  vertex  0.242475E+02  0.311879E+02  0.474600E+01
  vertex  0.240026E+02  0.303328E+02  0.379680E+01
  vertex  0.288027E+02  0.273533E+02  0.379680E+01
 endloop
endfacet
facet normal -0.415689E+00 -0.651029E+00  0.635109E+00
 outer loop
  vertex  0.288027E+02  0.273533E+02  0.379670E+01
  vertex  0.287629E+02  0.283048E+02  0.474600E+01
  vertex  0.242474E+02  0.311879E+02  0.474590E+01
 endloop
endfacet
facet normal -0.485841E+00 -0.797327E+00  0.358091E+00
 outer loop
  vertex  0.240026E+02  0.303328E+02  0.379680E+01
  vertex  0.238293E+02  0.297279E+02  0.221480E+01
  vertex  0.288308E+02  0.266803E+02  0.221480E+01
 endloop
endfacet
facet normal -0.497423E+00 -0.801402E+00  0.332151E+00
 outer loop
  vertex  0.288307E+02  0.266802E+02  0.221470E+01
  vertex  0.288027E+02  0.273533E+02  0.379680E+01
  vertex  0.240025E+02  0.303327E+02  0.379670E+01
 endloop
endfacet
facet normal -0.515019E+00 -0.850918E+00  0.103412E+00
 outer loop
  vertex  0.238293E+02  0.297279E+02  0.221480E+01
  vertex  0.237636E+02  0.294985E+02  0.000000E+00
  vertex  0.288415E+02  0.264251E+02  0.000000E+00
 endloop
endfacet
facet normal -0.517952E+00 -0.850066E+00  0.954693E-01
 outer loop
  vertex  0.288414E+02  0.264251E+02  0.000000E+00
  vertex  0.288308E+02  0.266803E+02  0.221480E+01
  vertex  0.238292E+02  0.297278E+02  0.221470E+01
 endloop
endfacet
facet normal  0.471918E+00  0.876099E+00  0.987075E-01
 outer loop
  vertex  0.285932E+02  0.323659E+02  0.000000E+00
  vertex  0.286039E+02  0.321106E+02  0.221480E+01
  vertex  0.325966E+02  0.299599E+02  0.221480E+01
 endloop
endfacet
facet normal  0.474105E+00  0.875430E+00  0.940524E-01
 outer loop
  vertex  0.325965E+02  0.299598E+02  0.221470E+01
  vertex  0.325000E+02  0.302500E+02  0.000000E+00
  vertex  0.285932E+02  0.323658E+02  0.000000E+00
 endloop
endfacet
facet normal  0.440515E+00  0.828911E+00  0.344751E+00
 outer loop
  vertex  0.286039E+02  0.321106E+02  0.221480E+01
  vertex  0.286320E+02  0.314377E+02  0.379680E+01
  vertex  0.328515E+02  0.291953E+02  0.379680E+01
 endloop
endfacet
facet normal  0.447701E+00  0.831195E+00  0.329664E+00
 outer loop
  vertex  0.328515E+02  0.291952E+02  0.379670E+01
  vertex  0.325966E+02  0.299599E+02  0.221480E+01
  vertex  0.286039E+02  0.321105E+02  0.221470E+01
 endloop
endfacet
facet normal  0.349520E+00  0.668994E+00  0.655959E+00
 outer loop
  vertex  0.286320E+02  0.314377E+02  0.379680E+01
  vertex  0.286718E+02  0.304862E+02  0.474600E+01
  vertex  0.332119E+02  0.281142E+02  0.474600E+01
 endloop
endfacet
facet normal  0.361490E+00  0.680255E+00  0.637635E+00
 outer loop
  vertex  0.332118E+02  0.281142E+02  0.474590E+01
  vertex  0.328515E+02  0.291953E+02  0.379680E+01
  vertex  0.286319E+02  0.314377E+02  0.379670E+01
 endloop
endfacet
facet normal  0.144446E+00  0.281247E+00  0.948702E+00
 outer loop
  vertex  0.286718E+02  0.304862E+02  0.474600E+01
  vertex  0.287174E+02  0.293955E+02  0.506240E+01
  vertex  0.336250E+02  0.268750E+02  0.506240E+01
 endloop
endfacet
facet normal  0.152450E+00  0.291834E+00  0.944241E+00
 outer loop
  vertex  0.336250E+02  0.268750E+02  0.506230E+01
  vertex  0.332119E+02  0.281142E+02  0.474600E+01
  vertex  0.286718E+02  0.304862E+02  0.474590E+01
 endloop
endfacet
facet normal -0.142302E+00 -0.281239E+00  0.949028E+00
 outer loop
  vertex  0.287174E+02  0.293955E+02  0.506240E+01
  vertex  0.287629E+02  0.283048E+02  0.474600E+01
  vertex  0.340380E+02  0.256357E+02  0.474600E+01
 endloop
endfacet
facet normal -0.149545E+00 -0.291143E+00  0.944919E+00
 outer loop
  vertex  0.340379E+02  0.256357E+02  0.474590E+01
  vertex  0.336250E+02  0.268750E+02  0.506240E+01
  vertex  0.287173E+02  0.293955E+02  0.506230E+01
 endloop
endfacet
facet normal -0.336180E+00 -0.672156E+00  0.659689E+00
 outer loop
  vertex  0.287629E+02  0.283048E+02  0.474600E+01
  vertex  0.288027E+02  0.273533E+02  0.379680E+01
  vertex  0.343984E+02  0.245546E+02  0.379680E+01
 endloop
endfacet
facet normal -0.344870E+00 -0.681576E+00  0.645383E+00
 outer loop
  vertex  0.343983E+02  0.245545E+02  0.379670E+01
  vertex  0.340380E+02  0.256357E+02  0.474600E+01
  vertex  0.287628E+02  0.283048E+02  0.474590E+01
 endloop
endfacet
facet normal -0.416576E+00 -0.839192E+00  0.349602E+00
 outer loop
  vertex  0.288027E+02  0.273533E+02  0.379680E+01
  vertex  0.288308E+02  0.266803E+02  0.221480E+01
  vertex  0.346533E+02  0.237900E+02  0.221480E+01
 endloop
endfacet
facet normal -0.420863E+00 -0.841459E+00  0.338853E+00
 outer loop
  vertex  0.346533E+02  0.237900E+02  0.221470E+01
  vertex  0.343984E+02  0.245546E+02  0.379680E+01
  vertex  0.288027E+02  0.273533E+02  0.379670E+01
 endloop
endfacet
facet normal -0.441422E+00 -0.891642E+00  0.100606E+00
 outer loop
  vertex  0.288308E+02  0.266803E+02  0.221480E+01
  vertex  0.288415E+02  0.264251E+02  0.000000E+00
  vertex  0.347500E+02  0.235000E+02  0.000000E+00
 endloop
endfacet
facet normal -0.442502E+00 -0.891462E+00  0.974062E-01
 outer loop
  vertex  0.347500E+02  0.235000E+02  0.000000E+00
  vertex  0.346533E+02  0.237900E+02  0.221480E+01
  vertex  0.288307E+02  0.266802E+02  0.221470E+01
 endloop
endfacet
facet normal -0.883494E-01  0.426704E+00  0.900066E+00
 outer loop
  vertex  0.775000E+02  0.640000E+02  0.337499E+02
  vertex  0.706234E+02  0.640000E+02  0.330749E+02
  vertex  0.701958E+02  0.595736E+02  0.351314E+02
 endloop
endfacet
facet normal -0.883412E-01  0.426692E+00  0.900072E+00
 outer loop
  vertex  0.701958E+02  0.595736E+02  0.351314E+02
  vertex  0.775000E+02  0.595736E+02  0.358483E+02
  vertex  0.775000E+02  0.640000E+02  0.337499E+02
 endloop
endfacet
facet normal -0.263472E+00  0.427264E+00  0.864886E+00
 outer loop
  vertex  0.706234E+02  0.640000E+02  0.330749E+02
  vertex  0.642531E+02  0.640000E+02  0.311343E+02
  vertex  0.634295E+02  0.595736E+02  0.330701E+02
 endloop
endfacet
facet normal -0.263491E+00  0.427269E+00  0.864878E+00
 outer loop
  vertex  0.634295E+02  0.595736E+02  0.330700E+02
  vertex  0.701958E+02  0.595736E+02  0.351314E+02
  vertex  0.706233E+02  0.640000E+02  0.330749E+02
 endloop
endfacet
facet normal -0.427474E+00  0.427826E+00  0.796386E+00
 outer loop
  vertex  0.642531E+02  0.640000E+02  0.311343E+02
  vertex  0.585156E+02  0.640000E+02  0.280546E+02
  vertex  0.573352E+02  0.595736E+02  0.297989E+02
 endloop
endfacet
facet normal -0.427474E+00  0.427815E+00  0.796392E+00
 outer loop
  vertex  0.573352E+02  0.595736E+02  0.297989E+02
  vertex  0.634295E+02  0.595736E+02  0.330701E+02
  vertex  0.642530E+02  0.640000E+02  0.311343E+02
 endloop
endfacet
facet normal -0.573872E+00  0.428132E+00  0.698121E+00
 outer loop
  vertex  0.585156E+02  0.640000E+02  0.280546E+02
  vertex  0.535374E+02  0.640000E+02  0.239624E+02
  vertex  0.520476E+02  0.595736E+02  0.254523E+02
 endloop
endfacet
facet normal -0.573876E+00  0.428143E+00  0.698112E+00
 outer loop
  vertex  0.520475E+02  0.595736E+02  0.254522E+02
  vertex  0.573352E+02  0.595736E+02  0.297989E+02
  vertex  0.585155E+02  0.640000E+02  0.280545E+02
 endloop
endfacet
facet normal -0.698119E+00  0.428141E+00  0.573868E+00
 outer loop
  vertex  0.535374E+02  0.640000E+02  0.239624E+02
  vertex  0.494453E+02  0.640000E+02  0.189843E+02
  vertex  0.477010E+02  0.595736E+02  0.201647E+02
 endloop
endfacet
facet normal -0.698128E+00  0.428117E+00  0.573876E+00
 outer loop
  vertex  0.477010E+02  0.595736E+02  0.201646E+02
  vertex  0.520476E+02  0.595736E+02  0.254523E+02
  vertex  0.535373E+02  0.640000E+02  0.239624E+02
 endloop
endfacet
facet normal -0.796387E+00  0.427823E+00  0.427474E+00
 outer loop
  vertex  0.494453E+02  0.640000E+02  0.189843E+02
  vertex  0.463656E+02  0.640000E+02  0.132468E+02
  vertex  0.444298E+02  0.595736E+02  0.140704E+02
 endloop
endfacet
facet normal -0.796382E+00  0.427826E+00  0.427482E+00
 outer loop
  vertex  0.444297E+02  0.595736E+02  0.140704E+02
  vertex  0.477010E+02  0.595736E+02  0.201647E+02
  vertex  0.494453E+02  0.640000E+02  0.189843E+02
 endloop
endfacet
facet normal -0.864885E+00  0.427258E+00  0.263486E+00
 outer loop
  vertex  0.463656E+02  0.640000E+02  0.132468E+02
  vertex  0.444249E+02  0.640000E+02  0.687650E+01
  vertex  0.423685E+02  0.595736E+02  0.730410E+01
 endloop
endfacet
facet normal -0.864880E+00  0.427265E+00  0.263491E+00
 outer loop
  vertex  0.423684E+02  0.595736E+02  0.730410E+01
  vertex  0.444298E+02  0.595736E+02  0.140704E+02
  vertex  0.463656E+02  0.640000E+02  0.132468E+02
 endloop
endfacet
facet normal -0.900072E+00  0.426693E+00  0.883384E-01
 outer loop
  vertex  0.444249E+02  0.640000E+02  0.687650E+01
  vertex  0.437500E+02  0.640000E+02  0.000000E+00
  vertex  0.416516E+02  0.595736E+02  0.000000E+00
 endloop
endfacet
facet normal -0.900073E+00  0.426688E+00  0.883547E-01
 outer loop
  vertex  0.416515E+02  0.595736E+02  0.000000E+00
  vertex  0.423685E+02  0.595736E+02  0.730410E+01
  vertex  0.444249E+02  0.640000E+02  0.687650E+01
 endloop
endfacet
facet normal -0.887743E-01  0.417163E+00  0.904485E+00
 outer loop
  vertex  0.775000E+02  0.595736E+02  0.358483E+02
  vertex  0.701958E+02  0.595736E+02  0.351314E+02
  vertex  0.697817E+02  0.551669E+02  0.371232E+02
 endloop
endfacet
facet normal -0.887919E-01  0.417172E+00  0.904480E+00
 outer loop
  vertex  0.697817E+02  0.551669E+02  0.371231E+02
  vertex  0.775000E+02  0.551669E+02  0.378808E+02
  vertex  0.775000E+02  0.595736E+02  0.358483E+02
 endloop
endfacet
facet normal -0.264776E+00  0.417724E+00  0.869138E+00
 outer loop
  vertex  0.701958E+02  0.595736E+02  0.351314E+02
  vertex  0.634295E+02  0.595736E+02  0.330701E+02
  vertex  0.626317E+02  0.551669E+02  0.349450E+02
 endloop
endfacet
facet normal -0.264784E+00  0.417725E+00  0.869135E+00
 outer loop
  vertex  0.626316E+02  0.551669E+02  0.349449E+02
  vertex  0.697817E+02  0.551669E+02  0.371232E+02
  vertex  0.701958E+02  0.595736E+02  0.351314E+02
 endloop
endfacet
facet normal -0.429580E+00  0.418278E+00  0.800315E+00
 outer loop
  vertex  0.634295E+02  0.595736E+02  0.330701E+02
  vertex  0.573352E+02  0.595736E+02  0.297989E+02
  vertex  0.561920E+02  0.551669E+02  0.314884E+02
 endloop
endfacet
facet normal -0.429587E+00  0.418294E+00  0.800304E+00
 outer loop
  vertex  0.561920E+02  0.551669E+02  0.314883E+02
  vertex  0.626317E+02  0.551669E+02  0.349450E+02
  vertex  0.634295E+02  0.595736E+02  0.330700E+02
 endloop
endfacet
facet normal -0.576705E+00  0.418604E+00  0.701557E+00
 outer loop
  vertex  0.573352E+02  0.595736E+02  0.297989E+02
  vertex  0.520476E+02  0.595736E+02  0.254523E+02
  vertex  0.506045E+02  0.551669E+02  0.268954E+02
 endloop
endfacet
facet normal -0.576702E+00  0.418587E+00  0.701570E+00
 outer loop
  vertex  0.506044E+02  0.551669E+02  0.268953E+02
  vertex  0.561920E+02  0.551669E+02  0.314884E+02
  vertex  0.573352E+02  0.595736E+02  0.297989E+02
 endloop
endfacet
facet normal -0.701563E+00  0.418586E+00  0.576710E+00
 outer loop
  vertex  0.520476E+02  0.595736E+02  0.254523E+02
  vertex  0.477010E+02  0.595736E+02  0.201647E+02
  vertex  0.460115E+02  0.551669E+02  0.213079E+02
 endloop
endfacet
facet normal -0.701571E+00  0.418600E+00  0.576690E+00
 outer loop
  vertex  0.460115E+02  0.551669E+02  0.213078E+02
  vertex  0.506045E+02  0.551669E+02  0.268954E+02
  vertex  0.520475E+02  0.595736E+02  0.254522E+02
 endloop
endfacet
facet normal -0.800315E+00  0.418278E+00  0.429580E+00
 outer loop
  vertex  0.477010E+02  0.595736E+02  0.201647E+02
  vertex  0.444298E+02  0.595736E+02  0.140704E+02
  vertex  0.425549E+02  0.551669E+02  0.148682E+02
 endloop
endfacet
facet normal -0.800312E+00  0.418286E+00  0.429579E+00
 outer loop
  vertex  0.425549E+02  0.551669E+02  0.148682E+02
  vertex  0.460115E+02  0.551669E+02  0.213079E+02
  vertex  0.477010E+02  0.595736E+02  0.201646E+02
 endloop
endfacet
facet normal -0.869137E+00  0.417725E+00  0.264776E+00
 outer loop
  vertex  0.444298E+02  0.595736E+02  0.140704E+02
  vertex  0.423685E+02  0.595736E+02  0.730410E+01
  vertex  0.403767E+02  0.551669E+02  0.771820E+01
 endloop
endfacet
facet normal -0.869145E+00  0.417707E+00  0.264779E+00
 outer loop
  vertex  0.403767E+02  0.551669E+02  0.771820E+01
  vertex  0.425549E+02  0.551669E+02  0.148682E+02
  vertex  0.444297E+02  0.595736E+02  0.140704E+02
 endloop
endfacet
facet normal -0.904481E+00  0.417173E+00  0.887751E-01
 outer loop
  vertex  0.423685E+02  0.595736E+02  0.730410E+01
  vertex  0.416516E+02  0.595736E+02  0.000000E+00
  vertex  0.396191E+02  0.551669E+02  0.000000E+00
 endloop
endfacet
facet normal -0.904491E+00  0.417147E+00  0.887946E-01
 outer loop
  vertex  0.396190E+02  0.551669E+02  0.000000E+00
  vertex  0.403767E+02  0.551669E+02  0.771820E+01
  vertex  0.423684E+02  0.595736E+02  0.730410E+01
 endloop
endfacet
facet normal -0.896394E-01  0.397457E+00  0.913232E+00
 outer loop
  vertex  0.775000E+02  0.551669E+02  0.378808E+02
  vertex  0.697817E+02  0.551669E+02  0.371232E+02
  vertex  0.693945E+02  0.507999E+02  0.389858E+02
 endloop
endfacet
facet normal -0.896378E-01  0.397473E+00  0.913225E+00
 outer loop
  vertex  0.693945E+02  0.507999E+02  0.389858E+02
  vertex  0.775000E+02  0.507999E+02  0.397814E+02
  vertex  0.775000E+02  0.551669E+02  0.378807E+02
 endloop
endfacet
facet normal -0.267342E+00  0.398019E+00  0.877559E+00
 outer loop
  vertex  0.697817E+02  0.551669E+02  0.371232E+02
  vertex  0.626317E+02  0.551669E+02  0.349450E+02
  vertex  0.618857E+02  0.507999E+02  0.366984E+02
 endloop
endfacet
facet normal -0.267342E+00  0.398018E+00  0.877559E+00
 outer loop
  vertex  0.618857E+02  0.507999E+02  0.366983E+02
  vertex  0.693945E+02  0.507999E+02  0.389858E+02
  vertex  0.697817E+02  0.551669E+02  0.371231E+02
 endloop
endfacet
facet normal -0.433757E+00  0.398544E+00  0.808095E+00
 outer loop
  vertex  0.626317E+02  0.551669E+02  0.349450E+02
  vertex  0.561920E+02  0.551669E+02  0.314884E+02
  vertex  0.551229E+02  0.507999E+02  0.330683E+02
 endloop
endfacet
facet normal -0.433764E+00  0.398561E+00  0.808083E+00
 outer loop
  vertex  0.551228E+02  0.507999E+02  0.330682E+02
  vertex  0.618857E+02  0.507999E+02  0.366984E+02
  vertex  0.626316E+02  0.551669E+02  0.349449E+02
 endloop
endfacet
facet normal -0.582318E+00  0.398833E+00  0.708405E+00
 outer loop
  vertex  0.561920E+02  0.551669E+02  0.314884E+02
  vertex  0.506045E+02  0.551669E+02  0.268954E+02
  vertex  0.492551E+02  0.507999E+02  0.282448E+02
 endloop
endfacet
facet normal -0.582318E+00  0.398858E+00  0.708391E+00
 outer loop
  vertex  0.492551E+02  0.507999E+02  0.282448E+02
  vertex  0.551229E+02  0.507999E+02  0.330683E+02
  vertex  0.561920E+02  0.551669E+02  0.314883E+02
 endloop
endfacet
facet normal -0.708401E+00  0.398845E+00  0.582315E+00
 outer loop
  vertex  0.506045E+02  0.551669E+02  0.268954E+02
  vertex  0.460115E+02  0.551669E+02  0.213079E+02
  vertex  0.444316E+02  0.507999E+02  0.223770E+02
 endloop
endfacet
facet normal -0.708394E+00  0.398831E+00  0.582333E+00
 outer loop
  vertex  0.444315E+02  0.507999E+02  0.223770E+02
  vertex  0.492551E+02  0.507999E+02  0.282448E+02
  vertex  0.506044E+02  0.551669E+02  0.268953E+02
 endloop
endfacet
facet normal -0.808091E+00  0.398555E+00  0.433754E+00
 outer loop
  vertex  0.460115E+02  0.551669E+02  0.213079E+02
  vertex  0.425549E+02  0.551669E+02  0.148682E+02
  vertex  0.408015E+02  0.507999E+02  0.156142E+02
 endloop
endfacet
facet normal -0.808086E+00  0.398553E+00  0.433766E+00
 outer loop
  vertex  0.408014E+02  0.507999E+02  0.156141E+02
  vertex  0.444316E+02  0.507999E+02  0.223770E+02
  vertex  0.460115E+02  0.551669E+02  0.213078E+02
 endloop
endfacet
facet normal -0.877566E+00  0.398001E+00  0.267345E+00
 outer loop
  vertex  0.425549E+02  0.551669E+02  0.148682E+02
  vertex  0.403767E+02  0.551669E+02  0.771820E+01
  vertex  0.385141E+02  0.507999E+02  0.810540E+01
 endloop
endfacet
facet normal -0.877559E+00  0.398019E+00  0.267342E+00
 outer loop
  vertex  0.385140E+02  0.507999E+02  0.810540E+01
  vertex  0.408015E+02  0.507999E+02  0.156142E+02
  vertex  0.425549E+02  0.551669E+02  0.148682E+02
 endloop
endfacet
facet normal -0.913232E+00  0.397456E+00  0.896410E-01
 outer loop
  vertex  0.403767E+02  0.551669E+02  0.771820E+01
  vertex  0.396191E+02  0.551669E+02  0.000000E+00
  vertex  0.377185E+02  0.507999E+02  0.000000E+00
 endloop
endfacet
facet normal -0.913231E+00  0.397458E+00  0.896511E-01
 outer loop
  vertex  0.377184E+02  0.507999E+02  0.000000E+00
  vertex  0.385141E+02  0.507999E+02  0.810540E+01
  vertex  0.403767E+02  0.551669E+02  0.771820E+01
 endloop
endfacet
facet normal -0.909042E-01  0.366094E+00  0.926127E+00
 outer loop
  vertex  0.775000E+02  0.507999E+02  0.397814E+02
  vertex  0.693945E+02  0.507999E+02  0.389858E+02
  vertex  0.690475E+02  0.464921E+02  0.406546E+02
 endloop
endfacet
facet normal -0.909230E-01  0.366120E+00  0.926115E+00
 outer loop
  vertex  0.690475E+02  0.464920E+02  0.406545E+02
  vertex  0.775000E+02  0.464921E+02  0.414843E+02
  vertex  0.775000E+02  0.507999E+02  0.397813E+02
 endloop
endfacet
facet normal -0.271118E+00  0.366615E+00  0.889993E+00
 outer loop
  vertex  0.693945E+02  0.507999E+02  0.389858E+02
  vertex  0.618857E+02  0.507999E+02  0.366984E+02
  vertex  0.612173E+02  0.464921E+02  0.382693E+02
 endloop
endfacet
facet normal -0.271132E+00  0.366613E+00  0.889990E+00
 outer loop
  vertex  0.612173E+02  0.464920E+02  0.382692E+02
  vertex  0.690475E+02  0.464921E+02  0.406546E+02
  vertex  0.693945E+02  0.507999E+02  0.389858E+02
 endloop
endfacet
facet normal -0.439922E+00  0.367124E+00  0.819566E+00
 outer loop
  vertex  0.618857E+02  0.507999E+02  0.366984E+02
  vertex  0.551229E+02  0.507999E+02  0.330683E+02
  vertex  0.541650E+02  0.464921E+02  0.344838E+02
 endloop
endfacet
facet normal -0.439932E+00  0.367141E+00  0.819553E+00
 outer loop
  vertex  0.541650E+02  0.464920E+02  0.344837E+02
  vertex  0.612173E+02  0.464921E+02  0.382693E+02
  vertex  0.618857E+02  0.507999E+02  0.366983E+02
 endloop
endfacet
facet normal -0.590599E+00  0.367424E+00  0.718465E+00
 outer loop
  vertex  0.551229E+02  0.507999E+02  0.330683E+02
  vertex  0.492551E+02  0.507999E+02  0.282448E+02
  vertex  0.480460E+02  0.464921E+02  0.294539E+02
 endloop
endfacet
facet normal -0.590606E+00  0.367413E+00  0.718466E+00
 outer loop
  vertex  0.480460E+02  0.464920E+02  0.294538E+02
  vertex  0.541650E+02  0.464921E+02  0.344838E+02
  vertex  0.551228E+02  0.507999E+02  0.330682E+02
 endloop
endfacet
facet normal -0.718469E+00  0.367410E+00  0.590603E+00
 outer loop
  vertex  0.492551E+02  0.507999E+02  0.282448E+02
  vertex  0.444316E+02  0.507999E+02  0.223770E+02
  vertex  0.430161E+02  0.464921E+02  0.233349E+02
 endloop
endfacet
facet normal -0.718479E+00  0.367423E+00  0.590584E+00
 outer loop
  vertex  0.430161E+02  0.464920E+02  0.233348E+02
  vertex  0.480460E+02  0.464921E+02  0.294539E+02
  vertex  0.492551E+02  0.507999E+02  0.282448E+02
 endloop
endfacet
facet normal -0.819566E+00  0.367125E+00  0.439922E+00
 outer loop
  vertex  0.444316E+02  0.507999E+02  0.223770E+02
  vertex  0.408015E+02  0.507999E+02  0.156142E+02
  vertex  0.392306E+02  0.464921E+02  0.162826E+02
 endloop
endfacet
facet normal -0.819569E+00  0.367107E+00  0.439931E+00
 outer loop
  vertex  0.392305E+02  0.464920E+02  0.162826E+02
  vertex  0.430161E+02  0.464921E+02  0.233349E+02
  vertex  0.444315E+02  0.507999E+02  0.223770E+02
 endloop
endfacet
facet normal -0.889994E+00  0.366614E+00  0.271118E+00
 outer loop
  vertex  0.408015E+02  0.507999E+02  0.156142E+02
  vertex  0.385141E+02  0.507999E+02  0.810540E+01
  vertex  0.368453E+02  0.464921E+02  0.845240E+01
 endloop
endfacet
facet normal -0.889996E+00  0.366603E+00  0.271125E+00
 outer loop
  vertex  0.368452E+02  0.464920E+02  0.845240E+01
  vertex  0.392306E+02  0.464921E+02  0.162826E+02
  vertex  0.408014E+02  0.507999E+02  0.156141E+02
 endloop
endfacet
facet normal -0.926124E+00  0.366102E+00  0.909054E-01
 outer loop
  vertex  0.385141E+02  0.507999E+02  0.810540E+01
  vertex  0.377185E+02  0.507999E+02  0.000000E+00
  vertex  0.360156E+02  0.464921E+02  0.000000E+00
 endloop
endfacet
facet normal -0.926133E+00  0.366077E+00  0.909172E-01
 outer loop
  vertex  0.360155E+02  0.464920E+02  0.000000E+00
  vertex  0.368453E+02  0.464921E+02  0.845240E+01
  vertex  0.385140E+02  0.507999E+02  0.810540E+01
 endloop
endfacet
facet normal -0.925265E-01  0.320834E+00  0.942605E+00
 outer loop
  vertex  0.775000E+02  0.464921E+02  0.414843E+02
  vertex  0.690475E+02  0.464921E+02  0.406546E+02
  vertex  0.687543E+02  0.422635E+02  0.420651E+02
 endloop
endfacet
facet normal -0.925173E-01  0.320844E+00  0.942603E+00
 outer loop
  vertex  0.687543E+02  0.422635E+02  0.420651E+02
  vertex  0.775000E+02  0.422635E+02  0.429235E+02
  vertex  0.775000E+02  0.464920E+02  0.414842E+02
 endloop
endfacet
facet normal -0.275956E+00  0.321294E+00  0.905880E+00
 outer loop
  vertex  0.690475E+02  0.464921E+02  0.406546E+02
  vertex  0.612173E+02  0.464921E+02  0.382693E+02
  vertex  0.606524E+02  0.422635E+02  0.395970E+02
 endloop
endfacet
facet normal -0.275957E+00  0.321327E+00  0.905868E+00
 outer loop
  vertex  0.606524E+02  0.422635E+02  0.395970E+02
  vertex  0.687543E+02  0.422635E+02  0.420651E+02
  vertex  0.690475E+02  0.464920E+02  0.406545E+02
 endloop
endfacet
facet normal -0.447796E+00  0.321765E+00  0.834234E+00
 outer loop
  vertex  0.612173E+02  0.464921E+02  0.382693E+02
  vertex  0.541650E+02  0.464921E+02  0.344838E+02
  vertex  0.533554E+02  0.422635E+02  0.356802E+02
 endloop
endfacet
facet normal -0.447798E+00  0.321780E+00  0.834227E+00
 outer loop
  vertex  0.533554E+02  0.422635E+02  0.356801E+02
  vertex  0.606524E+02  0.422635E+02  0.395970E+02
  vertex  0.612173E+02  0.464920E+02  0.382692E+02
 endloop
endfacet
facet normal -0.601189E+00  0.321998E+00  0.731361E+00
 outer loop
  vertex  0.541650E+02  0.464921E+02  0.344838E+02
  vertex  0.480460E+02  0.464921E+02  0.294539E+02
  vertex  0.470242E+02  0.422635E+02  0.304757E+02
 endloop
endfacet
facet normal -0.601190E+00  0.322046E+00  0.731339E+00
 outer loop
  vertex  0.470242E+02  0.422635E+02  0.304757E+02
  vertex  0.533554E+02  0.422635E+02  0.356802E+02
  vertex  0.541650E+02  0.464920E+02  0.344837E+02
 endloop
endfacet
facet normal -0.731354E+00  0.322025E+00  0.601183E+00
 outer loop
  vertex  0.480460E+02  0.464921E+02  0.294539E+02
  vertex  0.430161E+02  0.464921E+02  0.233349E+02
  vertex  0.418197E+02  0.422635E+02  0.241445E+02
 endloop
endfacet
facet normal -0.731341E+00  0.322018E+00  0.601203E+00
 outer loop
  vertex  0.418196E+02  0.422635E+02  0.241445E+02
  vertex  0.470242E+02  0.422635E+02  0.304757E+02
  vertex  0.480460E+02  0.464920E+02  0.294538E+02
 endloop
endfacet
facet normal -0.834236E+00  0.321755E+00  0.447798E+00
 outer loop
  vertex  0.430161E+02  0.464921E+02  0.233349E+02
  vertex  0.392306E+02  0.464921E+02  0.162826E+02
  vertex  0.379029E+02  0.422635E+02  0.168475E+02
 endloop
endfacet
facet normal -0.834234E+00  0.321781E+00  0.447784E+00
 outer loop
  vertex  0.379029E+02  0.422635E+02  0.168474E+02
  vertex  0.418197E+02  0.422635E+02  0.241445E+02
  vertex  0.430161E+02  0.464920E+02  0.233348E+02
 endloop
endfacet
facet normal -0.905878E+00  0.321300E+00  0.275956E+00
 outer loop
  vertex  0.392306E+02  0.464921E+02  0.162826E+02
  vertex  0.368453E+02  0.464921E+02  0.845240E+01
  vertex  0.354348E+02  0.422635E+02  0.874560E+01
 endloop
endfacet
facet normal -0.905881E+00  0.321282E+00  0.275968E+00
 outer loop
  vertex  0.354347E+02  0.422635E+02  0.874550E+01
  vertex  0.379029E+02  0.422635E+02  0.168475E+02
  vertex  0.392305E+02  0.464920E+02  0.162826E+02
 endloop
endfacet
facet normal -0.942611E+00  0.320816E+00  0.925281E-01
 outer loop
  vertex  0.368453E+02  0.464921E+02  0.845240E+01
  vertex  0.360156E+02  0.464921E+02  0.000000E+00
  vertex  0.345764E+02  0.422635E+02  0.000000E+00
 endloop
endfacet
facet normal -0.942611E+00  0.320819E+00  0.925192E-01
 outer loop
  vertex  0.345764E+02  0.422635E+02  0.000000E+00
  vertex  0.354348E+02  0.422635E+02  0.874560E+01
  vertex  0.368452E+02  0.464920E+02  0.845240E+01
 endloop
endfacet
facet normal -0.943662E-01  0.258319E+00  0.961440E+00
 outer loop
  vertex  0.775000E+02  0.422635E+02  0.429235E+02
  vertex  0.687543E+02  0.422635E+02  0.420651E+02
  vertex  0.685282E+02  0.381337E+02  0.431525E+02
 endloop
endfacet
facet normal -0.943761E-01  0.258342E+00  0.961433E+00
 outer loop
  vertex  0.685281E+02  0.381337E+02  0.431525E+02
  vertex  0.775000E+02  0.381337E+02  0.440332E+02
  vertex  0.775000E+02  0.422635E+02  0.429235E+02
 endloop
endfacet
facet normal -0.281489E+00  0.258712E+00  0.924030E+00
 outer loop
  vertex  0.687543E+02  0.422635E+02  0.420651E+02
  vertex  0.606524E+02  0.422635E+02  0.395970E+02
  vertex  0.602169E+02  0.381337E+02  0.406206E+02
 endloop
endfacet
facet normal -0.281487E+00  0.258714E+00  0.924030E+00
 outer loop
  vertex  0.602168E+02  0.381337E+02  0.406206E+02
  vertex  0.685282E+02  0.381337E+02  0.431525E+02
  vertex  0.687543E+02  0.422635E+02  0.420651E+02
 endloop
endfacet
facet normal -0.456792E+00  0.259105E+00  0.851003E+00
 outer loop
  vertex  0.606524E+02  0.422635E+02  0.395970E+02
  vertex  0.533554E+02  0.422635E+02  0.356802E+02
  vertex  0.527313E+02  0.381337E+02  0.366026E+02
 endloop
endfacet
facet normal -0.456790E+00  0.259098E+00  0.851006E+00
 outer loop
  vertex  0.527313E+02  0.381337E+02  0.366026E+02
  vertex  0.602169E+02  0.381337E+02  0.406206E+02
  vertex  0.606524E+02  0.422635E+02  0.395970E+02
 endloop
endfacet
facet normal -0.613299E+00  0.259313E+00  0.746070E+00
 outer loop
  vertex  0.533554E+02  0.422635E+02  0.356802E+02
  vertex  0.470242E+02  0.422635E+02  0.304757E+02
  vertex  0.462364E+02  0.381337E+02  0.312635E+02
 endloop
endfacet
facet normal -0.613298E+00  0.259335E+00  0.746064E+00
 outer loop
  vertex  0.462364E+02  0.381337E+02  0.312635E+02
  vertex  0.527313E+02  0.381337E+02  0.366026E+02
  vertex  0.533554E+02  0.422635E+02  0.356801E+02
 endloop
endfacet
facet normal -0.746069E+00  0.259318E+00  0.613299E+00
 outer loop
  vertex  0.470242E+02  0.422635E+02  0.304757E+02
  vertex  0.418197E+02  0.422635E+02  0.241445E+02
  vertex  0.408973E+02  0.381337E+02  0.247686E+02
 endloop
endfacet
facet normal -0.746068E+00  0.259313E+00  0.613302E+00
 outer loop
  vertex  0.408973E+02  0.381337E+02  0.247686E+02
  vertex  0.462364E+02  0.381337E+02  0.312635E+02
  vertex  0.470242E+02  0.422635E+02  0.304757E+02
 endloop
endfacet
facet normal -0.851005E+00  0.259098E+00  0.456792E+00
 outer loop
  vertex  0.418197E+02  0.422635E+02  0.241445E+02
  vertex  0.379029E+02  0.422635E+02  0.168475E+02
  vertex  0.368793E+02  0.381337E+02  0.172830E+02
 endloop
endfacet
facet normal -0.851005E+00  0.259085E+00  0.456800E+00
 outer loop
  vertex  0.368792E+02  0.381337E+02  0.172830E+02
  vertex  0.408973E+02  0.381337E+02  0.247686E+02
  vertex  0.418196E+02  0.422635E+02  0.241445E+02
 endloop
endfacet
facet normal -0.924030E+00  0.258713E+00  0.281489E+00
 outer loop
  vertex  0.379029E+02  0.422635E+02  0.168475E+02
  vertex  0.354348E+02  0.422635E+02  0.874560E+01
  vertex  0.343474E+02  0.381337E+02  0.897170E+01
 endloop
endfacet
facet normal -0.924029E+00  0.258718E+00  0.281487E+00
 outer loop
  vertex  0.343474E+02  0.381337E+02  0.897160E+01
  vertex  0.368793E+02  0.381337E+02  0.172830E+02
  vertex  0.379029E+02  0.422635E+02  0.168474E+02
 endloop
endfacet
facet normal -0.961433E+00  0.258342E+00  0.943666E-01
 outer loop
  vertex  0.354348E+02  0.422635E+02  0.874560E+01
  vertex  0.345764E+02  0.422635E+02  0.000000E+00
  vertex  0.334667E+02  0.381337E+02  0.000000E+00
 endloop
endfacet
facet normal -0.961444E+00  0.258300E+00  0.943793E-01
 outer loop
  vertex  0.334667E+02  0.381337E+02  0.000000E+00
  vertex  0.343474E+02  0.381337E+02  0.897170E+01
  vertex  0.354347E+02  0.422635E+02  0.874550E+01
 endloop
endfacet
facet normal -0.961953E-01  0.174458E+00  0.979955E+00
 outer loop
  vertex  0.775000E+02  0.381337E+02  0.440332E+02
  vertex  0.685282E+02  0.381337E+02  0.431525E+02
  vertex  0.683827E+02  0.341226E+02  0.438523E+02
 endloop
endfacet
facet normal -0.962063E-01  0.174485E+00  0.979949E+00
 outer loop
  vertex  0.683826E+02  0.341226E+02  0.438522E+02
  vertex  0.775000E+02  0.341226E+02  0.447473E+02
  vertex  0.775000E+02  0.381337E+02  0.440331E+02
 endloop
endfacet
facet normal -0.286929E+00  0.174726E+00  0.941883E+00
 outer loop
  vertex  0.685282E+02  0.381337E+02  0.431525E+02
  vertex  0.602169E+02  0.381337E+02  0.406206E+02
  vertex  0.599366E+02  0.341226E+02  0.412793E+02
 endloop
endfacet
facet normal -0.286929E+00  0.174727E+00  0.941882E+00
 outer loop
  vertex  0.599365E+02  0.341226E+02  0.412793E+02
  vertex  0.683827E+02  0.341226E+02  0.438523E+02
  vertex  0.685281E+02  0.381337E+02  0.431525E+02
 endloop
endfacet
facet normal -0.465641E+00  0.175013E+00  0.867496E+00
 outer loop
  vertex  0.602169E+02  0.381337E+02  0.406206E+02
  vertex  0.527313E+02  0.381337E+02  0.366026E+02
  vertex  0.523296E+02  0.341226E+02  0.371962E+02
 endloop
endfacet
facet normal -0.465637E+00  0.174988E+00  0.867503E+00
 outer loop
  vertex  0.523296E+02  0.341226E+02  0.371962E+02
  vertex  0.599366E+02  0.341226E+02  0.412793E+02
  vertex  0.602168E+02  0.381337E+02  0.406206E+02
 endloop
endfacet
facet normal -0.625206E+00  0.175159E+00  0.760550E+00
 outer loop
  vertex  0.527313E+02  0.381337E+02  0.366026E+02
  vertex  0.462364E+02  0.381337E+02  0.312635E+02
  vertex  0.457294E+02  0.341226E+02  0.317705E+02
 endloop
endfacet
facet normal -0.625208E+00  0.175166E+00  0.760547E+00
 outer loop
  vertex  0.457294E+02  0.341226E+02  0.317705E+02
  vertex  0.523296E+02  0.341226E+02  0.371962E+02
  vertex  0.527313E+02  0.381337E+02  0.366026E+02
 endloop
endfacet
facet normal -0.760549E+00  0.175166E+00  0.625206E+00
 outer loop
  vertex  0.462364E+02  0.381337E+02  0.312635E+02
  vertex  0.408973E+02  0.381337E+02  0.247686E+02
  vertex  0.403037E+02  0.341226E+02  0.251703E+02
 endloop
endfacet
facet normal -0.760547E+00  0.175159E+00  0.625210E+00
 outer loop
  vertex  0.403036E+02  0.341226E+02  0.251702E+02
  vertex  0.457294E+02  0.341226E+02  0.317705E+02
  vertex  0.462364E+02  0.381337E+02  0.312635E+02
 endloop
endfacet
facet normal -0.867498E+00  0.174999E+00  0.465642E+00
 outer loop
  vertex  0.408973E+02  0.381337E+02  0.247686E+02
  vertex  0.368793E+02  0.381337E+02  0.172830E+02
  vertex  0.362206E+02  0.341226E+02  0.175633E+02
 endloop
endfacet
facet normal -0.867502E+00  0.175013E+00  0.465630E+00
 outer loop
  vertex  0.362206E+02  0.341226E+02  0.175632E+02
  vertex  0.403037E+02  0.341226E+02  0.251703E+02
  vertex  0.408973E+02  0.381337E+02  0.247686E+02
 endloop
endfacet
facet normal -0.941881E+00  0.174735E+00  0.286928E+00
 outer loop
  vertex  0.368793E+02  0.381337E+02  0.172830E+02
  vertex  0.343474E+02  0.381337E+02  0.897170E+01
  vertex  0.336476E+02  0.341226E+02  0.911720E+01
 endloop
endfacet
facet normal -0.941883E+00  0.174703E+00  0.286941E+00
 outer loop
  vertex  0.336475E+02  0.341226E+02  0.911710E+01
  vertex  0.362206E+02  0.341226E+02  0.175633E+02
  vertex  0.368792E+02  0.381337E+02  0.172830E+02
 endloop
endfacet
facet normal -0.979954E+00  0.174462E+00  0.961963E-01
 outer loop
  vertex  0.343474E+02  0.381337E+02  0.897170E+01
  vertex  0.334667E+02  0.381337E+02  0.000000E+00
  vertex  0.327526E+02  0.341226E+02  0.000000E+00
 endloop
endfacet
facet normal -0.979954E+00  0.174461E+00  0.961979E-01
 outer loop
  vertex  0.327526E+02  0.341226E+02  0.000000E+00
  vertex  0.336476E+02  0.341226E+02  0.911720E+01
  vertex  0.343474E+02  0.381337E+02  0.897160E+01
 endloop
endfacet
facet normal -0.974902E-01  0.647934E-01  0.993125E+00
 outer loop
  vertex  0.775000E+02  0.341226E+02  0.447473E+02
  vertex  0.683827E+02  0.341226E+02  0.438523E+02
  vertex  0.683312E+02  0.302500E+02  0.440999E+02
 endloop
endfacet
facet normal -0.975044E-01  0.648301E-01  0.993121E+00
 outer loop
  vertex  0.683311E+02  0.302500E+02  0.440998E+02
  vertex  0.775000E+02  0.302500E+02  0.450000E+02
  vertex  0.775000E+02  0.341226E+02  0.447472E+02
 endloop
endfacet
facet normal -0.290800E+00  0.649242E-01  0.954578E+00
 outer loop
  vertex  0.683827E+02  0.341226E+02  0.438523E+02
  vertex  0.599366E+02  0.341226E+02  0.412793E+02
  vertex  0.598375E+02  0.302500E+02  0.415125E+02
 endloop
endfacet
facet normal -0.290790E+00  0.649166E-01  0.954582E+00
 outer loop
  vertex  0.598375E+02  0.302500E+02  0.415125E+02
  vertex  0.683312E+02  0.302500E+02  0.440999E+02
  vertex  0.683826E+02  0.341226E+02  0.438522E+02
 endloop
endfacet
facet normal -0.471934E+00  0.649953E-01  0.879235E+00
 outer loop
  vertex  0.599366E+02  0.341226E+02  0.412793E+02
  vertex  0.523296E+02  0.341226E+02  0.371962E+02
  vertex  0.521875E+02  0.302500E+02  0.374062E+02
 endloop
endfacet
facet normal -0.471944E+00  0.650101E-01  0.879228E+00
 outer loop
  vertex  0.521875E+02  0.302500E+02  0.374062E+02
  vertex  0.598375E+02  0.302500E+02  0.415125E+02
  vertex  0.599365E+02  0.341226E+02  0.412793E+02
 endloop
endfacet
facet normal -0.633681E+00  0.650658E-01  0.770854E+00
 outer loop
  vertex  0.523296E+02  0.341226E+02  0.371962E+02
  vertex  0.457294E+02  0.341226E+02  0.317705E+02
  vertex  0.455500E+02  0.302500E+02  0.319499E+02
 endloop
endfacet
facet normal -0.633678E+00  0.650534E-01  0.770857E+00
 outer loop
  vertex  0.455499E+02  0.302500E+02  0.319498E+02
  vertex  0.521875E+02  0.302500E+02  0.374062E+02
  vertex  0.523296E+02  0.341226E+02  0.371962E+02
 endloop
endfacet
facet normal -0.770853E+00  0.650695E-01  0.633681E+00
 outer loop
  vertex  0.457294E+02  0.341226E+02  0.317705E+02
  vertex  0.403037E+02  0.341226E+02  0.251703E+02
  vertex  0.400937E+02  0.302500E+02  0.253125E+02
 endloop
endfacet
facet normal -0.770852E+00  0.650659E-01  0.633682E+00
 outer loop
  vertex  0.400937E+02  0.302500E+02  0.253125E+02
  vertex  0.455500E+02  0.302500E+02  0.319499E+02
  vertex  0.457294E+02  0.341226E+02  0.317705E+02
 endloop
endfacet
facet normal -0.879233E+00  0.650347E-01  0.471933E+00
 outer loop
  vertex  0.403037E+02  0.341226E+02  0.251703E+02
  vertex  0.362206E+02  0.341226E+02  0.175633E+02
  vertex  0.359874E+02  0.302500E+02  0.176625E+02
 endloop
endfacet
facet normal -0.879229E+00  0.649971E-01  0.471945E+00
 outer loop
  vertex  0.359874E+02  0.302500E+02  0.176625E+02
  vertex  0.400937E+02  0.302500E+02  0.253125E+02
  vertex  0.403036E+02  0.341226E+02  0.251702E+02
 endloop
endfacet
facet normal -0.954580E+00  0.648988E-01  0.290801E+00
 outer loop
  vertex  0.362206E+02  0.341226E+02  0.175633E+02
  vertex  0.336476E+02  0.341226E+02  0.911720E+01
  vertex  0.334000E+02  0.302500E+02  0.916870E+01
 endloop
endfacet
facet normal -0.954582E+00  0.649392E-01  0.290787E+00
 outer loop
  vertex  0.334000E+02  0.302500E+02  0.916870E+01
  vertex  0.359874E+02  0.302500E+02  0.176625E+02
  vertex  0.362206E+02  0.341226E+02  0.175632E+02
 endloop
endfacet
facet normal -0.993126E+00  0.647795E-01  0.974909E-01
 outer loop
  vertex  0.336476E+02  0.341226E+02  0.911720E+01
  vertex  0.327526E+02  0.341226E+02  0.000000E+00
  vertex  0.325000E+02  0.302500E+02  0.000000E+00
 endloop
endfacet
facet normal -0.993127E+00  0.647696E-01  0.974856E-01
 outer loop
  vertex  0.325000E+02  0.302500E+02  0.000000E+00
  vertex  0.334000E+02  0.302500E+02  0.916870E+01
  vertex  0.336475E+02  0.341226E+02  0.911710E+01
 endloop
endfacet
facet normal -0.711338E-02 -0.999975E+00  0.652122E-03
 outer loop
  vertex  0.670574E+02  0.100757E+02  0.217100E+01
  vertex  0.668443E+02  0.100758E+02  0.000000E+00
  vertex  0.775000E+02  0.100000E+02  0.000000E+00
 endloop
endfacet
facet normal -0.683603E-02 -0.999975E+00  0.203231E-02
 outer loop
  vertex  0.676700E+02  0.100757E+02  0.418230E+01
  vertex  0.670574E+02  0.100758E+02  0.217100E+01
  vertex  0.775000E+02  0.100000E+02  0.000000E+00
 endloop
endfacet
facet normal -0.629650E-02 -0.999975E+00  0.332449E-02
 outer loop
  vertex  0.686424E+02  0.100757E+02  0.599370E+01
  vertex  0.676701E+02  0.100758E+02  0.418230E+01
  vertex  0.775000E+02  0.100000E+02  0.000000E+00
 endloop
endfacet
facet normal -0.552627E-02 -0.999975E+00  0.447946E-02
 outer loop
  vertex  0.699345E+02  0.100757E+02  0.756540E+01
  vertex  0.686424E+02  0.100758E+02  0.599370E+01
  vertex  0.775000E+02  0.100000E+02  0.000000E+00
 endloop
endfacet
facet normal -0.455514E-02 -0.999975E+00  0.546377E-02
 outer loop
  vertex  0.715062E+02  0.100757E+02  0.885750E+01
  vertex  0.699345E+02  0.100758E+02  0.756550E+01
  vertex  0.775000E+02  0.100000E+02  0.000000E+00
 endloop
endfacet
facet normal -0.340994E-02 -0.999975E+00  0.625002E-02
 outer loop
  vertex  0.733175E+02  0.100757E+02  0.982970E+01
  vertex  0.715062E+02  0.100758E+02  0.885750E+01
  vertex  0.775000E+02  0.100000E+02  0.000000E+00
 endloop
endfacet
facet normal -0.212354E-02 -0.999975E+00  0.680751E-02
 outer loop
  vertex  0.753289E+02  0.100757E+02  0.104425E+02
  vertex  0.733176E+02  0.100758E+02  0.982980E+01
  vertex  0.775000E+02  0.100000E+02  0.000000E+00
 endloop
endfacet
facet normal -0.743086E-03 -0.999975E+00  0.710411E-02
 outer loop
  vertex  0.775000E+02  0.100757E+02  0.106555E+02
  vertex  0.753289E+02  0.100758E+02  0.104425E+02
  vertex  0.775000E+02  0.100000E+02  0.000000E+00
 endloop
endfacet
facet normal -0.262918E-01 -0.999651E+00  0.258079E-02
 outer loop
  vertex  0.668443E+02  0.100758E+02  0.000000E+00
  vertex  0.670574E+02  0.100758E+02  0.217100E+01
  vertex  0.590761E+02  0.102900E+02  0.383040E+01
 endloop
endfacet
facet normal -0.263044E-01 -0.999651E+00  0.255534E-02
 outer loop
  vertex  0.590760E+02  0.102899E+02  0.383030E+01
  vertex  0.587001E+02  0.102900E+02  0.000000E+00
  vertex  0.668442E+02  0.100757E+02  0.000000E+00
 endloop
endfacet
facet normal -0.252305E-01 -0.999652E+00  0.768587E-02
 outer loop
  vertex  0.670574E+02  0.100758E+02  0.217100E+01
  vertex  0.676701E+02  0.100758E+02  0.418230E+01
  vertex  0.601571E+02  0.102900E+02  0.737890E+01
 endloop
endfacet
facet normal -0.252477E-01 -0.999652E+00  0.766314E-02
 outer loop
  vertex  0.601571E+02  0.102899E+02  0.737890E+01
  vertex  0.590761E+02  0.102900E+02  0.383040E+01
  vertex  0.670574E+02  0.100757E+02  0.217100E+01
 endloop
endfacet
facet normal -0.232019E-01 -0.999653E+00  0.124541E-01
 outer loop
  vertex  0.676701E+02  0.100758E+02  0.418230E+01
  vertex  0.686424E+02  0.100758E+02  0.599370E+01
  vertex  0.618726E+02  0.102900E+02  0.105748E+02
 endloop
endfacet
facet normal -0.232235E-01 -0.999653E+00  0.124350E-01
 outer loop
  vertex  0.618726E+02  0.102899E+02  0.105747E+02
  vertex  0.601571E+02  0.102900E+02  0.737890E+01
  vertex  0.676700E+02  0.100757E+02  0.418230E+01
 endloop
endfacet
facet normal -0.203238E-01 -0.999654E+00  0.167072E-01
 outer loop
  vertex  0.686424E+02  0.100758E+02  0.599370E+01
  vertex  0.699345E+02  0.100758E+02  0.756550E+01
  vertex  0.641521E+02  0.102900E+02  0.133478E+02
 endloop
endfacet
facet normal -0.203495E-01 -0.999654E+00  0.166911E-01
 outer loop
  vertex  0.641520E+02  0.102899E+02  0.133478E+02
  vertex  0.618726E+02  0.102900E+02  0.105748E+02
  vertex  0.686424E+02  0.100757E+02  0.599370E+01
 endloop
endfacet
facet normal -0.167071E-01 -0.999654E+00  0.203239E-01
 outer loop
  vertex  0.699345E+02  0.100758E+02  0.756550E+01
  vertex  0.715062E+02  0.100758E+02  0.885750E+01
  vertex  0.669251E+02  0.102900E+02  0.156273E+02
 endloop
endfacet
facet normal -0.167344E-01 -0.999654E+00  0.203135E-01
 outer loop
  vertex  0.669251E+02  0.102899E+02  0.156273E+02
  vertex  0.641521E+02  0.102900E+02  0.133478E+02
  vertex  0.699345E+02  0.100757E+02  0.756540E+01
 endloop
endfacet
facet normal -0.124540E-01 -0.999653E+00  0.232018E-01
 outer loop
  vertex  0.715062E+02  0.100758E+02  0.885750E+01
  vertex  0.733176E+02  0.100758E+02  0.982980E+01
  vertex  0.701210E+02  0.102900E+02  0.173428E+02
 endloop
endfacet
facet normal -0.124831E-01 -0.999653E+00  0.231971E-01
 outer loop
  vertex  0.701210E+02  0.102899E+02  0.173428E+02
  vertex  0.669251E+02  0.102900E+02  0.156273E+02
  vertex  0.715062E+02  0.100757E+02  0.885750E+01
 endloop
endfacet
facet normal -0.768589E-02 -0.999652E+00  0.252304E-01
 outer loop
  vertex  0.733176E+02  0.100758E+02  0.982980E+01
  vertex  0.753289E+02  0.100758E+02  0.104425E+02
  vertex  0.736695E+02  0.102900E+02  0.184238E+02
 endloop
endfacet
facet normal -0.771396E-02 -0.999652E+00  0.252317E-01
 outer loop
  vertex  0.736695E+02  0.102899E+02  0.184237E+02
  vertex  0.701210E+02  0.102900E+02  0.173428E+02
  vertex  0.733175E+02  0.100757E+02  0.982970E+01
 endloop
endfacet
facet normal -0.258061E-02 -0.999651E+00  0.262917E-01
 outer loop
  vertex  0.753289E+02  0.100758E+02  0.104425E+02
  vertex  0.775000E+02  0.100758E+02  0.106556E+02
  vertex  0.775000E+02  0.102900E+02  0.187998E+02
 endloop
endfacet
facet normal -0.260762E-02 -0.999651E+00  0.262988E-01
 outer loop
  vertex  0.775000E+02  0.102899E+02  0.187998E+02
  vertex  0.736695E+02  0.102900E+02  0.184238E+02
  vertex  0.753289E+02  0.100757E+02  0.104425E+02
 endloop
endfacet
facet normal -0.556852E-01 -0.998433E+00  0.546617E-02
 outer loop
  vertex  0.587001E+02  0.102900E+02  0.000000E+00
  vertex  0.590761E+02  0.102900E+02  0.383040E+01
  vertex  0.532266E+02  0.106229E+02  0.504660E+01
 endloop
endfacet
facet normal -0.557036E-01 -0.998432E+00  0.546716E-02
 outer loop
  vertex  0.532266E+02  0.106229E+02  0.504650E+01
  vertex  0.527313E+02  0.106229E+02  0.000000E+00
  vertex  0.587000E+02  0.102899E+02  0.000000E+00
 endloop
endfacet
facet normal -0.534373E-01 -0.998438E+00  0.162789E-01
 outer loop
  vertex  0.590761E+02  0.102900E+02  0.383040E+01
  vertex  0.601571E+02  0.102900E+02  0.737890E+01
  vertex  0.546508E+02  0.106229E+02  0.972170E+01
 endloop
endfacet
facet normal -0.534541E-01 -0.998438E+00  0.162832E-01
 outer loop
  vertex  0.546507E+02  0.106229E+02  0.972160E+01
  vertex  0.532266E+02  0.106229E+02  0.504660E+01
  vertex  0.590760E+02  0.102899E+02  0.383030E+01
 endloop
endfacet
facet normal -0.491410E-01 -0.998443E+00  0.263780E-01
 outer loop
  vertex  0.601571E+02  0.102900E+02  0.737890E+01
  vertex  0.618726E+02  0.102900E+02  0.105748E+02
  vertex  0.569110E+02  0.106229E+02  0.139323E+02
 endloop
endfacet
facet normal -0.491556E-01 -0.998443E+00  0.263856E-01
 outer loop
  vertex  0.569109E+02  0.106229E+02  0.139322E+02
  vertex  0.546508E+02  0.106229E+02  0.972170E+01
  vertex  0.601571E+02  0.102899E+02  0.737890E+01
 endloop
endfacet
facet normal -0.430459E-01 -0.998446E+00  0.353852E-01
 outer loop
  vertex  0.618726E+02  0.102900E+02  0.105748E+02
  vertex  0.641521E+02  0.102900E+02  0.133478E+02
  vertex  0.599142E+02  0.106229E+02  0.175857E+02
 endloop
endfacet
facet normal -0.430586E-01 -0.998445E+00  0.353952E-01
 outer loop
  vertex  0.599141E+02  0.106229E+02  0.175856E+02
  vertex  0.569110E+02  0.106229E+02  0.139323E+02
  vertex  0.618726E+02  0.102899E+02  0.105747E+02
 endloop
endfacet
facet normal -0.353852E-01 -0.998446E+00  0.430460E-01
 outer loop
  vertex  0.641521E+02  0.102900E+02  0.133478E+02
  vertex  0.669251E+02  0.102900E+02  0.156273E+02
  vertex  0.635676E+02  0.106229E+02  0.205889E+02
 endloop
endfacet
facet normal -0.353954E-01 -0.998445E+00  0.430600E-01
 outer loop
  vertex  0.635676E+02  0.106229E+02  0.205888E+02
  vertex  0.599142E+02  0.106229E+02  0.175857E+02
  vertex  0.641520E+02  0.102899E+02  0.133478E+02
 endloop
endfacet
facet normal -0.263778E-01 -0.998443E+00  0.491408E-01
 outer loop
  vertex  0.669251E+02  0.102900E+02  0.156273E+02
  vertex  0.701210E+02  0.102900E+02  0.173428E+02
  vertex  0.677782E+02  0.106229E+02  0.228491E+02
 endloop
endfacet
facet normal -0.263866E-01 -0.998443E+00  0.491552E-01
 outer loop
  vertex  0.677781E+02  0.106229E+02  0.228491E+02
  vertex  0.635676E+02  0.106229E+02  0.205889E+02
  vertex  0.669251E+02  0.102899E+02  0.156273E+02
 endloop
endfacet
facet normal -0.162789E-01 -0.998438E+00  0.534373E-01
 outer loop
  vertex  0.701210E+02  0.102900E+02  0.173428E+02
  vertex  0.736695E+02  0.102900E+02  0.184238E+02
  vertex  0.724533E+02  0.106229E+02  0.242733E+02
 endloop
endfacet
facet normal -0.162838E-01 -0.998438E+00  0.534534E-01
 outer loop
  vertex  0.724533E+02  0.106229E+02  0.242733E+02
  vertex  0.677782E+02  0.106229E+02  0.228491E+02
  vertex  0.701210E+02  0.102899E+02  0.173428E+02
 endloop
endfacet
facet normal -0.546613E-02 -0.998433E+00  0.556860E-01
 outer loop
  vertex  0.736695E+02  0.102900E+02  0.184238E+02
  vertex  0.775000E+02  0.102900E+02  0.187998E+02
  vertex  0.775000E+02  0.106229E+02  0.247686E+02
 endloop
endfacet
facet normal -0.546670E-02 -0.998433E+00  0.557012E-01
 outer loop
  vertex  0.775000E+02  0.106229E+02  0.247686E+02
  vertex  0.724533E+02  0.106229E+02  0.242733E+02
  vertex  0.736695E+02  0.102899E+02  0.184237E+02
 endloop
endfacet
facet normal -0.103964E+00 -0.994529E+00  0.102036E-01
 outer loop
  vertex  0.527313E+02  0.106229E+02  0.000000E+00
  vertex  0.532266E+02  0.106229E+02  0.504660E+01
  vertex  0.491795E+02  0.110546E+02  0.588800E+01
 endloop
endfacet
facet normal -0.103961E+00 -0.994529E+00  0.101885E-01
 outer loop
  vertex  0.491795E+02  0.110545E+02  0.588800E+01
  vertex  0.486015E+02  0.110546E+02  0.000000E+00
  vertex  0.527313E+02  0.106229E+02  0.000000E+00
 endloop
endfacet
facet normal -0.997670E-01 -0.994547E+00  0.303925E-01
 outer loop
  vertex  0.532266E+02  0.106229E+02  0.504660E+01
  vertex  0.546508E+02  0.106229E+02  0.972170E+01
  vertex  0.508411E+02  0.110546E+02  0.113426E+02
 endloop
endfacet
facet normal -0.997718E-01 -0.994547E+00  0.303733E-01
 outer loop
  vertex  0.508410E+02  0.110545E+02  0.113425E+02
  vertex  0.491795E+02  0.110546E+02  0.588800E+01
  vertex  0.532266E+02  0.106229E+02  0.504650E+01
 endloop
endfacet
facet normal -0.917449E-01 -0.994564E+00  0.492476E-01
 outer loop
  vertex  0.546508E+02  0.106229E+02  0.972170E+01
  vertex  0.569110E+02  0.106229E+02  0.139323E+02
  vertex  0.534781E+02  0.110546E+02  0.162553E+02
 endloop
endfacet
facet normal -0.917555E-01 -0.994564E+00  0.492297E-01
 outer loop
  vertex  0.534780E+02  0.110545E+02  0.162553E+02
  vertex  0.508411E+02  0.110546E+02  0.113426E+02
  vertex  0.546507E+02  0.106229E+02  0.972160E+01
 endloop
endfacet
facet normal -0.803683E-01 -0.994573E+00  0.660651E-01
 outer loop
  vertex  0.569110E+02  0.106229E+02  0.139323E+02
  vertex  0.599142E+02  0.106229E+02  0.175857E+02
  vertex  0.569821E+02  0.110546E+02  0.205178E+02
 endloop
endfacet
facet normal -0.803757E-01 -0.994574E+00  0.660513E-01
 outer loop
  vertex  0.569821E+02  0.110545E+02  0.205177E+02
  vertex  0.534781E+02  0.110546E+02  0.162553E+02
  vertex  0.569109E+02  0.106229E+02  0.139322E+02
 endloop
endfacet
facet normal -0.660638E-01 -0.994574E+00  0.803667E-01
 outer loop
  vertex  0.599142E+02  0.106229E+02  0.175857E+02
  vertex  0.635676E+02  0.106229E+02  0.205889E+02
  vertex  0.612446E+02  0.110546E+02  0.240218E+02
 endloop
endfacet
facet normal -0.660786E-01 -0.994574E+00  0.803543E-01
 outer loop
  vertex  0.612445E+02  0.110545E+02  0.240217E+02
  vertex  0.569821E+02  0.110546E+02  0.205178E+02
  vertex  0.599141E+02  0.106229E+02  0.175856E+02
 endloop
endfacet
facet normal -0.492484E-01 -0.994564E+00  0.917464E-01
 outer loop
  vertex  0.635676E+02  0.106229E+02  0.205889E+02
  vertex  0.677782E+02  0.106229E+02  0.228491E+02
  vertex  0.661573E+02  0.110546E+02  0.266588E+02
 endloop
endfacet
facet normal -0.492603E-01 -0.994564E+00  0.917336E-01
 outer loop
  vertex  0.661573E+02  0.110545E+02  0.266588E+02
  vertex  0.612446E+02  0.110546E+02  0.240218E+02
  vertex  0.635676E+02  0.106229E+02  0.205888E+02
 endloop
endfacet
facet normal -0.303930E-01 -0.994546E+00  0.997684E-01
 outer loop
  vertex  0.677782E+02  0.106229E+02  0.228491E+02
  vertex  0.724533E+02  0.106229E+02  0.242733E+02
  vertex  0.716119E+02  0.110546E+02  0.283204E+02
 endloop
endfacet
facet normal -0.304079E-01 -0.994547E+00  0.997613E-01
 outer loop
  vertex  0.716119E+02  0.110545E+02  0.283204E+02
  vertex  0.661573E+02  0.110546E+02  0.266588E+02
  vertex  0.677781E+02  0.106229E+02  0.228491E+02
 endloop
endfacet
facet normal -0.102031E-01 -0.994529E+00  0.103961E+00
 outer loop
  vertex  0.724533E+02  0.106229E+02  0.242733E+02
  vertex  0.775000E+02  0.106229E+02  0.247686E+02
  vertex  0.775000E+02  0.110546E+02  0.288984E+02
 endloop
endfacet
facet normal -0.102203E-01 -0.994529E+00  0.103960E+00
 outer loop
  vertex  0.775000E+02  0.110545E+02  0.288983E+02
  vertex  0.716119E+02  0.110546E+02  0.283204E+02
  vertex  0.724533E+02  0.106229E+02  0.242733E+02
 endloop
endfacet
facet normal -0.190882E+00 -0.981434E+00  0.187380E-01
 outer loop
  vertex  0.486015E+02  0.110546E+02  0.000000E+00
  vertex  0.491795E+02  0.110546E+02  0.588800E+01
  vertex  0.466052E+02  0.115655E+02  0.642320E+01
 endloop
endfacet
facet normal -0.190920E+00 -0.981427E+00  0.187407E-01
 outer loop
  vertex  0.466052E+02  0.115655E+02  0.642320E+01
  vertex  0.459747E+02  0.115655E+02  0.000000E+00
  vertex  0.486015E+02  0.110545E+02  0.000000E+00
 endloop
endfacet
facet normal -0.183192E+00 -0.981492E+00  0.558045E-01
 outer loop
  vertex  0.491795E+02  0.110546E+02  0.588800E+01
  vertex  0.508411E+02  0.110546E+02  0.113426E+02
  vertex  0.484179E+02  0.115655E+02  0.123736E+02
 endloop
endfacet
facet normal -0.183222E+00 -0.981486E+00  0.558157E-01
 outer loop
  vertex  0.484179E+02  0.115655E+02  0.123736E+02
  vertex  0.466052E+02  0.115655E+02  0.642320E+01
  vertex  0.491795E+02  0.110545E+02  0.588800E+01
 endloop
endfacet
facet normal -0.168470E+00 -0.981550E+00  0.904302E-01
 outer loop
  vertex  0.508411E+02  0.110546E+02  0.113426E+02
  vertex  0.534781E+02  0.110546E+02  0.162553E+02
  vertex  0.512946E+02  0.115655E+02  0.177329E+02
 endloop
endfacet
facet normal -0.168506E+00 -0.981542E+00  0.904487E-01
 outer loop
  vertex  0.512946E+02  0.115655E+02  0.177329E+02
  vertex  0.484179E+02  0.115655E+02  0.123736E+02
  vertex  0.508410E+02  0.110545E+02  0.113425E+02
 endloop
endfacet
facet normal -0.147571E+00 -0.981584E+00  0.121311E+00
 outer loop
  vertex  0.534781E+02  0.110546E+02  0.162553E+02
  vertex  0.569821E+02  0.110546E+02  0.205178E+02
  vertex  0.551170E+02  0.115655E+02  0.223829E+02
 endloop
endfacet
facet normal -0.147611E+00 -0.981574E+00  0.121339E+00
 outer loop
  vertex  0.551170E+02  0.115655E+02  0.223829E+02
  vertex  0.512946E+02  0.115655E+02  0.177329E+02
  vertex  0.534780E+02  0.110545E+02  0.162553E+02
 endloop
endfacet
facet normal -0.121316E+00 -0.981582E+00  0.147577E+00
 outer loop
  vertex  0.569821E+02  0.110546E+02  0.205178E+02
  vertex  0.612446E+02  0.110546E+02  0.240218E+02
  vertex  0.597670E+02  0.115655E+02  0.262053E+02
 endloop
endfacet
facet normal -0.121328E+00 -0.981578E+00  0.147597E+00
 outer loop
  vertex  0.597669E+02  0.115655E+02  0.262052E+02
  vertex  0.551170E+02  0.115655E+02  0.223829E+02
  vertex  0.569821E+02  0.110545E+02  0.205177E+02
 endloop
endfacet
facet normal -0.904306E-01 -0.981550E+00  0.168471E+00
 outer loop
  vertex  0.612446E+02  0.110546E+02  0.240218E+02
  vertex  0.661573E+02  0.110546E+02  0.266588E+02
  vertex  0.651263E+02  0.115655E+02  0.290820E+02
 endloop
endfacet
facet normal -0.904466E-01 -0.981543E+00  0.168499E+00
 outer loop
  vertex  0.651262E+02  0.115655E+02  0.290820E+02
  vertex  0.597670E+02  0.115655E+02  0.262053E+02
  vertex  0.612445E+02  0.110545E+02  0.240217E+02
 endloop
endfacet
facet normal -0.558032E-01 -0.981493E+00  0.183187E+00
 outer loop
  vertex  0.661573E+02  0.110546E+02  0.266588E+02
  vertex  0.716119E+02  0.110546E+02  0.283204E+02
  vertex  0.710767E+02  0.115655E+02  0.308947E+02
 endloop
endfacet
facet normal -0.558149E-01 -0.981485E+00  0.183226E+00
 outer loop
  vertex  0.710766E+02  0.115655E+02  0.308946E+02
  vertex  0.651263E+02  0.115655E+02  0.290820E+02
  vertex  0.661573E+02  0.110545E+02  0.266588E+02
 endloop
endfacet
facet normal -0.187380E-01 -0.981434E+00  0.190884E+00
 outer loop
  vertex  0.716119E+02  0.110546E+02  0.283204E+02
  vertex  0.775000E+02  0.110546E+02  0.288984E+02
  vertex  0.775000E+02  0.115655E+02  0.315252E+02
 endloop
endfacet
facet normal -0.187373E-01 -0.981427E+00  0.190919E+00
 outer loop
  vertex  0.775000E+02  0.115655E+02  0.315251E+02
  vertex  0.710767E+02  0.115655E+02  0.308947E+02
  vertex  0.716119E+02  0.110545E+02  0.283204E+02
 endloop
endfacet
facet normal -0.363534E+00 -0.930897E+00  0.356845E-01
 outer loop
  vertex  0.459747E+02  0.115655E+02  0.000000E+00
  vertex  0.466052E+02  0.115655E+02  0.642320E+01
  vertex  0.451743E+02  0.121357E+02  0.672070E+01
 endloop
endfacet
facet normal -0.363534E+00 -0.930897E+00  0.356850E-01
 outer loop
  vertex  0.451743E+02  0.121357E+02  0.672060E+01
  vertex  0.445146E+02  0.121357E+02  0.000000E+00
  vertex  0.459747E+02  0.115655E+02  0.000000E+00
 endloop
endfacet
facet normal -0.348942E+00 -0.931096E+00  0.106300E+00
 outer loop
  vertex  0.466052E+02  0.115655E+02  0.642320E+01
  vertex  0.484179E+02  0.115655E+02  0.123736E+02
  vertex  0.470710E+02  0.121357E+02  0.129467E+02
 endloop
endfacet
facet normal -0.348934E+00 -0.931100E+00  0.106294E+00
 outer loop
  vertex  0.470709E+02  0.121357E+02  0.129467E+02
  vertex  0.451743E+02  0.121357E+02  0.672070E+01
  vertex  0.466052E+02  0.115655E+02  0.642320E+01
 endloop
endfacet
facet normal -0.320948E+00 -0.931297E+00  0.172275E+00
 outer loop
  vertex  0.484179E+02  0.115655E+02  0.123736E+02
  vertex  0.512946E+02  0.115655E+02  0.177329E+02
  vertex  0.500809E+02  0.121357E+02  0.185542E+02
 endloop
endfacet
facet normal -0.320955E+00 -0.931295E+00  0.172274E+00
 outer loop
  vertex  0.500808E+02  0.121357E+02  0.185541E+02
  vertex  0.470710E+02  0.121357E+02  0.129467E+02
  vertex  0.484179E+02  0.115655E+02  0.123736E+02
 endloop
endfacet
facet normal -0.281176E+00 -0.931406E+00  0.231133E+00
 outer loop
  vertex  0.512946E+02  0.115655E+02  0.177329E+02
  vertex  0.551170E+02  0.115655E+02  0.223829E+02
  vertex  0.540803E+02  0.121357E+02  0.234195E+02
 endloop
endfacet
facet normal -0.281176E+00 -0.931408E+00  0.231128E+00
 outer loop
  vertex  0.540802E+02  0.121357E+02  0.234195E+02
  vertex  0.500809E+02  0.121357E+02  0.185542E+02
  vertex  0.512946E+02  0.115655E+02  0.177329E+02
 endloop
endfacet
facet normal -0.231131E+00 -0.931407E+00  0.281174E+00
 outer loop
  vertex  0.551170E+02  0.115655E+02  0.223829E+02
  vertex  0.597670E+02  0.115655E+02  0.262053E+02
  vertex  0.589457E+02  0.121357E+02  0.274190E+02
 endloop
endfacet
facet normal -0.231136E+00 -0.931405E+00  0.281177E+00
 outer loop
  vertex  0.589457E+02  0.121357E+02  0.274190E+02
  vertex  0.540803E+02  0.121357E+02  0.234195E+02
  vertex  0.551170E+02  0.115655E+02  0.223829E+02
 endloop
endfacet
facet normal -0.172278E+00 -0.931294E+00  0.320954E+00
 outer loop
  vertex  0.597670E+02  0.115655E+02  0.262053E+02
  vertex  0.651263E+02  0.115655E+02  0.290820E+02
  vertex  0.645532E+02  0.121357E+02  0.304289E+02
 endloop
endfacet
facet normal -0.172268E+00 -0.931300E+00  0.320943E+00
 outer loop
  vertex  0.645531E+02  0.121357E+02  0.304288E+02
  vertex  0.589457E+02  0.121357E+02  0.274190E+02
  vertex  0.597669E+02  0.115655E+02  0.262052E+02
 endloop
endfacet
facet normal -0.106297E+00 -0.931099E+00  0.348934E+00
 outer loop
  vertex  0.651263E+02  0.115655E+02  0.290820E+02
  vertex  0.710767E+02  0.115655E+02  0.308947E+02
  vertex  0.707792E+02  0.121357E+02  0.323256E+02
 endloop
endfacet
facet normal -0.106301E+00 -0.931093E+00  0.348949E+00
 outer loop
  vertex  0.707791E+02  0.121357E+02  0.323255E+02
  vertex  0.645532E+02  0.121357E+02  0.304289E+02
  vertex  0.651262E+02  0.115655E+02  0.290820E+02
 endloop
endfacet
facet normal -0.356840E-01 -0.930897E+00  0.363535E+00
 outer loop
  vertex  0.710767E+02  0.115655E+02  0.308947E+02
  vertex  0.775000E+02  0.115655E+02  0.315252E+02
  vertex  0.775000E+02  0.121357E+02  0.329853E+02
 endloop
endfacet
facet normal -0.356765E-01 -0.930905E+00  0.363516E+00
 outer loop
  vertex  0.775000E+02  0.121357E+02  0.329852E+02
  vertex  0.707792E+02  0.121357E+02  0.323256E+02
  vertex  0.710766E+02  0.115655E+02  0.308946E+02
 endloop
endfacet
facet normal -0.694106E+00 -0.716641E+00  0.681333E-01
 outer loop
  vertex  0.445146E+02  0.121357E+02  0.000000E+00
  vertex  0.451743E+02  0.121357E+02  0.672070E+01
  vertex  0.445574E+02  0.127454E+02  0.684900E+01
 endloop
endfacet
facet normal -0.694161E+00 -0.716588E+00  0.681299E-01
 outer loop
  vertex  0.445573E+02  0.127454E+02  0.684890E+01
  vertex  0.438851E+02  0.127454E+02  0.000000E+00
  vertex  0.445145E+02  0.121357E+02  0.000000E+00
 endloop
endfacet
facet normal -0.666560E+00 -0.717261E+00  0.203062E+00
 outer loop
  vertex  0.451743E+02  0.121357E+02  0.672070E+01
  vertex  0.470710E+02  0.121357E+02  0.129467E+02
  vertex  0.464902E+02  0.127454E+02  0.131938E+02
 endloop
endfacet
facet normal -0.666592E+00 -0.717230E+00  0.203066E+00
 outer loop
  vertex  0.464902E+02  0.127454E+02  0.131937E+02
  vertex  0.445574E+02  0.127454E+02  0.684900E+01
  vertex  0.451743E+02  0.121357E+02  0.672060E+01
 endloop
endfacet
facet normal -0.613475E+00 -0.717785E+00  0.329291E+00
 outer loop
  vertex  0.470710E+02  0.121357E+02  0.129467E+02
  vertex  0.500809E+02  0.121357E+02  0.185542E+02
  vertex  0.495576E+02  0.127454E+02  0.189083E+02
 endloop
endfacet
facet normal -0.613492E+00 -0.717769E+00  0.329296E+00
 outer loop
  vertex  0.495575E+02  0.127454E+02  0.189083E+02
  vertex  0.464902E+02  0.127454E+02  0.131938E+02
  vertex  0.470709E+02  0.121357E+02  0.129467E+02
 endloop
endfacet
facet normal -0.537628E+00 -0.718082E+00  0.441944E+00
 outer loop
  vertex  0.500809E+02  0.121357E+02  0.185542E+02
  vertex  0.540803E+02  0.121357E+02  0.234195E+02
  vertex  0.536334E+02  0.127454E+02  0.238665E+02
 endloop
endfacet
facet normal -0.537625E+00 -0.718090E+00  0.441935E+00
 outer loop
  vertex  0.536333E+02  0.127454E+02  0.238665E+02
  vertex  0.495576E+02  0.127454E+02  0.189083E+02
  vertex  0.500808E+02  0.121357E+02  0.185541E+02
 endloop
endfacet
facet normal -0.441935E+00 -0.718098E+00  0.537615E+00
 outer loop
  vertex  0.540803E+02  0.121357E+02  0.234195E+02
  vertex  0.589457E+02  0.121357E+02  0.274190E+02
  vertex  0.585916E+02  0.127454E+02  0.279423E+02
 endloop
endfacet
facet normal -0.441969E+00 -0.718055E+00  0.537643E+00
 outer loop
  vertex  0.585915E+02  0.127454E+02  0.279423E+02
  vertex  0.536334E+02  0.127454E+02  0.238665E+02
  vertex  0.540802E+02  0.121357E+02  0.234195E+02
 endloop
endfacet
facet normal -0.329275E+00 -0.717818E+00  0.613445E+00
 outer loop
  vertex  0.589457E+02  0.121357E+02  0.274190E+02
  vertex  0.645532E+02  0.121357E+02  0.304289E+02
  vertex  0.643061E+02  0.127454E+02  0.310097E+02
 endloop
endfacet
facet normal -0.329300E+00 -0.717786E+00  0.613469E+00
 outer loop
  vertex  0.643060E+02  0.127454E+02  0.310097E+02
  vertex  0.585916E+02  0.127454E+02  0.279423E+02
  vertex  0.589457E+02  0.121357E+02  0.274190E+02
 endloop
endfacet
facet normal -0.203077E+00 -0.717213E+00  0.666607E+00
 outer loop
  vertex  0.645532E+02  0.121357E+02  0.304289E+02
  vertex  0.707792E+02  0.121357E+02  0.323256E+02
  vertex  0.706509E+02  0.127454E+02  0.329425E+02
 endloop
endfacet
facet normal -0.203042E+00 -0.717298E+00  0.666526E+00
 outer loop
  vertex  0.706509E+02  0.127454E+02  0.329425E+02
  vertex  0.643061E+02  0.127454E+02  0.310097E+02
  vertex  0.645531E+02  0.121357E+02  0.304288E+02
 endloop
endfacet
facet normal -0.681315E-01 -0.716645E+00  0.694103E+00
 outer loop
  vertex  0.707792E+02  0.121357E+02  0.323256E+02
  vertex  0.775000E+02  0.121357E+02  0.329853E+02
  vertex  0.775000E+02  0.127454E+02  0.336148E+02
 endloop
endfacet
facet normal -0.681177E-01 -0.716690E+00  0.694057E+00
 outer loop
  vertex  0.775000E+02  0.127454E+02  0.336147E+02
  vertex  0.706509E+02  0.127454E+02  0.329425E+02
  vertex  0.707791E+02  0.121357E+02  0.323255E+02
 endloop
endfacet
facet normal -0.973240E+00 -0.208992E+00  0.955333E-01
 outer loop
  vertex  0.438851E+02  0.127454E+02  0.000000E+00
  vertex  0.445574E+02  0.127454E+02  0.684900E+01
  vertex  0.444249E+02  0.133750E+02  0.687650E+01
 endloop
endfacet
facet normal -0.973272E+00 -0.208848E+00  0.955226E-01
 outer loop
  vertex  0.444249E+02  0.133750E+02  0.687650E+01
  vertex  0.437500E+02  0.133750E+02  0.000000E+00
  vertex  0.438851E+02  0.127454E+02  0.000000E+00
 endloop
endfacet
facet normal -0.935450E+00 -0.209117E+00  0.284964E+00
 outer loop
  vertex  0.445574E+02  0.127454E+02  0.684900E+01
  vertex  0.464902E+02  0.127454E+02  0.131938E+02
  vertex  0.463656E+02  0.133750E+02  0.132468E+02
 endloop
endfacet
facet normal -0.935426E+00 -0.209206E+00  0.284976E+00
 outer loop
  vertex  0.463656E+02  0.133750E+02  0.132468E+02
  vertex  0.444249E+02  0.133750E+02  0.687650E+01
  vertex  0.445573E+02  0.127454E+02  0.684890E+01
 endloop
endfacet
facet normal -0.861540E+00 -0.209490E+00  0.462453E+00
 outer loop
  vertex  0.464902E+02  0.127454E+02  0.131938E+02
  vertex  0.495576E+02  0.127454E+02  0.189083E+02
  vertex  0.494453E+02  0.133750E+02  0.189843E+02
 endloop
endfacet
facet normal -0.861540E+00 -0.209504E+00  0.462446E+00
 outer loop
  vertex  0.494453E+02  0.133750E+02  0.189843E+02
  vertex  0.463656E+02  0.133750E+02  0.132468E+02
  vertex  0.464902E+02  0.127454E+02  0.131937E+02
 endloop
endfacet
facet normal -0.755314E+00 -0.209743E+00  0.620893E+00
 outer loop
  vertex  0.495576E+02  0.127454E+02  0.189083E+02
  vertex  0.536334E+02  0.127454E+02  0.238665E+02
  vertex  0.535374E+02  0.133750E+02  0.239624E+02
 endloop
endfacet
facet normal -0.755357E+00 -0.209559E+00  0.620903E+00
 outer loop
  vertex  0.535373E+02  0.133750E+02  0.239624E+02
  vertex  0.494453E+02  0.133750E+02  0.189843E+02
  vertex  0.495575E+02  0.127454E+02  0.189083E+02
 endloop
endfacet
facet normal -0.620902E+00 -0.209675E+00  0.755326E+00
 outer loop
  vertex  0.536334E+02  0.127454E+02  0.238665E+02
  vertex  0.585916E+02  0.127454E+02  0.279423E+02
  vertex  0.585156E+02  0.133750E+02  0.280546E+02
 endloop
endfacet
facet normal -0.620903E+00 -0.209629E+00  0.755338E+00
 outer loop
  vertex  0.585155E+02  0.133750E+02  0.280545E+02
  vertex  0.535374E+02  0.133750E+02  0.239624E+02
  vertex  0.536333E+02  0.127454E+02  0.238665E+02
 endloop
endfacet
facet normal -0.462459E+00 -0.209434E+00  0.861551E+00
 outer loop
  vertex  0.585916E+02  0.127454E+02  0.279423E+02
  vertex  0.643061E+02  0.127454E+02  0.310097E+02
  vertex  0.642531E+02  0.133750E+02  0.311343E+02
 endloop
endfacet
facet normal -0.462461E+00 -0.209423E+00  0.861552E+00
 outer loop
  vertex  0.642530E+02  0.133750E+02  0.311343E+02
  vertex  0.585156E+02  0.133750E+02  0.280546E+02
  vertex  0.585915E+02  0.127454E+02  0.279423E+02
 endloop
endfacet
facet normal -0.284952E+00 -0.209306E+00  0.935411E+00
 outer loop
  vertex  0.643061E+02  0.127454E+02  0.310097E+02
  vertex  0.706509E+02  0.127454E+02  0.329425E+02
  vertex  0.706234E+02  0.133750E+02  0.330750E+02
 endloop
endfacet
facet normal -0.284988E+00 -0.209075E+00  0.935452E+00
 outer loop
  vertex  0.706233E+02  0.133750E+02  0.330750E+02
  vertex  0.642531E+02  0.133750E+02  0.311343E+02
  vertex  0.643060E+02  0.127454E+02  0.310097E+02
 endloop
endfacet
facet normal -0.955319E-01 -0.208994E+00  0.973240E+00
 outer loop
  vertex  0.706509E+02  0.127454E+02  0.329425E+02
  vertex  0.775000E+02  0.127454E+02  0.336148E+02
  vertex  0.775000E+02  0.133750E+02  0.337500E+02
 endloop
endfacet
facet normal -0.955321E-01 -0.208992E+00  0.973240E+00
 outer loop
  vertex  0.775000E+02  0.133750E+02  0.337500E+02
  vertex  0.706234E+02  0.133750E+02  0.330750E+02
  vertex  0.706509E+02  0.127454E+02  0.329425E+02
 endloop
endfacet
facet normal  0.931974E+00 -0.350792E+00 -0.914826E-01
 outer loop
  vertex  0.469874E+02  0.649689E+02  0.634380E+01
  vertex  0.466300E+02  0.640000E+02  0.641810E+01
  vertex  0.460000E+02  0.640000E+02  0.000000E+00
 endloop
endfacet
facet normal  0.931972E+00 -0.350799E+00 -0.914812E-01
 outer loop
  vertex  0.460000E+02  0.640000E+02  0.000000E+00
  vertex  0.463647E+02  0.649689E+02  0.000000E+00
  vertex  0.469874E+02  0.649689E+02  0.634380E+01
 endloop
endfacet
facet normal  0.895616E+00 -0.351333E+00 -0.272830E+00
 outer loop
  vertex  0.487777E+02  0.649690E+02  0.122205E+02
  vertex  0.484412E+02  0.640000E+02  0.123637E+02
  vertex  0.466300E+02  0.640000E+02  0.641810E+01
 endloop
endfacet
facet normal  0.895640E+00 -0.351269E+00 -0.272835E+00
 outer loop
  vertex  0.466300E+02  0.640000E+02  0.641800E+01
  vertex  0.469874E+02  0.649689E+02  0.634380E+01
  vertex  0.487776E+02  0.649690E+02  0.122204E+02
 endloop
endfacet
facet normal  0.824763E+00 -0.351817E+00 -0.442708E+00
 outer loop
  vertex  0.516188E+02  0.649690E+02  0.175135E+02
  vertex  0.513156E+02  0.640000E+02  0.177187E+02
  vertex  0.484412E+02  0.640000E+02  0.123637E+02
 endloop
endfacet
facet normal  0.824773E+00 -0.351791E+00 -0.442710E+00
 outer loop
  vertex  0.484412E+02  0.640000E+02  0.123636E+02
  vertex  0.487777E+02  0.649690E+02  0.122205E+02
  vertex  0.516188E+02  0.649690E+02  0.175135E+02
 endloop
endfacet
facet normal  0.723044E+00 -0.352030E+00 -0.594376E+00
 outer loop
  vertex  0.553939E+02  0.649689E+02  0.221060E+02
  vertex  0.551350E+02  0.640000E+02  0.223649E+02
  vertex  0.513156E+02  0.640000E+02  0.177187E+02
 endloop
endfacet
facet normal  0.723032E+00 -0.352098E+00 -0.594350E+00
 outer loop
  vertex  0.513156E+02  0.640000E+02  0.177187E+02
  vertex  0.516188E+02  0.649690E+02  0.175135E+02
  vertex  0.553939E+02  0.649689E+02  0.221060E+02
 endloop
endfacet
facet normal  0.594352E+00 -0.352129E+00 -0.723015E+00
 outer loop
  vertex  0.599864E+02  0.649689E+02  0.258811E+02
  vertex  0.597812E+02  0.640000E+02  0.261843E+02
  vertex  0.551350E+02  0.640000E+02  0.223649E+02
 endloop
endfacet
facet normal  0.594340E+00 -0.352081E+00 -0.723048E+00
 outer loop
  vertex  0.551349E+02  0.640000E+02  0.223649E+02
  vertex  0.553939E+02  0.649689E+02  0.221060E+02
  vertex  0.599864E+02  0.649689E+02  0.258810E+02
 endloop
endfacet
facet normal  0.442699E+00 -0.351866E+00 -0.824747E+00
 outer loop
  vertex  0.652794E+02  0.649689E+02  0.287222E+02
  vertex  0.651362E+02  0.640000E+02  0.290587E+02
  vertex  0.597812E+02  0.640000E+02  0.261843E+02
 endloop
endfacet
facet normal  0.442713E+00 -0.351775E+00 -0.824779E+00
 outer loop
  vertex  0.597812E+02  0.640000E+02  0.261842E+02
  vertex  0.599864E+02  0.649689E+02  0.258811E+02
  vertex  0.652794E+02  0.649689E+02  0.287222E+02
 endloop
endfacet
facet normal  0.272835E+00 -0.351292E+00 -0.895631E+00
 outer loop
  vertex  0.711561E+02  0.649689E+02  0.305125E+02
  vertex  0.710818E+02  0.640000E+02  0.308699E+02
  vertex  0.651362E+02  0.640000E+02  0.290587E+02
 endloop
endfacet
facet normal  0.272841E+00 -0.351392E+00 -0.895590E+00
 outer loop
  vertex  0.651361E+02  0.640000E+02  0.290587E+02
  vertex  0.652794E+02  0.649689E+02  0.287222E+02
  vertex  0.711560E+02  0.649689E+02  0.305125E+02
 endloop
endfacet
facet normal  0.914810E-01 -0.350799E+00 -0.931972E+00
 outer loop
  vertex  0.775000E+02  0.649689E+02  0.311352E+02
  vertex  0.775000E+02  0.640000E+02  0.314999E+02
  vertex  0.710818E+02  0.640000E+02  0.308699E+02
 endloop
endfacet
facet normal  0.914831E-01 -0.350708E+00 -0.932006E+00
 outer loop
  vertex  0.710818E+02  0.640000E+02  0.308698E+02
  vertex  0.711561E+02  0.649689E+02  0.305125E+02
  vertex  0.775000E+02  0.649689E+02  0.311352E+02
 endloop
endfacet
facet normal  0.989526E+00 -0.106789E+00 -0.971307E-01
 outer loop
  vertex  0.470606E+02  0.656611E+02  0.632850E+01
  vertex  0.469874E+02  0.649689E+02  0.634380E+01
  vertex  0.463647E+02  0.649689E+02  0.000000E+00
 endloop
endfacet
facet normal  0.989526E+00 -0.106786E+00 -0.971327E-01
 outer loop
  vertex  0.463647E+02  0.649689E+02  0.000000E+00
  vertex  0.464394E+02  0.656611E+02  0.000000E+00
  vertex  0.470606E+02  0.656611E+02  0.632840E+01
 endloop
endfacet
facet normal  0.951109E+00 -0.106953E+00 -0.289747E+00
 outer loop
  vertex  0.488466E+02  0.656611E+02  0.121912E+02
  vertex  0.487777E+02  0.649690E+02  0.122205E+02
  vertex  0.469874E+02  0.649689E+02  0.634380E+01
 endloop
endfacet
facet normal  0.951111E+00 -0.106984E+00 -0.289728E+00
 outer loop
  vertex  0.469874E+02  0.649689E+02  0.634380E+01
  vertex  0.470606E+02  0.656611E+02  0.632850E+01
  vertex  0.488465E+02  0.656611E+02  0.121912E+02
 endloop
endfacet
facet normal  0.876023E+00 -0.107137E+00 -0.470219E+00
 outer loop
  vertex  0.516809E+02  0.656611E+02  0.174715E+02
  vertex  0.516188E+02  0.649690E+02  0.175135E+02
  vertex  0.487777E+02  0.649690E+02  0.122205E+02
 endloop
endfacet
facet normal  0.876018E+00 -0.107175E+00 -0.470219E+00
 outer loop
  vertex  0.487776E+02  0.649690E+02  0.122204E+02
  vertex  0.488466E+02  0.656611E+02  0.121912E+02
  vertex  0.516809E+02  0.656611E+02  0.174715E+02
 endloop
endfacet
facet normal  0.768039E+00 -0.107346E+00 -0.631342E+00
 outer loop
  vertex  0.554470E+02  0.656611E+02  0.220529E+02
  vertex  0.553939E+02  0.649689E+02  0.221060E+02
  vertex  0.516188E+02  0.649690E+02  0.175135E+02
 endloop
endfacet
facet normal  0.768049E+00 -0.107227E+00 -0.631351E+00
 outer loop
  vertex  0.516188E+02  0.649690E+02  0.175135E+02
  vertex  0.516809E+02  0.656611E+02  0.174715E+02
  vertex  0.554469E+02  0.656611E+02  0.220529E+02
 endloop
endfacet
facet normal  0.631349E+00 -0.107212E+00 -0.768052E+00
 outer loop
  vertex  0.600284E+02  0.656611E+02  0.258190E+02
  vertex  0.599864E+02  0.649689E+02  0.258811E+02
  vertex  0.553939E+02  0.649689E+02  0.221060E+02
 endloop
endfacet
facet normal  0.631352E+00 -0.107347E+00 -0.768030E+00
 outer loop
  vertex  0.553939E+02  0.649689E+02  0.221060E+02
  vertex  0.554470E+02  0.656611E+02  0.220529E+02
  vertex  0.600284E+02  0.656611E+02  0.258190E+02
 endloop
endfacet
facet normal  0.470221E+00 -0.107101E+00 -0.876026E+00
 outer loop
  vertex  0.653087E+02  0.656611E+02  0.286533E+02
  vertex  0.652794E+02  0.649689E+02  0.287222E+02
  vertex  0.599864E+02  0.649689E+02  0.258811E+02
 endloop
endfacet
facet normal  0.470215E+00 -0.106998E+00 -0.876042E+00
 outer loop
  vertex  0.599864E+02  0.649689E+02  0.258810E+02
  vertex  0.600284E+02  0.656611E+02  0.258190E+02
  vertex  0.653087E+02  0.656611E+02  0.286532E+02
 endloop
endfacet
facet normal  0.289748E+00 -0.106986E+00 -0.951105E+00
 outer loop
  vertex  0.711714E+02  0.656611E+02  0.304393E+02
  vertex  0.711561E+02  0.649689E+02  0.305125E+02
  vertex  0.652794E+02  0.649689E+02  0.287222E+02
 endloop
endfacet
facet normal  0.289745E+00 -0.106936E+00 -0.951111E+00
 outer loop
  vertex  0.652794E+02  0.649689E+02  0.287222E+02
  vertex  0.653087E+02  0.656611E+02  0.286533E+02
  vertex  0.711714E+02  0.656611E+02  0.304393E+02
 endloop
endfacet
facet normal  0.971291E-01 -0.106788E+00 -0.989526E+00
 outer loop
  vertex  0.775000E+02  0.656611E+02  0.310605E+02
  vertex  0.775000E+02  0.649689E+02  0.311352E+02
  vertex  0.711561E+02  0.649689E+02  0.305125E+02
 endloop
endfacet
facet normal  0.971138E-01 -0.106804E+00 -0.989526E+00
 outer loop
  vertex  0.711560E+02  0.649689E+02  0.305125E+02
  vertex  0.711714E+02  0.656611E+02  0.304393E+02
  vertex  0.775000E+02  0.656611E+02  0.310604E+02
 endloop
endfacet
facet normal  0.927337E+00  0.362988E+00 -0.910266E-01
 outer loop
  vertex  0.469013E+02  0.660764E+02  0.636170E+01
  vertex  0.470606E+02  0.656611E+02  0.632850E+01
  vertex  0.464394E+02  0.656611E+02  0.000000E+00
 endloop
endfacet
facet normal  0.927381E+00  0.362875E+00 -0.910225E-01
 outer loop
  vertex  0.464393E+02  0.656611E+02  0.000000E+00
  vertex  0.462768E+02  0.660764E+02  0.000000E+00
  vertex  0.469012E+02  0.660764E+02  0.636170E+01
 endloop
endfacet
facet normal  0.891135E+00  0.363566E+00 -0.271473E+00
 outer loop
  vertex  0.486966E+02  0.660764E+02  0.122550E+02
  vertex  0.488466E+02  0.656611E+02  0.121912E+02
  vertex  0.470606E+02  0.656611E+02  0.632850E+01
 endloop
endfacet
facet normal  0.891127E+00  0.363589E+00 -0.271468E+00
 outer loop
  vertex  0.470606E+02  0.656611E+02  0.632840E+01
  vertex  0.469013E+02  0.660764E+02  0.636170E+01
  vertex  0.486966E+02  0.660764E+02  0.122550E+02
 endloop
endfacet
facet normal  0.820585E+00  0.364186E+00 -0.440465E+00
 outer loop
  vertex  0.515457E+02  0.660764E+02  0.175630E+02
  vertex  0.516809E+02  0.656611E+02  0.174715E+02
  vertex  0.488466E+02  0.656611E+02  0.121912E+02
 endloop
endfacet
facet normal  0.820687E+00  0.363894E+00 -0.440516E+00
 outer loop
  vertex  0.488465E+02  0.656611E+02  0.121912E+02
  vertex  0.486966E+02  0.660764E+02  0.122550E+02
  vertex  0.515457E+02  0.660764E+02  0.175629E+02
 endloop
endfacet
facet normal  0.719346E+00  0.364512E+00 -0.591332E+00
 outer loop
  vertex  0.553315E+02  0.660764E+02  0.221684E+02
  vertex  0.554470E+02  0.656611E+02  0.220529E+02
  vertex  0.516809E+02  0.656611E+02  0.174715E+02
 endloop
endfacet
facet normal  0.719353E+00  0.364472E+00 -0.591347E+00
 outer loop
  vertex  0.516809E+02  0.656611E+02  0.174715E+02
  vertex  0.515457E+02  0.660764E+02  0.175630E+02
  vertex  0.553315E+02  0.660764E+02  0.221683E+02
 endloop
endfacet
facet normal  0.591341E+00  0.364472E+00 -0.719357E+00
 outer loop
  vertex  0.599369E+02  0.660764E+02  0.259542E+02
  vertex  0.600284E+02  0.656611E+02  0.258190E+02
  vertex  0.554470E+02  0.656611E+02  0.220529E+02
 endloop
endfacet
facet normal  0.591359E+00  0.364390E+00 -0.719385E+00
 outer loop
  vertex  0.554469E+02  0.656611E+02  0.220529E+02
  vertex  0.553315E+02  0.660764E+02  0.221684E+02
  vertex  0.599369E+02  0.660764E+02  0.259542E+02
 endloop
endfacet
facet normal  0.440486E+00  0.364068E+00 -0.820626E+00
 outer loop
  vertex  0.652449E+02  0.660764E+02  0.288033E+02
  vertex  0.653087E+02  0.656611E+02  0.286533E+02
  vertex  0.600284E+02  0.656611E+02  0.258190E+02
 endloop
endfacet
facet normal  0.440456E+00  0.364185E+00 -0.820590E+00
 outer loop
  vertex  0.600284E+02  0.656611E+02  0.258190E+02
  vertex  0.599369E+02  0.660764E+02  0.259542E+02
  vertex  0.652449E+02  0.660764E+02  0.288033E+02
 endloop
endfacet
facet normal  0.271478E+00  0.363531E+00 -0.891148E+00
 outer loop
  vertex  0.711382E+02  0.660764E+02  0.305986E+02
  vertex  0.711714E+02  0.656611E+02  0.304393E+02
  vertex  0.653087E+02  0.656611E+02  0.286533E+02
 endloop
endfacet
facet normal  0.271453E+00  0.363756E+00 -0.891064E+00
 outer loop
  vertex  0.653087E+02  0.656611E+02  0.286532E+02
  vertex  0.652449E+02  0.660764E+02  0.288033E+02
  vertex  0.711381E+02  0.660764E+02  0.305986E+02
 endloop
endfacet
facet normal  0.910220E-01  0.363068E+00 -0.927306E+00
 outer loop
  vertex  0.775000E+02  0.660764E+02  0.312231E+02
  vertex  0.775000E+02  0.656611E+02  0.310605E+02
  vertex  0.711714E+02  0.656611E+02  0.304393E+02
 endloop
endfacet
facet normal  0.910312E-01  0.362985E+00 -0.927338E+00
 outer loop
  vertex  0.711714E+02  0.656611E+02  0.304393E+02
  vertex  0.711382E+02  0.660764E+02  0.305986E+02
  vertex  0.775000E+02  0.660764E+02  0.312231E+02
 endloop
endfacet
facet normal  0.369998E+00  0.928322E+00 -0.363210E-01
 outer loop
  vertex  0.465610E+02  0.662148E+02  0.643240E+01
  vertex  0.469013E+02  0.660764E+02  0.636170E+01
  vertex  0.462768E+02  0.660764E+02  0.000000E+00
 endloop
endfacet
facet normal  0.370125E+00  0.928272E+00 -0.363170E-01
 outer loop
  vertex  0.462767E+02  0.660764E+02  0.000000E+00
  vertex  0.459296E+02  0.662148E+02  0.000000E+00
  vertex  0.465610E+02  0.662147E+02  0.643240E+01
 endloop
endfacet
facet normal  0.355160E+00  0.928523E+00 -0.108194E+00
 outer loop
  vertex  0.483763E+02  0.662148E+02  0.123913E+02
  vertex  0.486966E+02  0.660764E+02  0.122550E+02
  vertex  0.469013E+02  0.660764E+02  0.636170E+01
 endloop
endfacet
facet normal  0.355236E+00  0.928493E+00 -0.108203E+00
 outer loop
  vertex  0.469012E+02  0.660764E+02  0.636170E+01
  vertex  0.465610E+02  0.662148E+02  0.643240E+01
  vertex  0.483763E+02  0.662147E+02  0.123913E+02
 endloop
endfacet
facet normal  0.326735E+00  0.928702E+00 -0.175377E+00
 outer loop
  vertex  0.512571E+02  0.662148E+02  0.177582E+02
  vertex  0.515457E+02  0.660764E+02  0.175630E+02
  vertex  0.486966E+02  0.660764E+02  0.122550E+02
 endloop
endfacet
facet normal  0.326680E+00  0.928730E+00 -0.175332E+00
 outer loop
  vertex  0.486966E+02  0.660764E+02  0.122550E+02
  vertex  0.483763E+02  0.662148E+02  0.123913E+02
  vertex  0.512570E+02  0.662147E+02  0.177581E+02
 endloop
endfacet
facet normal  0.286212E+00  0.928831E+00 -0.235277E+00
 outer loop
  vertex  0.550850E+02  0.662148E+02  0.224149E+02
  vertex  0.553315E+02  0.660764E+02  0.221684E+02
  vertex  0.515457E+02  0.660764E+02  0.175630E+02
 endloop
endfacet
facet normal  0.286218E+00  0.928835E+00 -0.235256E+00
 outer loop
  vertex  0.515457E+02  0.660764E+02  0.175629E+02
  vertex  0.512571E+02  0.662148E+02  0.177582E+02
  vertex  0.550849E+02  0.662147E+02  0.224148E+02
 endloop
endfacet
facet normal  0.235272E+00  0.928834E+00 -0.286207E+00
 outer loop
  vertex  0.597416E+02  0.662148E+02  0.262428E+02
  vertex  0.599369E+02  0.660764E+02  0.259542E+02
  vertex  0.553315E+02  0.660764E+02  0.221684E+02
 endloop
endfacet
facet normal  0.235240E+00  0.928860E+00 -0.286150E+00
 outer loop
  vertex  0.553315E+02  0.660764E+02  0.221683E+02
  vertex  0.550850E+02  0.662148E+02  0.224149E+02
  vertex  0.597416E+02  0.662147E+02  0.262427E+02
 endloop
endfacet
facet normal  0.175344E+00  0.928730E+00 -0.326673E+00
 outer loop
  vertex  0.651086E+02  0.662148E+02  0.291236E+02
  vertex  0.652449E+02  0.660764E+02  0.288033E+02
  vertex  0.599369E+02  0.660764E+02  0.259542E+02
 endloop
endfacet
facet normal  0.175374E+00  0.928719E+00 -0.326687E+00
 outer loop
  vertex  0.599369E+02  0.660764E+02  0.259542E+02
  vertex  0.597416E+02  0.662148E+02  0.262428E+02
  vertex  0.651085E+02  0.662147E+02  0.291236E+02
 endloop
endfacet
facet normal  0.108190E+00  0.928528E+00 -0.355147E+00
 outer loop
  vertex  0.710675E+02  0.662148E+02  0.309389E+02
  vertex  0.711382E+02  0.660764E+02  0.305986E+02
  vertex  0.652449E+02  0.660764E+02  0.288033E+02
 endloop
endfacet
facet normal  0.108205E+00  0.928524E+00 -0.355156E+00
 outer loop
  vertex  0.652449E+02  0.660764E+02  0.288033E+02
  vertex  0.651086E+02  0.662148E+02  0.291236E+02
  vertex  0.710674E+02  0.662147E+02  0.309388E+02
 endloop
endfacet
facet normal  0.363240E-01  0.928308E+00 -0.370034E+00
 outer loop
  vertex  0.775000E+02  0.662148E+02  0.315703E+02
  vertex  0.775000E+02  0.660764E+02  0.312231E+02
  vertex  0.711382E+02  0.660764E+02  0.305986E+02
 endloop
endfacet
facet normal  0.363273E-01  0.928320E+00 -0.370004E+00
 outer loop
  vertex  0.711381E+02  0.660764E+02  0.305986E+02
  vertex  0.710675E+02  0.662148E+02  0.309389E+02
  vertex  0.775000E+02  0.662147E+02  0.315702E+02
 endloop
endfacet
facet normal -0.277482E+00  0.960345E+00  0.272375E-01
 outer loop
  vertex  0.460916E+02  0.660764E+02  0.653000E+01
  vertex  0.465610E+02  0.662148E+02  0.643240E+01
  vertex  0.459296E+02  0.662148E+02  0.000000E+00
 endloop
endfacet
facet normal -0.277342E+00  0.960386E+00  0.272203E-01
 outer loop
  vertex  0.459295E+02  0.662147E+02  0.000000E+00
  vertex  0.454506E+02  0.660764E+02  0.000000E+00
  vertex  0.460915E+02  0.660764E+02  0.653000E+01
 endloop
endfacet
facet normal -0.266344E+00  0.960457E+00  0.811382E-01
 outer loop
  vertex  0.479345E+02  0.660764E+02  0.125793E+02
  vertex  0.483763E+02  0.662148E+02  0.123913E+02
  vertex  0.465610E+02  0.662148E+02  0.643240E+01
 endloop
endfacet
facet normal -0.266136E+00  0.960520E+00  0.810789E-01
 outer loop
  vertex  0.465610E+02  0.662147E+02  0.643240E+01
  vertex  0.460916E+02  0.660764E+02  0.653000E+01
  vertex  0.479345E+02  0.660764E+02  0.125792E+02
 endloop
endfacet
facet normal -0.244938E+00  0.960583E+00  0.131476E+00
 outer loop
  vertex  0.508590E+02  0.660764E+02  0.180277E+02
  vertex  0.512571E+02  0.662148E+02  0.177582E+02
  vertex  0.483763E+02  0.662148E+02  0.123913E+02
 endloop
endfacet
facet normal -0.244796E+00  0.960630E+00  0.131397E+00
 outer loop
  vertex  0.483763E+02  0.662147E+02  0.123913E+02
  vertex  0.479345E+02  0.660764E+02  0.125793E+02
  vertex  0.508590E+02  0.660764E+02  0.180277E+02
 endloop
endfacet
facet normal -0.214554E+00  0.960657E+00  0.176368E+00
 outer loop
  vertex  0.547449E+02  0.660764E+02  0.227550E+02
  vertex  0.550850E+02  0.662148E+02  0.224149E+02
  vertex  0.512571E+02  0.662148E+02  0.177582E+02
 endloop
endfacet
facet normal -0.214430E+00  0.960703E+00  0.176263E+00
 outer loop
  vertex  0.512570E+02  0.662147E+02  0.177581E+02
  vertex  0.508590E+02  0.660764E+02  0.180277E+02
  vertex  0.547448E+02  0.660764E+02  0.227549E+02
 endloop
endfacet
facet normal -0.176400E+00  0.960643E+00  0.214589E+00
 outer loop
  vertex  0.594722E+02  0.660764E+02  0.266409E+02
  vertex  0.597416E+02  0.662148E+02  0.262428E+02
  vertex  0.550850E+02  0.662148E+02  0.224149E+02
 endloop
endfacet
facet normal -0.176245E+00  0.960712E+00  0.214408E+00
 outer loop
  vertex  0.550849E+02  0.662147E+02  0.224148E+02
  vertex  0.547449E+02  0.660764E+02  0.227550E+02
  vertex  0.594721E+02  0.660764E+02  0.266408E+02
 endloop
endfacet
facet normal -0.131485E+00  0.960576E+00  0.244959E+00
 outer loop
  vertex  0.649206E+02  0.660764E+02  0.295654E+02
  vertex  0.651086E+02  0.662148E+02  0.291236E+02
  vertex  0.597416E+02  0.662148E+02  0.262428E+02
 endloop
endfacet
facet normal -0.131373E+00  0.960643E+00  0.244759E+00
 outer loop
  vertex  0.597416E+02  0.662147E+02  0.262427E+02
  vertex  0.594722E+02  0.660764E+02  0.266409E+02
  vertex  0.649206E+02  0.660764E+02  0.295653E+02
 endloop
endfacet
facet normal -0.811291E-01  0.960466E+00  0.266314E+00
 outer loop
  vertex  0.709699E+02  0.660764E+02  0.314083E+02
  vertex  0.710675E+02  0.662148E+02  0.309389E+02
  vertex  0.651086E+02  0.662148E+02  0.291236E+02
 endloop
endfacet
facet normal -0.810917E-01  0.960506E+00  0.266182E+00
 outer loop
  vertex  0.651085E+02  0.662147E+02  0.291236E+02
  vertex  0.649206E+02  0.660764E+02  0.295654E+02
  vertex  0.709699E+02  0.660764E+02  0.314083E+02
 endloop
endfacet
facet normal -0.272360E-01  0.960348E+00  0.277472E+00
 outer loop
  vertex  0.775000E+02  0.660764E+02  0.320493E+02
  vertex  0.775000E+02  0.662148E+02  0.315703E+02
  vertex  0.710675E+02  0.662148E+02  0.309389E+02
 endloop
endfacet
facet normal -0.272153E-01  0.960412E+00  0.277252E+00
 outer loop
  vertex  0.710674E+02  0.662147E+02  0.309388E+02
  vertex  0.709699E+02  0.660764E+02  0.314083E+02
  vertex  0.775000E+02  0.660764E+02  0.320493E+02
 endloop
endfacet
facet normal -0.595987E+00  0.800860E+00  0.585034E-01
 outer loop
  vertex  0.455447E+02  0.656611E+02  0.664370E+01
  vertex  0.460916E+02  0.660764E+02  0.653000E+01
  vertex  0.454506E+02  0.660764E+02  0.000000E+00
 endloop
endfacet
facet normal -0.596028E+00  0.800829E+00  0.585109E-01
 outer loop
  vertex  0.454505E+02  0.660764E+02  0.000000E+00
  vertex  0.448925E+02  0.656611E+02  0.000000E+00
  vertex  0.455447E+02  0.656611E+02  0.664370E+01
 endloop
endfacet
facet normal -0.572189E+00  0.801382E+00  0.174316E+00
 outer loop
  vertex  0.474196E+02  0.656611E+02  0.127984E+02
  vertex  0.479345E+02  0.660764E+02  0.125793E+02
  vertex  0.460916E+02  0.660764E+02  0.653000E+01
 endloop
endfacet
facet normal -0.572324E+00  0.801278E+00  0.174349E+00
 outer loop
  vertex  0.460915E+02  0.660764E+02  0.653000E+01
  vertex  0.455447E+02  0.656611E+02  0.664370E+01
  vertex  0.474196E+02  0.656611E+02  0.127983E+02
 endloop
endfacet
facet normal -0.526492E+00  0.801837E+00  0.282602E+00
 outer loop
  vertex  0.503950E+02  0.656611E+02  0.183416E+02
  vertex  0.508590E+02  0.660764E+02  0.180277E+02
  vertex  0.479345E+02  0.660764E+02  0.125793E+02
 endloop
endfacet
facet normal -0.526455E+00  0.801867E+00  0.282583E+00
 outer loop
  vertex  0.479345E+02  0.660764E+02  0.125792E+02
  vertex  0.474196E+02  0.656611E+02  0.127984E+02
  vertex  0.503950E+02  0.656611E+02  0.183416E+02
 endloop
endfacet
facet normal -0.461407E+00  0.802027E+00  0.379283E+00
 outer loop
  vertex  0.543487E+02  0.656611E+02  0.231512E+02
  vertex  0.547449E+02  0.660764E+02  0.227550E+02
  vertex  0.508590E+02  0.660764E+02  0.180277E+02
 endloop
endfacet
facet normal -0.461335E+00  0.802086E+00  0.379246E+00
 outer loop
  vertex  0.508590E+02  0.660764E+02  0.180277E+02
  vertex  0.503950E+02  0.656611E+02  0.183416E+02
  vertex  0.543487E+02  0.656611E+02  0.231511E+02
 endloop
endfacet
facet normal -0.379232E+00  0.802087E+00  0.461345E+00
 outer loop
  vertex  0.591583E+02  0.656611E+02  0.271049E+02
  vertex  0.594722E+02  0.660764E+02  0.266409E+02
  vertex  0.547449E+02  0.660764E+02  0.227550E+02
 endloop
endfacet
facet normal -0.379289E+00  0.802035E+00  0.461388E+00
 outer loop
  vertex  0.547448E+02  0.660764E+02  0.227549E+02
  vertex  0.543487E+02  0.656611E+02  0.231512E+02
  vertex  0.591582E+02  0.656611E+02  0.271049E+02
 endloop
endfacet
facet normal -0.282597E+00  0.801843E+00  0.526485E+00
 outer loop
  vertex  0.647015E+02  0.656611E+02  0.300803E+02
  vertex  0.649206E+02  0.660764E+02  0.295654E+02
  vertex  0.594722E+02  0.660764E+02  0.266409E+02
 endloop
endfacet
facet normal -0.282586E+00  0.801857E+00  0.526469E+00
 outer loop
  vertex  0.594721E+02  0.660764E+02  0.266408E+02
  vertex  0.591583E+02  0.656611E+02  0.271049E+02
  vertex  0.647014E+02  0.656611E+02  0.300802E+02
 endloop
endfacet
facet normal -0.174337E+00  0.801328E+00  0.572259E+00
 outer loop
  vertex  0.708562E+02  0.656611E+02  0.319552E+02
  vertex  0.709699E+02  0.660764E+02  0.314083E+02
  vertex  0.649206E+02  0.660764E+02  0.295654E+02
 endloop
endfacet
facet normal -0.174287E+00  0.801431E+00  0.572130E+00
 outer loop
  vertex  0.649206E+02  0.660764E+02  0.295653E+02
  vertex  0.647015E+02  0.656611E+02  0.300803E+02
  vertex  0.708562E+02  0.656611E+02  0.319552E+02
 endloop
endfacet
facet normal -0.585001E-01  0.800880E+00  0.595960E+00
 outer loop
  vertex  0.775000E+02  0.656611E+02  0.326074E+02
  vertex  0.775000E+02  0.660764E+02  0.320493E+02
  vertex  0.709699E+02  0.660764E+02  0.314083E+02
 endloop
endfacet
facet normal -0.584971E-01  0.800861E+00  0.595987E+00
 outer loop
  vertex  0.709699E+02  0.660764E+02  0.314083E+02
  vertex  0.708562E+02  0.656611E+02  0.319552E+02
  vertex  0.775000E+02  0.656611E+02  0.326073E+02
 endloop
endfacet
facet normal -0.761908E+00  0.643353E+00  0.747949E-01
 outer loop
  vertex  0.449719E+02  0.649689E+02  0.676280E+01
  vertex  0.455447E+02  0.656611E+02  0.664370E+01
  vertex  0.448925E+02  0.656611E+02  0.000000E+00
 endloop
endfacet
facet normal -0.761957E+00  0.643294E+00  0.747896E-01
 outer loop
  vertex  0.448925E+02  0.656611E+02  0.000000E+00
  vertex  0.443081E+02  0.649689E+02  0.000000E+00
  vertex  0.449719E+02  0.649689E+02  0.676280E+01
 endloop
endfacet
facet normal -0.731848E+00  0.643969E+00  0.222942E+00
 outer loop
  vertex  0.468804E+02  0.649689E+02  0.130278E+02
  vertex  0.474196E+02  0.656611E+02  0.127984E+02
  vertex  0.455447E+02  0.656611E+02  0.664370E+01
 endloop
endfacet
facet normal -0.731847E+00  0.643968E+00  0.222945E+00
 outer loop
  vertex  0.455447E+02  0.656611E+02  0.664370E+01
  vertex  0.449719E+02  0.649689E+02  0.676280E+01
  vertex  0.468804E+02  0.649689E+02  0.130277E+02
 endloop
endfacet
facet normal -0.673654E+00  0.644546E+00  0.361594E+00
 outer loop
  vertex  0.499092E+02  0.649689E+02  0.186704E+02
  vertex  0.503950E+02  0.656611E+02  0.183416E+02
  vertex  0.474196E+02  0.656611E+02  0.127984E+02
 endloop
endfacet
facet normal -0.673616E+00  0.644602E+00  0.361567E+00
 outer loop
  vertex  0.474196E+02  0.656611E+02  0.127983E+02
  vertex  0.468804E+02  0.649689E+02  0.130278E+02
  vertex  0.499091E+02  0.649689E+02  0.186704E+02
 endloop
endfacet
facet normal -0.590378E+00  0.644921E+00  0.485316E+00
 outer loop
  vertex  0.539337E+02  0.649689E+02  0.235662E+02
  vertex  0.543487E+02  0.656611E+02  0.231512E+02
  vertex  0.503950E+02  0.656611E+02  0.183416E+02
 endloop
endfacet
facet normal -0.590400E+00  0.644891E+00  0.485328E+00
 outer loop
  vertex  0.503950E+02  0.656611E+02  0.183416E+02
  vertex  0.499092E+02  0.649689E+02  0.186704E+02
  vertex  0.539337E+02  0.649689E+02  0.235662E+02
 endloop
endfacet
facet normal -0.485333E+00  0.644890E+00  0.590398E+00
 outer loop
  vertex  0.588295E+02  0.649689E+02  0.275907E+02
  vertex  0.591583E+02  0.656611E+02  0.271049E+02
  vertex  0.543487E+02  0.656611E+02  0.231512E+02
 endloop
endfacet
facet normal -0.485291E+00  0.644970E+00  0.590344E+00
 outer loop
  vertex  0.543487E+02  0.656611E+02  0.231511E+02
  vertex  0.539337E+02  0.649689E+02  0.235662E+02
  vertex  0.588294E+02  0.649689E+02  0.275907E+02
 endloop
endfacet
facet normal -0.361584E+00  0.644571E+00  0.673636E+00
 outer loop
  vertex  0.644721E+02  0.649689E+02  0.306195E+02
  vertex  0.647015E+02  0.656611E+02  0.300803E+02
  vertex  0.591583E+02  0.656611E+02  0.271049E+02
 endloop
endfacet
facet normal -0.361607E+00  0.644515E+00  0.673678E+00
 outer loop
  vertex  0.591582E+02  0.656611E+02  0.271049E+02
  vertex  0.588295E+02  0.649689E+02  0.275907E+02
  vertex  0.644720E+02  0.649689E+02  0.306194E+02
 endloop
endfacet
facet normal -0.222942E+00  0.643969E+00  0.731848E+00
 outer loop
  vertex  0.707371E+02  0.649689E+02  0.325280E+02
  vertex  0.708562E+02  0.656611E+02  0.319552E+02
  vertex  0.647015E+02  0.656611E+02  0.300803E+02
 endloop
endfacet
facet normal -0.222924E+00  0.644011E+00  0.731816E+00
 outer loop
  vertex  0.647014E+02  0.656611E+02  0.300802E+02
  vertex  0.644721E+02  0.649689E+02  0.306195E+02
  vertex  0.707370E+02  0.649689E+02  0.325279E+02
 endloop
endfacet
facet normal -0.747987E-01  0.643294E+00  0.761957E+00
 outer loop
  vertex  0.775000E+02  0.649689E+02  0.331918E+02
  vertex  0.775000E+02  0.656611E+02  0.326074E+02
  vertex  0.708562E+02  0.656611E+02  0.319552E+02
 endloop
endfacet
facet normal -0.747727E-01  0.643352E+00  0.761911E+00
 outer loop
  vertex  0.708562E+02  0.656611E+02  0.319552E+02
  vertex  0.707371E+02  0.649689E+02  0.325280E+02
  vertex  0.775000E+02  0.649689E+02  0.331917E+02
 endloop
endfacet
facet normal -0.863386E+00  0.497376E+00  0.847452E-01
 outer loop
  vertex  0.444249E+02  0.640000E+02  0.687650E+01
  vertex  0.449719E+02  0.649689E+02  0.676280E+01
  vertex  0.443081E+02  0.649689E+02  0.000000E+00
 endloop
endfacet
facet normal -0.863409E+00  0.497336E+00  0.847401E-01
 outer loop
  vertex  0.443081E+02  0.649689E+02  0.000000E+00
  vertex  0.437500E+02  0.640000E+02  0.000000E+00
  vertex  0.444249E+02  0.640000E+02  0.687650E+01
 endloop
endfacet
facet normal -0.829593E+00  0.497904E+00  0.252718E+00
 outer loop
  vertex  0.463656E+02  0.640000E+02  0.132468E+02
  vertex  0.468804E+02  0.649689E+02  0.130278E+02
  vertex  0.449719E+02  0.649689E+02  0.676280E+01
 endloop
endfacet
facet normal -0.829546E+00  0.497982E+00  0.252720E+00
 outer loop
  vertex  0.449719E+02  0.649689E+02  0.676280E+01
  vertex  0.444249E+02  0.640000E+02  0.687650E+01
  vertex  0.463656E+02  0.640000E+02  0.132468E+02
 endloop
endfacet
facet normal -0.763798E+00  0.498522E+00  0.409986E+00
 outer loop
  vertex  0.494453E+02  0.640000E+02  0.189843E+02
  vertex  0.499092E+02  0.649689E+02  0.186704E+02
  vertex  0.468804E+02  0.649689E+02  0.130278E+02
 endloop
endfacet
facet normal -0.763795E+00  0.498532E+00  0.409980E+00
 outer loop
  vertex  0.468804E+02  0.649689E+02  0.130277E+02
  vertex  0.463656E+02  0.640000E+02  0.132468E+02
  vertex  0.494453E+02  0.640000E+02  0.189843E+02
 endloop
endfacet
facet normal -0.669499E+00  0.498886E+00  0.550349E+00
 outer loop
  vertex  0.535374E+02  0.640000E+02  0.239624E+02
  vertex  0.539337E+02  0.649689E+02  0.235662E+02
  vertex  0.499092E+02  0.649689E+02  0.186704E+02
 endloop
endfacet
facet normal -0.669545E+00  0.498805E+00  0.550366E+00
 outer loop
  vertex  0.499091E+02  0.649689E+02  0.186704E+02
  vertex  0.494453E+02  0.640000E+02  0.189843E+02
  vertex  0.535373E+02  0.640000E+02  0.239624E+02
 endloop
endfacet
facet normal -0.550360E+00  0.498857E+00  0.669512E+00
 outer loop
  vertex  0.585156E+02  0.640000E+02  0.280546E+02
  vertex  0.588295E+02  0.649689E+02  0.275907E+02
  vertex  0.539337E+02  0.649689E+02  0.235662E+02
 endloop
endfacet
facet normal -0.550348E+00  0.498876E+00  0.669507E+00
 outer loop
  vertex  0.539337E+02  0.649689E+02  0.235662E+02
  vertex  0.535374E+02  0.640000E+02  0.239624E+02
  vertex  0.585155E+02  0.640000E+02  0.280545E+02
 endloop
endfacet
facet normal -0.409992E+00  0.498501E+00  0.763809E+00
 outer loop
  vertex  0.642531E+02  0.640000E+02  0.311343E+02
  vertex  0.644721E+02  0.649689E+02  0.306195E+02
  vertex  0.588295E+02  0.649689E+02  0.275907E+02
 endloop
endfacet
facet normal -0.409996E+00  0.498491E+00  0.763812E+00
 outer loop
  vertex  0.588294E+02  0.649689E+02  0.275907E+02
  vertex  0.585156E+02  0.640000E+02  0.280546E+02
  vertex  0.642530E+02  0.640000E+02  0.311343E+02
 endloop
endfacet
facet normal -0.252716E+00  0.497919E+00  0.829585E+00
 outer loop
  vertex  0.706234E+02  0.640000E+02  0.330749E+02
  vertex  0.707371E+02  0.649689E+02  0.325280E+02
  vertex  0.644721E+02  0.649689E+02  0.306195E+02
 endloop
endfacet
facet normal -0.252717E+00  0.497949E+00  0.829567E+00
 outer loop
  vertex  0.644720E+02  0.649689E+02  0.306194E+02
  vertex  0.642531E+02  0.640000E+02  0.311343E+02
  vertex  0.706233E+02  0.640000E+02  0.330749E+02
 endloop
endfacet
facet normal -0.847462E-01  0.497336E+00  0.863409E+00
 outer loop
  vertex  0.775000E+02  0.640000E+02  0.337499E+02
  vertex  0.775000E+02  0.649689E+02  0.331918E+02
  vertex  0.707371E+02  0.649689E+02  0.325280E+02
 endloop
endfacet
facet normal -0.847493E-01  0.497369E+00  0.863389E+00
 outer loop
  vertex  0.707370E+02  0.649689E+02  0.325279E+02
  vertex  0.706234E+02  0.640000E+02  0.330749E+02
  vertex  0.775000E+02  0.640000E+02  0.337499E+02
 endloop
endfacet
facet normal -0.429272E+00  0.902194E+00  0.420924E-01
 outer loop
  vertex  0.707816E+02  0.696293E+02  0.139670E+01
  vertex  0.730899E+02  0.707500E+02  0.916800E+00
  vertex  0.730000E+02  0.707500E+02  0.000000E+00
 endloop
endfacet
facet normal -0.429249E+00  0.902203E+00  0.421351E-01
 outer loop
  vertex  0.730000E+02  0.707500E+02  0.000000E+00
  vertex  0.706445E+02  0.696293E+02  0.000000E+00
  vertex  0.707816E+02  0.696293E+02  0.139670E+01
 endloop
endfacet
facet normal -0.412044E+00  0.902473E+00  0.125546E+00
 outer loop
  vertex  0.711758E+02  0.696293E+02  0.269070E+01
  vertex  0.733487E+02  0.707500E+02  0.176620E+01
  vertex  0.730899E+02  0.707500E+02  0.916800E+00
 endloop
endfacet
facet normal -0.412079E+00  0.902463E+00  0.125501E+00
 outer loop
  vertex  0.730898E+02  0.707500E+02  0.916800E+00
  vertex  0.707816E+02  0.696293E+02  0.139670E+01
  vertex  0.711757E+02  0.696293E+02  0.269070E+01
 endloop
endfacet
facet normal -0.379012E+00  0.902755E+00  0.203427E+00
 outer loop
  vertex  0.718013E+02  0.696294E+02  0.385610E+01
  vertex  0.737593E+02  0.707500E+02  0.253120E+01
  vertex  0.733487E+02  0.707500E+02  0.176620E+01
 endloop
endfacet
facet normal -0.379061E+00  0.902746E+00  0.203376E+00
 outer loop
  vertex  0.733487E+02  0.707500E+02  0.176610E+01
  vertex  0.711758E+02  0.696293E+02  0.269070E+01
  vertex  0.718013E+02  0.696294E+02  0.385610E+01
 endloop
endfacet
facet normal -0.332037E+00  0.902895E+00  0.273004E+00
 outer loop
  vertex  0.726326E+02  0.696293E+02  0.486730E+01
  vertex  0.743050E+02  0.707500E+02  0.319490E+01
  vertex  0.737593E+02  0.707500E+02  0.253120E+01
 endloop
endfacet
facet normal -0.332009E+00  0.902908E+00  0.272998E+00
 outer loop
  vertex  0.737593E+02  0.707500E+02  0.253110E+01
  vertex  0.718013E+02  0.696294E+02  0.385610E+01
  vertex  0.726325E+02  0.696293E+02  0.486730E+01
 endloop
endfacet
facet normal -0.273008E+00  0.902893E+00  0.332040E+00
 outer loop
  vertex  0.736437E+02  0.696293E+02  0.569860E+01
  vertex  0.749687E+02  0.707500E+02  0.374060E+01
  vertex  0.743050E+02  0.707500E+02  0.319490E+01
 endloop
endfacet
facet normal -0.272994E+00  0.902895E+00  0.332047E+00
 outer loop
  vertex  0.743050E+02  0.707500E+02  0.319490E+01
  vertex  0.726326E+02  0.696293E+02  0.486730E+01
  vertex  0.736436E+02  0.696293E+02  0.569850E+01
 endloop
endfacet
facet normal -0.203441E+00  0.902741E+00  0.379040E+00
 outer loop
  vertex  0.748092E+02  0.696293E+02  0.632410E+01
  vertex  0.757337E+02  0.707500E+02  0.415120E+01
  vertex  0.749687E+02  0.707500E+02  0.374060E+01
 endloop
endfacet
facet normal -0.203441E+00  0.902741E+00  0.379040E+00
 outer loop
  vertex  0.749686E+02  0.707500E+02  0.374060E+01
  vertex  0.736437E+02  0.696293E+02  0.569860E+01
  vertex  0.748091E+02  0.696293E+02  0.632410E+01
 endloop
endfacet
facet normal -0.125498E+00  0.902477E+00  0.412050E+00
 outer loop
  vertex  0.761032E+02  0.696293E+02  0.671830E+01
  vertex  0.765831E+02  0.707500E+02  0.440990E+01
  vertex  0.757337E+02  0.707500E+02  0.415120E+01
 endloop
endfacet
facet normal -0.125493E+00  0.902478E+00  0.412050E+00
 outer loop
  vertex  0.757337E+02  0.707500E+02  0.415110E+01
  vertex  0.748092E+02  0.696293E+02  0.632410E+01
  vertex  0.761032E+02  0.696293E+02  0.671820E+01
 endloop
endfacet
facet normal -0.421335E-01  0.902203E+00  0.429249E+00
 outer loop
  vertex  0.775000E+02  0.696293E+02  0.685540E+01
  vertex  0.775000E+02  0.707500E+02  0.449990E+01
  vertex  0.765831E+02  0.707500E+02  0.440990E+01
 endloop
endfacet
facet normal -0.421323E-01  0.902202E+00  0.429250E+00
 outer loop
  vertex  0.765830E+02  0.707500E+02  0.440990E+01
  vertex  0.761032E+02  0.696293E+02  0.671830E+01
  vertex  0.775000E+02  0.696293E+02  0.685540E+01
 endloop
endfacet
facet normal -0.250666E+00  0.967761E+00  0.246054E-01
 outer loop
  vertex  0.674396E+02  0.687460E+02  0.209160E+01
  vertex  0.707816E+02  0.696293E+02  0.139670E+01
  vertex  0.706445E+02  0.696293E+02  0.000000E+00
 endloop
endfacet
facet normal -0.250667E+00  0.967761E+00  0.245933E-01
 outer loop
  vertex  0.706445E+02  0.696293E+02  0.000000E+00
  vertex  0.672343E+02  0.687460E+02  0.000000E+00
  vertex  0.674395E+02  0.687460E+02  0.209150E+01
 endloop
endfacet
facet normal -0.240573E+00  0.967860E+00  0.732865E-01
 outer loop
  vertex  0.680299E+02  0.687460E+02  0.402920E+01
  vertex  0.711758E+02  0.696293E+02  0.269070E+01
  vertex  0.707816E+02  0.696293E+02  0.139670E+01
 endloop
endfacet
facet normal -0.240572E+00  0.967861E+00  0.732793E-01
 outer loop
  vertex  0.707816E+02  0.696293E+02  0.139670E+01
  vertex  0.674396E+02  0.687460E+02  0.209160E+01
  vertex  0.680298E+02  0.687460E+02  0.402920E+01
 endloop
endfacet
facet normal -0.221324E+00  0.967948E+00  0.118709E+00
 outer loop
  vertex  0.689667E+02  0.687460E+02  0.577440E+01
  vertex  0.718013E+02  0.696294E+02  0.385610E+01
  vertex  0.711758E+02  0.696293E+02  0.269070E+01
 endloop
endfacet
facet normal -0.221261E+00  0.967957E+00  0.118757E+00
 outer loop
  vertex  0.711757E+02  0.696293E+02  0.269070E+01
  vertex  0.680299E+02  0.687460E+02  0.402920E+01
  vertex  0.689666E+02  0.687460E+02  0.577440E+01
 endloop
endfacet
facet normal -0.193764E+00  0.968014E+00  0.159387E+00
 outer loop
  vertex  0.702114E+02  0.687460E+02  0.728850E+01
  vertex  0.726326E+02  0.696293E+02  0.486730E+01
  vertex  0.718013E+02  0.696294E+02  0.385610E+01
 endloop
endfacet
facet normal -0.193834E+00  0.968005E+00  0.159357E+00
 outer loop
  vertex  0.718013E+02  0.696294E+02  0.385610E+01
  vertex  0.689667E+02  0.687460E+02  0.577440E+01
  vertex  0.702114E+02  0.687460E+02  0.728840E+01
 endloop
endfacet
facet normal -0.159348E+00  0.968011E+00  0.193813E+00
 outer loop
  vertex  0.717255E+02  0.687460E+02  0.853320E+01
  vertex  0.736437E+02  0.696293E+02  0.569860E+01
  vertex  0.726326E+02  0.696293E+02  0.486730E+01
 endloop
endfacet
facet normal -0.159335E+00  0.968011E+00  0.193821E+00
 outer loop
  vertex  0.726325E+02  0.696293E+02  0.486730E+01
  vertex  0.702114E+02  0.687460E+02  0.728850E+01
  vertex  0.717255E+02  0.687460E+02  0.853320E+01
 endloop
endfacet
facet normal -0.118746E+00  0.967959E+00  0.221259E+00
 outer loop
  vertex  0.734707E+02  0.687460E+02  0.947000E+01
  vertex  0.748092E+02  0.696293E+02  0.632410E+01
  vertex  0.736437E+02  0.696293E+02  0.569860E+01
 endloop
endfacet
facet normal -0.118767E+00  0.967957E+00  0.221255E+00
 outer loop
  vertex  0.736436E+02  0.696293E+02  0.569850E+01
  vertex  0.717255E+02  0.687460E+02  0.853320E+01
  vertex  0.734707E+02  0.687460E+02  0.947000E+01
 endloop
endfacet
facet normal -0.732862E-01  0.967861E+00  0.240570E+00
 outer loop
  vertex  0.754083E+02  0.687460E+02  0.100603E+02
  vertex  0.761032E+02  0.696293E+02  0.671830E+01
  vertex  0.748092E+02  0.696293E+02  0.632410E+01
 endloop
endfacet
facet normal -0.732807E-01  0.967860E+00  0.240577E+00
 outer loop
  vertex  0.748091E+02  0.696293E+02  0.632410E+01
  vertex  0.734707E+02  0.687460E+02  0.947000E+01
  vertex  0.754083E+02  0.687460E+02  0.100602E+02
 endloop
endfacet
facet normal -0.246038E-01  0.967761E+00  0.250667E+00
 outer loop
  vertex  0.775000E+02  0.687460E+02  0.102656E+02
  vertex  0.775000E+02  0.696293E+02  0.685540E+01
  vertex  0.761032E+02  0.696293E+02  0.671830E+01
 endloop
endfacet
facet normal -0.246023E-01  0.967763E+00  0.250660E+00
 outer loop
  vertex  0.761032E+02  0.696293E+02  0.671820E+01
  vertex  0.754083E+02  0.687460E+02  0.100603E+02
  vertex  0.775000E+02  0.687460E+02  0.102656E+02
 endloop
endfacet
facet normal -0.176507E+00  0.984147E+00  0.173249E-01
 outer loop
  vertex  0.634775E+02  0.680209E+02  0.291530E+01
  vertex  0.674396E+02  0.687460E+02  0.209160E+01
  vertex  0.672343E+02  0.687460E+02  0.000000E+00
 endloop
endfacet
facet normal -0.176513E+00  0.984145E+00  0.173568E-01
 outer loop
  vertex  0.672342E+02  0.687460E+02  0.000000E+00
  vertex  0.631914E+02  0.680209E+02  0.000000E+00
  vertex  0.634775E+02  0.680208E+02  0.291520E+01
 endloop
endfacet
facet normal -0.169389E+00  0.984197E+00  0.516055E-01
 outer loop
  vertex  0.643003E+02  0.680209E+02  0.561610E+01
  vertex  0.680299E+02  0.687460E+02  0.402920E+01
  vertex  0.674396E+02  0.687460E+02  0.209160E+01
 endloop
endfacet
facet normal -0.169385E+00  0.984196E+00  0.516413E-01
 outer loop
  vertex  0.674395E+02  0.687460E+02  0.209150E+01
  vertex  0.634775E+02  0.680209E+02  0.291530E+01
  vertex  0.643003E+02  0.680208E+02  0.561600E+01
 endloop
endfacet
facet normal -0.155775E+00  0.984247E+00  0.836177E-01
 outer loop
  vertex  0.656059E+02  0.680209E+02  0.804850E+01
  vertex  0.689667E+02  0.687460E+02  0.577440E+01
  vertex  0.680299E+02  0.687460E+02  0.402920E+01
 endloop
endfacet
facet normal -0.155768E+00  0.984245E+00  0.836496E-01
 outer loop
  vertex  0.680298E+02  0.687460E+02  0.402920E+01
  vertex  0.643003E+02  0.680209E+02  0.561610E+01
  vertex  0.656059E+02  0.680208E+02  0.804850E+01
 endloop
endfacet
facet normal -0.136453E+00  0.984275E+00  0.112175E+00
 outer loop
  vertex  0.673408E+02  0.680209E+02  0.101590E+02
  vertex  0.702114E+02  0.687460E+02  0.728850E+01
  vertex  0.689667E+02  0.687460E+02  0.577440E+01
 endloop
endfacet
facet normal -0.136444E+00  0.984273E+00  0.112201E+00
 outer loop
  vertex  0.689666E+02  0.687460E+02  0.577440E+01
  vertex  0.656059E+02  0.680209E+02  0.804850E+01
  vertex  0.673407E+02  0.680208E+02  0.101590E+02
 endloop
endfacet
facet normal -0.112177E+00  0.984274E+00  0.136456E+00
 outer loop
  vertex  0.694514E+02  0.680209E+02  0.118940E+02
  vertex  0.717255E+02  0.687460E+02  0.853320E+01
  vertex  0.702114E+02  0.687460E+02  0.728850E+01
 endloop
endfacet
facet normal -0.112145E+00  0.984275E+00  0.136479E+00
 outer loop
  vertex  0.702114E+02  0.687460E+02  0.728840E+01
  vertex  0.673408E+02  0.680209E+02  0.101590E+02
  vertex  0.694514E+02  0.680208E+02  0.118940E+02
 endloop
endfacet
facet normal -0.836191E-01  0.984247E+00  0.155777E+00
 outer loop
  vertex  0.718838E+02  0.680209E+02  0.131996E+02
  vertex  0.734707E+02  0.687460E+02  0.947000E+01
  vertex  0.717255E+02  0.687460E+02  0.853320E+01
 endloop
endfacet
facet normal -0.835871E-01  0.984246E+00  0.155795E+00
 outer loop
  vertex  0.717255E+02  0.687460E+02  0.853320E+01
  vertex  0.694514E+02  0.680209E+02  0.118940E+02
  vertex  0.718837E+02  0.680208E+02  0.131996E+02
 endloop
endfacet
facet normal -0.516055E-01  0.984197E+00  0.169390E+00
 outer loop
  vertex  0.745846E+02  0.680209E+02  0.140224E+02
  vertex  0.754083E+02  0.687460E+02  0.100603E+02
  vertex  0.734707E+02  0.687460E+02  0.947000E+01
 endloop
endfacet
facet normal -0.515669E-01  0.984196E+00  0.169405E+00
 outer loop
  vertex  0.734707E+02  0.687460E+02  0.947000E+01
  vertex  0.718838E+02  0.680209E+02  0.131996E+02
  vertex  0.745846E+02  0.680208E+02  0.140223E+02
 endloop
endfacet
facet normal -0.173244E-01  0.984146E+00  0.176509E+00
 outer loop
  vertex  0.775000E+02  0.680209E+02  0.143085E+02
  vertex  0.775000E+02  0.687460E+02  0.102656E+02
  vertex  0.754083E+02  0.687460E+02  0.100603E+02
 endloop
endfacet
facet normal -0.172882E-01  0.984147E+00  0.176510E+00
 outer loop
  vertex  0.754083E+02  0.687460E+02  0.100602E+02
  vertex  0.745846E+02  0.680209E+02  0.140224E+02
  vertex  0.775000E+02  0.680208E+02  0.143085E+02
 endloop
endfacet
facet normal -0.150101E+00  0.988561E+00  0.147306E-01
 outer loop
  vertex  0.593087E+02  0.673750E+02  0.378210E+01
  vertex  0.634775E+02  0.680209E+02  0.291530E+01
  vertex  0.631914E+02  0.680209E+02  0.000000E+00
 endloop
endfacet
facet normal -0.150081E+00  0.988564E+00  0.147303E-01
 outer loop
  vertex  0.631913E+02  0.680208E+02  0.000000E+00
  vertex  0.589375E+02  0.673750E+02  0.000000E+00
  vertex  0.593087E+02  0.673750E+02  0.378200E+01
 endloop
endfacet
facet normal -0.144042E+00  0.988598E+00  0.438826E-01
 outer loop
  vertex  0.603760E+02  0.673750E+02  0.728570E+01
  vertex  0.643003E+02  0.680209E+02  0.561610E+01
  vertex  0.634775E+02  0.680209E+02  0.291530E+01
 endloop
endfacet
facet normal -0.144023E+00  0.988601E+00  0.438709E-01
 outer loop
  vertex  0.634775E+02  0.680208E+02  0.291520E+01
  vertex  0.593087E+02  0.673750E+02  0.378210E+01
  vertex  0.603759E+02  0.673750E+02  0.728560E+01
 endloop
endfacet
facet normal -0.132469E+00  0.988633E+00  0.711035E-01
 outer loop
  vertex  0.620699E+02  0.673750E+02  0.104414E+02
  vertex  0.656059E+02  0.680209E+02  0.804850E+01
  vertex  0.643003E+02  0.680209E+02  0.561610E+01
 endloop
endfacet
facet normal -0.132445E+00  0.988637E+00  0.710952E-01
 outer loop
  vertex  0.643003E+02  0.680208E+02  0.561600E+01
  vertex  0.603760E+02  0.673750E+02  0.728570E+01
  vertex  0.620699E+02  0.673750E+02  0.104413E+02
 endloop
endfacet
facet normal -0.116041E+00  0.988653E+00  0.953888E-01
 outer loop
  vertex  0.643206E+02  0.673750E+02  0.131793E+02
  vertex  0.673408E+02  0.680209E+02  0.101590E+02
  vertex  0.656059E+02  0.680209E+02  0.804850E+01
 endloop
endfacet
facet normal -0.116021E+00  0.988657E+00  0.953752E-01
 outer loop
  vertex  0.656059E+02  0.680208E+02  0.804850E+01
  vertex  0.620699E+02  0.673750E+02  0.104414E+02
  vertex  0.643206E+02  0.673750E+02  0.131793E+02
 endloop
endfacet
facet normal -0.953885E-01  0.988654E+00  0.116039E+00
 outer loop
  vertex  0.670585E+02  0.673750E+02  0.154300E+02
  vertex  0.694514E+02  0.680209E+02  0.118940E+02
  vertex  0.673408E+02  0.680209E+02  0.101590E+02
 endloop
endfacet
facet normal -0.953771E-01  0.988657E+00  0.116023E+00
 outer loop
  vertex  0.673407E+02  0.680208E+02  0.101590E+02
  vertex  0.643206E+02  0.673750E+02  0.131793E+02
  vertex  0.670585E+02  0.673750E+02  0.154300E+02
 endloop
endfacet
facet normal -0.711027E-01  0.988634E+00  0.132468E+00
 outer loop
  vertex  0.702142E+02  0.673750E+02  0.171239E+02
  vertex  0.718838E+02  0.680209E+02  0.131996E+02
  vertex  0.694514E+02  0.680209E+02  0.118940E+02
 endloop
endfacet
facet normal -0.710917E-01  0.988637E+00  0.132450E+00
 outer loop
  vertex  0.694514E+02  0.680208E+02  0.118940E+02
  vertex  0.670585E+02  0.673750E+02  0.154300E+02
  vertex  0.702142E+02  0.673750E+02  0.171238E+02
 endloop
endfacet
facet normal -0.438832E-01  0.988598E+00  0.144045E+00
 outer loop
  vertex  0.737178E+02  0.673750E+02  0.181912E+02
  vertex  0.745846E+02  0.680209E+02  0.140224E+02
  vertex  0.718838E+02  0.680209E+02  0.131996E+02
 endloop
endfacet
facet normal -0.438749E-01  0.988601E+00  0.144023E+00
 outer loop
  vertex  0.718837E+02  0.680208E+02  0.131996E+02
  vertex  0.702142E+02  0.673750E+02  0.171239E+02
  vertex  0.737177E+02  0.673750E+02  0.181912E+02
 endloop
endfacet
facet normal -0.147299E-01  0.988561E+00  0.150100E+00
 outer loop
  vertex  0.775000E+02  0.673750E+02  0.185624E+02
  vertex  0.775000E+02  0.680209E+02  0.143085E+02
  vertex  0.745846E+02  0.680209E+02  0.140224E+02
 endloop
endfacet
facet normal -0.147289E-01  0.988565E+00  0.150075E+00
 outer loop
  vertex  0.745846E+02  0.680208E+02  0.140223E+02
  vertex  0.737178E+02  0.673750E+02  0.181912E+02
  vertex  0.775000E+02  0.673750E+02  0.185624E+02
 endloop
endfacet
facet normal -0.157765E+00  0.987355E+00  0.154841E-01
 outer loop
  vertex  0.553466E+02  0.667290E+02  0.460580E+01
  vertex  0.593087E+02  0.673750E+02  0.378210E+01
  vertex  0.589375E+02  0.673750E+02  0.000000E+00
 endloop
endfacet
facet normal -0.157763E+00  0.987355E+00  0.155036E-01
 outer loop
  vertex  0.589375E+02  0.673750E+02  0.000000E+00
  vertex  0.548945E+02  0.667290E+02  0.000000E+00
  vertex  0.553465E+02  0.667289E+02  0.460580E+01
 endloop
endfacet
facet normal -0.151403E+00  0.987396E+00  0.461216E-01
 outer loop
  vertex  0.566464E+02  0.667290E+02  0.887260E+01
  vertex  0.603760E+02  0.673750E+02  0.728570E+01
  vertex  0.593087E+02  0.673750E+02  0.378210E+01
 endloop
endfacet
facet normal -0.151396E+00  0.987396E+00  0.461441E-01
 outer loop
  vertex  0.593087E+02  0.673750E+02  0.378200E+01
  vertex  0.553466E+02  0.667290E+02  0.460580E+01
  vertex  0.566464E+02  0.667289E+02  0.887250E+01
 endloop
endfacet
facet normal -0.139235E+00  0.987435E+00  0.747377E-01
 outer loop
  vertex  0.587092E+02  0.667290E+02  0.127155E+02
  vertex  0.620699E+02  0.673750E+02  0.104414E+02
  vertex  0.603760E+02  0.673750E+02  0.728570E+01
 endloop
endfacet
facet normal -0.139225E+00  0.987435E+00  0.747611E-01
 outer loop
  vertex  0.603759E+02  0.673750E+02  0.728560E+01
  vertex  0.566464E+02  0.667290E+02  0.887260E+01
  vertex  0.587092E+02  0.667289E+02  0.127154E+02
 endloop
endfacet
facet normal -0.121965E+00  0.987457E+00  0.100262E+00
 outer loop
  vertex  0.614501E+02  0.667290E+02  0.160498E+02
  vertex  0.643206E+02  0.673750E+02  0.131793E+02
  vertex  0.620699E+02  0.673750E+02  0.104414E+02
 endloop
endfacet
facet normal -0.121955E+00  0.987457E+00  0.100276E+00
 outer loop
  vertex  0.620699E+02  0.673750E+02  0.104413E+02
  vertex  0.587092E+02  0.667290E+02  0.127155E+02
  vertex  0.614500E+02  0.667289E+02  0.160498E+02
 endloop
endfacet
facet normal -0.100263E+00  0.987457E+00  0.121966E+00
 outer loop
  vertex  0.647844E+02  0.667290E+02  0.187907E+02
  vertex  0.670585E+02  0.673750E+02  0.154300E+02
  vertex  0.643206E+02  0.673750E+02  0.131793E+02
 endloop
endfacet
facet normal -0.100244E+00  0.987457E+00  0.121982E+00
 outer loop
  vertex  0.643206E+02  0.673750E+02  0.131793E+02
  vertex  0.614501E+02  0.667290E+02  0.160498E+02
  vertex  0.647844E+02  0.667289E+02  0.187907E+02
 endloop
endfacet
facet normal -0.747371E-01  0.987435E+00  0.139234E+00
 outer loop
  vertex  0.686273E+02  0.667290E+02  0.208535E+02
  vertex  0.702142E+02  0.673750E+02  0.171239E+02
  vertex  0.670585E+02  0.673750E+02  0.154300E+02
 endloop
endfacet
facet normal -0.747211E-01  0.987435E+00  0.139246E+00
 outer loop
  vertex  0.670585E+02  0.673750E+02  0.154300E+02
  vertex  0.647844E+02  0.667290E+02  0.187907E+02
  vertex  0.686272E+02  0.667289E+02  0.208535E+02
 endloop
endfacet
facet normal -0.461217E-01  0.987396E+00  0.151402E+00
 outer loop
  vertex  0.728941E+02  0.667290E+02  0.221533E+02
  vertex  0.737178E+02  0.673750E+02  0.181912E+02
  vertex  0.702142E+02  0.673750E+02  0.171239E+02
 endloop
endfacet
facet normal -0.460983E-01  0.987396E+00  0.151408E+00
 outer loop
  vertex  0.702142E+02  0.673750E+02  0.171238E+02
  vertex  0.686273E+02  0.667290E+02  0.208535E+02
  vertex  0.728940E+02  0.667289E+02  0.221532E+02
 endloop
endfacet
facet normal -0.154835E-01  0.987356E+00  0.157763E+00
 outer loop
  vertex  0.775000E+02  0.667290E+02  0.226054E+02
  vertex  0.775000E+02  0.673750E+02  0.185624E+02
  vertex  0.737178E+02  0.673750E+02  0.181912E+02
 endloop
endfacet
facet normal -0.154649E-01  0.987355E+00  0.157769E+00
 outer loop
  vertex  0.737177E+02  0.673750E+02  0.181912E+02
  vertex  0.728941E+02  0.667290E+02  0.221533E+02
  vertex  0.775000E+02  0.667289E+02  0.226054E+02
 endloop
endfacet
facet normal -0.207934E+00  0.977930E+00  0.204105E-01
 outer loop
  vertex  0.520046E+02  0.660039E+02  0.530060E+01
  vertex  0.553466E+02  0.667290E+02  0.460580E+01
  vertex  0.548945E+02  0.667290E+02  0.000000E+00
 endloop
endfacet
facet normal -0.207906E+00  0.977935E+00  0.204262E-01
 outer loop
  vertex  0.548945E+02  0.667289E+02  0.000000E+00
  vertex  0.514843E+02  0.660039E+02  0.000000E+00
  vertex  0.520046E+02  0.660038E+02  0.530060E+01
 endloop
endfacet
facet normal -0.199554E+00  0.977999E+00  0.607904E-01
 outer loop
  vertex  0.535005E+02  0.660039E+02  0.102111E+02
  vertex  0.566464E+02  0.667290E+02  0.887260E+01
  vertex  0.553466E+02  0.667290E+02  0.460580E+01
 endloop
endfacet
facet normal -0.199529E+00  0.978004E+00  0.608002E-01
 outer loop
  vertex  0.553465E+02  0.667289E+02  0.460580E+01
  vertex  0.520046E+02  0.660039E+02  0.530060E+01
  vertex  0.535004E+02  0.660038E+02  0.102110E+02
 endloop
endfacet
facet normal -0.183522E+00  0.978067E+00  0.985113E-01
 outer loop
  vertex  0.558745E+02  0.660039E+02  0.146337E+02
  vertex  0.587092E+02  0.667290E+02  0.127155E+02
  vertex  0.566464E+02  0.667290E+02  0.887260E+01
 endloop
endfacet
facet normal -0.183486E+00  0.978073E+00  0.985152E-01
 outer loop
  vertex  0.566464E+02  0.667289E+02  0.887250E+01
  vertex  0.535005E+02  0.660039E+02  0.102111E+02
  vertex  0.558745E+02  0.660038E+02  0.146337E+02
 endloop
endfacet
facet normal -0.160767E+00  0.978105E+00  0.132155E+00
 outer loop
  vertex  0.590289E+02  0.660039E+02  0.184710E+02
  vertex  0.614501E+02  0.667290E+02  0.160498E+02
  vertex  0.587092E+02  0.667290E+02  0.127155E+02
 endloop
endfacet
facet normal -0.160730E+00  0.978111E+00  0.132152E+00
 outer loop
  vertex  0.587092E+02  0.667289E+02  0.127154E+02
  vertex  0.558745E+02  0.660039E+02  0.146337E+02
  vertex  0.590289E+02  0.660038E+02  0.184710E+02
 endloop
endfacet
facet normal -0.132155E+00  0.978105E+00  0.160766E+00
 outer loop
  vertex  0.628662E+02  0.660039E+02  0.216254E+02
  vertex  0.647844E+02  0.667290E+02  0.187907E+02
  vertex  0.614501E+02  0.667290E+02  0.160498E+02
 endloop
endfacet
facet normal -0.132129E+00  0.978110E+00  0.160760E+00
 outer loop
  vertex  0.614500E+02  0.667289E+02  0.160498E+02
  vertex  0.590289E+02  0.660039E+02  0.184710E+02
  vertex  0.628661E+02  0.660038E+02  0.216254E+02
 endloop
endfacet
facet normal -0.985108E-01  0.978067E+00  0.183521E+00
 outer loop
  vertex  0.672888E+02  0.660039E+02  0.239994E+02
  vertex  0.686273E+02  0.667290E+02  0.208535E+02
  vertex  0.647844E+02  0.667290E+02  0.187907E+02
 endloop
endfacet
facet normal -0.984800E-01  0.978072E+00  0.183510E+00
 outer loop
  vertex  0.647844E+02  0.667289E+02  0.187907E+02
  vertex  0.628662E+02  0.660039E+02  0.216254E+02
  vertex  0.672888E+02  0.660038E+02  0.239993E+02
 endloop
endfacet
facet normal -0.607902E-01  0.977999E+00  0.199554E+00
 outer loop
  vertex  0.721993E+02  0.660039E+02  0.254953E+02
  vertex  0.728941E+02  0.667290E+02  0.221533E+02
  vertex  0.686273E+02  0.667290E+02  0.208535E+02
 endloop
endfacet
facet normal -0.607658E-01  0.978004E+00  0.199537E+00
 outer loop
  vertex  0.686272E+02  0.667289E+02  0.208535E+02
  vertex  0.672888E+02  0.660039E+02  0.239994E+02
  vertex  0.721993E+02  0.660038E+02  0.254953E+02
 endloop
endfacet
facet normal -0.204101E-01  0.977930E+00  0.207933E+00
 outer loop
  vertex  0.775000E+02  0.660039E+02  0.260156E+02
  vertex  0.775000E+02  0.667290E+02  0.226054E+02
  vertex  0.728941E+02  0.667290E+02  0.221533E+02
 endloop
endfacet
facet normal -0.203890E-01  0.977937E+00  0.207905E+00
 outer loop
  vertex  0.728940E+02  0.667289E+02  0.221532E+02
  vertex  0.721993E+02  0.660039E+02  0.254953E+02
  vertex  0.775000E+02  0.660038E+02  0.260156E+02
 endloop
endfacet
facet normal -0.350922E+00  0.935771E+00  0.344462E-01
 outer loop
  vertex  0.496963E+02  0.651206E+02  0.578060E+01
  vertex  0.520046E+02  0.660039E+02  0.530060E+01
  vertex  0.514843E+02  0.660039E+02  0.000000E+00
 endloop
endfacet
facet normal -0.350902E+00  0.935778E+00  0.344593E-01
 outer loop
  vertex  0.514842E+02  0.660038E+02  0.000000E+00
  vertex  0.491289E+02  0.651206E+02  0.000000E+00
  vertex  0.496963E+02  0.651205E+02  0.578060E+01
 endloop
endfacet
facet normal -0.336820E+00  0.935962E+00  0.102606E+00
 outer loop
  vertex  0.513276E+02  0.651206E+02  0.111356E+02
  vertex  0.535005E+02  0.660039E+02  0.102111E+02
  vertex  0.520046E+02  0.660039E+02  0.530060E+01
 endloop
endfacet
facet normal -0.336786E+00  0.935974E+00  0.102606E+00
 outer loop
  vertex  0.520046E+02  0.660038E+02  0.530060E+01
  vertex  0.496963E+02  0.651206E+02  0.578060E+01
  vertex  0.513275E+02  0.651205E+02  0.111356E+02
 endloop
endfacet
facet normal -0.309789E+00  0.936151E+00  0.166291E+00
 outer loop
  vertex  0.539165E+02  0.651206E+02  0.159587E+02
  vertex  0.558745E+02  0.660039E+02  0.146337E+02
  vertex  0.535005E+02  0.660039E+02  0.102111E+02
 endloop
endfacet
facet normal -0.309767E+00  0.936158E+00  0.166293E+00
 outer loop
  vertex  0.535004E+02  0.660038E+02  0.102110E+02
  vertex  0.513276E+02  0.651206E+02  0.111356E+02
  vertex  0.539165E+02  0.651205E+02  0.159587E+02
 endloop
endfacet
facet normal -0.271397E+00  0.936254E+00  0.223098E+00
 outer loop
  vertex  0.573565E+02  0.651206E+02  0.201434E+02
  vertex  0.590289E+02  0.660039E+02  0.184710E+02
  vertex  0.558745E+02  0.660039E+02  0.146337E+02
 endloop
endfacet
facet normal -0.271361E+00  0.936267E+00  0.223086E+00
 outer loop
  vertex  0.558745E+02  0.660038E+02  0.146337E+02
  vertex  0.539165E+02  0.651206E+02  0.159587E+02
  vertex  0.573564E+02  0.651205E+02  0.201434E+02
 endloop
endfacet
facet normal -0.223097E+00  0.936255E+00  0.271395E+00
 outer loop
  vertex  0.615412E+02  0.651206E+02  0.235834E+02
  vertex  0.628662E+02  0.660039E+02  0.216254E+02
  vertex  0.590289E+02  0.660039E+02  0.184710E+02
 endloop
endfacet
facet normal -0.223068E+00  0.936266E+00  0.271378E+00
 outer loop
  vertex  0.590289E+02  0.660038E+02  0.184710E+02
  vertex  0.573565E+02  0.651206E+02  0.201434E+02
  vertex  0.615411E+02  0.651205E+02  0.235834E+02
 endloop
endfacet
facet normal -0.166295E+00  0.936147E+00  0.309797E+00
 outer loop
  vertex  0.663643E+02  0.651206E+02  0.261723E+02
  vertex  0.672888E+02  0.660039E+02  0.239994E+02
  vertex  0.628662E+02  0.660039E+02  0.216254E+02
 endloop
endfacet
facet normal -0.166259E+00  0.936161E+00  0.309776E+00
 outer loop
  vertex  0.628661E+02  0.660038E+02  0.216254E+02
  vertex  0.615412E+02  0.651206E+02  0.235834E+02
  vertex  0.663643E+02  0.651205E+02  0.261723E+02
 endloop
endfacet
facet normal -0.102607E+00  0.935961E+00  0.336821E+00
 outer loop
  vertex  0.717193E+02  0.651206E+02  0.278036E+02
  vertex  0.721993E+02  0.660039E+02  0.254953E+02
  vertex  0.672888E+02  0.660039E+02  0.239994E+02
 endloop
endfacet
facet normal -0.102579E+00  0.935979E+00  0.336781E+00
 outer loop
  vertex  0.672888E+02  0.660038E+02  0.239993E+02
  vertex  0.663643E+02  0.651206E+02  0.261723E+02
  vertex  0.717192E+02  0.651205E+02  0.278036E+02
 endloop
endfacet
facet normal -0.344456E-01  0.935770E+00  0.350924E+00
 outer loop
  vertex  0.775000E+02  0.651206E+02  0.283710E+02
  vertex  0.775000E+02  0.660039E+02  0.260156E+02
  vertex  0.721993E+02  0.660039E+02  0.254953E+02
 endloop
endfacet
facet normal -0.344253E-01  0.935783E+00  0.350891E+00
 outer loop
  vertex  0.721993E+02  0.660038E+02  0.254953E+02
  vertex  0.717193E+02  0.651206E+02  0.278036E+02
  vertex  0.775000E+02  0.651205E+02  0.283710E+02
 endloop
endfacet
facet normal -0.784493E+00  0.615338E+00  0.770029E-01
 outer loop
  vertex  0.488349E+02  0.640000E+02  0.595960E+01
  vertex  0.496963E+02  0.651206E+02  0.578060E+01
  vertex  0.491289E+02  0.651206E+02  0.000000E+00
 endloop
endfacet
facet normal -0.784526E+00  0.615298E+00  0.769849E-01
 outer loop
  vertex  0.491288E+02  0.651205E+02  0.000000E+00
  vertex  0.482500E+02  0.640000E+02  0.000000E+00
  vertex  0.488348E+02  0.640000E+02  0.595950E+01
 endloop
endfacet
facet normal -0.753602E+00  0.615940E+00  0.229570E+00
 outer loop
  vertex  0.505168E+02  0.640000E+02  0.114806E+02
  vertex  0.513276E+02  0.651206E+02  0.111356E+02
  vertex  0.496963E+02  0.651206E+02  0.578060E+01
 endloop
endfacet
facet normal -0.753568E+00  0.615988E+00  0.229551E+00
 outer loop
  vertex  0.496963E+02  0.651205E+02  0.578060E+01
  vertex  0.488349E+02  0.640000E+02  0.595960E+01
  vertex  0.505167E+02  0.640000E+02  0.114806E+02
 endloop
endfacet
facet normal -0.693696E+00  0.616552E+00  0.372356E+00
 outer loop
  vertex  0.531859E+02  0.640000E+02  0.164531E+02
  vertex  0.539165E+02  0.651206E+02  0.159587E+02
  vertex  0.513276E+02  0.651206E+02  0.111356E+02
 endloop
endfacet
facet normal -0.693697E+00  0.616550E+00  0.372358E+00
 outer loop
  vertex  0.513275E+02  0.651205E+02  0.111356E+02
  vertex  0.505168E+02  0.640000E+02  0.114806E+02
  vertex  0.531859E+02  0.640000E+02  0.164531E+02
 endloop
endfacet
facet normal -0.607980E+00  0.616908E+00  0.499785E+00
 outer loop
  vertex  0.567324E+02  0.640000E+02  0.207674E+02
  vertex  0.573565E+02  0.651206E+02  0.201434E+02
  vertex  0.539165E+02  0.651206E+02  0.159587E+02
 endloop
endfacet
facet normal -0.607976E+00  0.616930E+00  0.499762E+00
 outer loop
  vertex  0.539165E+02  0.651205E+02  0.159587E+02
  vertex  0.531859E+02  0.640000E+02  0.164531E+02
  vertex  0.567323E+02  0.640000E+02  0.207674E+02
 endloop
endfacet
facet normal -0.499791E+00  0.616895E+00  0.607987E+00
 outer loop
  vertex  0.610468E+02  0.640000E+02  0.243140E+02
  vertex  0.615412E+02  0.651206E+02  0.235834E+02
  vertex  0.573565E+02  0.651206E+02  0.201434E+02
 endloop
endfacet
facet normal -0.499782E+00  0.616908E+00  0.607982E+00
 outer loop
  vertex  0.573564E+02  0.651205E+02  0.201434E+02
  vertex  0.567324E+02  0.640000E+02  0.207674E+02
  vertex  0.610467E+02  0.640000E+02  0.243139E+02
 endloop
endfacet
facet normal -0.372355E+00  0.616555E+00  0.693694E+00
 outer loop
  vertex  0.660193E+02  0.640000E+02  0.269831E+02
  vertex  0.663643E+02  0.651206E+02  0.261723E+02
  vertex  0.615412E+02  0.651206E+02  0.235834E+02
 endloop
endfacet
facet normal -0.372352E+00  0.616565E+00  0.693687E+00
 outer loop
  vertex  0.615411E+02  0.651205E+02  0.235834E+02
  vertex  0.610468E+02  0.640000E+02  0.243140E+02
  vertex  0.660193E+02  0.640000E+02  0.269831E+02
 endloop
endfacet
facet normal -0.229577E+00  0.615912E+00  0.753623E+00
 outer loop
  vertex  0.715403E+02  0.640000E+02  0.286649E+02
  vertex  0.717193E+02  0.651206E+02  0.278036E+02
  vertex  0.663643E+02  0.651206E+02  0.261723E+02
 endloop
endfacet
facet normal -0.229546E+00  0.615974E+00  0.753582E+00
 outer loop
  vertex  0.663643E+02  0.651205E+02  0.261723E+02
  vertex  0.660193E+02  0.640000E+02  0.269831E+02
  vertex  0.715402E+02  0.640000E+02  0.286648E+02
 endloop
endfacet
facet normal -0.770036E-01  0.615308E+00  0.784517E+00
 outer loop
  vertex  0.775000E+02  0.640000E+02  0.292499E+02
  vertex  0.775000E+02  0.651206E+02  0.283710E+02
  vertex  0.717193E+02  0.651206E+02  0.278036E+02
 endloop
endfacet
facet normal -0.770065E-01  0.615324E+00  0.784504E+00
 outer loop
  vertex  0.717192E+02  0.651205E+02  0.278036E+02
  vertex  0.715403E+02  0.640000E+02  0.286649E+02
  vertex  0.775000E+02  0.640000E+02  0.292499E+02
 endloop
endfacet
facet normal -0.986268E+00 -0.133804E+00  0.968122E-01
 outer loop
  vertex  0.338737E+02  0.266871E+02  0.907020E+01
  vertex  0.334000E+02  0.302500E+02  0.916870E+01
  vertex  0.325000E+02  0.302500E+02  0.000000E+00
 endloop
endfacet
facet normal -0.986271E+00 -0.133785E+00  0.968086E-01
 outer loop
  vertex  0.325000E+02  0.302500E+02  0.000000E+00
  vertex  0.329833E+02  0.266871E+02  0.000000E+00
  vertex  0.338736E+02  0.266870E+02  0.907010E+01
 endloop
endfacet
facet normal -0.947967E+00 -0.134041E+00  0.288775E+00
 outer loop
  vertex  0.364334E+02  0.266871E+02  0.174727E+02
  vertex  0.359874E+02  0.302500E+02  0.176624E+02
  vertex  0.334000E+02  0.302500E+02  0.916870E+01
 endloop
endfacet
facet normal -0.947971E+00 -0.134019E+00  0.288773E+00
 outer loop
  vertex  0.334000E+02  0.302500E+02  0.916870E+01
  vertex  0.338737E+02  0.266871E+02  0.907020E+01
  vertex  0.364333E+02  0.266870E+02  0.174727E+02
 endloop
endfacet
facet normal -0.873119E+00 -0.134243E+00  0.468659E+00
 outer loop
  vertex  0.404955E+02  0.266871E+02  0.250405E+02
  vertex  0.400937E+02  0.302500E+02  0.253125E+02
  vertex  0.359874E+02  0.302500E+02  0.176624E+02
 endloop
endfacet
facet normal -0.873127E+00 -0.134236E+00  0.468647E+00
 outer loop
  vertex  0.359874E+02  0.302500E+02  0.176623E+02
  vertex  0.364334E+02  0.266871E+02  0.174727E+02
  vertex  0.404954E+02  0.266870E+02  0.250405E+02
 endloop
endfacet
facet normal -0.765489E+00 -0.134369E+00  0.629263E+00
 outer loop
  vertex  0.458932E+02  0.266871E+02  0.316067E+02
  vertex  0.455500E+02  0.302500E+02  0.319500E+02
  vertex  0.400937E+02  0.302500E+02  0.253125E+02
 endloop
endfacet
facet normal -0.765495E+00 -0.134366E+00  0.629256E+00
 outer loop
  vertex  0.400937E+02  0.302500E+02  0.253125E+02
  vertex  0.404955E+02  0.266871E+02  0.250405E+02
  vertex  0.458931E+02  0.266870E+02  0.316067E+02
 endloop
endfacet
facet normal -0.629258E+00 -0.134349E+00  0.765496E+00
 outer loop
  vertex  0.524594E+02  0.266871E+02  0.370044E+02
  vertex  0.521875E+02  0.302500E+02  0.374062E+02
  vertex  0.455500E+02  0.302500E+02  0.319500E+02
 endloop
endfacet
facet normal -0.629256E+00 -0.134390E+00  0.765491E+00
 outer loop
  vertex  0.455499E+02  0.302500E+02  0.319500E+02
  vertex  0.458932E+02  0.266871E+02  0.316067E+02
  vertex  0.524594E+02  0.266870E+02  0.370043E+02
 endloop
endfacet
facet normal -0.468664E+00 -0.134248E+00  0.873116E+00
 outer loop
  vertex  0.600272E+02  0.266871E+02  0.410665E+02
  vertex  0.598375E+02  0.302500E+02  0.415125E+02
  vertex  0.521875E+02  0.302500E+02  0.374062E+02
 endloop
endfacet
facet normal -0.468664E+00 -0.134231E+00  0.873118E+00
 outer loop
  vertex  0.521875E+02  0.302500E+02  0.374062E+02
  vertex  0.524594E+02  0.266871E+02  0.370044E+02
  vertex  0.600271E+02  0.266870E+02  0.410665E+02
 endloop
endfacet
facet normal -0.288776E+00 -0.134019E+00  0.947970E+00
 outer loop
  vertex  0.684297E+02  0.266871E+02  0.436262E+02
  vertex  0.683312E+02  0.302500E+02  0.440999E+02
  vertex  0.598375E+02  0.302500E+02  0.415125E+02
 endloop
endfacet
facet normal -0.288785E+00 -0.134041E+00  0.947964E+00
 outer loop
  vertex  0.598375E+02  0.302500E+02  0.415125E+02
  vertex  0.600272E+02  0.266871E+02  0.410665E+02
  vertex  0.684297E+02  0.266870E+02  0.436262E+02
 endloop
endfacet
facet normal -0.968217E-01 -0.133812E+00  0.986266E+00
 outer loop
  vertex  0.775000E+02  0.266871E+02  0.445166E+02
  vertex  0.775000E+02  0.302500E+02  0.450000E+02
  vertex  0.683312E+02  0.302500E+02  0.440999E+02
 endloop
endfacet
facet normal -0.968202E-01 -0.133779E+00  0.986270E+00
 outer loop
  vertex  0.683311E+02  0.302500E+02  0.440998E+02
  vertex  0.684297E+02  0.266871E+02  0.436262E+02
  vertex  0.775000E+02  0.266870E+02  0.445166E+02
 endloop
endfacet
facet normal -0.921447E+00 -0.377827E+00  0.904562E-01
 outer loop
  vertex  0.351226E+02  0.235791E+02  0.881050E+01
  vertex  0.338737E+02  0.266871E+02  0.907020E+01
  vertex  0.329833E+02  0.266871E+02  0.000000E+00
 endloop
endfacet
facet normal -0.921423E+00 -0.377891E+00  0.904385E-01
 outer loop
  vertex  0.329832E+02  0.266870E+02  0.000000E+00
  vertex  0.342578E+02  0.235791E+02  0.000000E+00
  vertex  0.351226E+02  0.235790E+02  0.881050E+01
 endloop
endfacet
facet normal -0.885487E+00 -0.378349E+00  0.269751E+00
 outer loop
  vertex  0.376090E+02  0.235791E+02  0.169725E+02
  vertex  0.364334E+02  0.266871E+02  0.174727E+02
  vertex  0.338737E+02  0.266871E+02  0.907020E+01
 endloop
endfacet
facet normal -0.885474E+00 -0.378385E+00  0.269742E+00
 outer loop
  vertex  0.338736E+02  0.266870E+02  0.907010E+01
  vertex  0.351226E+02  0.235791E+02  0.881050E+01
  vertex  0.376090E+02  0.235790E+02  0.169724E+02
 endloop
endfacet
facet normal -0.815405E+00 -0.378884E+00  0.437678E+00
 outer loop
  vertex  0.415549E+02  0.235791E+02  0.243237E+02
  vertex  0.404955E+02  0.266871E+02  0.250405E+02
  vertex  0.364334E+02  0.266871E+02  0.174727E+02
 endloop
endfacet
facet normal -0.815395E+00 -0.378902E+00  0.437680E+00
 outer loop
  vertex  0.364333E+02  0.266870E+02  0.174727E+02
  vertex  0.376090E+02  0.235791E+02  0.169725E+02
  vertex  0.415549E+02  0.235790E+02  0.243236E+02
 endloop
endfacet
facet normal -0.714812E+00 -0.379160E+00  0.587607E+00
 outer loop
  vertex  0.467980E+02  0.235791E+02  0.307019E+02
  vertex  0.458932E+02  0.266871E+02  0.316067E+02
  vertex  0.404955E+02  0.266871E+02  0.250405E+02
 endloop
endfacet
facet normal -0.714805E+00 -0.379202E+00  0.587588E+00
 outer loop
  vertex  0.404954E+02  0.266870E+02  0.250405E+02
  vertex  0.415549E+02  0.235791E+02  0.243237E+02
  vertex  0.467980E+02  0.235790E+02  0.307019E+02
 endloop
endfacet
facet normal -0.587604E+00 -0.379171E+00  0.714809E+00
 outer loop
  vertex  0.531762E+02  0.235791E+02  0.359450E+02
  vertex  0.524594E+02  0.266871E+02  0.370044E+02
  vertex  0.458932E+02  0.266871E+02  0.316067E+02
 endloop
endfacet
facet normal -0.587593E+00 -0.379186E+00  0.714810E+00
 outer loop
  vertex  0.458931E+02  0.266870E+02  0.316067E+02
  vertex  0.467980E+02  0.235791E+02  0.307019E+02
  vertex  0.531762E+02  0.235790E+02  0.359449E+02
 endloop
endfacet
facet normal -0.437681E+00 -0.378870E+00  0.815410E+00
 outer loop
  vertex  0.605274E+02  0.235791E+02  0.398909E+02
  vertex  0.600272E+02  0.266871E+02  0.410665E+02
  vertex  0.524594E+02  0.266871E+02  0.370044E+02
 endloop
endfacet
facet normal -0.437681E+00 -0.378871E+00  0.815409E+00
 outer loop
  vertex  0.524594E+02  0.266870E+02  0.370043E+02
  vertex  0.531762E+02  0.235791E+02  0.359450E+02
  vertex  0.605274E+02  0.235790E+02  0.398908E+02
 endloop
endfacet
facet normal -0.269750E+00 -0.378357E+00  0.885483E+00
 outer loop
  vertex  0.686894E+02  0.235791E+02  0.423773E+02
  vertex  0.684297E+02  0.266871E+02  0.436262E+02
  vertex  0.600272E+02  0.266871E+02  0.410665E+02
 endloop
endfacet
facet normal -0.269752E+00 -0.378367E+00  0.885478E+00
 outer loop
  vertex  0.600271E+02  0.266870E+02  0.410665E+02
  vertex  0.605274E+02  0.235791E+02  0.398909E+02
  vertex  0.686893E+02  0.235790E+02  0.423773E+02
 endloop
endfacet
facet normal -0.904542E-01 -0.377854E+00  0.921436E+00
 outer loop
  vertex  0.775000E+02  0.235791E+02  0.432421E+02
  vertex  0.775000E+02  0.266871E+02  0.445166E+02
  vertex  0.684297E+02  0.266871E+02  0.436262E+02
 endloop
endfacet
facet normal -0.904378E-01 -0.377837E+00  0.921445E+00
 outer loop
  vertex  0.684297E+02  0.266870E+02  0.436262E+02
  vertex  0.686894E+02  0.235791E+02  0.423773E+02
  vertex  0.775000E+02  0.235790E+02  0.432420E+02
 endloop
endfacet
facet normal -0.826481E+00 -0.557089E+00  0.811237E-01
 outer loop
  vertex  0.368883E+02  0.209061E+02  0.844340E+01
  vertex  0.351226E+02  0.235791E+02  0.881050E+01
  vertex  0.342578E+02  0.235791E+02  0.000000E+00
 endloop
endfacet
facet normal -0.826476E+00 -0.557096E+00  0.811200E-01
 outer loop
  vertex  0.342578E+02  0.235790E+02  0.000000E+00
  vertex  0.360595E+02  0.209061E+02  0.000000E+00
  vertex  0.368883E+02  0.209060E+02  0.844340E+01
 endloop
endfacet
facet normal -0.793994E+00 -0.557736E+00  0.241875E+00
 outer loop
  vertex  0.392712E+02  0.209061E+02  0.162653E+02
  vertex  0.376090E+02  0.235791E+02  0.169725E+02
  vertex  0.351226E+02  0.235791E+02  0.881050E+01
 endloop
endfacet
facet normal -0.794000E+00 -0.557730E+00  0.241870E+00
 outer loop
  vertex  0.351226E+02  0.235790E+02  0.881050E+01
  vertex  0.368883E+02  0.209061E+02  0.844340E+01
  vertex  0.392711E+02  0.209060E+02  0.162653E+02
 endloop
endfacet
facet normal -0.730968E+00 -0.558335E+00  0.392361E+00
 outer loop
  vertex  0.430526E+02  0.209061E+02  0.233102E+02
  vertex  0.415549E+02  0.235791E+02  0.243237E+02
  vertex  0.376090E+02  0.235791E+02  0.169725E+02
 endloop
endfacet
facet normal -0.730961E+00 -0.558355E+00  0.392346E+00
 outer loop
  vertex  0.376090E+02  0.235790E+02  0.169724E+02
  vertex  0.392712E+02  0.209061E+02  0.162653E+02
  vertex  0.430526E+02  0.209060E+02  0.233101E+02
 endloop
endfacet
facet normal -0.640703E+00 -0.558667E+00  0.526680E+00
 outer loop
  vertex  0.480772E+02  0.209061E+02  0.294227E+02
  vertex  0.467980E+02  0.235791E+02  0.307019E+02
  vertex  0.415549E+02  0.235791E+02  0.243237E+02
 endloop
endfacet
facet normal -0.640704E+00 -0.558682E+00  0.526662E+00
 outer loop
  vertex  0.415549E+02  0.235790E+02  0.243236E+02
  vertex  0.430526E+02  0.209061E+02  0.233102E+02
  vertex  0.480772E+02  0.209060E+02  0.294227E+02
 endloop
endfacet
facet normal -0.526674E+00 -0.558681E+00  0.640696E+00
 outer loop
  vertex  0.541897E+02  0.209061E+02  0.344473E+02
  vertex  0.531762E+02  0.235791E+02  0.359450E+02
  vertex  0.467980E+02  0.235791E+02  0.307019E+02
 endloop
endfacet
facet normal -0.526668E+00 -0.558681E+00  0.640701E+00
 outer loop
  vertex  0.467980E+02  0.235790E+02  0.307019E+02
  vertex  0.480772E+02  0.209061E+02  0.294227E+02
  vertex  0.541897E+02  0.209060E+02  0.344472E+02
 endloop
endfacet
facet normal -0.392356E+00 -0.558351E+00  0.730958E+00
 outer loop
  vertex  0.612346E+02  0.209061E+02  0.382287E+02
  vertex  0.605274E+02  0.235791E+02  0.398909E+02
  vertex  0.531762E+02  0.235791E+02  0.359450E+02
 endloop
endfacet
facet normal -0.392354E+00 -0.558330E+00  0.730976E+00
 outer loop
  vertex  0.531762E+02  0.235790E+02  0.359449E+02
  vertex  0.541897E+02  0.209061E+02  0.344473E+02
  vertex  0.612346E+02  0.209060E+02  0.382286E+02
 endloop
endfacet
facet normal -0.241879E+00 -0.557716E+00  0.794007E+00
 outer loop
  vertex  0.690565E+02  0.209061E+02  0.406116E+02
  vertex  0.686894E+02  0.235791E+02  0.423773E+02
  vertex  0.605274E+02  0.235791E+02  0.398909E+02
 endloop
endfacet
facet normal -0.241883E+00 -0.557731E+00  0.793995E+00
 outer loop
  vertex  0.605274E+02  0.235790E+02  0.398908E+02
  vertex  0.612346E+02  0.209061E+02  0.382287E+02
  vertex  0.690565E+02  0.209060E+02  0.406115E+02
 endloop
endfacet
facet normal -0.811232E-01 -0.557082E+00  0.826486E+00
 outer loop
  vertex  0.775000E+02  0.209061E+02  0.414404E+02
  vertex  0.775000E+02  0.235791E+02  0.432421E+02
  vertex  0.686894E+02  0.235791E+02  0.423773E+02
 endloop
endfacet
facet normal -0.811218E-01 -0.557105E+00  0.826470E+00
 outer loop
  vertex  0.686893E+02  0.235790E+02  0.423773E+02
  vertex  0.690565E+02  0.209061E+02  0.406116E+02
  vertex  0.775000E+02  0.209060E+02  0.414403E+02
 endloop
endfacet
facet normal -0.735903E+00 -0.673223E+00  0.722359E-01
 outer loop
  vertex  0.389124E+02  0.186484E+02  0.802260E+01
  vertex  0.368883E+02  0.209061E+02  0.844340E+01
  vertex  0.360595E+02  0.209061E+02  0.000000E+00
 endloop
endfacet
facet normal -0.735874E+00 -0.673257E+00  0.722069E-01
 outer loop
  vertex  0.360595E+02  0.209060E+02  0.000000E+00
  vertex  0.381250E+02  0.186484E+02  0.000000E+00
  vertex  0.389123E+02  0.186483E+02  0.802260E+01
 endloop
endfacet
facet normal -0.706825E+00 -0.673819E+00  0.215330E+00
 outer loop
  vertex  0.411765E+02  0.186484E+02  0.154546E+02
  vertex  0.392712E+02  0.209061E+02  0.162653E+02
  vertex  0.368883E+02  0.209061E+02  0.844340E+01
 endloop
endfacet
facet normal -0.706813E+00 -0.673839E+00  0.215306E+00
 outer loop
  vertex  0.368883E+02  0.209060E+02  0.844340E+01
  vertex  0.389124E+02  0.186484E+02  0.802260E+01
  vertex  0.411764E+02  0.186483E+02  0.154546E+02
 endloop
endfacet
facet normal -0.650558E+00 -0.674418E+00  0.349192E+00
 outer loop
  vertex  0.447695E+02  0.186484E+02  0.221484E+02
  vertex  0.430526E+02  0.209061E+02  0.233102E+02
  vertex  0.392712E+02  0.209061E+02  0.162653E+02
 endloop
endfacet
facet normal -0.650539E+00 -0.674441E+00  0.349182E+00
 outer loop
  vertex  0.392711E+02  0.209060E+02  0.162653E+02
  vertex  0.411765E+02  0.186484E+02  0.154546E+02
  vertex  0.447695E+02  0.186483E+02  0.221483E+02
 endloop
endfacet
facet normal -0.570137E+00 -0.674758E+00  0.468664E+00
 outer loop
  vertex  0.495437E+02  0.186484E+02  0.279562E+02
  vertex  0.480772E+02  0.209061E+02  0.294227E+02
  vertex  0.430526E+02  0.209061E+02  0.233102E+02
 endloop
endfacet
facet normal -0.570138E+00 -0.674753E+00  0.468669E+00
 outer loop
  vertex  0.430526E+02  0.209060E+02  0.233101E+02
  vertex  0.447695E+02  0.186484E+02  0.221484E+02
  vertex  0.495437E+02  0.186483E+02  0.279561E+02
 endloop
endfacet
facet normal -0.468670E+00 -0.674748E+00  0.570143E+00
 outer loop
  vertex  0.553515E+02  0.186484E+02  0.327304E+02
  vertex  0.541897E+02  0.209061E+02  0.344473E+02
  vertex  0.480772E+02  0.209061E+02  0.294227E+02
 endloop
endfacet
facet normal -0.468665E+00 -0.674775E+00  0.570116E+00
 outer loop
  vertex  0.480772E+02  0.209060E+02  0.294227E+02
  vertex  0.495437E+02  0.186484E+02  0.279562E+02
  vertex  0.553515E+02  0.186483E+02  0.327304E+02
 endloop
endfacet
facet normal -0.349195E+00 -0.674409E+00  0.650565E+00
 outer loop
  vertex  0.620453E+02  0.186484E+02  0.363234E+02
  vertex  0.612346E+02  0.209061E+02  0.382287E+02
  vertex  0.541897E+02  0.209061E+02  0.344473E+02
 endloop
endfacet
facet normal -0.349200E+00 -0.674419E+00  0.650553E+00
 outer loop
  vertex  0.541897E+02  0.209060E+02  0.344472E+02
  vertex  0.553515E+02  0.186484E+02  0.327304E+02
  vertex  0.620452E+02  0.186483E+02  0.363233E+02
 endloop
endfacet
facet normal -0.215329E+00 -0.673822E+00  0.706822E+00
 outer loop
  vertex  0.694773E+02  0.186484E+02  0.385875E+02
  vertex  0.690565E+02  0.209061E+02  0.406116E+02
  vertex  0.612346E+02  0.209061E+02  0.382287E+02
 endloop
endfacet
facet normal -0.215337E+00 -0.673819E+00  0.706823E+00
 outer loop
  vertex  0.612346E+02  0.209060E+02  0.382286E+02
  vertex  0.620453E+02  0.186484E+02  0.363234E+02
  vertex  0.694773E+02  0.186483E+02  0.385875E+02
 endloop
endfacet
facet normal -0.722351E-01 -0.673222E+00  0.735903E+00
 outer loop
  vertex  0.775000E+02  0.186484E+02  0.393750E+02
  vertex  0.775000E+02  0.209061E+02  0.414404E+02
  vertex  0.690565E+02  0.209061E+02  0.406116E+02
 endloop
endfacet
facet normal -0.722437E-01 -0.673222E+00  0.735903E+00
 outer loop
  vertex  0.690565E+02  0.209060E+02  0.406115E+02
  vertex  0.694773E+02  0.186484E+02  0.385875E+02
  vertex  0.775000E+02  0.186483E+02  0.393750E+02
 endloop
endfacet
facet normal -0.668168E+00 -0.741114E+00  0.655792E-01
 outer loop
  vertex  0.409366E+02  0.167862E+02  0.760180E+01
  vertex  0.389124E+02  0.186484E+02  0.802260E+01
  vertex  0.381250E+02  0.186484E+02  0.000000E+00
 endloop
endfacet
facet normal -0.668167E+00 -0.741116E+00  0.655705E-01
 outer loop
  vertex  0.381250E+02  0.186483E+02  0.000000E+00
  vertex  0.401904E+02  0.167862E+02  0.000000E+00
  vertex  0.409365E+02  0.167861E+02  0.760170E+01
 endloop
endfacet
facet normal -0.641672E+00 -0.741650E+00  0.195480E+00
 outer loop
  vertex  0.430819E+02  0.167862E+02  0.146440E+02
  vertex  0.411765E+02  0.186484E+02  0.154546E+02
  vertex  0.389124E+02  0.186484E+02  0.802260E+01
 endloop
endfacet
facet normal -0.641633E+00 -0.741691E+00  0.195453E+00
 outer loop
  vertex  0.389123E+02  0.186483E+02  0.802260E+01
  vertex  0.409366E+02  0.167862E+02  0.760180E+01
  vertex  0.430819E+02  0.167861E+02  0.146440E+02
 endloop
endfacet
facet normal -0.590508E+00 -0.742182E+00  0.316964E+00
 outer loop
  vertex  0.464864E+02  0.167862E+02  0.209866E+02
  vertex  0.447695E+02  0.186484E+02  0.221484E+02
  vertex  0.411765E+02  0.186484E+02  0.154546E+02
 endloop
endfacet
facet normal -0.590482E+00 -0.742213E+00  0.316940E+00
 outer loop
  vertex  0.411764E+02  0.186483E+02  0.154546E+02
  vertex  0.430819E+02  0.167862E+02  0.146440E+02
  vertex  0.464864E+02  0.167861E+02  0.209866E+02
 endloop
endfacet
facet normal -0.517463E+00 -0.742490E+00  0.425371E+00
 outer loop
  vertex  0.510102E+02  0.167862E+02  0.264897E+02
  vertex  0.495437E+02  0.186484E+02  0.279562E+02
  vertex  0.447695E+02  0.186484E+02  0.221484E+02
 endloop
endfacet
facet normal -0.517467E+00 -0.742489E+00  0.425368E+00
 outer loop
  vertex  0.447695E+02  0.186483E+02  0.221483E+02
  vertex  0.464864E+02  0.167862E+02  0.209866E+02
  vertex  0.510102E+02  0.167861E+02  0.264897E+02
 endloop
endfacet
facet normal -0.425377E+00 -0.742481E+00  0.517470E+00
 outer loop
  vertex  0.565133E+02  0.167862E+02  0.310135E+02
  vertex  0.553515E+02  0.186484E+02  0.327304E+02
  vertex  0.495437E+02  0.186484E+02  0.279562E+02
 endloop
endfacet
facet normal -0.425379E+00 -0.742496E+00  0.517448E+00
 outer loop
  vertex  0.495437E+02  0.186483E+02  0.279561E+02
  vertex  0.510102E+02  0.167862E+02  0.264897E+02
  vertex  0.565133E+02  0.167861E+02  0.310135E+02
 endloop
endfacet
facet normal -0.316965E+00 -0.742180E+00  0.590509E+00
 outer loop
  vertex  0.628559E+02  0.167862E+02  0.344180E+02
  vertex  0.620453E+02  0.186484E+02  0.363234E+02
  vertex  0.553515E+02  0.186484E+02  0.327304E+02
 endloop
endfacet
facet normal -0.316961E+00 -0.742200E+00  0.590487E+00
 outer loop
  vertex  0.553515E+02  0.186483E+02  0.327304E+02
  vertex  0.565133E+02  0.167862E+02  0.310135E+02
  vertex  0.628558E+02  0.167861E+02  0.344179E+02
 endloop
endfacet
facet normal -0.195478E+00 -0.741657E+00  0.641664E+00
 outer loop
  vertex  0.698981E+02  0.167862E+02  0.365633E+02
  vertex  0.694773E+02  0.186484E+02  0.385875E+02
  vertex  0.620453E+02  0.186484E+02  0.363234E+02
 endloop
endfacet
facet normal -0.195484E+00 -0.741657E+00  0.641663E+00
 outer loop
  vertex  0.620452E+02  0.186483E+02  0.363233E+02
  vertex  0.628559E+02  0.167862E+02  0.344180E+02
  vertex  0.698981E+02  0.167861E+02  0.365633E+02
 endloop
endfacet
facet normal -0.655866E-01 -0.741113E+00  0.668169E+00
 outer loop
  vertex  0.775000E+02  0.167862E+02  0.373095E+02
  vertex  0.775000E+02  0.186484E+02  0.393750E+02
  vertex  0.694773E+02  0.186484E+02  0.385875E+02
 endloop
endfacet
facet normal -0.655947E-01 -0.741133E+00  0.668146E+00
 outer loop
  vertex  0.694773E+02  0.186483E+02  0.385875E+02
  vertex  0.698981E+02  0.167862E+02  0.365633E+02
  vertex  0.775000E+02  0.167861E+02  0.373095E+02
 endloop
endfacet
facet normal -0.635137E+00 -0.769880E+00  0.623457E-01
 outer loop
  vertex  0.427023E+02  0.152998E+02  0.723470E+01
  vertex  0.409366E+02  0.167862E+02  0.760180E+01
  vertex  0.401904E+02  0.167862E+02  0.000000E+00
 endloop
endfacet
facet normal -0.635098E+00 -0.769912E+00  0.623344E-01
 outer loop
  vertex  0.401903E+02  0.167861E+02  0.000000E+00
  vertex  0.419921E+02  0.152998E+02  0.000000E+00
  vertex  0.427023E+02  0.152997E+02  0.723470E+01
 endloop
endfacet
facet normal -0.609900E+00 -0.770391E+00  0.185797E+00
 outer loop
  vertex  0.447440E+02  0.152998E+02  0.139368E+02
  vertex  0.430819E+02  0.167862E+02  0.146440E+02
  vertex  0.409366E+02  0.167862E+02  0.760180E+01
 endloop
endfacet
facet normal -0.609867E+00 -0.770423E+00  0.185767E+00
 outer loop
  vertex  0.409365E+02  0.167861E+02  0.760170E+01
  vertex  0.427023E+02  0.152998E+02  0.723470E+01
  vertex  0.447439E+02  0.152997E+02  0.139368E+02
 endloop
endfacet
facet normal -0.561224E+00 -0.770895E+00  0.301246E+00
 outer loop
  vertex  0.479841E+02  0.152998E+02  0.199731E+02
  vertex  0.464864E+02  0.167862E+02  0.209866E+02
  vertex  0.430819E+02  0.167862E+02  0.146440E+02
 endloop
endfacet
facet normal -0.561208E+00 -0.770914E+00  0.301226E+00
 outer loop
  vertex  0.430819E+02  0.167861E+02  0.146440E+02
  vertex  0.447440E+02  0.152998E+02  0.139368E+02
  vertex  0.479841E+02  0.152997E+02  0.199731E+02
 endloop
endfacet
facet normal -0.491796E+00 -0.771165E+00  0.404279E+00
 outer loop
  vertex  0.522894E+02  0.152998E+02  0.252105E+02
  vertex  0.510102E+02  0.167862E+02  0.264897E+02
  vertex  0.464864E+02  0.167862E+02  0.209866E+02
 endloop
endfacet
facet normal -0.491781E+00 -0.771198E+00  0.404234E+00
 outer loop
  vertex  0.464864E+02  0.167861E+02  0.209866E+02
  vertex  0.479841E+02  0.152998E+02  0.199731E+02
  vertex  0.522893E+02  0.152997E+02  0.252105E+02
 endloop
endfacet
facet normal -0.404271E+00 -0.771176E+00  0.491786E+00
 outer loop
  vertex  0.575268E+02  0.152998E+02  0.295158E+02
  vertex  0.565133E+02  0.167862E+02  0.310135E+02
  vertex  0.510102E+02  0.167862E+02  0.264897E+02
 endloop
endfacet
facet normal -0.404271E+00 -0.771186E+00  0.491769E+00
 outer loop
  vertex  0.510102E+02  0.167861E+02  0.264897E+02
  vertex  0.522894E+02  0.152998E+02  0.252105E+02
  vertex  0.575267E+02  0.152997E+02  0.295158E+02
 endloop
endfacet
facet normal -0.301248E+00 -0.770893E+00  0.561226E+00
 outer loop
  vertex  0.635631E+02  0.152998E+02  0.327559E+02
  vertex  0.628559E+02  0.167862E+02  0.344180E+02
  vertex  0.565133E+02  0.167862E+02  0.310135E+02
 endloop
endfacet
facet normal -0.301249E+00 -0.770916E+00  0.561193E+00
 outer loop
  vertex  0.565133E+02  0.167861E+02  0.310135E+02
  vertex  0.575268E+02  0.152998E+02  0.295158E+02
  vertex  0.635630E+02  0.152997E+02  0.327559E+02
 endloop
endfacet
facet normal -0.185797E+00 -0.770390E+00  0.609900E+00
 outer loop
  vertex  0.702652E+02  0.152998E+02  0.347976E+02
  vertex  0.698981E+02  0.167862E+02  0.365633E+02
  vertex  0.628559E+02  0.167862E+02  0.344180E+02
 endloop
endfacet
facet normal -0.185799E+00 -0.770400E+00  0.609887E+00
 outer loop
  vertex  0.628558E+02  0.167861E+02  0.344179E+02
  vertex  0.635631E+02  0.152998E+02  0.327559E+02
  vertex  0.702651E+02  0.152997E+02  0.347975E+02
 endloop
endfacet
facet normal -0.623456E-01 -0.769873E+00  0.635144E+00
 outer loop
  vertex  0.775000E+02  0.152998E+02  0.355078E+02
  vertex  0.775000E+02  0.167862E+02  0.373095E+02
  vertex  0.698981E+02  0.167862E+02  0.365633E+02
 endloop
endfacet
facet normal -0.623559E-01 -0.769901E+00  0.635110E+00
 outer loop
  vertex  0.698981E+02  0.167861E+02  0.365633E+02
  vertex  0.702652E+02  0.152998E+02  0.347976E+02
  vertex  0.775000E+02  0.152997E+02  0.355078E+02
 endloop
endfacet
facet normal -0.662208E+00 -0.746495E+00  0.650063E-01
 outer loop
  vertex  0.439512E+02  0.141693E+02  0.697500E+01
  vertex  0.427023E+02  0.152998E+02  0.723470E+01
  vertex  0.419921E+02  0.152998E+02  0.000000E+00
 endloop
endfacet
facet normal -0.662116E+00 -0.746579E+00  0.649782E-01
 outer loop
  vertex  0.419920E+02  0.152997E+02  0.000000E+00
  vertex  0.432666E+02  0.141693E+02  0.000000E+00
  vertex  0.439511E+02  0.141693E+02  0.697490E+01
 endloop
endfacet
facet normal -0.635939E+00 -0.747028E+00  0.193730E+00
 outer loop
  vertex  0.459196E+02  0.141693E+02  0.134366E+02
  vertex  0.447440E+02  0.152998E+02  0.139368E+02
  vertex  0.427023E+02  0.152998E+02  0.723470E+01
 endloop
endfacet
facet normal -0.635899E+00 -0.747065E+00  0.193718E+00
 outer loop
  vertex  0.427023E+02  0.152997E+02  0.723470E+01
  vertex  0.439512E+02  0.141693E+02  0.697500E+01
  vertex  0.459196E+02  0.141693E+02  0.134365E+02
 endloop
endfacet
facet normal -0.585217E+00 -0.747560E+00  0.314126E+00
 outer loop
  vertex  0.490434E+02  0.141693E+02  0.192562E+02
  vertex  0.479841E+02  0.152998E+02  0.199731E+02
  vertex  0.447440E+02  0.152998E+02  0.139368E+02
 endloop
endfacet
facet normal -0.585172E+00 -0.747609E+00  0.314094E+00
 outer loop
  vertex  0.447439E+02  0.152997E+02  0.139368E+02
  vertex  0.459196E+02  0.141693E+02  0.134366E+02
  vertex  0.490433E+02  0.141693E+02  0.192562E+02
 endloop
endfacet
facet normal -0.512835E+00 -0.747852E+00  0.421566E+00
 outer loop
  vertex  0.531942E+02  0.141693E+02  0.243057E+02
  vertex  0.522894E+02  0.152998E+02  0.252105E+02
  vertex  0.479841E+02  0.152998E+02  0.199731E+02
 endloop
endfacet
facet normal -0.512809E+00 -0.747889E+00  0.421531E+00
 outer loop
  vertex  0.479841E+02  0.152997E+02  0.199731E+02
  vertex  0.490434E+02  0.141693E+02  0.192562E+02
  vertex  0.531941E+02  0.141693E+02  0.243057E+02
 endloop
endfacet
facet normal -0.421560E+00 -0.747860E+00  0.512828E+00
 outer loop
  vertex  0.582437E+02  0.141693E+02  0.284565E+02
  vertex  0.575268E+02  0.152998E+02  0.295158E+02
  vertex  0.522894E+02  0.152998E+02  0.252105E+02
 endloop
endfacet
facet normal -0.421530E+00 -0.747897E+00  0.512799E+00
 outer loop
  vertex  0.522893E+02  0.152997E+02  0.252105E+02
  vertex  0.531942E+02  0.141693E+02  0.243057E+02
  vertex  0.582436E+02  0.141693E+02  0.284564E+02
 endloop
endfacet
facet normal -0.314128E+00 -0.747557E+00  0.585220E+00
 outer loop
  vertex  0.640633E+02  0.141693E+02  0.315803E+02
  vertex  0.635631E+02  0.152998E+02  0.327559E+02
  vertex  0.575268E+02  0.152998E+02  0.295158E+02
 endloop
endfacet
facet normal -0.314098E+00 -0.747602E+00  0.585179E+00
 outer loop
  vertex  0.575267E+02  0.152997E+02  0.295158E+02
  vertex  0.582437E+02  0.141693E+02  0.284565E+02
  vertex  0.640633E+02  0.141693E+02  0.315802E+02
 endloop
endfacet
facet normal -0.193727E+00 -0.747037E+00  0.635929E+00
 outer loop
  vertex  0.705249E+02  0.141693E+02  0.335487E+02
  vertex  0.702652E+02  0.152998E+02  0.347976E+02
  vertex  0.635631E+02  0.152998E+02  0.327559E+02
 endloop
endfacet
facet normal -0.193706E+00 -0.747064E+00  0.635904E+00
 outer loop
  vertex  0.635630E+02  0.152997E+02  0.327559E+02
  vertex  0.640633E+02  0.141693E+02  0.315803E+02
  vertex  0.705249E+02  0.141693E+02  0.335486E+02
 endloop
endfacet
facet normal -0.650022E-01 -0.746524E+00  0.662176E+00
 outer loop
  vertex  0.775000E+02  0.141693E+02  0.342333E+02
  vertex  0.775000E+02  0.152998E+02  0.355078E+02
  vertex  0.702652E+02  0.152998E+02  0.347976E+02
 endloop
endfacet
facet normal -0.649854E-01 -0.746501E+00  0.662203E+00
 outer loop
  vertex  0.702651E+02  0.152997E+02  0.347975E+02
  vertex  0.705249E+02  0.141693E+02  0.335487E+02
  vertex  0.775000E+02  0.141693E+02  0.342332E+02
 endloop
endfacet
facet normal -0.851268E+00 -0.518037E+00  0.835520E-01
 outer loop
  vertex  0.444249E+02  0.133750E+02  0.687650E+01
  vertex  0.439512E+02  0.141693E+02  0.697500E+01
  vertex  0.432666E+02  0.141693E+02  0.000000E+00
 endloop
endfacet
facet normal -0.851254E+00 -0.518060E+00  0.835471E-01
 outer loop
  vertex  0.432666E+02  0.141693E+02  0.000000E+00
  vertex  0.437500E+02  0.133750E+02  0.000000E+00
  vertex  0.444249E+02  0.133750E+02  0.687650E+01
 endloop
endfacet
facet normal -0.817826E+00 -0.518740E+00  0.249135E+00
 outer loop
  vertex  0.463656E+02  0.133750E+02  0.132468E+02
  vertex  0.459196E+02  0.141693E+02  0.134366E+02
  vertex  0.439512E+02  0.141693E+02  0.697500E+01
 endloop
endfacet
facet normal -0.817841E+00 -0.518709E+00  0.249154E+00
 outer loop
  vertex  0.439511E+02  0.141693E+02  0.697490E+01
  vertex  0.444249E+02  0.133750E+02  0.687650E+01
  vertex  0.463656E+02  0.133750E+02  0.132468E+02
 endloop
endfacet
facet normal -0.752956E+00 -0.519334E+00  0.404166E+00
 outer loop
  vertex  0.494453E+02  0.133750E+02  0.189843E+02
  vertex  0.490434E+02  0.141693E+02  0.192562E+02
  vertex  0.459196E+02  0.141693E+02  0.134366E+02
 endloop
endfacet
facet normal -0.752967E+00 -0.519316E+00  0.404168E+00
 outer loop
  vertex  0.459196E+02  0.141693E+02  0.134365E+02
  vertex  0.463656E+02  0.133750E+02  0.132468E+02
  vertex  0.494453E+02  0.133750E+02  0.189843E+02
 endloop
endfacet
facet normal -0.660004E+00 -0.519661E+00  0.542538E+00
 outer loop
  vertex  0.535374E+02  0.133750E+02  0.239624E+02
  vertex  0.531942E+02  0.141693E+02  0.243057E+02
  vertex  0.490434E+02  0.141693E+02  0.192562E+02
 endloop
endfacet
facet normal -0.659980E+00 -0.519727E+00  0.542504E+00
 outer loop
  vertex  0.490433E+02  0.141693E+02  0.192562E+02
  vertex  0.494453E+02  0.133750E+02  0.189843E+02
  vertex  0.535373E+02  0.133750E+02  0.239624E+02
 endloop
endfacet
facet normal -0.542536E+00 -0.519665E+00  0.660002E+00
 outer loop
  vertex  0.585156E+02  0.133750E+02  0.280546E+02
  vertex  0.582437E+02  0.141693E+02  0.284565E+02
  vertex  0.531942E+02  0.141693E+02  0.243057E+02
 endloop
endfacet
facet normal -0.542514E+00 -0.519721E+00  0.659976E+00
 outer loop
  vertex  0.531941E+02  0.141693E+02  0.243057E+02
  vertex  0.535374E+02  0.133750E+02  0.239624E+02
  vertex  0.585155E+02  0.133750E+02  0.280545E+02
 endloop
endfacet
facet normal -0.404160E+00 -0.519352E+00  0.752946E+00
 outer loop
  vertex  0.642531E+02  0.133750E+02  0.311343E+02
  vertex  0.640633E+02  0.141693E+02  0.315803E+02
  vertex  0.582437E+02  0.141693E+02  0.284565E+02
 endloop
endfacet
facet normal -0.404178E+00 -0.519301E+00  0.752972E+00
 outer loop
  vertex  0.582436E+02  0.141693E+02  0.284564E+02
  vertex  0.585156E+02  0.133750E+02  0.280546E+02
  vertex  0.642530E+02  0.133750E+02  0.311343E+02
 endloop
endfacet
facet normal -0.249150E+00 -0.518654E+00  0.817877E+00
 outer loop
  vertex  0.706234E+02  0.133750E+02  0.330750E+02
  vertex  0.705249E+02  0.141693E+02  0.335487E+02
  vertex  0.640633E+02  0.141693E+02  0.315803E+02
 endloop
endfacet
facet normal -0.249165E+00 -0.518666E+00  0.817865E+00
 outer loop
  vertex  0.640633E+02  0.141693E+02  0.315802E+02
  vertex  0.642531E+02  0.133750E+02  0.311343E+02
  vertex  0.706233E+02  0.133750E+02  0.330750E+02
 endloop
endfacet
facet normal -0.835546E-01 -0.517982E+00  0.851301E+00
 outer loop
  vertex  0.775000E+02  0.133750E+02  0.337500E+02
  vertex  0.775000E+02  0.141693E+02  0.342333E+02
  vertex  0.705249E+02  0.141693E+02  0.335487E+02
 endloop
endfacet
facet normal -0.835642E-01 -0.517956E+00  0.851316E+00
 outer loop
  vertex  0.705249E+02  0.141693E+02  0.335486E+02
  vertex  0.706234E+02  0.133750E+02  0.330750E+02
  vertex  0.775000E+02  0.133750E+02  0.337500E+02
 endloop
endfacet
facet normal -0.110463E+00  0.980823E+00  0.160572E+00
 outer loop
  vertex  0.115750E+03  0.420625E+02  0.000000E+00
  vertex  0.115750E+03  0.412648E+02  0.487260E+01
  vertex  0.122305E+03  0.420244E+02  0.474250E+01
 endloop
endfacet
facet normal -0.102118E+00  0.983538E+00  0.149080E+00
 outer loop
  vertex  0.122305E+03  0.420243E+02  0.474240E+01
  vertex  0.122162E+03  0.427282E+02  0.000000E+00
  vertex  0.115750E+03  0.420625E+02  0.000000E+00
 endloop
endfacet
facet normal -0.107006E+00  0.851012E+00  0.514128E+00
 outer loop
  vertex  0.115750E+03  0.412648E+02  0.487260E+01
  vertex  0.115750E+03  0.391621E+02  0.835310E+01
  vertex  0.122685E+03  0.401688E+02  0.813010E+01
 endloop
endfacet
facet normal -0.910511E-01  0.869071E+00  0.486236E+00
 outer loop
  vertex  0.122685E+03  0.401688E+02  0.813010E+01
  vertex  0.122305E+03  0.420244E+02  0.474250E+01
  vertex  0.115750E+03  0.412648E+02  0.487260E+01
 endloop
endfacet
facet normal -0.735978E-01  0.573246E+00  0.816072E+00
 outer loop
  vertex  0.115750E+03  0.391621E+02  0.835310E+01
  vertex  0.115750E+03  0.361892E+02  0.104414E+02
  vertex  0.123221E+03  0.375453E+02  0.101626E+02
 endloop
endfacet
facet normal -0.620180E-01  0.603273E+00  0.795120E+00
 outer loop
  vertex  0.123221E+03  0.375452E+02  0.101625E+02
  vertex  0.122685E+03  0.401688E+02  0.813010E+01
  vertex  0.115750E+03  0.391621E+02  0.835300E+01
 endloop
endfacet
facet normal -0.745945E-02  0.200090E+00  0.979749E+00
 outer loop
  vertex  0.115750E+03  0.361892E+02  0.104414E+02
  vertex  0.115750E+03  0.327812E+02  0.111374E+02
  vertex  0.123836E+03  0.345379E+02  0.108402E+02
 endloop
endfacet
facet normal -0.337892E-02  0.219136E+00  0.975689E+00
 outer loop
  vertex  0.123836E+03  0.345378E+02  0.108402E+02
  vertex  0.123221E+03  0.375453E+02  0.101626E+02
  vertex  0.115750E+03  0.361892E+02  0.104413E+02
 endloop
endfacet
facet normal  0.807436E-01 -0.199442E+00  0.976577E+00
 outer loop
  vertex  0.115750E+03  0.327812E+02  0.111374E+02
  vertex  0.115750E+03  0.293732E+02  0.104414E+02
  vertex  0.124451E+03  0.315305E+02  0.101626E+02
 endloop
endfacet
facet normal  0.800696E-01 -0.203523E+00  0.975791E+00
 outer loop
  vertex  0.124451E+03  0.315305E+02  0.101625E+02
  vertex  0.123836E+03  0.345379E+02  0.108402E+02
  vertex  0.115750E+03  0.327812E+02  0.111373E+02
 endloop
endfacet
facet normal  0.173097E+00 -0.566128E+00  0.805939E+00
 outer loop
  vertex  0.115750E+03  0.293732E+02  0.104414E+02
  vertex  0.115750E+03  0.264003E+02  0.835310E+01
  vertex  0.124987E+03  0.289071E+02  0.813010E+01
 endloop
endfacet
facet normal  0.169709E+00 -0.581658E+00  0.795533E+00
 outer loop
  vertex  0.124987E+03  0.289071E+02  0.813010E+01
  vertex  0.124451E+03  0.315305E+02  0.101626E+02
  vertex  0.115750E+03  0.293731E+02  0.104413E+02
 endloop
endfacet
facet normal  0.244465E+00 -0.829956E+00  0.501407E+00
 outer loop
  vertex  0.115750E+03  0.264003E+02  0.835310E+01
  vertex  0.115750E+03  0.242976E+02  0.487260E+01
  vertex  0.125366E+03  0.270515E+02  0.474250E+01
 endloop
endfacet
facet normal  0.239702E+00 -0.839922E+00  0.486902E+00
 outer loop
  vertex  0.125366E+03  0.270515E+02  0.474240E+01
  vertex  0.124987E+03  0.289071E+02  0.813010E+01
  vertex  0.115750E+03  0.264002E+02  0.835300E+01
 endloop
endfacet
facet normal  0.276684E+00 -0.948340E+00  0.155234E+00
 outer loop
  vertex  0.115750E+03  0.242976E+02  0.487260E+01
  vertex  0.115750E+03  0.235000E+02  0.000000E+00
  vertex  0.125510E+03  0.263476E+02  0.000000E+00
 endloop
endfacet
facet normal  0.274100E+00 -0.950037E+00  0.149325E+00
 outer loop
  vertex  0.125510E+03  0.263476E+02  0.000000E+00
  vertex  0.125366E+03  0.270515E+02  0.474250E+01
  vertex  0.115750E+03  0.242975E+02  0.487260E+01
 endloop
endfacet
facet normal -0.382170E+00  0.912327E+00  0.146988E+00
 outer loop
  vertex  0.122162E+03  0.427282E+02  0.000000E+00
  vertex  0.122305E+03  0.420244E+02  0.474250E+01
  vertex  0.126770E+03  0.439496E+02  0.439960E+01
 endloop
endfacet
facet normal -0.378437E+00  0.914603E+00  0.142433E+00
 outer loop
  vertex  0.126770E+03  0.439496E+02  0.439960E+01
  vertex  0.126543E+03  0.445410E+02  0.000000E+00
  vertex  0.122161E+03  0.427281E+02  0.000000E+00
 endloop
endfacet
facet normal -0.325464E+00  0.813464E+00  0.482026E+00
 outer loop
  vertex  0.122305E+03  0.420244E+02  0.474250E+01
  vertex  0.122685E+03  0.401688E+02  0.813010E+01
  vertex  0.127367E+03  0.423904E+02  0.754230E+01
 endloop
endfacet
facet normal -0.319100E+00  0.823423E+00  0.469202E+00
 outer loop
  vertex  0.127367E+03  0.423903E+02  0.754230E+01
  vertex  0.126770E+03  0.439496E+02  0.439960E+01
  vertex  0.122305E+03  0.420243E+02  0.474240E+01
 endloop
endfacet
facet normal -0.188406E+00  0.577112E+00  0.794635E+00
 outer loop
  vertex  0.122685E+03  0.401688E+02  0.813010E+01
  vertex  0.123221E+03  0.375453E+02  0.101626E+02
  vertex  0.128212E+03  0.401861E+02  0.942790E+01
 endloop
endfacet
facet normal -0.185188E+00  0.596856E+00  0.780685E+00
 outer loop
  vertex  0.128212E+03  0.401861E+02  0.942790E+01
  vertex  0.127367E+03  0.423904E+02  0.754230E+01
  vertex  0.122685E+03  0.401688E+02  0.813010E+01
 endloop
endfacet
facet normal  0.131291E-01  0.222336E+00  0.974882E+00
 outer loop
  vertex  0.123221E+03  0.375453E+02  0.101626E+02
  vertex  0.123836E+03  0.345379E+02  0.108402E+02
  vertex  0.129180E+03  0.376591E+02  0.100564E+02
 endloop
endfacet
facet normal  0.125628E-01  0.245862E+00  0.969223E+00
 outer loop
  vertex  0.129180E+03  0.376590E+02  0.100564E+02
  vertex  0.128212E+03  0.401861E+02  0.942790E+01
  vertex  0.123221E+03  0.375452E+02  0.101625E+02
 endloop
endfacet
facet normal  0.230331E+00 -0.168841E+00  0.958353E+00
 outer loop
  vertex  0.123836E+03  0.345379E+02  0.108402E+02
  vertex  0.124451E+03  0.315305E+02  0.101626E+02
  vertex  0.130148E+03  0.351322E+02  0.942790E+01
 endloop
endfacet
facet normal  0.229382E+00 -0.151263E+00  0.961511E+00
 outer loop
  vertex  0.130148E+03  0.351321E+02  0.942790E+01
  vertex  0.129180E+03  0.376591E+02  0.100564E+02
  vertex  0.123836E+03  0.345378E+02  0.108402E+02
 endloop
endfacet
facet normal  0.411771E+00 -0.504026E+00  0.759211E+00
 outer loop
  vertex  0.124451E+03  0.315305E+02  0.101626E+02
  vertex  0.124987E+03  0.289071E+02  0.813010E+01
  vertex  0.130992E+03  0.329279E+02  0.754230E+01
 endloop
endfacet
facet normal  0.412078E+00 -0.495931E+00  0.764358E+00
 outer loop
  vertex  0.130992E+03  0.329278E+02  0.754230E+01
  vertex  0.130148E+03  0.351322E+02  0.942790E+01
  vertex  0.124451E+03  0.315305E+02  0.101625E+02
 endloop
endfacet
facet normal  0.524764E+00 -0.720455E+00  0.453395E+00
 outer loop
  vertex  0.124987E+03  0.289071E+02  0.813010E+01
  vertex  0.125366E+03  0.270515E+02  0.474250E+01
  vertex  0.131590E+03  0.313687E+02  0.439960E+01
 endloop
endfacet
facet normal  0.525479E+00 -0.718171E+00  0.456182E+00
 outer loop
  vertex  0.131590E+03  0.313687E+02  0.439960E+01
  vertex  0.130992E+03  0.329279E+02  0.754230E+01
  vertex  0.124987E+03  0.289071E+02  0.813010E+01
 endloop
endfacet
facet normal  0.569333E+00 -0.810514E+00  0.137574E+00
 outer loop
  vertex  0.125366E+03  0.270515E+02  0.474250E+01
  vertex  0.125510E+03  0.263476E+02  0.000000E+00
  vertex  0.131816E+03  0.307773E+02  0.000000E+00
 endloop
endfacet
facet normal  0.569641E+00 -0.810179E+00  0.138276E+00
 outer loop
  vertex  0.131816E+03  0.307772E+02  0.000000E+00
  vertex  0.131590E+03  0.313687E+02  0.439960E+01
  vertex  0.125366E+03  0.270515E+02  0.474240E+01
 endloop
endfacet
facet normal -0.678452E+00  0.722673E+00  0.132086E+00
 outer loop
  vertex  0.126543E+03  0.445410E+02  0.000000E+00
  vertex  0.126770E+03  0.439496E+02  0.439960E+01
  vertex  0.129663E+03  0.467551E+02  0.391490E+01
 endloop
endfacet
facet normal -0.679071E+00  0.721926E+00  0.132987E+00
 outer loop
  vertex  0.129663E+03  0.467551E+02  0.391490E+01
  vertex  0.129395E+03  0.472238E+02  0.000000E+00
  vertex  0.126543E+03  0.445410E+02  0.000000E+00
 endloop
endfacet
facet normal -0.582748E+00  0.678430E+00  0.447367E+00
 outer loop
  vertex  0.126770E+03  0.439496E+02  0.439960E+01
  vertex  0.127367E+03  0.423904E+02  0.754230E+01
  vertex  0.130371E+03  0.455192E+02  0.671120E+01
 endloop
endfacet
facet normal -0.582748E+00  0.678423E+00  0.447379E+00
 outer loop
  vertex  0.130371E+03  0.455191E+02  0.671120E+01
  vertex  0.129663E+03  0.467551E+02  0.391490E+01
  vertex  0.126770E+03  0.439496E+02  0.439960E+01
 endloop
endfacet
facet normal -0.346372E+00  0.529625E+00  0.774289E+00
 outer loop
  vertex  0.127367E+03  0.423904E+02  0.754230E+01
  vertex  0.128212E+03  0.401861E+02  0.942790E+01
  vertex  0.131372E+03  0.437720E+02  0.838900E+01
 endloop
endfacet
facet normal -0.347872E+00  0.538000E+00  0.767816E+00
 outer loop
  vertex  0.131372E+03  0.437719E+02  0.838890E+01
  vertex  0.130371E+03  0.455192E+02  0.671120E+01
  vertex  0.127367E+03  0.423903E+02  0.754230E+01
 endloop
endfacet
facet normal  0.169302E-01  0.247429E+00  0.968758E+00
 outer loop
  vertex  0.128212E+03  0.401861E+02  0.942790E+01
  vertex  0.129180E+03  0.376591E+02  0.100564E+02
  vertex  0.132520E+03  0.417691E+02  0.894830E+01
 endloop
endfacet
facet normal  0.692855E-02  0.272629E+00  0.962094E+00
 outer loop
  vertex  0.132520E+03  0.417691E+02  0.894830E+01
  vertex  0.131372E+03  0.437720E+02  0.838900E+01
  vertex  0.128212E+03  0.401861E+02  0.942790E+01
 endloop
endfacet
facet normal  0.381128E+00 -0.829904E-01  0.920790E+00
 outer loop
  vertex  0.129180E+03  0.376591E+02  0.100564E+02
  vertex  0.130148E+03  0.351322E+02  0.942790E+01
  vertex  0.133667E+03  0.397662E+02  0.838900E+01
 endloop
endfacet
facet normal  0.367909E+00 -0.486232E-01  0.928590E+00
 outer loop
  vertex  0.133667E+03  0.397662E+02  0.838890E+01
  vertex  0.132520E+03  0.417691E+02  0.894830E+01
  vertex  0.129180E+03  0.376590E+02  0.100564E+02
 endloop
endfacet
facet normal  0.635822E+00 -0.346394E+00  0.689741E+00
 outer loop
  vertex  0.130148E+03  0.351322E+02  0.942790E+01
  vertex  0.130992E+03  0.329279E+02  0.754230E+01
  vertex  0.134668E+03  0.380190E+02  0.671120E+01
 endloop
endfacet
facet normal  0.629654E+00 -0.319387E+00  0.708187E+00
 outer loop
  vertex  0.134668E+03  0.380190E+02  0.671120E+01
  vertex  0.133667E+03  0.397662E+02  0.838900E+01
  vertex  0.130148E+03  0.351321E+02  0.942790E+01
 endloop
endfacet
facet normal  0.769013E+00 -0.502298E+00  0.395367E+00
 outer loop
  vertex  0.130992E+03  0.329279E+02  0.754230E+01
  vertex  0.131590E+03  0.313687E+02  0.439960E+01
  vertex  0.135376E+03  0.367832E+02  0.391490E+01
 endloop
endfacet
facet normal  0.769744E+00 -0.488596E+00  0.410814E+00
 outer loop
  vertex  0.135376E+03  0.367831E+02  0.391490E+01
  vertex  0.134668E+03  0.380190E+02  0.671120E+01
  vertex  0.130992E+03  0.329278E+02  0.754230E+01
 endloop
endfacet
facet normal  0.816848E+00 -0.564657E+00  0.117992E+00
 outer loop
  vertex  0.131590E+03  0.313687E+02  0.439960E+01
  vertex  0.131816E+03  0.307773E+02  0.000000E+00
  vertex  0.135644E+03  0.363144E+02  0.000000E+00
 endloop
endfacet
facet normal  0.818436E+00 -0.561207E+00  0.123329E+00
 outer loop
  vertex  0.135644E+03  0.363143E+02  0.000000E+00
  vertex  0.135376E+03  0.367832E+02  0.391490E+01
  vertex  0.131590E+03  0.313687E+02  0.439960E+01
 endloop
endfacet
facet normal -0.864619E+00  0.488429E+00  0.117774E+00
 outer loop
  vertex  0.129395E+03  0.472238E+02  0.000000E+00
  vertex  0.129663E+03  0.467551E+02  0.391490E+01
  vertex  0.131509E+03  0.501555E+02  0.335910E+01
 endloop
endfacet
facet normal -0.866971E+00  0.482600E+00  0.124331E+00
 outer loop
  vertex  0.131509E+03  0.501554E+02  0.335910E+01
  vertex  0.131219E+03  0.505000E+02  0.000000E+00
  vertex  0.129395E+03  0.472238E+02  0.000000E+00
 endloop
endfacet
facet normal -0.764477E+00  0.495405E+00  0.412490E+00
 outer loop
  vertex  0.129663E+03  0.467551E+02  0.391490E+01
  vertex  0.130371E+03  0.455192E+02  0.671120E+01
  vertex  0.132273E+03  0.492475E+02  0.575850E+01
 endloop
endfacet
facet normal -0.763829E+00  0.484250E+00  0.426692E+00
 outer loop
  vertex  0.132273E+03  0.492475E+02  0.575850E+01
  vertex  0.131509E+03  0.501555E+02  0.335910E+01
  vertex  0.129663E+03  0.467551E+02  0.391490E+01
 endloop
endfacet
facet normal -0.486595E+00  0.443861E+00  0.752471E+00
 outer loop
  vertex  0.130371E+03  0.455192E+02  0.671120E+01
  vertex  0.131372E+03  0.437720E+02  0.838900E+01
  vertex  0.133354E+03  0.479638E+02  0.719820E+01
 endloop
endfacet
facet normal -0.484208E+00  0.440236E+00  0.756131E+00
 outer loop
  vertex  0.133354E+03  0.479637E+02  0.719820E+01
  vertex  0.132273E+03  0.492475E+02  0.575850E+01
  vertex  0.130371E+03  0.455191E+02  0.671120E+01
 endloop
endfacet
facet normal -0.982293E-02  0.263719E+00  0.964549E+00
 outer loop
  vertex  0.131372E+03  0.437720E+02  0.838900E+01
  vertex  0.132520E+03  0.417691E+02  0.894830E+01
  vertex  0.134594E+03  0.464921E+02  0.767810E+01
 endloop
endfacet
facet normal -0.305983E-01  0.286474E+00  0.957599E+00
 outer loop
  vertex  0.134594E+03  0.464920E+02  0.767810E+01
  vertex  0.133354E+03  0.479638E+02  0.719820E+01
  vertex  0.131372E+03  0.437719E+02  0.838890E+01
 endloop
endfacet
facet normal  0.456781E+00  0.132682E-01  0.889480E+00
 outer loop
  vertex  0.132520E+03  0.417691E+02  0.894830E+01
  vertex  0.133667E+03  0.397662E+02  0.838900E+01
  vertex  0.135833E+03  0.450205E+02  0.719820E+01
 endloop
endfacet
facet normal  0.420488E+00  0.588284E-01  0.905389E+00
 outer loop
  vertex  0.135833E+03  0.450205E+02  0.719820E+01
  vertex  0.134594E+03  0.464921E+02  0.767810E+01
  vertex  0.132520E+03  0.417691E+02  0.894830E+01
 endloop
endfacet
facet normal  0.746000E+00 -0.186571E+00  0.639277E+00
 outer loop
  vertex  0.133667E+03  0.397662E+02  0.838900E+01
  vertex  0.134668E+03  0.380190E+02  0.671120E+01
  vertex  0.136914E+03  0.437368E+02  0.575850E+01
 endloop
endfacet
facet normal  0.724269E+00 -0.145892E+00  0.673906E+00
 outer loop
  vertex  0.136914E+03  0.437368E+02  0.575850E+01
  vertex  0.135833E+03  0.450205E+02  0.719820E+01
  vertex  0.133667E+03  0.397662E+02  0.838890E+01
 endloop
endfacet
facet normal  0.883113E+00 -0.303558E+00  0.357720E+00
 outer loop
  vertex  0.134668E+03  0.380190E+02  0.671120E+01
  vertex  0.135376E+03  0.367832E+02  0.391490E+01
  vertex  0.137679E+03  0.428287E+02  0.335910E+01
 endloop
endfacet
facet normal  0.878601E+00 -0.280824E+00  0.386262E+00
 outer loop
  vertex  0.137679E+03  0.428287E+02  0.335910E+01
  vertex  0.136914E+03  0.437368E+02  0.575850E+01
  vertex  0.134668E+03  0.380190E+02  0.671120E+01
 endloop
endfacet
facet normal  0.930527E+00 -0.350606E+00  0.105802E+00
 outer loop
  vertex  0.135376E+03  0.367832E+02  0.391490E+01
  vertex  0.135644E+03  0.363144E+02  0.000000E+00
  vertex  0.137969E+03  0.424843E+02  0.000000E+00
 endloop
endfacet
facet normal  0.931695E+00 -0.344306E+00  0.115749E+00
 outer loop
  vertex  0.137969E+03  0.424842E+02  0.000000E+00
  vertex  0.137679E+03  0.428287E+02  0.335910E+01
  vertex  0.135376E+03  0.367831E+02  0.391490E+01
 endloop
endfacet
facet normal -0.930338E+00  0.347875E+00  0.115994E+00
 outer loop
  vertex  0.131219E+03  0.505000E+02  0.000000E+00
  vertex  0.131509E+03  0.501555E+02  0.335910E+01
  vertex  0.132827E+03  0.538656E+02  0.280340E+01
 endloop
endfacet
facet normal -0.932536E+00  0.336518E+00  0.130889E+00
 outer loop
  vertex  0.132827E+03  0.538656E+02  0.280340E+01
  vertex  0.132515E+03  0.540925E+02  0.000000E+00
  vertex  0.131219E+03  0.505000E+02  0.000000E+00
 endloop
endfacet
facet normal -0.829698E+00  0.380510E+00  0.408427E+00
 outer loop
  vertex  0.131509E+03  0.501555E+02  0.335910E+01
  vertex  0.132273E+03  0.492475E+02  0.575850E+01
  vertex  0.133648E+03  0.532675E+02  0.480590E+01
 endloop
endfacet
facet normal -0.821332E+00  0.358276E+00  0.443906E+00
 outer loop
  vertex  0.133648E+03  0.532675E+02  0.480590E+01
  vertex  0.132827E+03  0.538656E+02  0.280340E+01
  vertex  0.131509E+03  0.501554E+02  0.335910E+01
 endloop
endfacet
facet normal -0.546461E+00  0.377982E+00  0.747335E+00
 outer loop
  vertex  0.132273E+03  0.492475E+02  0.575850E+01
  vertex  0.133354E+03  0.479638E+02  0.719820E+01
  vertex  0.134809E+03  0.524218E+02  0.600730E+01
 endloop
endfacet
facet normal -0.529293E+00  0.362747E+00  0.766983E+00
 outer loop
  vertex  0.134809E+03  0.524217E+02  0.600720E+01
  vertex  0.133648E+03  0.532675E+02  0.480590E+01
  vertex  0.132273E+03  0.492475E+02  0.575850E+01
 endloop
endfacet
facet normal -0.583885E-01  0.264708E+00  0.962559E+00
 outer loop
  vertex  0.133354E+03  0.479638E+02  0.719820E+01
  vertex  0.134594E+03  0.464921E+02  0.767810E+01
  vertex  0.136141E+03  0.514525E+02  0.640780E+01
 endloop
endfacet
facet normal -0.821176E-01  0.282138E+00  0.955853E+00
 outer loop
  vertex  0.136141E+03  0.514524E+02  0.640780E+01
  vertex  0.134809E+03  0.524218E+02  0.600730E+01
  vertex  0.133354E+03  0.479637E+02  0.719820E+01
 endloop
endfacet
facet normal  0.429104E+00  0.676324E-01  0.900720E+00
 outer loop
  vertex  0.134594E+03  0.464921E+02  0.767810E+01
  vertex  0.135833E+03  0.450205E+02  0.719820E+01
  vertex  0.137472E+03  0.504831E+02  0.600730E+01
 endloop
endfacet
facet normal  0.366400E+00  0.121960E+00  0.922430E+00
 outer loop
  vertex  0.137472E+03  0.504831E+02  0.600720E+01
  vertex  0.136141E+03  0.514525E+02  0.640780E+01
  vertex  0.134594E+03  0.464920E+02  0.767810E+01
 endloop
endfacet
facet normal  0.744816E+00 -0.110765E+00  0.658013E+00
 outer loop
  vertex  0.135833E+03  0.450205E+02  0.719820E+01
  vertex  0.136914E+03  0.437368E+02  0.575850E+01
  vertex  0.138633E+03  0.496375E+02  0.480590E+01
 endloop
endfacet
facet normal  0.698660E+00 -0.540836E-01  0.713407E+00
 outer loop
  vertex  0.138633E+03  0.496375E+02  0.480590E+01
  vertex  0.137472E+03  0.504831E+02  0.600730E+01
  vertex  0.135833E+03  0.450205E+02  0.719820E+01
 endloop
endfacet
facet normal  0.900752E+00 -0.224272E+00  0.371952E+00
 outer loop
  vertex  0.136914E+03  0.437368E+02  0.575850E+01
  vertex  0.137679E+03  0.428287E+02  0.335910E+01
  vertex  0.139454E+03  0.490393E+02  0.280340E+01
 endloop
endfacet
facet normal  0.886975E+00 -0.190493E+00  0.420699E+00
 outer loop
  vertex  0.139454E+03  0.490392E+02  0.280340E+01
  vertex  0.138633E+03  0.496375E+02  0.480590E+01
  vertex  0.136914E+03  0.437368E+02  0.575850E+01
 endloop
endfacet
facet normal  0.956072E+00 -0.271552E+00  0.110384E+00
 outer loop
  vertex  0.137679E+03  0.428287E+02  0.335910E+01
  vertex  0.137969E+03  0.424843E+02  0.000000E+00
  vertex  0.139766E+03  0.488125E+02  0.000000E+00
 endloop
endfacet
facet normal  0.956576E+00 -0.262121E+00  0.127499E+00
 outer loop
  vertex  0.139766E+03  0.488125E+02  0.000000E+00
  vertex  0.139454E+03  0.490393E+02  0.280340E+01
  vertex  0.137679E+03  0.428287E+02  0.335910E+01
 endloop
endfacet
facet normal -0.929872E+00  0.343701E+00  0.131174E+00
 outer loop
  vertex  0.132515E+03  0.540925E+02  0.000000E+00
  vertex  0.132827E+03  0.538656E+02  0.280340E+01
  vertex  0.134139E+03  0.575999E+02  0.231860E+01
 endloop
endfacet
facet normal -0.931865E+00  0.325824E+00  0.159583E+00
 outer loop
  vertex  0.134139E+03  0.575998E+02  0.231850E+01
  vertex  0.133785E+03  0.577246E+02  0.000000E+00
  vertex  0.132515E+03  0.540924E+02  0.000000E+00
 endloop
endfacet
facet normal -0.810204E+00  0.380394E+00  0.445948E+00
 outer loop
  vertex  0.132827E+03  0.538656E+02  0.280340E+01
  vertex  0.133648E+03  0.532675E+02  0.480590E+01
  vertex  0.135070E+03  0.572714E+02  0.397480E+01
 endloop
endfacet
facet normal -0.787883E+00  0.343174E+00  0.511344E+00
 outer loop
  vertex  0.135070E+03  0.572714E+02  0.397480E+01
  vertex  0.134139E+03  0.575999E+02  0.231860E+01
  vertex  0.132827E+03  0.538656E+02  0.280340E+01
 endloop
endfacet
facet normal -0.523908E+00  0.370326E+00  0.767059E+00
 outer loop
  vertex  0.133648E+03  0.532675E+02  0.480590E+01
  vertex  0.134809E+03  0.524218E+02  0.600730E+01
  vertex  0.136388E+03  0.568069E+02  0.496850E+01
 endloop
endfacet
facet normal -0.486944E+00  0.339989E+00  0.804545E+00
 outer loop
  vertex  0.136388E+03  0.568069E+02  0.496850E+01
  vertex  0.135070E+03  0.572714E+02  0.397480E+01
  vertex  0.133648E+03  0.532675E+02  0.480590E+01
 endloop
endfacet
facet normal -0.101394E+00  0.257758E+00  0.960875E+00
 outer loop
  vertex  0.134809E+03  0.524218E+02  0.600730E+01
  vertex  0.136141E+03  0.514525E+02  0.640780E+01
  vertex  0.137898E+03  0.562744E+02  0.529980E+01
 endloop
endfacet
facet normal -0.115221E+00  0.268042E+00  0.956492E+00
 outer loop
  vertex  0.137898E+03  0.562743E+02  0.529970E+01
  vertex  0.136388E+03  0.568069E+02  0.496850E+01
  vertex  0.134809E+03  0.524217E+02  0.600720E+01
 endloop
endfacet
facet normal  0.330212E+00  0.643978E-01  0.941707E+00
 outer loop
  vertex  0.136141E+03  0.514525E+02  0.640780E+01
  vertex  0.137472E+03  0.504831E+02  0.600730E+01
  vertex  0.139409E+03  0.557419E+02  0.496850E+01
 endloop
endfacet
facet normal  0.255119E+00  0.127239E+00  0.958501E+00
 outer loop
  vertex  0.139409E+03  0.557419E+02  0.496850E+01
  vertex  0.137898E+03  0.562744E+02  0.529980E+01
  vertex  0.136141E+03  0.514524E+02  0.640780E+01
 endloop
endfacet
facet normal  0.662192E+00 -0.137211E+00  0.736665E+00
 outer loop
  vertex  0.137472E+03  0.504831E+02  0.600730E+01
  vertex  0.138633E+03  0.496375E+02  0.480590E+01
  vertex  0.140726E+03  0.552774E+02  0.397480E+01
 endloop
endfacet
facet normal  0.588187E+00 -0.573040E-01  0.806693E+00
 outer loop
  vertex  0.140726E+03  0.552774E+02  0.397480E+01
  vertex  0.139409E+03  0.557419E+02  0.496850E+01
  vertex  0.137472E+03  0.504831E+02  0.600720E+01
 endloop
endfacet
facet normal  0.854718E+00 -0.283034E+00  0.435143E+00
 outer loop
  vertex  0.138633E+03  0.496375E+02  0.480590E+01
  vertex  0.139454E+03  0.490393E+02  0.280340E+01
  vertex  0.141658E+03  0.549488E+02  0.231860E+01
 endloop
endfacet
facet normal  0.827432E+00 -0.231715E+00  0.511531E+00
 outer loop
  vertex  0.141658E+03  0.549487E+02  0.231850E+01
  vertex  0.140726E+03  0.552774E+02  0.397480E+01
  vertex  0.138633E+03  0.496375E+02  0.480590E+01
 endloop
endfacet
facet normal  0.928670E+00 -0.346895E+00  0.131287E+00
 outer loop
  vertex  0.139454E+03  0.490393E+02  0.280340E+01
  vertex  0.139766E+03  0.488125E+02  0.000000E+00
  vertex  0.142012E+03  0.548242E+02  0.000000E+00
 endloop
endfacet
facet normal  0.929174E+00 -0.333413E+00  0.159596E+00
 outer loop
  vertex  0.142012E+03  0.548241E+02  0.000000E+00
  vertex  0.141658E+03  0.549488E+02  0.231860E+01
  vertex  0.139454E+03  0.490392E+02  0.280340E+01
 endloop
endfacet
facet normal -0.867435E+00  0.471919E+00  0.157633E+00
 outer loop
  vertex  0.133785E+03  0.577246E+02  0.000000E+00
  vertex  0.134139E+03  0.575999E+02  0.231860E+01
  vertex  0.135966E+03  0.610732E+02  0.197570E+01
 endloop
endfacet
facet normal -0.870948E+00  0.447620E+00  0.202696E+00
 outer loop
  vertex  0.135966E+03  0.610732E+02  0.197570E+01
  vertex  0.135530E+03  0.611193E+02  0.000000E+00
  vertex  0.133785E+03  0.577246E+02  0.000000E+00
 endloop
endfacet
facet normal -0.720268E+00  0.480288E+00  0.500538E+00
 outer loop
  vertex  0.134139E+03  0.575999E+02  0.231860E+01
  vertex  0.135070E+03  0.572714E+02  0.397480E+01
  vertex  0.137116E+03  0.609514E+02  0.338700E+01
 endloop
endfacet
facet normal -0.685664E+00  0.419449E+00  0.594918E+00
 outer loop
  vertex  0.137116E+03  0.609514E+02  0.338700E+01
  vertex  0.135966E+03  0.610732E+02  0.197570E+01
  vertex  0.134139E+03  0.575998E+02  0.231850E+01
 endloop
endfacet
facet normal -0.450867E+00  0.413461E+00  0.791056E+00
 outer loop
  vertex  0.135070E+03  0.572714E+02  0.397480E+01
  vertex  0.136388E+03  0.568069E+02  0.496850E+01
  vertex  0.138742E+03  0.607794E+02  0.423370E+01
 endloop
endfacet
facet normal -0.401253E+00  0.357721E+00  0.843227E+00
 outer loop
  vertex  0.138742E+03  0.607793E+02  0.423360E+01
  vertex  0.137116E+03  0.609514E+02  0.338700E+01
  vertex  0.135070E+03  0.572714E+02  0.397480E+01
 endloop
endfacet
facet normal -0.121989E+00  0.251365E+00  0.960174E+00
 outer loop
  vertex  0.136388E+03  0.568069E+02  0.496850E+01
  vertex  0.137898E+03  0.562744E+02  0.529980E+01
  vertex  0.140605E+03  0.605821E+02  0.451600E+01
 endloop
endfacet
facet normal -0.119245E+00  0.248461E+00  0.961274E+00
 outer loop
  vertex  0.140605E+03  0.605820E+02  0.451590E+01
  vertex  0.138742E+03  0.607794E+02  0.423370E+01
  vertex  0.136388E+03  0.568069E+02  0.496850E+01
 endloop
endfacet
facet normal  0.217893E+00  0.108255E-01  0.975913E+00
 outer loop
  vertex  0.137898E+03  0.562744E+02  0.529980E+01
  vertex  0.139409E+03  0.557419E+02  0.496850E+01
  vertex  0.142469E+03  0.603848E+02  0.423370E+01
 endloop
endfacet
facet normal  0.157615E+00  0.800172E-01  0.984253E+00
 outer loop
  vertex  0.142469E+03  0.603847E+02  0.423360E+01
  vertex  0.140605E+03  0.605821E+02  0.451600E+01
  vertex  0.137898E+03  0.562743E+02  0.529970E+01
 endloop
endfacet
facet normal  0.521630E+00 -0.259236E+00  0.812834E+00
 outer loop
  vertex  0.139409E+03  0.557419E+02  0.496850E+01
  vertex  0.140726E+03  0.552774E+02  0.397480E+01
  vertex  0.144095E+03  0.602128E+02  0.338700E+01
 endloop
endfacet
facet normal  0.443700E+00 -0.152710E+00  0.883068E+00
 outer loop
  vertex  0.144095E+03  0.602127E+02  0.338700E+01
  vertex  0.142469E+03  0.603848E+02  0.423370E+01
  vertex  0.139409E+03  0.557419E+02  0.496850E+01
 endloop
endfacet
facet normal  0.724902E+00 -0.472175E+00  0.501566E+00
 outer loop
  vertex  0.140726E+03  0.552774E+02  0.397480E+01
  vertex  0.141658E+03  0.549488E+02  0.231860E+01
  vertex  0.145245E+03  0.600910E+02  0.197570E+01
 endloop
endfacet
facet normal  0.692737E+00 -0.401481E+00  0.599107E+00
 outer loop
  vertex  0.145245E+03  0.600909E+02  0.197570E+01
  vertex  0.144095E+03  0.602128E+02  0.338700E+01
  vertex  0.140726E+03  0.552774E+02  0.397480E+01
 endloop
endfacet
facet normal  0.808400E+00 -0.568189E+00  0.153785E+00
 outer loop
  vertex  0.141658E+03  0.549488E+02  0.231860E+01
  vertex  0.142012E+03  0.548242E+02  0.000000E+00
  vertex  0.145681E+03  0.600449E+02  0.000000E+00
 endloop
endfacet
facet normal  0.810903E+00 -0.552800E+00  0.191961E+00
 outer loop
  vertex  0.145681E+03  0.600448E+02  0.000000E+00
  vertex  0.145245E+03  0.600910E+02  0.197570E+01
  vertex  0.141658E+03  0.549487E+02  0.231850E+01
 endloop
endfacet
facet normal -0.700413E+00  0.692997E+00  0.170810E+00
 outer loop
  vertex  0.135530E+03  0.611193E+02  0.000000E+00
  vertex  0.135966E+03  0.610732E+02  0.197570E+01
  vertex  0.138830E+03  0.640000E+02  0.184570E+01
 endloop
endfacet
facet normal -0.708783E+00  0.669341E+00  0.222731E+00
 outer loop
  vertex  0.138830E+03  0.640000E+02  0.184570E+01
  vertex  0.138250E+03  0.640000E+02  0.000000E+00
  vertex  0.135530E+03  0.611193E+02  0.000000E+00
 endloop
endfacet
facet normal -0.566967E+00  0.641036E+00  0.517321E+00
 outer loop
  vertex  0.135966E+03  0.610732E+02  0.197570E+01
  vertex  0.137116E+03  0.609514E+02  0.338700E+01
  vertex  0.140359E+03  0.640000E+02  0.316400E+01
 endloop
endfacet
facet normal -0.541790E+00  0.558116E+00  0.628467E+00
 outer loop
  vertex  0.140359E+03  0.640000E+02  0.316400E+01
  vertex  0.138830E+03  0.640000E+02  0.184570E+01
  vertex  0.135966E+03  0.610732E+02  0.197570E+01
 endloop
endfacet
facet normal -0.360670E+00  0.491859E+00  0.792459E+00
 outer loop
  vertex  0.137116E+03  0.609514E+02  0.338700E+01
  vertex  0.138742E+03  0.607794E+02  0.423370E+01
  vertex  0.142521E+03  0.640000E+02  0.395500E+01
 endloop
endfacet
facet normal -0.315129E+00  0.398277E+00  0.861435E+00
 outer loop
  vertex  0.142521E+03  0.640000E+02  0.395490E+01
  vertex  0.140359E+03  0.640000E+02  0.316400E+01
  vertex  0.137116E+03  0.609514E+02  0.338700E+01
 endloop
endfacet
facet normal -0.120651E+00  0.238938E+00  0.963510E+00
 outer loop
  vertex  0.138742E+03  0.607794E+02  0.423370E+01
  vertex  0.140605E+03  0.605821E+02  0.451600E+01
  vertex  0.145000E+03  0.640000E+02  0.421870E+01
 endloop
endfacet
facet normal -0.103493E+00  0.205639E+00  0.973140E+00
 outer loop
  vertex  0.145000E+03  0.640000E+02  0.421860E+01
  vertex  0.142521E+03  0.640000E+02  0.395500E+01
  vertex  0.138742E+03  0.607793E+02  0.423360E+01
 endloop
endfacet
facet normal  0.136984E+00 -0.113955E+00  0.983997E+00
 outer loop
  vertex  0.140605E+03  0.605821E+02  0.451600E+01
  vertex  0.142469E+03  0.603848E+02  0.423370E+01
  vertex  0.147479E+03  0.640000E+02  0.395500E+01
 endloop
endfacet
facet normal  0.105707E+00 -0.495566E-01  0.993162E+00
 outer loop
  vertex  0.147479E+03  0.640000E+02  0.395490E+01
  vertex  0.145000E+03  0.640000E+02  0.421870E+01
  vertex  0.140605E+03  0.605820E+02  0.451590E+01
 endloop
endfacet
facet normal  0.363080E+00 -0.484805E+00  0.795699E+00
 outer loop
  vertex  0.142469E+03  0.603848E+02  0.423370E+01
  vertex  0.144095E+03  0.602128E+02  0.338700E+01
  vertex  0.149641E+03  0.640000E+02  0.316400E+01
 endloop
endfacet
facet normal  0.318606E+00 -0.374357E+00  0.870831E+00
 outer loop
  vertex  0.149641E+03  0.640000E+02  0.316400E+01
  vertex  0.147479E+03  0.640000E+02  0.395500E+01
  vertex  0.142469E+03  0.603847E+02  0.423360E+01
 endloop
endfacet
facet normal  0.494322E+00 -0.733761E+00  0.466091E+00
 outer loop
  vertex  0.144095E+03  0.602128E+02  0.338700E+01
  vertex  0.145245E+03  0.600910E+02  0.197570E+01
  vertex  0.151170E+03  0.640000E+02  0.184570E+01
 endloop
endfacet
facet normal  0.482555E+00 -0.673625E+00  0.559795E+00
 outer loop
  vertex  0.151170E+03  0.640000E+02  0.184570E+01
  vertex  0.149641E+03  0.640000E+02  0.316400E+01
  vertex  0.144095E+03  0.602127E+02  0.338700E+01
 endloop
endfacet
facet normal  0.540709E+00 -0.829690E+00  0.138740E+00
 outer loop
  vertex  0.145245E+03  0.600910E+02  0.197570E+01
  vertex  0.145681E+03  0.600449E+02  0.000000E+00
  vertex  0.151750E+03  0.640000E+02  0.000000E+00
 endloop
endfacet
facet normal  0.545177E+00 -0.820623E+00  0.171346E+00
 outer loop
  vertex  0.151750E+03  0.640000E+02  0.000000E+00
  vertex  0.151170E+03  0.640000E+02  0.184570E+01
  vertex  0.145245E+03  0.600909E+02  0.197570E+01
 endloop
endfacet
facet normal  0.180297E-02 -0.995219E+00  0.976543E-01
 outer loop
  vertex  0.415000E+02  0.555625E+02  0.000000E+00
  vertex  0.415966E+02  0.557800E+02  0.221480E+01
  vertex  0.359113E+02  0.557697E+02  0.221480E+01
 endloop
endfacet
facet normal  0.176384E-02 -0.995232E+00  0.975166E-01
 outer loop
  vertex  0.359113E+02  0.557696E+02  0.221470E+01
  vertex  0.359145E+02  0.555526E+02  0.000000E+00
  vertex  0.415000E+02  0.555625E+02  0.000000E+00
 endloop
endfacet
facet normal  0.181784E-02 -0.940223E+00  0.340554E+00
 outer loop
  vertex  0.415966E+02  0.557800E+02  0.221480E+01
  vertex  0.418515E+02  0.563535E+02  0.379680E+01
  vertex  0.359028E+02  0.563420E+02  0.379680E+01
 endloop
endfacet
facet normal  0.169320E-02 -0.940367E+00  0.340156E+00
 outer loop
  vertex  0.359028E+02  0.563419E+02  0.379670E+01
  vertex  0.359113E+02  0.557697E+02  0.221480E+01
  vertex  0.415965E+02  0.557799E+02  0.221470E+01
 endloop
endfacet
facet normal  0.157639E-02 -0.760659E+00  0.649150E+00
 outer loop
  vertex  0.418515E+02  0.563535E+02  0.379680E+01
  vertex  0.422119E+02  0.571643E+02  0.474600E+01
  vertex  0.358909E+02  0.571512E+02  0.474600E+01
 endloop
endfacet
facet normal  0.148221E-02 -0.760992E+00  0.648759E+00
 outer loop
  vertex  0.358908E+02  0.571511E+02  0.474590E+01
  vertex  0.359028E+02  0.563420E+02  0.379680E+01
  vertex  0.418515E+02  0.563535E+02  0.379670E+01
 endloop
endfacet
facet normal  0.707496E-03 -0.322553E+00  0.946551E+00
 outer loop
  vertex  0.422119E+02  0.571643E+02  0.474600E+01
  vertex  0.426250E+02  0.580937E+02  0.506240E+01
  vertex  0.358771E+02  0.580789E+02  0.506240E+01
 endloop
endfacet
facet normal  0.678700E-03 -0.322731E+00  0.946490E+00
 outer loop
  vertex  0.358771E+02  0.580788E+02  0.506230E+01
  vertex  0.358909E+02  0.571512E+02  0.474600E+01
  vertex  0.422118E+02  0.571642E+02  0.474590E+01
 endloop
endfacet
facet normal -0.746402E-03  0.322568E+00  0.946546E+00
 outer loop
  vertex  0.426250E+02  0.580937E+02  0.506240E+01
  vertex  0.430380E+02  0.590231E+02  0.474600E+01
  vertex  0.358634E+02  0.590065E+02  0.474600E+01
 endloop
endfacet
facet normal -0.694309E-03  0.322913E+00  0.946428E+00
 outer loop
  vertex  0.358633E+02  0.590065E+02  0.474590E+01
  vertex  0.358771E+02  0.580789E+02  0.506240E+01
  vertex  0.426250E+02  0.580937E+02  0.506230E+01
 endloop
endfacet
facet normal -0.183450E-02  0.760707E+00  0.649093E+00
 outer loop
  vertex  0.430380E+02  0.590231E+02  0.474600E+01
  vertex  0.433984E+02  0.598339E+02  0.379680E+01
  vertex  0.358515E+02  0.598157E+02  0.379680E+01
 endloop
endfacet
facet normal -0.175196E-02  0.761018E+00  0.648728E+00
 outer loop
  vertex  0.358515E+02  0.598157E+02  0.379670E+01
  vertex  0.358634E+02  0.590065E+02  0.474600E+01
  vertex  0.430379E+02  0.590231E+02  0.474590E+01
 endloop
endfacet
facet normal -0.232327E-02  0.940249E+00  0.340479E+00
 outer loop
  vertex  0.433984E+02  0.598339E+02  0.379680E+01
  vertex  0.436533E+02  0.604074E+02  0.221480E+01
  vertex  0.358430E+02  0.603881E+02  0.221480E+01
 endloop
endfacet
facet normal -0.226328E-02  0.940360E+00  0.340173E+00
 outer loop
  vertex  0.358429E+02  0.603880E+02  0.221470E+01
  vertex  0.358515E+02  0.598157E+02  0.379680E+01
  vertex  0.433983E+02  0.598339E+02  0.379670E+01
 endloop
endfacet
facet normal -0.249091E-02  0.995216E+00  0.976702E-01
 outer loop
  vertex  0.436533E+02  0.604074E+02  0.221480E+01
  vertex  0.437500E+02  0.606250E+02  0.000000E+00
  vertex  0.358398E+02  0.606052E+02  0.000000E+00
 endloop
endfacet
facet normal -0.244523E-02  0.995227E+00  0.975590E-01
 outer loop
  vertex  0.358398E+02  0.606052E+02  0.000000E+00
  vertex  0.358430E+02  0.603881E+02  0.221480E+01
  vertex  0.436533E+02  0.604073E+02  0.221470E+01
 endloop
endfacet
facet normal  0.143434E-01 -0.995126E+00  0.975646E-01
 outer loop
  vertex  0.359145E+02  0.555526E+02  0.000000E+00
  vertex  0.359113E+02  0.557697E+02  0.221480E+01
  vertex  0.309021E+02  0.556975E+02  0.221480E+01
 endloop
endfacet
facet normal  0.139803E-01 -0.995214E+00  0.967091E-01
 outer loop
  vertex  0.309020E+02  0.556974E+02  0.221470E+01
  vertex  0.309882E+02  0.554834E+02  0.000000E+00
  vertex  0.359145E+02  0.555526E+02  0.000000E+00
 endloop
endfacet
facet normal  0.143882E-01 -0.940238E+00  0.340215E+00
 outer loop
  vertex  0.359113E+02  0.557697E+02  0.221480E+01
  vertex  0.359028E+02  0.563420E+02  0.379680E+01
  vertex  0.306751E+02  0.562620E+02  0.379680E+01
 endloop
endfacet
facet normal  0.135531E-01 -0.941125E+00  0.337786E+00
 outer loop
  vertex  0.306751E+02  0.562620E+02  0.379670E+01
  vertex  0.309021E+02  0.556975E+02  0.221480E+01
  vertex  0.359113E+02  0.557696E+02  0.221470E+01
 endloop
endfacet
facet normal  0.125189E-01 -0.760860E+00  0.648796E+00
 outer loop
  vertex  0.359028E+02  0.563420E+02  0.379680E+01
  vertex  0.358909E+02  0.571512E+02  0.474600E+01
  vertex  0.303542E+02  0.570601E+02  0.474600E+01
 endloop
endfacet
facet normal  0.116794E-01 -0.763364E+00  0.645863E+00
 outer loop
  vertex  0.303542E+02  0.570601E+02  0.474590E+01
  vertex  0.306751E+02  0.562620E+02  0.379680E+01
  vertex  0.359028E+02  0.563419E+02  0.379670E+01
 endloop
endfacet
facet normal  0.569207E-02 -0.322720E+00  0.946478E+00
 outer loop
  vertex  0.358909E+02  0.571512E+02  0.474600E+01
  vertex  0.358771E+02  0.580789E+02  0.506240E+01
  vertex  0.299863E+02  0.579750E+02  0.506240E+01
 endloop
endfacet
facet normal  0.535623E-02 -0.324848E+00  0.945751E+00
 outer loop
  vertex  0.299862E+02  0.579749E+02  0.506230E+01
  vertex  0.303542E+02  0.570601E+02  0.474600E+01
  vertex  0.358908E+02  0.571511E+02  0.474590E+01
 endloop
endfacet
facet normal -0.602085E-02  0.322746E+00  0.946466E+00
 outer loop
  vertex  0.358771E+02  0.580789E+02  0.506240E+01
  vertex  0.358634E+02  0.590065E+02  0.474600E+01
  vertex  0.296184E+02  0.588900E+02  0.474600E+01
 endloop
endfacet
facet normal -0.570857E-02  0.324873E+00  0.945741E+00
 outer loop
  vertex  0.296184E+02  0.588899E+02  0.474590E+01
  vertex  0.299863E+02  0.579750E+02  0.506240E+01
  vertex  0.358771E+02  0.580788E+02  0.506230E+01
 endloop
endfacet
facet normal -0.148124E-01  0.760822E+00  0.648792E+00
 outer loop
  vertex  0.358634E+02  0.590065E+02  0.474600E+01
  vertex  0.358515E+02  0.598157E+02  0.379680E+01
  vertex  0.292974E+02  0.596881E+02  0.379680E+01
 endloop
endfacet
facet normal -0.142241E-01  0.763019E+00  0.646220E+00
 outer loop
  vertex  0.292973E+02  0.596880E+02  0.379670E+01
  vertex  0.296184E+02  0.588900E+02  0.474600E+01
  vertex  0.358633E+02  0.590065E+02  0.474590E+01
 endloop
endfacet
facet normal -0.188092E-01  0.940142E+00  0.340263E+00
 outer loop
  vertex  0.358515E+02  0.598157E+02  0.379680E+01
  vertex  0.358430E+02  0.603881E+02  0.221480E+01
  vertex  0.290704E+02  0.602526E+02  0.221480E+01
 endloop
endfacet
facet normal -0.183122E-01  0.940850E+00  0.338328E+00
 outer loop
  vertex  0.290704E+02  0.602526E+02  0.221470E+01
  vertex  0.292974E+02  0.596881E+02  0.379680E+01
  vertex  0.358515E+02  0.598157E+02  0.379670E+01
 endloop
endfacet
facet normal -0.201023E-01  0.995026E+00  0.975648E-01
 outer loop
  vertex  0.358430E+02  0.603881E+02  0.221480E+01
  vertex  0.358398E+02  0.606052E+02  0.000000E+00
  vertex  0.289843E+02  0.604667E+02  0.000000E+00
 endloop
endfacet
facet normal -0.198928E-01  0.995089E+00  0.969664E-01
 outer loop
  vertex  0.289843E+02  0.604667E+02  0.000000E+00
  vertex  0.290704E+02  0.602526E+02  0.221480E+01
  vertex  0.358429E+02  0.603880E+02  0.221470E+01
 endloop
endfacet
facet normal  0.452345E-01 -0.994171E+00  0.978629E-01
 outer loop
  vertex  0.309882E+02  0.554834E+02  0.000000E+00
  vertex  0.309021E+02  0.556975E+02  0.221480E+01
  vertex  0.265944E+02  0.555015E+02  0.221480E+01
 endloop
endfacet
facet normal  0.440400E-01 -0.994455E+00  0.954978E-01
 outer loop
  vertex  0.265944E+02  0.555014E+02  0.221470E+01
  vertex  0.267475E+02  0.552955E+02  0.000000E+00
  vertex  0.309881E+02  0.554833E+02  0.000000E+00
 endloop
endfacet
facet normal  0.454686E-01 -0.938779E+00  0.341507E+00
 outer loop
  vertex  0.309021E+02  0.556975E+02  0.221480E+01
  vertex  0.306751E+02  0.562620E+02  0.379680E+01
  vertex  0.261906E+02  0.560448E+02  0.379680E+01
 endloop
endfacet
facet normal  0.428258E-01 -0.941516E+00  0.334237E+00
 outer loop
  vertex  0.261905E+02  0.560447E+02  0.379670E+01
  vertex  0.265944E+02  0.555015E+02  0.221480E+01
  vertex  0.309020E+02  0.556974E+02  0.221470E+01
 endloop
endfacet
facet normal  0.396023E-01 -0.758163E+00  0.650862E+00
 outer loop
  vertex  0.306751E+02  0.562620E+02  0.379680E+01
  vertex  0.303542E+02  0.570601E+02  0.474600E+01
  vertex  0.256198E+02  0.568128E+02  0.474600E+01
 endloop
endfacet
facet normal  0.371052E-01 -0.765808E+00  0.641999E+00
 outer loop
  vertex  0.256198E+02  0.568128E+02  0.474590E+01
  vertex  0.261906E+02  0.560448E+02  0.379680E+01
  vertex  0.306751E+02  0.562620E+02  0.379670E+01
 endloop
endfacet
facet normal  0.179784E-01 -0.320320E+00  0.947139E+00
 outer loop
  vertex  0.303542E+02  0.570601E+02  0.474600E+01
  vertex  0.299863E+02  0.579750E+02  0.506240E+01
  vertex  0.249655E+02  0.576932E+02  0.506240E+01
 endloop
endfacet
facet normal  0.170911E-01 -0.326819E+00  0.944933E+00
 outer loop
  vertex  0.249654E+02  0.576931E+02  0.506230E+01
  vertex  0.256198E+02  0.568128E+02  0.474600E+01
  vertex  0.303542E+02  0.570601E+02  0.474590E+01
 endloop
endfacet
facet normal -0.190649E-01  0.319890E+00  0.947263E+00
 outer loop
  vertex  0.299863E+02  0.579750E+02  0.506240E+01
  vertex  0.296184E+02  0.588900E+02  0.474600E+01
  vertex  0.243112E+02  0.585737E+02  0.474600E+01
 endloop
endfacet
facet normal -0.182825E-01  0.326180E+00  0.945131E+00
 outer loop
  vertex  0.243111E+02  0.585736E+02  0.474590E+01
  vertex  0.249655E+02  0.576932E+02  0.506240E+01
  vertex  0.299862E+02  0.579749E+02  0.506230E+01
 endloop
endfacet
facet normal -0.471650E-01  0.756633E+00  0.652137E+00
 outer loop
  vertex  0.296184E+02  0.588900E+02  0.474600E+01
  vertex  0.292974E+02  0.596881E+02  0.379680E+01
  vertex  0.237404E+02  0.593417E+02  0.379680E+01
 endloop
endfacet
facet normal -0.454526E-01  0.763094E+00  0.644687E+00
 outer loop
  vertex  0.237404E+02  0.593417E+02  0.379670E+01
  vertex  0.243112E+02  0.585737E+02  0.474600E+01
  vertex  0.296184E+02  0.588899E+02  0.474590E+01
 endloop
endfacet
facet normal -0.600975E-01  0.937373E+00  0.343105E+00
 outer loop
  vertex  0.292974E+02  0.596881E+02  0.379680E+01
  vertex  0.290704E+02  0.602526E+02  0.221480E+01
  vertex  0.233367E+02  0.598850E+02  0.221480E+01
 endloop
endfacet
facet normal -0.585423E-01  0.939501E+00  0.337506E+00
 outer loop
  vertex  0.233367E+02  0.598849E+02  0.221470E+01
  vertex  0.237404E+02  0.593417E+02  0.379680E+01
  vertex  0.292973E+02  0.596880E+02  0.379670E+01
 endloop
endfacet
facet normal -0.643176E-01  0.993057E+00  0.984970E-01
 outer loop
  vertex  0.290704E+02  0.602526E+02  0.221480E+01
  vertex  0.289843E+02  0.604667E+02  0.000000E+00
  vertex  0.231835E+02  0.600910E+02  0.000000E+00
 endloop
endfacet
facet normal -0.636796E-01  0.993270E+00  0.967456E-01
 outer loop
  vertex  0.231835E+02  0.600909E+02  0.000000E+00
  vertex  0.233367E+02  0.598850E+02  0.221480E+01
  vertex  0.290704E+02  0.602526E+02  0.221470E+01
 endloop
endfacet
facet normal  0.105408E+00 -0.989457E+00  0.993153E-01
 outer loop
  vertex  0.267475E+02  0.552955E+02  0.000000E+00
  vertex  0.265944E+02  0.555015E+02  0.221480E+01
  vertex  0.230133E+02  0.551200E+02  0.221480E+01
 endloop
endfacet
facet normal  0.102677E+00 -0.990205E+00  0.946115E-01
 outer loop
  vertex  0.230132E+02  0.551199E+02  0.221470E+01
  vertex  0.232187E+02  0.549296E+02  0.000000E+00
  vertex  0.267474E+02  0.552955E+02  0.000000E+00
 endloop
endfacet
facet normal  0.105987E+00 -0.931832E+00  0.347068E+00
 outer loop
  vertex  0.265944E+02  0.555015E+02  0.221480E+01
  vertex  0.261906E+02  0.560448E+02  0.379680E+01
  vertex  0.224716E+02  0.556218E+02  0.379680E+01
 endloop
endfacet
facet normal  0.999171E-01 -0.938068E+00  0.331731E+00
 outer loop
  vertex  0.224715E+02  0.556217E+02  0.379670E+01
  vertex  0.230133E+02  0.551200E+02  0.221480E+01
  vertex  0.265944E+02  0.555014E+02  0.221470E+01
 endloop
endfacet
facet normal  0.918429E-01 -0.746392E+00  0.659138E+00
 outer loop
  vertex  0.261906E+02  0.560448E+02  0.379680E+01
  vertex  0.256198E+02  0.568128E+02  0.474600E+01
  vertex  0.217059E+02  0.563312E+02  0.474600E+01
 endloop
endfacet
facet normal  0.868004E-01 -0.763153E+00  0.640362E+00
 outer loop
  vertex  0.217059E+02  0.563311E+02  0.474590E+01
  vertex  0.224716E+02  0.556218E+02  0.379680E+01
  vertex  0.261905E+02  0.560447E+02  0.379670E+01
 endloop
endfacet
facet normal  0.411996E-01 -0.310661E+00  0.949628E+00
 outer loop
  vertex  0.256198E+02  0.568128E+02  0.474600E+01
  vertex  0.249655E+02  0.576932E+02  0.506240E+01
  vertex  0.208281E+02  0.571445E+02  0.506240E+01
 endloop
endfacet
facet normal  0.399451E-01 -0.324432E+00  0.945065E+00
 outer loop
  vertex  0.208281E+02  0.571445E+02  0.506230E+01
  vertex  0.217059E+02  0.563312E+02  0.474600E+01
  vertex  0.256198E+02  0.568128E+02  0.474590E+01
 endloop
endfacet
facet normal -0.436434E-01  0.308968E+00  0.950071E+00
 outer loop
  vertex  0.249655E+02  0.576932E+02  0.506240E+01
  vertex  0.243112E+02  0.585737E+02  0.474600E+01
  vertex  0.199503E+02  0.579577E+02  0.474600E+01
 endloop
endfacet
facet normal -0.426817E-01  0.322059E+00  0.945757E+00
 outer loop
  vertex  0.199503E+02  0.579576E+02  0.474590E+01
  vertex  0.208281E+02  0.571445E+02  0.506240E+01
  vertex  0.249654E+02  0.576931E+02  0.506230E+01
 endloop
endfacet
facet normal -0.109485E+00  0.739512E+00  0.664180E+00
 outer loop
  vertex  0.243112E+02  0.585737E+02  0.474600E+01
  vertex  0.237404E+02  0.593417E+02  0.379680E+01
  vertex  0.191845E+02  0.586672E+02  0.379680E+01
 endloop
endfacet
facet normal -0.106396E+00  0.753426E+00  0.648867E+00
 outer loop
  vertex  0.191844E+02  0.586671E+02  0.379670E+01
  vertex  0.199503E+02  0.579577E+02  0.474600E+01
  vertex  0.243111E+02  0.585736E+02  0.474590E+01
 endloop
endfacet
facet normal -0.141057E+00  0.924714E+00  0.353564E+00
 outer loop
  vertex  0.237404E+02  0.593417E+02  0.379680E+01
  vertex  0.233367E+02  0.598850E+02  0.221480E+01
  vertex  0.186429E+02  0.591690E+02  0.221480E+01
 endloop
endfacet
facet normal -0.137621E+00  0.929605E+00  0.341900E+00
 outer loop
  vertex  0.186429E+02  0.591689E+02  0.221470E+01
  vertex  0.191845E+02  0.586672E+02  0.379680E+01
  vertex  0.237404E+02  0.593417E+02  0.379670E+01
 endloop
endfacet
facet normal -0.151578E+00  0.983175E+00  0.101931E+00
 outer loop
  vertex  0.233367E+02  0.598850E+02  0.221480E+01
  vertex  0.231835E+02  0.600910E+02  0.000000E+00
  vertex  0.184375E+02  0.593593E+02  0.000000E+00
 endloop
endfacet
facet normal -0.150043E+00  0.983771E+00  0.983985E-01
 outer loop
  vertex  0.184375E+02  0.593592E+02  0.000000E+00
  vertex  0.186429E+02  0.591690E+02  0.221480E+01
  vertex  0.233367E+02  0.598849E+02  0.221470E+01
 endloop
endfacet
facet normal  0.215886E+00 -0.970919E+00  0.103488E+00
 outer loop
  vertex  0.232187E+02  0.549296E+02  0.000000E+00
  vertex  0.230133E+02  0.551200E+02  0.221480E+01
  vertex  0.201840E+02  0.544909E+02  0.221480E+01
 endloop
endfacet
facet normal  0.210253E+00 -0.972985E+00  0.953647E-01
 outer loop
  vertex  0.201840E+02  0.544908E+02  0.221470E+01
  vertex  0.204282E+02  0.543265E+02  0.000000E+00
  vertex  0.232187E+02  0.549295E+02  0.000000E+00
 endloop
endfacet
facet normal  0.215793E+00 -0.907020E+00  0.361592E+00
 outer loop
  vertex  0.230133E+02  0.551200E+02  0.221480E+01
  vertex  0.224716E+02  0.556218E+02  0.379680E+01
  vertex  0.195403E+02  0.549244E+02  0.379680E+01
 endloop
endfacet
facet normal  0.204479E+00 -0.919678E+00  0.335233E+00
 outer loop
  vertex  0.195403E+02  0.549244E+02  0.379670E+01
  vertex  0.201840E+02  0.544909E+02  0.221480E+01
  vertex  0.230132E+02  0.551199E+02  0.221470E+01
 endloop
endfacet
facet normal  0.183473E+00 -0.710695E+00  0.679154E+00
 outer loop
  vertex  0.224716E+02  0.556218E+02  0.379680E+01
  vertex  0.217059E+02  0.563312E+02  0.474600E+01
  vertex  0.186303E+02  0.555372E+02  0.474600E+01
 endloop
endfacet
facet normal  0.176352E+00 -0.741229E+00  0.647672E+00
 outer loop
  vertex  0.186303E+02  0.555372E+02  0.474590E+01
  vertex  0.195403E+02  0.549244E+02  0.379680E+01
  vertex  0.224715E+02  0.556217E+02  0.379670E+01
 endloop
endfacet
facet normal  0.797017E-01 -0.285523E+00  0.955052E+00
 outer loop
  vertex  0.217059E+02  0.563312E+02  0.474600E+01
  vertex  0.208281E+02  0.571445E+02  0.506240E+01
  vertex  0.175871E+02  0.562398E+02  0.506240E+01
 endloop
endfacet
facet normal  0.796590E-01 -0.308483E+00  0.947888E+00
 outer loop
  vertex  0.175870E+02  0.562397E+02  0.506230E+01
  vertex  0.186303E+02  0.555372E+02  0.474600E+01
  vertex  0.217059E+02  0.563311E+02  0.474590E+01
 endloop
endfacet
facet normal -0.838781E-01  0.281389E+00  0.955921E+00
 outer loop
  vertex  0.208281E+02  0.571445E+02  0.506240E+01
  vertex  0.199503E+02  0.579577E+02  0.474600E+01
  vertex  0.165439E+02  0.569423E+02  0.474600E+01
 endloop
endfacet
facet normal -0.843972E-01  0.302449E+00  0.949422E+00
 outer loop
  vertex  0.165438E+02  0.569422E+02  0.474590E+01
  vertex  0.175871E+02  0.562398E+02  0.506240E+01
  vertex  0.208281E+02  0.571445E+02  0.506230E+01
 endloop
endfacet
facet normal -0.216219E+00  0.690322E+00  0.690438E+00
 outer loop
  vertex  0.199503E+02  0.579577E+02  0.474600E+01
  vertex  0.191845E+02  0.586672E+02  0.379680E+01
  vertex  0.156339E+02  0.575551E+02  0.379680E+01
 endloop
endfacet
facet normal -0.213104E+00  0.715042E+00  0.665809E+00
 outer loop
  vertex  0.156338E+02  0.575550E+02  0.379670E+01
  vertex  0.165439E+02  0.569423E+02  0.474600E+01
  vertex  0.199503E+02  0.579576E+02  0.474590E+01
 endloop
endfacet
facet normal -0.284804E+00  0.881317E+00  0.377051E+00
 outer loop
  vertex  0.191845E+02  0.586672E+02  0.379680E+01
  vertex  0.186429E+02  0.591690E+02  0.221480E+01
  vertex  0.149902E+02  0.579886E+02  0.221480E+01
 endloop
endfacet
facet normal -0.279092E+00  0.891144E+00  0.357730E+00
 outer loop
  vertex  0.149902E+02  0.579886E+02  0.221470E+01
  vertex  0.156339E+02  0.575551E+02  0.379680E+01
  vertex  0.191844E+02  0.586671E+02  0.379670E+01
 endloop
endfacet
facet normal -0.308735E+00  0.944788E+00  0.109810E+00
 outer loop
  vertex  0.186429E+02  0.591690E+02  0.221480E+01
  vertex  0.184375E+02  0.593593E+02  0.000000E+00
  vertex  0.147460E+02  0.581530E+02  0.000000E+00
 endloop
endfacet
facet normal -0.305809E+00  0.946404E+00  0.103924E+00
 outer loop
  vertex  0.147460E+02  0.581529E+02  0.000000E+00
  vertex  0.149902E+02  0.579886E+02  0.221480E+01
  vertex  0.186429E+02  0.591689E+02  0.221470E+01
 endloop
endfacet
facet normal  0.413221E+00 -0.903638E+00  0.112635E+00
 outer loop
  vertex  0.204282E+02  0.543265E+02  0.000000E+00
  vertex  0.201840E+02  0.544909E+02  0.221480E+01
  vertex  0.181319E+02  0.535525E+02  0.221480E+01
 endloop
endfacet
facet normal  0.403818E+00 -0.909252E+00  0.100951E+00
 outer loop
  vertex  0.181319E+02  0.535525E+02  0.221470E+01
  vertex  0.184023E+02  0.534267E+02  0.000000E+00
  vertex  0.204281E+02  0.543264E+02  0.000000E+00
 endloop
endfacet
facet normal  0.405234E+00 -0.826241E+00  0.391294E+00
 outer loop
  vertex  0.201840E+02  0.544909E+02  0.221480E+01
  vertex  0.195403E+02  0.549244E+02  0.379680E+01
  vertex  0.174190E+02  0.538840E+02  0.379680E+01
 endloop
endfacet
facet normal  0.388994E+00 -0.850709E+00  0.353522E+00
 outer loop
  vertex  0.174190E+02  0.538839E+02  0.379670E+01
  vertex  0.181319E+02  0.535525E+02  0.221480E+01
  vertex  0.201840E+02  0.544908E+02  0.221470E+01
 endloop
endfacet
facet normal  0.329477E+00 -0.617310E+00  0.714404E+00
 outer loop
  vertex  0.195403E+02  0.549244E+02  0.379680E+01
  vertex  0.186303E+02  0.555372E+02  0.474600E+01
  vertex  0.164112E+02  0.543528E+02  0.474600E+01
 endloop
endfacet
facet normal  0.325539E+00 -0.663685E+00  0.673459E+00
 outer loop
  vertex  0.164111E+02  0.543527E+02  0.474590E+01
  vertex  0.174190E+02  0.538840E+02  0.379680E+01
  vertex  0.195403E+02  0.549244E+02  0.379670E+01
 endloop
endfacet
facet normal  0.135014E+00 -0.233205E+00  0.963009E+00
 outer loop
  vertex  0.186303E+02  0.555372E+02  0.474600E+01
  vertex  0.175871E+02  0.562398E+02  0.506240E+01
  vertex  0.152558E+02  0.548901E+02  0.506240E+01
 endloop
endfacet
facet normal  0.139738E+00 -0.261734E+00  0.954970E+00
 outer loop
  vertex  0.152558E+02  0.548900E+02  0.506230E+01
  vertex  0.164112E+02  0.543528E+02  0.474600E+01
  vertex  0.186303E+02  0.555372E+02  0.474590E+01
 endloop
endfacet
facet normal -0.140150E+00  0.226049E+00  0.963981E+00
 outer loop
  vertex  0.175871E+02  0.562398E+02  0.506240E+01
  vertex  0.165439E+02  0.569423E+02  0.474600E+01
  vertex  0.141005E+02  0.554274E+02  0.474600E+01
 endloop
endfacet
facet normal -0.145371E+00  0.251174E+00  0.956963E+00
 outer loop
  vertex  0.141005E+02  0.554273E+02  0.474590E+01
  vertex  0.152558E+02  0.548901E+02  0.506240E+01
  vertex  0.175870E+02  0.562397E+02  0.506230E+01
 endloop
endfacet
facet normal -0.374232E+00  0.573293E+00  0.728893E+00
 outer loop
  vertex  0.165439E+02  0.569423E+02  0.474600E+01
  vertex  0.156339E+02  0.575551E+02  0.379680E+01
  vertex  0.130926E+02  0.558962E+02  0.379680E+01
 endloop
endfacet
facet normal -0.376484E+00  0.607297E+00  0.699607E+00
 outer loop
  vertex  0.130925E+02  0.558961E+02  0.379670E+01
  vertex  0.141005E+02  0.554274E+02  0.474600E+01
  vertex  0.165438E+02  0.569422E+02  0.474590E+01
 endloop
endfacet
facet normal -0.509059E+00  0.754669E+00  0.413926E+00
 outer loop
  vertex  0.156339E+02  0.575551E+02  0.379680E+01
  vertex  0.149902E+02  0.579886E+02  0.221480E+01
  vertex  0.123797E+02  0.562277E+02  0.221480E+01
 endloop
endfacet
facet normal -0.503644E+00  0.771580E+00  0.388598E+00
 outer loop
  vertex  0.123796E+02  0.562276E+02  0.221470E+01
  vertex  0.130926E+02  0.558962E+02  0.379680E+01
  vertex  0.156338E+02  0.575550E+02  0.379670E+01
 endloop
endfacet
facet normal -0.559463E+00  0.819748E+00  0.122533E+00
 outer loop
  vertex  0.149902E+02  0.579886E+02  0.221480E+01
  vertex  0.147460E+02  0.581530E+02  0.000000E+00
  vertex  0.121093E+02  0.563535E+02  0.000000E+00
 endloop
endfacet
facet normal -0.555525E+00  0.823561E+00  0.114626E+00
 outer loop
  vertex  0.121092E+02  0.563535E+02  0.000000E+00
  vertex  0.123797E+02  0.562277E+02  0.221480E+01
  vertex  0.149902E+02  0.579886E+02  0.221470E+01
 endloop
endfacet
facet normal  0.717644E+00 -0.684823E+00  0.126513E+00
 outer loop
  vertex  0.184023E+02  0.534267E+02  0.000000E+00
  vertex  0.181319E+02  0.535525E+02  0.221480E+01
  vertex  0.168821E+02  0.522428E+02  0.221480E+01
 endloop
endfacet
facet normal  0.708378E+00 -0.696588E+00  0.113869E+00
 outer loop
  vertex  0.168820E+02  0.522428E+02  0.221470E+01
  vertex  0.171674E+02  0.521710E+02  0.000000E+00
  vertex  0.184022E+02  0.534267E+02  0.000000E+00
 endloop
endfacet
facet normal  0.675171E+00 -0.599465E+00  0.429868E+00
 outer loop
  vertex  0.181319E+02  0.535525E+02  0.221480E+01
  vertex  0.174190E+02  0.538840E+02  0.379680E+01
  vertex  0.161299E+02  0.524321E+02  0.379680E+01
 endloop
endfacet
facet normal  0.665444E+00 -0.634981E+00  0.392407E+00
 outer loop
  vertex  0.161298E+02  0.524320E+02  0.379670E+01
  vertex  0.168821E+02  0.522428E+02  0.221480E+01
  vertex  0.181319E+02  0.535525E+02  0.221470E+01
 endloop
endfacet
facet normal  0.512742E+00 -0.417117E+00  0.750406E+00
 outer loop
  vertex  0.174190E+02  0.538840E+02  0.379680E+01
  vertex  0.164112E+02  0.543528E+02  0.474600E+01
  vertex  0.150664E+02  0.526997E+02  0.474600E+01
 endloop
endfacet
facet normal  0.522170E+00 -0.463602E+00  0.715830E+00
 outer loop
  vertex  0.150663E+02  0.526996E+02  0.474590E+01
  vertex  0.161299E+02  0.524321E+02  0.379680E+01
  vertex  0.174190E+02  0.538839E+02  0.379670E+01
 endloop
endfacet
facet normal  0.196952E+00 -0.147265E+00  0.969290E+00
 outer loop
  vertex  0.164112E+02  0.543528E+02  0.474600E+01
  vertex  0.152558E+02  0.548901E+02  0.506240E+01
  vertex  0.138474E+02  0.530065E+02  0.506240E+01
 endloop
endfacet
facet normal  0.207528E+00 -0.168764E+00  0.963561E+00
 outer loop
  vertex  0.138473E+02  0.530065E+02  0.506230E+01
  vertex  0.150664E+02  0.526997E+02  0.474600E+01
  vertex  0.164111E+02  0.543527E+02  0.474590E+01
 endloop
endfacet
facet normal -0.200595E+00  0.139689E+00  0.969664E+00
 outer loop
  vertex  0.152558E+02  0.548901E+02  0.506240E+01
  vertex  0.141005E+02  0.554274E+02  0.474600E+01
  vertex  0.126283E+02  0.533133E+02  0.474600E+01
 endloop
endfacet
facet normal -0.210770E+00  0.157656E+00  0.964739E+00
 outer loop
  vertex  0.126282E+02  0.533133E+02  0.474590E+01
  vertex  0.138474E+02  0.530065E+02  0.506240E+01
  vertex  0.152558E+02  0.548900E+02  0.506230E+01
 endloop
endfacet
facet normal -0.545442E+00  0.359921E+00  0.756934E+00
 outer loop
  vertex  0.141005E+02  0.554274E+02  0.474600E+01
  vertex  0.130926E+02  0.558962E+02  0.379680E+01
  vertex  0.115648E+02  0.535809E+02  0.379680E+01
 endloop
endfacet
facet normal -0.557419E+00  0.388224E+00  0.733871E+00
 outer loop
  vertex  0.115648E+02  0.535808E+02  0.379670E+01
  vertex  0.126283E+02  0.533133E+02  0.474600E+01
  vertex  0.141005E+02  0.554273E+02  0.474590E+01
 endloop
endfacet
facet normal -0.756363E+00  0.482318E+00  0.441909E+00
 outer loop
  vertex  0.130926E+02  0.558962E+02  0.379680E+01
  vertex  0.123797E+02  0.562277E+02  0.221480E+01
  vertex  0.108126E+02  0.537702E+02  0.221480E+01
 endloop
endfacet
facet normal -0.757499E+00  0.499858E+00  0.419926E+00
 outer loop
  vertex  0.108126E+02  0.537701E+02  0.221470E+01
  vertex  0.115648E+02  0.535809E+02  0.379680E+01
  vertex  0.130925E+02  0.558961E+02  0.379670E+01
 endloop
endfacet
facet normal -0.838680E+00  0.528286E+00  0.132399E+00
 outer loop
  vertex  0.123797E+02  0.562277E+02  0.221480E+01
  vertex  0.121093E+02  0.563535E+02  0.000000E+00
  vertex  0.105273E+02  0.538420E+02  0.000000E+00
 endloop
endfacet
facet normal -0.836541E+00  0.533439E+00  0.125067E+00
 outer loop
  vertex  0.105272E+02  0.538419E+02  0.000000E+00
  vertex  0.108126E+02  0.537702E+02  0.221480E+01
  vertex  0.123796E+02  0.562276E+02  0.221470E+01
 endloop
endfacet
facet normal  0.963426E+00 -0.233393E+00  0.131671E+00
 outer loop
  vertex  0.171674E+02  0.521710E+02  0.000000E+00
  vertex  0.168821E+02  0.522428E+02  0.221480E+01
  vertex  0.164599E+02  0.505000E+02  0.221480E+01
 endloop
endfacet
facet normal  0.962444E+00 -0.240409E+00  0.126112E+00
 outer loop
  vertex  0.164598E+02  0.505000E+02  0.221470E+01
  vertex  0.167500E+02  0.505000E+02  0.000000E+00
  vertex  0.171674E+02  0.521710E+02  0.000000E+00
 endloop
endfacet
facet normal  0.876051E+00 -0.197056E+00  0.440118E+00
 outer loop
  vertex  0.168821E+02  0.522428E+02  0.221480E+01
  vertex  0.161299E+02  0.524321E+02  0.379680E+01
  vertex  0.156953E+02  0.505000E+02  0.379680E+01
 endloop
endfacet
facet normal  0.879679E+00 -0.213031E+00  0.425186E+00
 outer loop
  vertex  0.156953E+02  0.505000E+02  0.379670E+01
  vertex  0.164599E+02  0.505000E+02  0.221480E+01
  vertex  0.168820E+02  0.522428E+02  0.221470E+01
 endloop
endfacet
facet normal  0.641391E+00 -0.131853E+00  0.755799E+00
 outer loop
  vertex  0.161299E+02  0.524321E+02  0.379680E+01
  vertex  0.150664E+02  0.526997E+02  0.474600E+01
  vertex  0.146142E+02  0.505000E+02  0.474600E+01
 endloop
endfacet
facet normal  0.652565E+00 -0.146721E+00  0.743392E+00
 outer loop
  vertex  0.146141E+02  0.505000E+02  0.474590E+01
  vertex  0.156953E+02  0.505000E+02  0.379680E+01
  vertex  0.161298E+02  0.524320E+02  0.379670E+01
 endloop
endfacet
facet normal  0.240281E+00 -0.452857E-01  0.969646E+00
 outer loop
  vertex  0.150664E+02  0.526997E+02  0.474600E+01
  vertex  0.138474E+02  0.530065E+02  0.506240E+01
  vertex  0.133750E+02  0.505000E+02  0.506240E+01
 endloop
endfacet
facet normal  0.246998E+00 -0.507236E-01  0.967687E+00
 outer loop
  vertex  0.133750E+02  0.505000E+02  0.506230E+01
  vertex  0.146142E+02  0.505000E+02  0.474600E+01
  vertex  0.150663E+02  0.526996E+02  0.474590E+01
 endloop
endfacet
facet normal -0.241025E+00  0.422027E-01  0.969601E+00
 outer loop
  vertex  0.138474E+02  0.530065E+02  0.506240E+01
  vertex  0.126283E+02  0.533133E+02  0.474600E+01
  vertex  0.121357E+02  0.505000E+02  0.474600E+01
 endloop
endfacet
facet normal -0.247175E+00  0.466136E-01  0.967849E+00
 outer loop
  vertex  0.121357E+02  0.505000E+02  0.474590E+01
  vertex  0.133750E+02  0.505000E+02  0.506240E+01
  vertex  0.138473E+02  0.530065E+02  0.506230E+01
 endloop
endfacet
facet normal -0.646907E+00  0.107129E+00  0.755007E+00
 outer loop
  vertex  0.126283E+02  0.533133E+02  0.474600E+01
  vertex  0.115648E+02  0.535809E+02  0.379680E+01
  vertex  0.110546E+02  0.505000E+02  0.379680E+01
 endloop
endfacet
facet normal -0.655423E+00  0.114766E+00  0.746491E+00
 outer loop
  vertex  0.110545E+02  0.505000E+02  0.379670E+01
  vertex  0.121357E+02  0.505000E+02  0.474600E+01
  vertex  0.126282E+02  0.533133E+02  0.474590E+01
 endloop
endfacet
facet normal -0.887299E+00  0.141796E+00  0.438855E+00
 outer loop
  vertex  0.115648E+02  0.535809E+02  0.379680E+01
  vertex  0.108126E+02  0.537702E+02  0.221480E+01
  vertex  0.102900E+02  0.505000E+02  0.221480E+01
 endloop
endfacet
facet normal -0.890499E+00  0.147486E+00  0.430418E+00
 outer loop
  vertex  0.102899E+02  0.505000E+02  0.221470E+01
  vertex  0.110546E+02  0.505000E+02  0.379680E+01
  vertex  0.115648E+02  0.535808E+02  0.379670E+01
 endloop
endfacet
facet normal -0.979248E+00  0.154506E+00  0.131151E+00
 outer loop
  vertex  0.108126E+02  0.537702E+02  0.221480E+01
  vertex  0.105273E+02  0.538420E+02  0.000000E+00
  vertex  0.100000E+02  0.505000E+02  0.000000E+00
 endloop
endfacet
facet normal -0.979317E+00  0.156510E+00  0.128229E+00
 outer loop
  vertex  0.100000E+02  0.505000E+02  0.000000E+00
  vertex  0.102900E+02  0.505000E+02  0.221480E+01
  vertex  0.108126E+02  0.537701E+02  0.221470E+01
 endloop
endfacet
facet normal -0.530788E+00  0.830929E+00  0.166798E+00
 outer loop
  vertex  0.138250E+03  0.640000E+02  0.000000E+00
  vertex  0.138830E+03  0.640000E+02  0.184570E+01
  vertex  0.139697E+03  0.645604E+02  0.181390E+01
 endloop
endfacet
facet normal -0.543620E+00  0.819696E+00  0.180489E+00
 outer loop
  vertex  0.139697E+03  0.645604E+02  0.181380E+01
  vertex  0.139085E+03  0.645537E+02  0.000000E+00
  vertex  0.138250E+03  0.640000E+02  0.000000E+00
 endloop
endfacet
facet normal -0.428993E+00  0.753860E+00  0.497654E+00
 outer loop
  vertex  0.138830E+03  0.640000E+02  0.184570E+01
  vertex  0.140359E+03  0.640000E+02  0.316400E+01
  vertex  0.141312E+03  0.645780E+02  0.310960E+01
 endloop
endfacet
facet normal -0.442220E+00  0.715111E+00  0.541348E+00
 outer loop
  vertex  0.141312E+03  0.645780E+02  0.310960E+01
  vertex  0.139697E+03  0.645604E+02  0.181390E+01
  vertex  0.138830E+03  0.640000E+02  0.184570E+01
 endloop
endfacet
facet normal -0.279161E+00  0.582945E+00  0.763049E+00
 outer loop
  vertex  0.140359E+03  0.640000E+02  0.316400E+01
  vertex  0.142521E+03  0.640000E+02  0.395500E+01
  vertex  0.143594E+03  0.646029E+02  0.388700E+01
 endloop
endfacet
facet normal -0.277920E+00  0.533281E+00  0.798982E+00
 outer loop
  vertex  0.143594E+03  0.646028E+02  0.388700E+01
  vertex  0.141312E+03  0.645780E+02  0.310960E+01
  vertex  0.140359E+03  0.640000E+02  0.316400E+01
 endloop
endfacet
facet normal -0.100846E+00  0.302241E+00  0.947882E+00
 outer loop
  vertex  0.142521E+03  0.640000E+02  0.395500E+01
  vertex  0.145000E+03  0.640000E+02  0.421870E+01
  vertex  0.146211E+03  0.646315E+02  0.414620E+01
 endloop
endfacet
facet normal -0.976408E-01  0.281320E+00  0.954634E+00
 outer loop
  vertex  0.146211E+03  0.646315E+02  0.414620E+01
  vertex  0.143594E+03  0.646029E+02  0.388700E+01
  vertex  0.142521E+03  0.640000E+02  0.395490E+01
 endloop
endfacet
facet normal  0.105119E+00 -0.113108E+00  0.988006E+00
 outer loop
  vertex  0.145000E+03  0.640000E+02  0.421870E+01
  vertex  0.147479E+03  0.640000E+02  0.395500E+01
  vertex  0.148828E+03  0.646601E+02  0.388700E+01
 endloop
endfacet
facet normal  0.991158E-01 -0.763548E-01  0.992142E+00
 outer loop
  vertex  0.148828E+03  0.646601E+02  0.388700E+01
  vertex  0.146211E+03  0.646315E+02  0.414620E+01
  vertex  0.145000E+03  0.640000E+02  0.421860E+01
 endloop
endfacet
facet normal  0.286411E+00 -0.552347E+00  0.782868E+00
 outer loop
  vertex  0.147479E+03  0.640000E+02  0.395500E+01
  vertex  0.149641E+03  0.640000E+02  0.316400E+01
  vertex  0.151111E+03  0.646851E+02  0.310960E+01
 endloop
endfacet
facet normal  0.284543E+00 -0.497367E+00  0.819550E+00
 outer loop
  vertex  0.151111E+03  0.646850E+02  0.310960E+01
  vertex  0.148828E+03  0.646601E+02  0.388700E+01
  vertex  0.147479E+03  0.640000E+02  0.395490E+01
 endloop
endfacet
facet normal  0.377580E+00 -0.815827E+00  0.438017E+00
 outer loop
  vertex  0.149641E+03  0.640000E+02  0.316400E+01
  vertex  0.151170E+03  0.640000E+02  0.184570E+01
  vertex  0.152725E+03  0.647027E+02  0.181390E+01
 endloop
endfacet
facet normal  0.386843E+00 -0.792620E+00  0.471281E+00
 outer loop
  vertex  0.152725E+03  0.647026E+02  0.181380E+01
  vertex  0.151111E+03  0.646851E+02  0.310960E+01
  vertex  0.149641E+03  0.640000E+02  0.316400E+01
 endloop
endfacet
facet normal  0.404670E+00 -0.905575E+00  0.127186E+00
 outer loop
  vertex  0.151170E+03  0.640000E+02  0.184570E+01
  vertex  0.151750E+03  0.640000E+02  0.000000E+00
  vertex  0.153337E+03  0.647094E+02  0.000000E+00
 endloop
endfacet
facet normal  0.410272E+00 -0.901884E+00  0.135211E+00
 outer loop
  vertex  0.153337E+03  0.647093E+02  0.000000E+00
  vertex  0.152725E+03  0.647027E+02  0.181390E+01
  vertex  0.151170E+03  0.640000E+02  0.184570E+01
 endloop
endfacet
facet normal -0.435732E+00  0.888511E+00  0.143827E+00
 outer loop
  vertex  0.139085E+03  0.645537E+02  0.000000E+00
  vertex  0.139697E+03  0.645604E+02  0.181390E+01
  vertex  0.140488E+03  0.649619E+02  0.173030E+01
 endloop
endfacet
facet normal -0.445819E+00  0.881834E+00  0.153672E+00
 outer loop
  vertex  0.140488E+03  0.649618E+02  0.173020E+01
  vertex  0.139867E+03  0.649492E+02  0.000000E+00
  vertex  0.139085E+03  0.645537E+02  0.000000E+00
 endloop
endfacet
facet normal -0.351864E+00  0.832905E+00  0.427154E+00
 outer loop
  vertex  0.139697E+03  0.645604E+02  0.181390E+01
  vertex  0.141312E+03  0.645780E+02  0.310960E+01
  vertex  0.142126E+03  0.649955E+02  0.296630E+01
 endloop
endfacet
facet normal -0.363023E+00  0.810852E+00  0.459058E+00
 outer loop
  vertex  0.142126E+03  0.649954E+02  0.296630E+01
  vertex  0.140488E+03  0.649619E+02  0.173030E+01
  vertex  0.139697E+03  0.645604E+02  0.181380E+01
 endloop
endfacet
facet normal -0.232241E+00  0.715395E+00  0.658995E+00
 outer loop
  vertex  0.141312E+03  0.645780E+02  0.310960E+01
  vertex  0.143594E+03  0.646029E+02  0.388700E+01
  vertex  0.144442E+03  0.650430E+02  0.370780E+01
 endloop
endfacet
facet normal -0.233415E+00  0.690317E+00  0.684821E+00
 outer loop
  vertex  0.144442E+03  0.650429E+02  0.370770E+01
  vertex  0.142126E+03  0.649955E+02  0.296630E+01
  vertex  0.141312E+03  0.645780E+02  0.310960E+01
 endloop
endfacet
facet normal -0.898586E-01  0.519322E+00  0.849841E+00
 outer loop
  vertex  0.143594E+03  0.646029E+02  0.388700E+01
  vertex  0.146211E+03  0.646315E+02  0.414620E+01
  vertex  0.147096E+03  0.650975E+02  0.395500E+01
 endloop
endfacet
facet normal -0.897953E-01  0.518903E+00  0.850104E+00
 outer loop
  vertex  0.147096E+03  0.650975E+02  0.395490E+01
  vertex  0.144442E+03  0.650430E+02  0.370780E+01
  vertex  0.143594E+03  0.646028E+02  0.388700E+01
 endloop
endfacet
facet normal  0.950576E-01  0.178520E+00  0.979334E+00
 outer loop
  vertex  0.146211E+03  0.646315E+02  0.414620E+01
  vertex  0.148828E+03  0.646601E+02  0.388700E+01
  vertex  0.149751E+03  0.651519E+02  0.370780E+01
 endloop
endfacet
facet normal  0.853866E-01  0.235097E+00  0.968214E+00
 outer loop
  vertex  0.149751E+03  0.651519E+02  0.370770E+01
  vertex  0.147096E+03  0.650975E+02  0.395500E+01
  vertex  0.146211E+03  0.646315E+02  0.414620E+01
 endloop
endfacet
facet normal  0.308240E+00 -0.323380E+00  0.894658E+00
 outer loop
  vertex  0.148828E+03  0.646601E+02  0.388700E+01
  vertex  0.151111E+03  0.646851E+02  0.310960E+01
  vertex  0.152066E+03  0.651995E+02  0.296630E+01
 endloop
endfacet
facet normal  0.301197E+00 -0.227692E+00  0.925979E+00
 outer loop
  vertex  0.152066E+03  0.651995E+02  0.296630E+01
  vertex  0.149751E+03  0.651519E+02  0.370780E+01
  vertex  0.148828E+03  0.646601E+02  0.388700E+01
 endloop
endfacet
facet normal  0.437344E+00 -0.722724E+00  0.535164E+00
 outer loop
  vertex  0.151111E+03  0.646851E+02  0.310960E+01
  vertex  0.152725E+03  0.647027E+02  0.181390E+01
  vertex  0.153704E+03  0.652331E+02  0.173030E+01
 endloop
endfacet
facet normal  0.451841E+00 -0.677598E+00  0.580259E+00
 outer loop
  vertex  0.153704E+03  0.652331E+02  0.173020E+01
  vertex  0.152066E+03  0.651995E+02  0.296630E+01
  vertex  0.151111E+03  0.646850E+02  0.310960E+01
 endloop
endfacet
facet normal  0.471437E+00 -0.868001E+00  0.155958E+00
 outer loop
  vertex  0.152725E+03  0.647027E+02  0.181390E+01
  vertex  0.153337E+03  0.647094E+02  0.000000E+00
  vertex  0.154325E+03  0.652458E+02  0.000000E+00
 endloop
endfacet
facet normal  0.480760E+00 -0.860932E+00  0.166332E+00
 outer loop
  vertex  0.154325E+03  0.652457E+02  0.000000E+00
  vertex  0.153704E+03  0.652331E+02  0.173030E+01
  vertex  0.152725E+03  0.647026E+02  0.181380E+01
 endloop
endfacet
facet normal -0.322609E+00  0.940242E+00  0.108942E+00
 outer loop
  vertex  0.139867E+03  0.649492E+02  0.000000E+00
  vertex  0.140488E+03  0.649619E+02  0.173030E+01
  vertex  0.141154E+03  0.652040E+02  0.161210E+01
 endloop
endfacet
facet normal -0.328662E+00  0.937517E+00  0.114206E+00
 outer loop
  vertex  0.141154E+03  0.652040E+02  0.161210E+01
  vertex  0.140544E+03  0.651865E+02  0.000000E+00
  vertex  0.139867E+03  0.649492E+02  0.000000E+00
 endloop
endfacet
facet normal -0.261526E+00  0.909969E+00  0.321807E+00
 outer loop
  vertex  0.140488E+03  0.649619E+02  0.173030E+01
  vertex  0.142126E+03  0.649955E+02  0.296630E+01
  vertex  0.142763E+03  0.652502E+02  0.276360E+01
 endloop
endfacet
facet normal -0.268111E+00  0.901960E+00  0.338503E+00
 outer loop
  vertex  0.142763E+03  0.652501E+02  0.276360E+01
  vertex  0.141154E+03  0.652040E+02  0.161210E+01
  vertex  0.140488E+03  0.649618E+02  0.173020E+01
 endloop
endfacet
facet normal -0.176792E+00  0.849157E+00  0.497672E+00
 outer loop
  vertex  0.142126E+03  0.649955E+02  0.296630E+01
  vertex  0.144442E+03  0.650430E+02  0.370780E+01
  vertex  0.145038E+03  0.653155E+02  0.345450E+01
 endloop
endfacet
facet normal -0.177467E+00  0.844932E+00  0.504575E+00
 outer loop
  vertex  0.145038E+03  0.653154E+02  0.345440E+01
  vertex  0.142763E+03  0.652502E+02  0.276360E+01
  vertex  0.142126E+03  0.649954E+02  0.296630E+01
 endloop
endfacet
facet normal -0.766012E-01  0.749803E+00  0.657212E+00
 outer loop
  vertex  0.144442E+03  0.650430E+02  0.370780E+01
  vertex  0.147096E+03  0.650975E+02  0.395500E+01
  vertex  0.147645E+03  0.653904E+02  0.368480E+01
 endloop
endfacet
facet normal -0.784108E-01  0.765074E+00  0.639150E+00
 outer loop
  vertex  0.147645E+03  0.653904E+02  0.368470E+01
  vertex  0.145038E+03  0.653155E+02  0.345450E+01
  vertex  0.144442E+03  0.650429E+02  0.370770E+01
 endloop
endfacet
facet normal  0.652769E-01  0.561945E+00  0.824595E+00
 outer loop
  vertex  0.147096E+03  0.650975E+02  0.395500E+01
  vertex  0.149751E+03  0.651519E+02  0.370780E+01
  vertex  0.150252E+03  0.654653E+02  0.345450E+01
 endloop
endfacet
facet normal  0.510082E-01  0.623694E+00  0.780002E+00
 outer loop
  vertex  0.150252E+03  0.654653E+02  0.345440E+01
  vertex  0.147645E+03  0.653904E+02  0.368480E+01
  vertex  0.147096E+03  0.650975E+02  0.395490E+01
 endloop
endfacet
facet normal  0.297963E+00  0.161307E+00  0.940850E+00
 outer loop
  vertex  0.149751E+03  0.651519E+02  0.370780E+01
  vertex  0.152066E+03  0.651995E+02  0.296630E+01
  vertex  0.152527E+03  0.655306E+02  0.276360E+01
 endloop
endfacet
facet normal  0.268438E+00  0.307684E+00  0.912837E+00
 outer loop
  vertex  0.152527E+03  0.655306E+02  0.276360E+01
  vertex  0.150252E+03  0.654653E+02  0.345450E+01
  vertex  0.149751E+03  0.651519E+02  0.370770E+01
 endloop
endfacet
facet normal  0.546257E+00 -0.441469E+00  0.711835E+00
 outer loop
  vertex  0.152066E+03  0.651995E+02  0.296630E+01
  vertex  0.153704E+03  0.652331E+02  0.173030E+01
  vertex  0.154136E+03  0.655768E+02  0.161210E+01
 endloop
endfacet
facet normal  0.559617E+00 -0.307748E+00  0.769493E+00
 outer loop
  vertex  0.154136E+03  0.655767E+02  0.161210E+01
  vertex  0.152527E+03  0.655306E+02  0.276360E+01
  vertex  0.152066E+03  0.651995E+02  0.296630E+01
 endloop
endfacet
facet normal  0.622514E+00 -0.751640E+00  0.217976E+00
 outer loop
  vertex  0.153704E+03  0.652331E+02  0.173030E+01
  vertex  0.154325E+03  0.652458E+02  0.000000E+00
  vertex  0.154746E+03  0.655943E+02  0.000000E+00
 endloop
endfacet
facet normal  0.643876E+00 -0.727882E+00  0.235821E+00
 outer loop
  vertex  0.154746E+03  0.655942E+02  0.000000E+00
  vertex  0.154136E+03  0.655768E+02  0.161210E+01
  vertex  0.153704E+03  0.652331E+02  0.173020E+01
 endloop
endfacet
facet normal -0.151851E+00  0.987297E+00  0.467587E-01
 outer loop
  vertex  0.140544E+03  0.651865E+02  0.000000E+00
  vertex  0.141154E+03  0.652040E+02  0.161210E+01
  vertex  0.141645E+03  0.652860E+02  0.147650E+01
 endloop
endfacet
facet normal -0.150596E+00  0.987533E+00  0.458084E-01
 outer loop
  vertex  0.141645E+03  0.652860E+02  0.147650E+01
  vertex  0.141063E+03  0.652656E+02  0.000000E+00
  vertex  0.140544E+03  0.651865E+02  0.000000E+00
 endloop
endfacet
facet normal -0.130237E+00  0.981174E+00  0.142607E+00
 outer loop
  vertex  0.141154E+03  0.652040E+02  0.161210E+01
  vertex  0.142763E+03  0.652502E+02  0.276360E+01
  vertex  0.143183E+03  0.653397E+02  0.253120E+01
 endloop
endfacet
facet normal -0.126760E+00  0.982726E+00  0.134836E+00
 outer loop
  vertex  0.143183E+03  0.653396E+02  0.253110E+01
  vertex  0.141645E+03  0.652860E+02  0.147650E+01
  vertex  0.141154E+03  0.652040E+02  0.161210E+01
 endloop
endfacet
facet normal -0.970055E-01  0.968869E+00  0.227779E+00
 outer loop
  vertex  0.142763E+03  0.652502E+02  0.276360E+01
  vertex  0.145038E+03  0.653155E+02  0.345450E+01
  vertex  0.145356E+03  0.654157E+02  0.316400E+01
 endloop
endfacet
facet normal -0.939790E-01  0.974074E+00  0.205784E+00
 outer loop
  vertex  0.145356E+03  0.654157E+02  0.316400E+01
  vertex  0.143183E+03  0.653397E+02  0.253120E+01
  vertex  0.142763E+03  0.652501E+02  0.276360E+01
 endloop
endfacet
facet normal -0.545685E-01  0.949501E+00  0.308982E+00
 outer loop
  vertex  0.145038E+03  0.653155E+02  0.345450E+01
  vertex  0.147645E+03  0.653904E+02  0.368480E+01
  vertex  0.147848E+03  0.655029E+02  0.337490E+01
 endloop
endfacet
facet normal -0.564631E-01  0.961195E+00  0.270030E+00
 outer loop
  vertex  0.147848E+03  0.655028E+02  0.337490E+01
  vertex  0.145356E+03  0.654157E+02  0.316400E+01
  vertex  0.145038E+03  0.653154E+02  0.345440E+01
 endloop
endfacet
facet normal  0.866239E-02  0.917948E+00  0.396607E+00
 outer loop
  vertex  0.147645E+03  0.653904E+02  0.368480E+01
  vertex  0.150252E+03  0.654653E+02  0.345450E+01
  vertex  0.150339E+03  0.655900E+02  0.316400E+01
 endloop
endfacet
facet normal -0.416379E-02  0.940812E+00  0.338905E+00
 outer loop
  vertex  0.150339E+03  0.655899E+02  0.316400E+01
  vertex  0.147848E+03  0.655029E+02  0.337490E+01
  vertex  0.147645E+03  0.653904E+02  0.368470E+01
 endloop
endfacet
facet normal  0.125222E+00  0.860627E+00  0.493600E+00
 outer loop
  vertex  0.150252E+03  0.654653E+02  0.345450E+01
  vertex  0.152527E+03  0.655306E+02  0.276360E+01
  vertex  0.152512E+03  0.656660E+02  0.253120E+01
 endloop
endfacet
facet normal  0.892998E-01  0.905259E+00  0.415370E+00
 outer loop
  vertex  0.152512E+03  0.656660E+02  0.253110E+01
  vertex  0.150339E+03  0.655900E+02  0.316400E+01
  vertex  0.150252E+03  0.654653E+02  0.345440E+01
 endloop
endfacet
facet normal  0.372881E+00  0.746626E+00  0.550917E+00
 outer loop
  vertex  0.152527E+03  0.655306E+02  0.276360E+01
  vertex  0.154136E+03  0.655768E+02  0.161210E+01
  vertex  0.154050E+03  0.657198E+02  0.147650E+01
 endloop
endfacet
facet normal  0.291797E+00  0.834252E+00  0.467844E+00
 outer loop
  vertex  0.154050E+03  0.657198E+02  0.147650E+01
  vertex  0.152512E+03  0.656660E+02  0.253120E+01
  vertex  0.152527E+03  0.655306E+02  0.276360E+01
 endloop
endfacet
facet normal  0.755792E+00  0.585884E+00  0.292437E+00
 outer loop
  vertex  0.154136E+03  0.655768E+02  0.161210E+01
  vertex  0.154746E+03  0.655943E+02  0.000000E+00
  vertex  0.154633E+03  0.657402E+02  0.000000E+00
 endloop
endfacet
facet normal  0.683328E+00  0.674663E+00  0.279091E+00
 outer loop
  vertex  0.154633E+03  0.657401E+02  0.000000E+00
  vertex  0.154050E+03  0.657198E+02  0.147650E+01
  vertex  0.154136E+03  0.655767E+02  0.161210E+01
 endloop
endfacet
facet normal  0.231363E+00  0.967215E+00 -0.104717E+00
 outer loop
  vertex  0.141063E+03  0.652656E+02  0.000000E+00
  vertex  0.141645E+03  0.652860E+02  0.147650E+01
  vertex  0.141914E+03  0.652072E+02  0.134100E+01
 endloop
endfacet
facet normal  0.247399E+00  0.962058E+00 -0.115057E+00
 outer loop
  vertex  0.141914E+03  0.652071E+02  0.134090E+01
  vertex  0.141370E+03  0.651865E+02  0.000000E+00
  vertex  0.141063E+03  0.652656E+02  0.000000E+00
 endloop
endfacet
facet normal  0.126774E+00  0.963970E+00 -0.233859E+00
 outer loop
  vertex  0.141645E+03  0.652860E+02  0.147650E+01
  vertex  0.143183E+03  0.653397E+02  0.253120E+01
  vertex  0.143346E+03  0.652618E+02  0.229880E+01
 endloop
endfacet
facet normal  0.143729E+00  0.952264E+00 -0.269325E+00
 outer loop
  vertex  0.143346E+03  0.652618E+02  0.229870E+01
  vertex  0.141914E+03  0.652072E+02  0.134100E+01
  vertex  0.141645E+03  0.652860E+02  0.147650E+01
 endloop
endfacet
facet normal  0.398959E-01  0.966611E+00 -0.253123E+00
 outer loop
  vertex  0.143183E+03  0.653397E+02  0.253120E+01
  vertex  0.145356E+03  0.654157E+02  0.316400E+01
  vertex  0.145372E+03  0.653390E+02  0.287360E+01
 endloop
endfacet
facet normal  0.454139E-01  0.956453E+00 -0.288331E+00
 outer loop
  vertex  0.145372E+03  0.653389E+02  0.287360E+01
  vertex  0.143346E+03  0.652618E+02  0.229880E+01
  vertex  0.143183E+03  0.653396E+02  0.253110E+01
 endloop
endfacet
facet normal -0.146222E-01  0.973170E+00 -0.229622E+00
 outer loop
  vertex  0.145356E+03  0.654157E+02  0.316400E+01
  vertex  0.147848E+03  0.655029E+02  0.337490E+01
  vertex  0.147694E+03  0.654275E+02  0.306510E+01
 endloop
endfacet
facet normal -0.156809E-01  0.966508E+00 -0.256156E+00
 outer loop
  vertex  0.147694E+03  0.654274E+02  0.306500E+01
  vertex  0.145372E+03  0.653390E+02  0.287360E+01
  vertex  0.145356E+03  0.654157E+02  0.316400E+01
 endloop
endfacet
facet normal -0.506279E-01  0.979805E+00 -0.193440E+00
 outer loop
  vertex  0.147848E+03  0.655029E+02  0.337490E+01
  vertex  0.150339E+03  0.655900E+02  0.316400E+01
  vertex  0.150016E+03  0.655160E+02  0.287360E+01
 endloop
endfacet
facet normal -0.545043E-01  0.976115E+00 -0.210308E+00
 outer loop
  vertex  0.150016E+03  0.655159E+02  0.287360E+01
  vertex  0.147694E+03  0.654275E+02  0.306510E+01
  vertex  0.147848E+03  0.655028E+02  0.337490E+01
 endloop
endfacet
facet normal -0.782576E-01  0.985521E+00 -0.150413E+00
 outer loop
  vertex  0.150339E+03  0.655900E+02  0.316400E+01
  vertex  0.152512E+03  0.656660E+02  0.253120E+01
  vertex  0.152042E+03  0.655932E+02  0.229880E+01
 endloop
endfacet
facet normal -0.825366E-01  0.983870E+00 -0.158704E+00
 outer loop
  vertex  0.152042E+03  0.655932E+02  0.229870E+01
  vertex  0.150016E+03  0.655160E+02  0.287360E+01
  vertex  0.150339E+03  0.655899E+02  0.316400E+01
 endloop
endfacet
facet normal -0.101203E+00  0.990126E+00 -0.970019E-01
 outer loop
  vertex  0.152512E+03  0.656660E+02  0.253120E+01
  vertex  0.154050E+03  0.657198E+02  0.147650E+01
  vertex  0.153475E+03  0.656478E+02  0.134100E+01
 endloop
endfacet
facet normal -0.104115E+00  0.989583E+00 -0.994232E-01
 outer loop
  vertex  0.153475E+03  0.656477E+02  0.134090E+01
  vertex  0.152042E+03  0.655932E+02  0.229880E+01
  vertex  0.152512E+03  0.656660E+02  0.253110E+01
 endloop
endfacet
facet normal -0.115880E+00  0.992746E+00 -0.320517E-01
 outer loop
  vertex  0.154050E+03  0.657198E+02  0.147650E+01
  vertex  0.154633E+03  0.657402E+02  0.000000E+00
  vertex  0.154019E+03  0.656685E+02  0.000000E+00
 endloop
endfacet
facet normal -0.116856E+00  0.992632E+00 -0.320344E-01
 outer loop
  vertex  0.154019E+03  0.656685E+02  0.000000E+00
  vertex  0.153475E+03  0.656478E+02  0.134100E+01
  vertex  0.154050E+03  0.657198E+02  0.147650E+01
 endloop
endfacet
facet normal  0.912958E+00  0.166395E+00 -0.372587E+00
 outer loop
  vertex  0.141370E+03  0.651865E+02  0.000000E+00
  vertex  0.141914E+03  0.652072E+02  0.134100E+01
  vertex  0.141909E+03  0.649670E+02  0.122270E+01
 endloop
endfacet
facet normal  0.912717E+00  0.168851E+00 -0.372071E+00
 outer loop
  vertex  0.141909E+03  0.649670E+02  0.122260E+01
  vertex  0.141414E+03  0.649492E+02  0.000000E+00
  vertex  0.141370E+03  0.651865E+02  0.000000E+00
 endloop
endfacet
facet normal  0.507093E+00  0.367671E+00 -0.779535E+00
 outer loop
  vertex  0.141914E+03  0.652072E+02  0.134100E+01
  vertex  0.143346E+03  0.652618E+02  0.229880E+01
  vertex  0.143214E+03  0.650141E+02  0.209610E+01
 endloop
endfacet
facet normal  0.506629E+00  0.373136E+00 -0.777236E+00
 outer loop
  vertex  0.143214E+03  0.650140E+02  0.209610E+01
  vertex  0.141909E+03  0.649670E+02  0.122270E+01
  vertex  0.141914E+03  0.652071E+02  0.134090E+01
 endloop
endfacet
facet normal  0.209936E+00  0.543321E+00 -0.812852E+00
 outer loop
  vertex  0.143346E+03  0.652618E+02  0.229880E+01
  vertex  0.145372E+03  0.653390E+02  0.287360E+01
  vertex  0.145060E+03  0.650806E+02  0.262020E+01
 endloop
endfacet
facet normal  0.209856E+00  0.549577E+00 -0.808657E+00
 outer loop
  vertex  0.145060E+03  0.650805E+02  0.262010E+01
  vertex  0.143214E+03  0.650141E+02  0.209610E+01
  vertex  0.143346E+03  0.652618E+02  0.229870E+01
 endloop
endfacet
facet normal  0.354923E-01  0.671095E+00 -0.740521E+00
 outer loop
  vertex  0.145372E+03  0.653390E+02  0.287360E+01
  vertex  0.147694E+03  0.654275E+02  0.306510E+01
  vertex  0.147175E+03  0.651568E+02  0.279490E+01
 endloop
endfacet
facet normal  0.363021E-01  0.677131E+00 -0.734967E+00
 outer loop
  vertex  0.147175E+03  0.651567E+02  0.279480E+01
  vertex  0.145060E+03  0.650806E+02  0.262020E+01
  vertex  0.145372E+03  0.653389E+02  0.287360E+01
 endloop
endfacet
facet normal -0.813649E-01  0.772672E+00 -0.629569E+00
 outer loop
  vertex  0.147694E+03  0.654275E+02  0.306510E+01
  vertex  0.150016E+03  0.655160E+02  0.287360E+01
  vertex  0.149291E+03  0.652331E+02  0.262020E+01
 endloop
endfacet
facet normal -0.796519E-01  0.776594E+00 -0.624946E+00
 outer loop
  vertex  0.149291E+03  0.652331E+02  0.262010E+01
  vertex  0.147175E+03  0.651568E+02  0.279490E+01
  vertex  0.147694E+03  0.654274E+02  0.306500E+01
 endloop
endfacet
facet normal -0.169969E+00  0.858562E+00 -0.483717E+00
 outer loop
  vertex  0.150016E+03  0.655160E+02  0.287360E+01
  vertex  0.152042E+03  0.655932E+02  0.229880E+01
  vertex  0.151136E+03  0.652996E+02  0.209610E+01
 endloop
endfacet
facet normal -0.167521E+00  0.860688E+00 -0.480783E+00
 outer loop
  vertex  0.151136E+03  0.652995E+02  0.209610E+01
  vertex  0.149291E+03  0.652331E+02  0.262020E+01
  vertex  0.150016E+03  0.655159E+02  0.287360E+01
 endloop
endfacet
facet normal -0.235217E+00  0.924759E+00 -0.299154E+00
 outer loop
  vertex  0.152042E+03  0.655932E+02  0.229880E+01
  vertex  0.153475E+03  0.656478E+02  0.134100E+01
  vertex  0.152441E+03  0.653466E+02  0.122270E+01
 endloop
endfacet
facet normal -0.233121E+00  0.925481E+00 -0.298563E+00
 outer loop
  vertex  0.152441E+03  0.653466E+02  0.122260E+01
  vertex  0.151136E+03  0.652996E+02  0.209610E+01
  vertex  0.152042E+03  0.655932E+02  0.229870E+01
 endloop
endfacet
facet normal -0.269258E+00  0.958437E+00 -0.943302E-01
 outer loop
  vertex  0.153475E+03  0.656478E+02  0.134100E+01
  vertex  0.154019E+03  0.656685E+02  0.000000E+00
  vertex  0.152936E+03  0.653645E+02  0.000000E+00
 endloop
endfacet
facet normal -0.268434E+00  0.958638E+00 -0.946393E-01
 outer loop
  vertex  0.152936E+03  0.653645E+02  0.000000E+00
  vertex  0.152441E+03  0.653466E+02  0.122270E+01
  vertex  0.153475E+03  0.656477E+02  0.134090E+01
 endloop
endfacet
facet normal  0.770159E+00 -0.560916E+00 -0.303691E+00
 outer loop
  vertex  0.141414E+03  0.649492E+02  0.000000E+00
  vertex  0.141909E+03  0.649670E+02  0.122270E+01
  vertex  0.141583E+03  0.645648E+02  0.113910E+01
 endloop
endfacet
facet normal  0.785775E+00 -0.541201E+00 -0.299431E+00
 outer loop
  vertex  0.141583E+03  0.645647E+02  0.113900E+01
  vertex  0.141142E+03  0.645537E+02  0.000000E+00
  vertex  0.141414E+03  0.649492E+02  0.000000E+00
 endloop
endfacet
facet normal  0.533605E+00 -0.327322E+00 -0.779824E+00
 outer loop
  vertex  0.141909E+03  0.649670E+02  0.122270E+01
  vertex  0.143214E+03  0.650141E+02  0.209610E+01
  vertex  0.142747E+03  0.645942E+02  0.195280E+01
 endloop
endfacet
facet normal  0.553736E+00 -0.286349E+00 -0.781909E+00
 outer loop
  vertex  0.142747E+03  0.645942E+02  0.195280E+01
  vertex  0.141583E+03  0.645648E+02  0.113910E+01
  vertex  0.141909E+03  0.649670E+02  0.122260E+01
 endloop
endfacet
facet normal  0.273892E+00 -0.229260E-01 -0.961487E+00
 outer loop
  vertex  0.143214E+03  0.650141E+02  0.209610E+01
  vertex  0.145060E+03  0.650806E+02  0.262020E+01
  vertex  0.144393E+03  0.646358E+02  0.244100E+01
 endloop
endfacet
facet normal  0.284020E+00  0.113226E-01 -0.958751E+00
 outer loop
  vertex  0.144393E+03  0.646358E+02  0.244090E+01
  vertex  0.142747E+03  0.645942E+02  0.195280E+01
  vertex  0.143214E+03  0.650140E+02  0.209610E+01
 endloop
endfacet
facet normal  0.703801E-01  0.256328E+00 -0.964024E+00
 outer loop
  vertex  0.145060E+03  0.650806E+02  0.262020E+01
  vertex  0.147175E+03  0.651568E+02  0.279490E+01
  vertex  0.146280E+03  0.646834E+02  0.260370E+01
 endloop
endfacet
facet normal  0.757709E-01  0.272761E+00 -0.959094E+00
 outer loop
  vertex  0.146280E+03  0.646834E+02  0.260360E+01
  vertex  0.144393E+03  0.646358E+02  0.244100E+01
  vertex  0.145060E+03  0.650805E+02  0.262010E+01
 endloop
endfacet
facet normal -0.891020E-01  0.505711E+00 -0.858089E+00
 outer loop
  vertex  0.147175E+03  0.651568E+02  0.279490E+01
  vertex  0.149291E+03  0.652331E+02  0.262020E+01
  vertex  0.148167E+03  0.647311E+02  0.244100E+01
 endloop
endfacet
facet normal -0.867430E-01  0.509622E+00 -0.856015E+00
 outer loop
  vertex  0.148167E+03  0.647311E+02  0.244090E+01
  vertex  0.146280E+03  0.646834E+02  0.260370E+01
  vertex  0.147175E+03  0.651567E+02  0.279480E+01
 endloop
endfacet
facet normal -0.214072E+00  0.717626E+00 -0.662712E+00
 outer loop
  vertex  0.149291E+03  0.652331E+02  0.262020E+01
  vertex  0.151136E+03  0.652996E+02  0.209610E+01
  vertex  0.149813E+03  0.647727E+02  0.195280E+01
 endloop
endfacet
facet normal -0.214735E+00  0.717079E+00 -0.663089E+00
 outer loop
  vertex  0.149813E+03  0.647726E+02  0.195280E+01
  vertex  0.148167E+03  0.647311E+02  0.244100E+01
  vertex  0.149291E+03  0.652331E+02  0.262010E+01
 endloop
endfacet
facet normal -0.299250E+00  0.865995E+00 -0.400628E+00
 outer loop
  vertex  0.151136E+03  0.652996E+02  0.209610E+01
  vertex  0.152441E+03  0.653466E+02  0.122270E+01
  vertex  0.150978E+03  0.648021E+02  0.113910E+01
 endloop
endfacet
facet normal -0.301426E+00  0.865558E+00 -0.399938E+00
 outer loop
  vertex  0.150978E+03  0.648021E+02  0.113900E+01
  vertex  0.149813E+03  0.647727E+02  0.195280E+01
  vertex  0.151136E+03  0.652995E+02  0.209610E+01
 endloop
endfacet
facet normal -0.338902E+00  0.932671E+00 -0.123573E+00
 outer loop
  vertex  0.152441E+03  0.653466E+02  0.122270E+01
  vertex  0.152936E+03  0.653645E+02  0.000000E+00
  vertex  0.151419E+03  0.648132E+02  0.000000E+00
 endloop
endfacet
facet normal -0.339851E+00  0.932445E+00 -0.122666E+00
 outer loop
  vertex  0.151419E+03  0.648132E+02  0.000000E+00
  vertex  0.150978E+03  0.648021E+02  0.113910E+01
  vertex  0.152441E+03  0.653466E+02  0.122260E+01
 endloop
endfacet
facet normal  0.618930E+00 -0.750203E+00 -0.232640E+00
 outer loop
  vertex  0.141142E+03  0.645537E+02  0.000000E+00
  vertex  0.141583E+03  0.645648E+02  0.113910E+01
  vertex  0.140887E+03  0.640000E+02  0.110740E+01
 endloop
endfacet
facet normal  0.636974E+00 -0.738092E+00 -0.222451E+00
 outer loop
  vertex  0.140887E+03  0.640000E+02  0.110730E+01
  vertex  0.140500E+03  0.640000E+02  0.000000E+00
  vertex  0.141142E+03  0.645537E+02  0.000000E+00
 endloop
endfacet
facet normal  0.467404E+00 -0.602467E+00 -0.646967E+00
 outer loop
  vertex  0.141583E+03  0.645648E+02  0.113910E+01
  vertex  0.142747E+03  0.645942E+02  0.195280E+01
  vertex  0.141906E+03  0.640000E+02  0.189840E+01
 endloop
endfacet
facet normal  0.499365E+00 -0.579900E+00 -0.643701E+00
 outer loop
  vertex  0.141906E+03  0.640000E+02  0.189830E+01
  vertex  0.140887E+03  0.640000E+02  0.110740E+01
  vertex  0.141583E+03  0.645647E+02  0.113900E+01
 endloop
endfacet
facet normal  0.274038E+00 -0.355209E+00 -0.893717E+00
 outer loop
  vertex  0.142747E+03  0.645942E+02  0.195280E+01
  vertex  0.144393E+03  0.646358E+02  0.244100E+01
  vertex  0.143348E+03  0.640000E+02  0.237300E+01
 endloop
endfacet
facet normal  0.294620E+00 -0.335159E+00 -0.894912E+00
 outer loop
  vertex  0.143348E+03  0.640000E+02  0.237290E+01
  vertex  0.141906E+03  0.640000E+02  0.189840E+01
  vertex  0.142747E+03  0.645942E+02  0.195280E+01
 endloop
endfacet
facet normal  0.872127E-01 -0.578942E-01 -0.994506E+00
 outer loop
  vertex  0.144393E+03  0.646358E+02  0.244100E+01
  vertex  0.146280E+03  0.646834E+02  0.260370E+01
  vertex  0.145000E+03  0.640000E+02  0.253120E+01
 endloop
endfacet
facet normal  0.951233E-01 -0.502902E-01 -0.994194E+00
 outer loop
  vertex  0.145000E+03  0.640000E+02  0.253110E+01
  vertex  0.143348E+03  0.640000E+02  0.237300E+01
  vertex  0.144393E+03  0.646358E+02  0.244090E+01
 endloop
endfacet
facet normal -0.894930E-01  0.274498E+00 -0.957414E+00
 outer loop
  vertex  0.146280E+03  0.646834E+02  0.260370E+01
  vertex  0.148167E+03  0.647311E+02  0.244100E+01
  vertex  0.146652E+03  0.640000E+02  0.237300E+01
 endloop
endfacet
facet normal -0.917430E-01  0.273316E+00 -0.957539E+00
 outer loop
  vertex  0.146652E+03  0.640000E+02  0.237290E+01
  vertex  0.145000E+03  0.640000E+02  0.253120E+01
  vertex  0.146280E+03  0.646834E+02  0.260360E+01
 endloop
endfacet
facet normal -0.242537E+00  0.593797E+00 -0.767190E+00
 outer loop
  vertex  0.148167E+03  0.647311E+02  0.244100E+01
  vertex  0.149813E+03  0.647727E+02  0.195280E+01
  vertex  0.148094E+03  0.640000E+02  0.189840E+01
 endloop
endfacet
facet normal -0.251882E+00  0.592953E+00 -0.764828E+00
 outer loop
  vertex  0.148094E+03  0.640000E+02  0.189830E+01
  vertex  0.146652E+03  0.640000E+02  0.237300E+01
  vertex  0.148167E+03  0.647311E+02  0.244090E+01
 endloop
endfacet
facet normal -0.343781E+00  0.817353E+00 -0.462329E+00
 outer loop
  vertex  0.149813E+03  0.647727E+02  0.195280E+01
  vertex  0.150978E+03  0.648021E+02  0.113910E+01
  vertex  0.149113E+03  0.640000E+02  0.110740E+01
 endloop
endfacet
facet normal -0.352949E+00  0.817642E+00 -0.454850E+00
 outer loop
  vertex  0.149113E+03  0.640000E+02  0.110730E+01
  vertex  0.148094E+03  0.640000E+02  0.189840E+01
  vertex  0.149813E+03  0.647726E+02  0.195280E+01
 endloop
endfacet
facet normal -0.386234E+00  0.911579E+00 -0.140882E+00
 outer loop
  vertex  0.150978E+03  0.648021E+02  0.113910E+01
  vertex  0.151419E+03  0.648132E+02  0.000000E+00
  vertex  0.149500E+03  0.640000E+02  0.000000E+00
 endloop
endfacet
facet normal -0.389576E+00  0.910887E+00 -0.136072E+00
 outer loop
  vertex  0.149500E+03  0.640000E+02  0.000000E+00
  vertex  0.149113E+03  0.640000E+02  0.110740E+01
  vertex  0.150978E+03  0.648021E+02  0.113900E+01
 endloop
endfacet
facet normal  0.572197E-01  0.998346E+00  0.557362E-02
 outer loop
  vertex  0.825736E+02  0.805783E+02  0.105840E+01
  vertex  0.826767E+02  0.805783E+02  0.000000E+00
  vertex  0.775000E+02  0.808750E+02  0.000000E+00
 endloop
endfacet
facet normal  0.549120E-01  0.998353E+00  0.166324E-01
 outer loop
  vertex  0.822772E+02  0.805783E+02  0.203730E+01
  vertex  0.825737E+02  0.805783E+02  0.105840E+01
  vertex  0.775000E+02  0.808750E+02  0.000000E+00
 endloop
endfacet
facet normal  0.504880E-01  0.998360E+00  0.270046E-01
 outer loop
  vertex  0.818065E+02  0.805783E+02  0.291750E+01
  vertex  0.822773E+02  0.805783E+02  0.203730E+01
  vertex  0.775000E+02  0.808750E+02  0.000000E+00
 endloop
endfacet
facet normal  0.441935E-01  0.998363E+00  0.362950E-01
 outer loop
  vertex  0.811802E+02  0.805783E+02  0.368020E+01
  vertex  0.818065E+02  0.805783E+02  0.291760E+01
  vertex  0.775000E+02  0.808750E+02  0.000000E+00
 endloop
endfacet
facet normal  0.362851E-01  0.998364E+00  0.442013E-01
 outer loop
  vertex  0.804176E+02  0.805783E+02  0.430640E+01
  vertex  0.811803E+02  0.805783E+02  0.368030E+01
  vertex  0.775000E+02  0.808750E+02  0.000000E+00
 endloop
endfacet
facet normal  0.269981E-01  0.998359E+00  0.504918E-01
 outer loop
  vertex  0.795373E+02  0.805783E+02  0.477720E+01
  vertex  0.804176E+02  0.805783E+02  0.430650E+01
  vertex  0.775000E+02  0.808750E+02  0.000000E+00
 endloop
endfacet
facet normal  0.166222E-01  0.998353E+00  0.549152E-01
 outer loop
  vertex  0.785584E+02  0.805783E+02  0.507360E+01
  vertex  0.795373E+02  0.805783E+02  0.477730E+01
  vertex  0.775000E+02  0.808750E+02  0.000000E+00
 endloop
endfacet
facet normal  0.556842E-02  0.998346E+00  0.572196E-01
 outer loop
  vertex  0.775000E+02  0.805783E+02  0.517670E+01
  vertex  0.785584E+02  0.805783E+02  0.507370E+01
  vertex  0.775000E+02  0.808750E+02  0.000000E+00
 endloop
endfacet
facet normal  0.309785E+00  0.950329E+00  0.301463E-01
 outer loop
  vertex  0.826767E+02  0.805783E+02  0.000000E+00
  vertex  0.825737E+02  0.805783E+02  0.105840E+01
  vertex  0.850115E+02  0.797675E+02  0.156700E+01
 endloop
endfacet
facet normal  0.309772E+00  0.950332E+00  0.301673E-01
 outer loop
  vertex  0.850114E+02  0.797675E+02  0.156700E+01
  vertex  0.851640E+02  0.797675E+02  0.000000E+00
  vertex  0.826766E+02  0.805783E+02  0.000000E+00
 endloop
endfacet
facet normal  0.297354E+00  0.950513E+00  0.900361E-01
 outer loop
  vertex  0.825737E+02  0.805783E+02  0.105840E+01
  vertex  0.822773E+02  0.805783E+02  0.203730E+01
  vertex  0.845727E+02  0.797675E+02  0.301610E+01
 endloop
endfacet
facet normal  0.297339E+00  0.950517E+00  0.900424E-01
 outer loop
  vertex  0.845727E+02  0.797675E+02  0.301600E+01
  vertex  0.850115E+02  0.797675E+02  0.156700E+01
  vertex  0.825736E+02  0.805783E+02  0.105840E+01
 endloop
endfacet
facet normal  0.273455E+00  0.950702E+00  0.146247E+00
 outer loop
  vertex  0.822773E+02  0.805783E+02  0.203730E+01
  vertex  0.818065E+02  0.805783E+02  0.291760E+01
  vertex  0.838757E+02  0.797675E+02  0.431930E+01
 endloop
endfacet
facet normal  0.273441E+00  0.950706E+00  0.146246E+00
 outer loop
  vertex  0.838757E+02  0.797675E+02  0.431930E+01
  vertex  0.845727E+02  0.797675E+02  0.301610E+01
  vertex  0.822772E+02  0.805783E+02  0.203730E+01
 endloop
endfacet
facet normal  0.239405E+00  0.950815E+00  0.196561E+00
 outer loop
  vertex  0.818065E+02  0.805783E+02  0.291760E+01
  vertex  0.811803E+02  0.805783E+02  0.368030E+01
  vertex  0.829486E+02  0.797675E+02  0.544860E+01
 endloop
endfacet
facet normal  0.239408E+00  0.950815E+00  0.196560E+00
 outer loop
  vertex  0.829486E+02  0.797675E+02  0.544850E+01
  vertex  0.838757E+02  0.797675E+02  0.431930E+01
  vertex  0.818065E+02  0.805783E+02  0.291750E+01
 endloop
endfacet
facet normal  0.196566E+00  0.950812E+00  0.239412E+00
 outer loop
  vertex  0.811803E+02  0.805783E+02  0.368030E+01
  vertex  0.804176E+02  0.805783E+02  0.430650E+01
  vertex  0.818193E+02  0.797675E+02  0.637570E+01
 endloop
endfacet
facet normal  0.196518E+00  0.950819E+00  0.239426E+00
 outer loop
  vertex  0.818192E+02  0.797675E+02  0.637560E+01
  vertex  0.829486E+02  0.797675E+02  0.544860E+01
  vertex  0.811802E+02  0.805783E+02  0.368020E+01
 endloop
endfacet
facet normal  0.146247E+00  0.950703E+00  0.273452E+00
 outer loop
  vertex  0.804176E+02  0.805783E+02  0.430650E+01
  vertex  0.795373E+02  0.805783E+02  0.477730E+01
  vertex  0.805161E+02  0.797675E+02  0.707270E+01
 endloop
endfacet
facet normal  0.146239E+00  0.950705E+00  0.273449E+00
 outer loop
  vertex  0.805160E+02  0.797675E+02  0.707270E+01
  vertex  0.818193E+02  0.797675E+02  0.637570E+01
  vertex  0.804176E+02  0.805783E+02  0.430640E+01
 endloop
endfacet
facet normal  0.900350E-01  0.950513E+00  0.297351E+00
 outer loop
  vertex  0.795373E+02  0.805783E+02  0.477730E+01
  vertex  0.785584E+02  0.805783E+02  0.507370E+01
  vertex  0.790670E+02  0.797675E+02  0.751150E+01
 endloop
endfacet
facet normal  0.900197E-01  0.950516E+00  0.297349E+00
 outer loop
  vertex  0.790670E+02  0.797675E+02  0.751140E+01
  vertex  0.805161E+02  0.797675E+02  0.707270E+01
  vertex  0.795373E+02  0.805783E+02  0.477720E+01
 endloop
endfacet
facet normal  0.301471E-01  0.950329E+00  0.309784E+00
 outer loop
  vertex  0.785584E+02  0.805783E+02  0.507370E+01
  vertex  0.775000E+02  0.805783E+02  0.517670E+01
  vertex  0.775000E+02  0.797675E+02  0.766400E+01
 endloop
endfacet
facet normal  0.301470E-01  0.950333E+00  0.309773E+00
 outer loop
  vertex  0.775000E+02  0.797675E+02  0.766400E+01
  vertex  0.790670E+02  0.797675E+02  0.751150E+01
  vertex  0.785584E+02  0.805783E+02  0.507360E+01
 endloop
endfacet
facet normal  0.924477E+00  0.370470E+00  0.899721E-01
 outer loop
  vertex  0.851640E+02  0.797675E+02  0.000000E+00
  vertex  0.850115E+02  0.797675E+02  0.156700E+01
  vertex  0.854853E+02  0.785612E+02  0.166570E+01
 endloop
endfacet
facet normal  0.924474E+00  0.370463E+00  0.900279E-01
 outer loop
  vertex  0.854852E+02  0.785612E+02  0.166560E+01
  vertex  0.856474E+02  0.785612E+02  0.000000E+00
  vertex  0.851640E+02  0.797675E+02  0.000000E+00
 endloop
endfacet
facet normal  0.888750E+00  0.371077E+00  0.269119E+00
 outer loop
  vertex  0.850115E+02  0.797675E+02  0.156700E+01
  vertex  0.845727E+02  0.797675E+02  0.301610E+01
  vertex  0.850188E+02  0.785612E+02  0.320620E+01
 endloop
endfacet
facet normal  0.888696E+00  0.371154E+00  0.269193E+00
 outer loop
  vertex  0.850187E+02  0.785612E+02  0.320610E+01
  vertex  0.854853E+02  0.785612E+02  0.166570E+01
  vertex  0.850114E+02  0.797675E+02  0.156700E+01
 endloop
endfacet
facet normal  0.818642E+00  0.371648E+00  0.437839E+00
 outer loop
  vertex  0.845727E+02  0.797675E+02  0.301610E+01
  vertex  0.838757E+02  0.797675E+02  0.431930E+01
  vertex  0.842777E+02  0.785612E+02  0.459160E+01
 endloop
endfacet
facet normal  0.818558E+00  0.371754E+00  0.437906E+00
 outer loop
  vertex  0.842777E+02  0.785612E+02  0.459150E+01
  vertex  0.850188E+02  0.785612E+02  0.320620E+01
  vertex  0.845727E+02  0.797675E+02  0.301600E+01
 endloop
endfacet
facet normal  0.717435E+00  0.372008E+00  0.588980E+00
 outer loop
  vertex  0.838757E+02  0.797675E+02  0.431930E+01
  vertex  0.829486E+02  0.797675E+02  0.544860E+01
  vertex  0.832921E+02  0.785612E+02  0.579210E+01
 endloop
endfacet
facet normal  0.717360E+00  0.372030E+00  0.589057E+00
 outer loop
  vertex  0.832920E+02  0.785612E+02  0.579200E+01
  vertex  0.842777E+02  0.785612E+02  0.459160E+01
  vertex  0.838757E+02  0.797675E+02  0.431930E+01
 endloop
endfacet
facet normal  0.588972E+00  0.372033E+00  0.717428E+00
 outer loop
  vertex  0.829486E+02  0.797675E+02  0.544860E+01
  vertex  0.818193E+02  0.797675E+02  0.637570E+01
  vertex  0.820916E+02  0.785612E+02  0.677770E+01
 endloop
endfacet
facet normal  0.588919E+00  0.372057E+00  0.717459E+00
 outer loop
  vertex  0.820915E+02  0.785612E+02  0.677760E+01
  vertex  0.832921E+02  0.785612E+02  0.579210E+01
  vertex  0.829486E+02  0.797675E+02  0.544850E+01
 endloop
endfacet
facet normal  0.437825E+00  0.371728E+00  0.818613E+00
 outer loop
  vertex  0.818193E+02  0.797675E+02  0.637570E+01
  vertex  0.805161E+02  0.797675E+02  0.707270E+01
  vertex  0.807062E+02  0.785612E+02  0.751880E+01
 endloop
endfacet
facet normal  0.437816E+00  0.371737E+00  0.818614E+00
 outer loop
  vertex  0.807061E+02  0.785612E+02  0.751870E+01
  vertex  0.820916E+02  0.785612E+02  0.677770E+01
  vertex  0.818192E+02  0.797675E+02  0.637560E+01
 endloop
endfacet
facet normal  0.269120E+00  0.371093E+00  0.888743E+00
 outer loop
  vertex  0.805161E+02  0.797675E+02  0.707270E+01
  vertex  0.790670E+02  0.797675E+02  0.751150E+01
  vertex  0.791657E+02  0.785612E+02  0.798530E+01
 endloop
endfacet
facet normal  0.269132E+00  0.371098E+00  0.888738E+00
 outer loop
  vertex  0.791657E+02  0.785612E+02  0.798530E+01
  vertex  0.807062E+02  0.785612E+02  0.751880E+01
  vertex  0.805160E+02  0.797675E+02  0.707270E+01
 endloop
endfacet
facet normal  0.899700E-01  0.370466E+00  0.924478E+00
 outer loop
  vertex  0.790670E+02  0.797675E+02  0.751150E+01
  vertex  0.775000E+02  0.797675E+02  0.766400E+01
  vertex  0.775000E+02  0.785612E+02  0.814740E+01
 endloop
endfacet
facet normal  0.899091E-01  0.370534E+00  0.924457E+00
 outer loop
  vertex  0.775000E+02  0.785612E+02  0.814730E+01
  vertex  0.791657E+02  0.785612E+02  0.798530E+01
  vertex  0.790670E+02  0.797675E+02  0.751140E+01
 endloop
endfacet
facet normal  0.868260E+00 -0.488861E+00  0.844969E-01
 outer loop
  vertex  0.856474E+02  0.785612E+02  0.000000E+00
  vertex  0.854853E+02  0.785612E+02  0.166570E+01
  vertex  0.846669E+02  0.770781E+02  0.149470E+01
 endloop
endfacet
facet normal  0.868313E+00 -0.488752E+00  0.845884E-01
 outer loop
  vertex  0.846669E+02  0.770781E+02  0.149460E+01
  vertex  0.848125E+02  0.770781E+02  0.000000E+00
  vertex  0.856473E+02  0.785612E+02  0.000000E+00
 endloop
endfacet
facet normal  0.834473E+00 -0.489693E+00  0.252698E+00
 outer loop
  vertex  0.854853E+02  0.785612E+02  0.166570E+01
  vertex  0.850188E+02  0.785612E+02  0.320620E+01
  vertex  0.842481E+02  0.770781E+02  0.287720E+01
 endloop
endfacet
facet normal  0.834509E+00 -0.489571E+00  0.252816E+00
 outer loop
  vertex  0.842481E+02  0.770781E+02  0.287710E+01
  vertex  0.846669E+02  0.770781E+02  0.149470E+01
  vertex  0.854852E+02  0.785612E+02  0.166560E+01
 endloop
endfacet
facet normal  0.768399E+00 -0.490517E+00  0.411042E+00
 outer loop
  vertex  0.850188E+02  0.785612E+02  0.320620E+01
  vertex  0.842777E+02  0.785612E+02  0.459160E+01
  vertex  0.835829E+02  0.770781E+02  0.412060E+01
 endloop
endfacet
facet normal  0.768426E+00 -0.490430E+00  0.411096E+00
 outer loop
  vertex  0.835829E+02  0.770781E+02  0.412060E+01
  vertex  0.842481E+02  0.770781E+02  0.287720E+01
  vertex  0.850187E+02  0.785612E+02  0.320610E+01
 endloop
endfacet
facet normal  0.673316E+00 -0.490988E+00  0.552789E+00
 outer loop
  vertex  0.842777E+02  0.785612E+02  0.459160E+01
  vertex  0.832921E+02  0.785612E+02  0.579210E+01
  vertex  0.826982E+02  0.770781E+02  0.519820E+01
 endloop
endfacet
facet normal  0.673299E+00 -0.490958E+00  0.552837E+00
 outer loop
  vertex  0.826981E+02  0.770781E+02  0.519820E+01
  vertex  0.835829E+02  0.770781E+02  0.412060E+01
  vertex  0.842777E+02  0.785612E+02  0.459150E+01
 endloop
endfacet
facet normal  0.552788E+00 -0.490988E+00  0.673318E+00
 outer loop
  vertex  0.832921E+02  0.785612E+02  0.579210E+01
  vertex  0.820916E+02  0.785612E+02  0.677770E+01
  vertex  0.816206E+02  0.770781E+02  0.608290E+01
 endloop
endfacet
facet normal  0.552781E+00 -0.490924E+00  0.673370E+00
 outer loop
  vertex  0.816205E+02  0.770781E+02  0.608290E+01
  vertex  0.826982E+02  0.770781E+02  0.519820E+01
  vertex  0.832920E+02  0.785612E+02  0.579200E+01
 endloop
endfacet
facet normal  0.411050E+00 -0.490493E+00  0.768410E+00
 outer loop
  vertex  0.820916E+02  0.785612E+02  0.677770E+01
  vertex  0.807062E+02  0.785612E+02  0.751880E+01
  vertex  0.803772E+02  0.770781E+02  0.674810E+01
 endloop
endfacet
facet normal  0.411016E+00 -0.490454E+00  0.768453E+00
 outer loop
  vertex  0.803771E+02  0.770781E+02  0.674800E+01
  vertex  0.816206E+02  0.770781E+02  0.608290E+01
  vertex  0.820915E+02  0.785612E+02  0.677760E+01
 endloop
endfacet
facet normal  0.252709E+00 -0.489632E+00  0.834505E+00
 outer loop
  vertex  0.807062E+02  0.785612E+02  0.751880E+01
  vertex  0.791657E+02  0.785612E+02  0.798530E+01
  vertex  0.789947E+02  0.770781E+02  0.716690E+01
 endloop
endfacet
facet normal  0.252771E+00 -0.489642E+00  0.834481E+00
 outer loop
  vertex  0.789946E+02  0.770781E+02  0.716690E+01
  vertex  0.803772E+02  0.770781E+02  0.674810E+01
  vertex  0.807061E+02  0.785612E+02  0.751870E+01
 endloop
endfacet
facet normal  0.844967E-01 -0.488844E+00  0.868270E+00
 outer loop
  vertex  0.791657E+02  0.785612E+02  0.798530E+01
  vertex  0.775000E+02  0.785612E+02  0.814740E+01
  vertex  0.775000E+02  0.770781E+02  0.731240E+01
 endloop
endfacet
facet normal  0.844623E-01 -0.488861E+00  0.868263E+00
 outer loop
  vertex  0.775000E+02  0.770781E+02  0.731230E+01
  vertex  0.789947E+02  0.770781E+02  0.716690E+01
  vertex  0.791657E+02  0.785612E+02  0.798530E+01
 endloop
endfacet
facet normal  0.743454E+00 -0.664854E+00  0.724202E-01
 outer loop
  vertex  0.848125E+02  0.770781E+02  0.000000E+00
  vertex  0.846669E+02  0.770781E+02  0.149470E+01
  vertex  0.832283E+02  0.754367E+02  0.119420E+01
 endloop
endfacet
facet normal  0.743471E+00 -0.664836E+00  0.724128E-01
 outer loop
  vertex  0.832283E+02  0.754366E+02  0.119420E+01
  vertex  0.833447E+02  0.754367E+02  0.000000E+00
  vertex  0.848125E+02  0.770781E+02  0.000000E+00
 endloop
endfacet
facet normal  0.714201E+00 -0.665664E+00  0.216353E+00
 outer loop
  vertex  0.846669E+02  0.770781E+02  0.149470E+01
  vertex  0.842481E+02  0.770781E+02  0.287720E+01
  vertex  0.828934E+02  0.754367E+02  0.229900E+01
 endloop
endfacet
facet normal  0.714233E+00 -0.665599E+00  0.216447E+00
 outer loop
  vertex  0.828934E+02  0.754366E+02  0.229900E+01
  vertex  0.832283E+02  0.754367E+02  0.119420E+01
  vertex  0.846669E+02  0.770781E+02  0.149460E+01
 endloop
endfacet
facet normal  0.657347E+00 -0.666500E+00  0.351670E+00
 outer loop
  vertex  0.842481E+02  0.770781E+02  0.287720E+01
  vertex  0.835829E+02  0.770781E+02  0.412060E+01
  vertex  0.823615E+02  0.754367E+02  0.329280E+01
 endloop
endfacet
facet normal  0.657350E+00 -0.666432E+00  0.351794E+00
 outer loop
  vertex  0.823615E+02  0.754366E+02  0.329270E+01
  vertex  0.828934E+02  0.754367E+02  0.229900E+01
  vertex  0.842481E+02  0.770781E+02  0.287710E+01
 endloop
endfacet
facet normal  0.575862E+00 -0.666979E+00  0.472780E+00
 outer loop
  vertex  0.835829E+02  0.770781E+02  0.412060E+01
  vertex  0.826982E+02  0.770781E+02  0.519820E+01
  vertex  0.816542E+02  0.754367E+02  0.415420E+01
 endloop
endfacet
facet normal  0.575849E+00 -0.666958E+00  0.472826E+00
 outer loop
  vertex  0.816541E+02  0.754366E+02  0.415420E+01
  vertex  0.823615E+02  0.754367E+02  0.329280E+01
  vertex  0.835829E+02  0.770781E+02  0.412060E+01
 endloop
endfacet
facet normal  0.472790E+00 -0.666960E+00  0.575877E+00
 outer loop
  vertex  0.826982E+02  0.770781E+02  0.519820E+01
  vertex  0.816206E+02  0.770781E+02  0.608290E+01
  vertex  0.807928E+02  0.754367E+02  0.486150E+01
 endloop
endfacet
facet normal  0.472832E+00 -0.666966E+00  0.575835E+00
 outer loop
  vertex  0.807928E+02  0.754366E+02  0.486140E+01
  vertex  0.816542E+02  0.754367E+02  0.415420E+01
  vertex  0.826981E+02  0.770781E+02  0.519820E+01
 endloop
endfacet
facet normal  0.351692E+00 -0.666448E+00  0.657388E+00
 outer loop
  vertex  0.816206E+02  0.770781E+02  0.608290E+01
  vertex  0.803772E+02  0.770781E+02  0.674810E+01
  vertex  0.797990E+02  0.754367E+02  0.539340E+01
 endloop
endfacet
facet normal  0.351843E+00 -0.666499E+00  0.657256E+00
 outer loop
  vertex  0.797990E+02  0.754366E+02  0.539340E+01
  vertex  0.807928E+02  0.754367E+02  0.486150E+01
  vertex  0.816205E+02  0.770781E+02  0.608290E+01
 endloop
endfacet
facet normal  0.216367E+00 -0.665610E+00  0.714247E+00
 outer loop
  vertex  0.803772E+02  0.770781E+02  0.674810E+01
  vertex  0.789947E+02  0.770781E+02  0.716690E+01
  vertex  0.786942E+02  0.754367E+02  0.572830E+01
 endloop
endfacet
facet normal  0.216527E+00 -0.665642E+00  0.714169E+00
 outer loop
  vertex  0.786941E+02  0.754366E+02  0.572830E+01
  vertex  0.797990E+02  0.754367E+02  0.539340E+01
  vertex  0.803771E+02  0.770781E+02  0.674800E+01
 endloop
endfacet
facet normal  0.723747E-01 -0.664814E+00  0.743495E+00
 outer loop
  vertex  0.789947E+02  0.770781E+02  0.716690E+01
  vertex  0.775000E+02  0.770781E+02  0.731240E+01
  vertex  0.775000E+02  0.754367E+02  0.584470E+01
 endloop
endfacet
facet normal  0.724580E-01 -0.664854E+00  0.743450E+00
 outer loop
  vertex  0.775000E+02  0.754366E+02  0.584460E+01
  vertex  0.786942E+02  0.754367E+02  0.572830E+01
  vertex  0.789946E+02  0.770781E+02  0.716690E+01
 endloop
endfacet
facet normal  0.762847E+00 -0.642290E+00  0.743566E-01
 outer loop
  vertex  0.833447E+02  0.754367E+02  0.000000E+00
  vertex  0.832283E+02  0.754367E+02  0.119420E+01
  vertex  0.818413E+02  0.737558E+02  0.904300E+00
 endloop
endfacet
facet normal  0.762859E+00 -0.642266E+00  0.744291E-01
 outer loop
  vertex  0.818413E+02  0.737557E+02  0.904200E+00
  vertex  0.819296E+02  0.737558E+02  0.000000E+00
  vertex  0.833447E+02  0.754366E+02  0.000000E+00
 endloop
endfacet
facet normal  0.732806E+00 -0.643156E+00  0.222137E+00
 outer loop
  vertex  0.832283E+02  0.754367E+02  0.119420E+01
  vertex  0.828934E+02  0.754367E+02  0.229900E+01
  vertex  0.815872E+02  0.737558E+02  0.174130E+01
 endloop
endfacet
facet normal  0.732776E+00 -0.643065E+00  0.222501E+00
 outer loop
  vertex  0.815871E+02  0.737557E+02  0.174120E+01
  vertex  0.818413E+02  0.737558E+02  0.904300E+00
  vertex  0.832283E+02  0.754366E+02  0.119420E+01
 endloop
endfacet
facet normal  0.674474E+00 -0.644027E+00  0.360990E+00
 outer loop
  vertex  0.828934E+02  0.754367E+02  0.229900E+01
  vertex  0.823615E+02  0.754367E+02  0.329280E+01
  vertex  0.811838E+02  0.737558E+02  0.249440E+01
 endloop
endfacet
facet normal  0.674400E+00 -0.643962E+00  0.361245E+00
 outer loop
  vertex  0.811837E+02  0.737557E+02  0.249440E+01
  vertex  0.815872E+02  0.737558E+02  0.174130E+01
  vertex  0.828934E+02  0.754366E+02  0.229900E+01
 endloop
endfacet
facet normal  0.590897E+00 -0.644538E+00  0.485192E+00
 outer loop
  vertex  0.823615E+02  0.754367E+02  0.329280E+01
  vertex  0.816542E+02  0.754367E+02  0.415420E+01
  vertex  0.806474E+02  0.737558E+02  0.314740E+01
 endloop
endfacet
facet normal  0.590800E+00 -0.644491E+00  0.485373E+00
 outer loop
  vertex  0.806473E+02  0.737557E+02  0.314730E+01
  vertex  0.811838E+02  0.737558E+02  0.249440E+01
  vertex  0.823615E+02  0.754366E+02  0.329270E+01
 endloop
endfacet
facet normal  0.485215E+00 -0.644494E+00  0.590927E+00
 outer loop
  vertex  0.816542E+02  0.754367E+02  0.415420E+01
  vertex  0.807928E+02  0.754367E+02  0.486150E+01
  vertex  0.799944E+02  0.737558E+02  0.368380E+01
 endloop
endfacet
facet normal  0.485305E+00 -0.644552E+00  0.590789E+00
 outer loop
  vertex  0.799944E+02  0.737557E+02  0.368370E+01
  vertex  0.806474E+02  0.737558E+02  0.314740E+01
  vertex  0.816541E+02  0.754366E+02  0.415420E+01
 endloop
endfacet
facet normal  0.361023E+00 -0.643949E+00  0.674531E+00
 outer loop
  vertex  0.807928E+02  0.754367E+02  0.486150E+01
  vertex  0.797990E+02  0.754367E+02  0.539340E+01
  vertex  0.792413E+02  0.737558E+02  0.408720E+01
 endloop
endfacet
facet normal  0.361279E+00 -0.644042E+00  0.674305E+00
 outer loop
  vertex  0.792413E+02  0.737557E+02  0.408720E+01
  vertex  0.799944E+02  0.737558E+02  0.368380E+01
  vertex  0.807928E+02  0.754366E+02  0.486140E+01
 endloop
endfacet
facet normal  0.222160E+00 -0.643058E+00  0.732886E+00
 outer loop
  vertex  0.797990E+02  0.754367E+02  0.539340E+01
  vertex  0.786942E+02  0.754367E+02  0.572830E+01
  vertex  0.784043E+02  0.737558E+02  0.434130E+01
 endloop
endfacet
facet normal  0.222475E+00 -0.643197E+00  0.732668E+00
 outer loop
  vertex  0.784042E+02  0.737557E+02  0.434130E+01
  vertex  0.792413E+02  0.737558E+02  0.408720E+01
  vertex  0.797990E+02  0.754366E+02  0.539340E+01
 endloop
endfacet
facet normal  0.743589E-01 -0.642248E+00  0.762882E+00
 outer loop
  vertex  0.786942E+02  0.754367E+02  0.572830E+01
  vertex  0.775000E+02  0.754367E+02  0.584470E+01
  vertex  0.775000E+02  0.737558E+02  0.442960E+01
 endloop
endfacet
facet normal  0.744711E-01 -0.642315E+00  0.762814E+00
 outer loop
  vertex  0.775000E+02  0.737557E+02  0.442950E+01
  vertex  0.784043E+02  0.737558E+02  0.434130E+01
  vertex  0.786941E+02  0.754366E+02  0.572830E+01
 endloop
endfacet
facet normal  0.917407E+00 -0.387737E+00  0.895825E-01
 outer loop
  vertex  0.819296E+02  0.737558E+02  0.000000E+00
  vertex  0.818413E+02  0.737558E+02  0.904300E+00
  vertex  0.811779E+02  0.721540E+02  0.765100E+00
 endloop
endfacet
facet normal  0.917432E+00 -0.387607E+00  0.898787E-01
 outer loop
  vertex  0.811779E+02  0.721539E+02  0.765100E+00
  vertex  0.812529E+02  0.721540E+02  0.000000E+00
  vertex  0.819296E+02  0.737557E+02  0.000000E+00
 endloop
endfacet
facet normal  0.881652E+00 -0.388649E+00  0.267660E+00
 outer loop
  vertex  0.818413E+02  0.737558E+02  0.904300E+00
  vertex  0.815872E+02  0.737558E+02  0.174130E+01
  vertex  0.809623E+02  0.721540E+02  0.147380E+01
 endloop
endfacet
facet normal  0.881590E+00 -0.388431E+00  0.268179E+00
 outer loop
  vertex  0.809623E+02  0.721539E+02  0.147370E+01
  vertex  0.811779E+02  0.721540E+02  0.765100E+00
  vertex  0.818413E+02  0.737557E+02  0.904200E+00
 endloop
endfacet
facet normal  0.811860E+00 -0.389578E+00  0.434871E+00
 outer loop
  vertex  0.815872E+02  0.737558E+02  0.174130E+01
  vertex  0.811838E+02  0.737558E+02  0.249440E+01
  vertex  0.806201E+02  0.721540E+02  0.211180E+01
 endloop
endfacet
facet normal  0.811710E+00 -0.389319E+00  0.435381E+00
 outer loop
  vertex  0.806201E+02  0.721539E+02  0.211170E+01
  vertex  0.809623E+02  0.721540E+02  0.147380E+01
  vertex  0.815871E+02  0.737557E+02  0.174120E+01
 endloop
endfacet
facet normal  0.711493E+00 -0.390126E+00  0.584448E+00
 outer loop
  vertex  0.811838E+02  0.737558E+02  0.249440E+01
  vertex  0.806474E+02  0.737558E+02  0.314740E+01
  vertex  0.801652E+02  0.721540E+02  0.266520E+01
 endloop
endfacet
facet normal  0.711262E+00 -0.389975E+00  0.584830E+00
 outer loop
  vertex  0.801651E+02  0.721539E+02  0.266510E+01
  vertex  0.806201E+02  0.721540E+02  0.211180E+01
  vertex  0.811837E+02  0.737557E+02  0.249440E+01
 endloop
endfacet
facet normal  0.584481E+00 -0.390006E+00  0.711532E+00
 outer loop
  vertex  0.806474E+02  0.737558E+02  0.314740E+01
  vertex  0.799944E+02  0.737558E+02  0.368380E+01
  vertex  0.796118E+02  0.721540E+02  0.312010E+01
 endloop
endfacet
facet normal  0.584743E+00 -0.390091E+00  0.711270E+00
 outer loop
  vertex  0.796118E+02  0.721539E+02  0.312010E+01
  vertex  0.801652E+02  0.721540E+02  0.266520E+01
  vertex  0.806473E+02  0.737557E+02  0.314730E+01
 endloop
endfacet
facet normal  0.434914E+00 -0.389384E+00  0.811930E+00
 outer loop
  vertex  0.799944E+02  0.737558E+02  0.368380E+01
  vertex  0.792413E+02  0.737558E+02  0.408720E+01
  vertex  0.789738E+02  0.721540E+02  0.346230E+01
 endloop
endfacet
facet normal  0.435369E+00 -0.389577E+00  0.811593E+00
 outer loop
  vertex  0.789738E+02  0.721539E+02  0.346230E+01
  vertex  0.796118E+02  0.721540E+02  0.312010E+01
  vertex  0.799944E+02  0.737557E+02  0.368370E+01
 endloop
endfacet
facet normal  0.267680E+00 -0.388441E+00  0.881737E+00
 outer loop
  vertex  0.792413E+02  0.737558E+02  0.408720E+01
  vertex  0.784043E+02  0.737558E+02  0.434130E+01
  vertex  0.782651E+02  0.721540E+02  0.367790E+01
 endloop
endfacet
facet normal  0.268177E+00 -0.388694E+00  0.881475E+00
 outer loop
  vertex  0.782650E+02  0.721539E+02  0.367790E+01
  vertex  0.789738E+02  0.721540E+02  0.346230E+01
  vertex  0.792413E+02  0.737557E+02  0.408720E+01
 endloop
endfacet
facet normal  0.895857E-01 -0.387595E+00  0.917466E+00
 outer loop
  vertex  0.784043E+02  0.737558E+02  0.434130E+01
  vertex  0.775000E+02  0.737558E+02  0.442960E+01
  vertex  0.775000E+02  0.721540E+02  0.375290E+01
 endloop
endfacet
facet normal  0.898568E-01 -0.387764E+00  0.917369E+00
 outer loop
  vertex  0.775000E+02  0.721539E+02  0.375280E+01
  vertex  0.782651E+02  0.721540E+02  0.367790E+01
  vertex  0.784042E+02  0.737557E+02  0.434130E+01
 endloop
endfacet
facet normal  0.879543E+00  0.467944E+00  0.862149E-01
 outer loop
  vertex  0.812529E+02  0.721540E+02  0.000000E+00
  vertex  0.811779E+02  0.721540E+02  0.765100E+00
  vertex  0.819100E+02  0.707500E+02  0.916800E+00
 endloop
endfacet
facet normal  0.879461E+00  0.468077E+00  0.863310E-01
 outer loop
  vertex  0.819100E+02  0.707500E+02  0.916800E+00
  vertex  0.820000E+02  0.707500E+02  0.000000E+00
  vertex  0.812528E+02  0.721539E+02  0.000000E+00
 endloop
endfacet
facet normal  0.845308E+00  0.468321E+00  0.257158E+00
 outer loop
  vertex  0.811779E+02  0.721540E+02  0.765100E+00
  vertex  0.809623E+02  0.721540E+02  0.147380E+01
  vertex  0.816512E+02  0.707500E+02  0.176620E+01
 endloop
endfacet
facet normal  0.845061E+00  0.468516E+00  0.257611E+00
 outer loop
  vertex  0.816511E+02  0.707500E+02  0.176610E+01
  vertex  0.819100E+02  0.707500E+02  0.916800E+00
  vertex  0.811779E+02  0.721539E+02  0.765100E+00
 endloop
endfacet
facet normal  0.778428E+00  0.468748E+00  0.417522E+00
 outer loop
  vertex  0.809623E+02  0.721540E+02  0.147380E+01
  vertex  0.806201E+02  0.721540E+02  0.211180E+01
  vertex  0.812406E+02  0.707500E+02  0.253120E+01
 endloop
endfacet
facet normal  0.778213E+00  0.468907E+00  0.417745E+00
 outer loop
  vertex  0.812406E+02  0.707500E+02  0.253110E+01
  vertex  0.816512E+02  0.707500E+02  0.176620E+01
  vertex  0.809623E+02  0.721539E+02  0.147370E+01
 endloop
endfacet
facet normal  0.682274E+00  0.469001E+00  0.560839E+00
 outer loop
  vertex  0.806201E+02  0.721540E+02  0.211180E+01
  vertex  0.801652E+02  0.721540E+02  0.266520E+01
  vertex  0.806949E+02  0.707500E+02  0.319490E+01
 endloop
endfacet
facet normal  0.682167E+00  0.469103E+00  0.560884E+00
 outer loop
  vertex  0.806949E+02  0.707500E+02  0.319490E+01
  vertex  0.812406E+02  0.707500E+02  0.253120E+01
  vertex  0.806201E+02  0.721539E+02  0.211170E+01
 endloop
endfacet
facet normal  0.560822E+00  0.469050E+00  0.682255E+00
 outer loop
  vertex  0.801652E+02  0.721540E+02  0.266520E+01
  vertex  0.796118E+02  0.721540E+02  0.312010E+01
  vertex  0.800312E+02  0.707500E+02  0.374060E+01
 endloop
endfacet
facet normal  0.560834E+00  0.469097E+00  0.682212E+00
 outer loop
  vertex  0.800311E+02  0.707500E+02  0.374060E+01
  vertex  0.806949E+02  0.707500E+02  0.319490E+01
  vertex  0.801651E+02  0.721539E+02  0.266510E+01
 endloop
endfacet
facet normal  0.417490E+00  0.468870E+00  0.778372E+00
 outer loop
  vertex  0.796118E+02  0.721540E+02  0.312010E+01
  vertex  0.789738E+02  0.721540E+02  0.346230E+01
  vertex  0.792662E+02  0.707500E+02  0.415120E+01
 endloop
endfacet
facet normal  0.417615E+00  0.468779E+00  0.778360E+00
 outer loop
  vertex  0.792661E+02  0.707500E+02  0.415110E+01
  vertex  0.800312E+02  0.707500E+02  0.374060E+01
  vertex  0.796118E+02  0.721539E+02  0.312010E+01
 endloop
endfacet
facet normal  0.257136E+00  0.468463E+00  0.845236E+00
 outer loop
  vertex  0.789738E+02  0.721540E+02  0.346230E+01
  vertex  0.782651E+02  0.721540E+02  0.367790E+01
  vertex  0.784168E+02  0.707500E+02  0.440990E+01
 endloop
endfacet
facet normal  0.257424E+00  0.468360E+00  0.845205E+00
 outer loop
  vertex  0.784168E+02  0.707500E+02  0.440990E+01
  vertex  0.792662E+02  0.707500E+02  0.415120E+01
  vertex  0.789738E+02  0.721539E+02  0.346230E+01
 endloop
endfacet
facet normal  0.862176E-01  0.467958E+00  0.879535E+00
 outer loop
  vertex  0.782651E+02  0.721540E+02  0.367790E+01
  vertex  0.775000E+02  0.721540E+02  0.375290E+01
  vertex  0.775000E+02  0.707500E+02  0.449990E+01
 endloop
endfacet
facet normal  0.862471E-01  0.467927E+00  0.879549E+00
 outer loop
  vertex  0.775000E+02  0.707500E+02  0.449980E+01
  vertex  0.784168E+02  0.707500E+02  0.440990E+01
  vertex  0.782650E+02  0.721539E+02  0.367790E+01
 endloop
endfacet
facet normal  0.711344E-02 -0.999975E+00  0.652454E-03
 outer loop
  vertex  0.775000E+02  0.100000E+02  0.000000E+00
  vertex  0.881556E+02  0.100758E+02  0.000000E+00
  vertex  0.879424E+02  0.100757E+02  0.217100E+01
 endloop
endfacet
facet normal  0.683602E-02 -0.999975E+00  0.203264E-02
 outer loop
  vertex  0.775000E+02  0.100000E+02  0.000000E+00
  vertex  0.879425E+02  0.100758E+02  0.217100E+01
  vertex  0.873298E+02  0.100757E+02  0.418230E+01
 endloop
endfacet
facet normal  0.629631E-02 -0.999975E+00  0.332508E-02
 outer loop
  vertex  0.775000E+02  0.100000E+02  0.000000E+00
  vertex  0.873298E+02  0.100758E+02  0.418230E+01
  vertex  0.863573E+02  0.100757E+02  0.599370E+01
 endloop
endfacet
facet normal  0.552635E-02 -0.999975E+00  0.447952E-02
 outer loop
  vertex  0.775000E+02  0.100000E+02  0.000000E+00
  vertex  0.863574E+02  0.100758E+02  0.599370E+01
  vertex  0.850653E+02  0.100757E+02  0.756540E+01
 endloop
endfacet
facet normal  0.455501E-02 -0.999975E+00  0.546396E-02
 outer loop
  vertex  0.775000E+02  0.100000E+02  0.000000E+00
  vertex  0.850654E+02  0.100758E+02  0.756550E+01
  vertex  0.834936E+02  0.100757E+02  0.885750E+01
 endloop
endfacet
facet normal  0.340967E-02 -0.999975E+00  0.625024E-02
 outer loop
  vertex  0.775000E+02  0.100000E+02  0.000000E+00
  vertex  0.834937E+02  0.100758E+02  0.885750E+01
  vertex  0.816822E+02  0.100757E+02  0.982970E+01
 endloop
endfacet
facet normal  0.212347E-02 -0.999975E+00  0.680757E-02
 outer loop
  vertex  0.775000E+02  0.100000E+02  0.000000E+00
  vertex  0.816823E+02  0.100758E+02  0.982980E+01
  vertex  0.796709E+02  0.100757E+02  0.104425E+02
 endloop
endfacet
facet normal  0.743120E-03 -0.999975E+00  0.710411E-02
 outer loop
  vertex  0.775000E+02  0.100000E+02  0.000000E+00
  vertex  0.796710E+02  0.100758E+02  0.104425E+02
  vertex  0.775000E+02  0.100757E+02  0.106555E+02
 endloop
endfacet
facet normal  0.262918E-01 -0.999651E+00  0.258079E-02
 outer loop
  vertex  0.959238E+02  0.102900E+02  0.383040E+01
  vertex  0.879425E+02  0.100758E+02  0.217100E+01
  vertex  0.881556E+02  0.100758E+02  0.000000E+00
 endloop
endfacet
facet normal  0.263040E-01 -0.999651E+00  0.255667E-02
 outer loop
  vertex  0.881556E+02  0.100757E+02  0.000000E+00
  vertex  0.962998E+02  0.102900E+02  0.000000E+00
  vertex  0.959237E+02  0.102899E+02  0.383030E+01
 endloop
endfacet
facet normal  0.252305E-01 -0.999652E+00  0.768587E-02
 outer loop
  vertex  0.948428E+02  0.102900E+02  0.737890E+01
  vertex  0.873298E+02  0.100758E+02  0.418230E+01
  vertex  0.879425E+02  0.100758E+02  0.217100E+01
 endloop
endfacet
facet normal  0.252472E-01 -0.999652E+00  0.766372E-02
 outer loop
  vertex  0.879424E+02  0.100757E+02  0.217100E+01
  vertex  0.959238E+02  0.102900E+02  0.383040E+01
  vertex  0.948427E+02  0.102899E+02  0.737890E+01
 endloop
endfacet
facet normal  0.232010E-01 -0.999653E+00  0.124549E-01
 outer loop
  vertex  0.931273E+02  0.102900E+02  0.105748E+02
  vertex  0.863574E+02  0.100758E+02  0.599370E+01
  vertex  0.873298E+02  0.100758E+02  0.418230E+01
 endloop
endfacet
facet normal  0.232230E-01 -0.999653E+00  0.124355E-01
 outer loop
  vertex  0.873298E+02  0.100757E+02  0.418230E+01
  vertex  0.948428E+02  0.102900E+02  0.737890E+01
  vertex  0.931272E+02  0.102899E+02  0.105747E+02
 endloop
endfacet
facet normal  0.203245E-01 -0.999654E+00  0.167064E-01
 outer loop
  vertex  0.908478E+02  0.102900E+02  0.133478E+02
  vertex  0.850654E+02  0.100758E+02  0.756550E+01
  vertex  0.863574E+02  0.100758E+02  0.599370E+01
 endloop
endfacet
facet normal  0.203488E-01 -0.999654E+00  0.166913E-01
 outer loop
  vertex  0.863573E+02  0.100757E+02  0.599370E+01
  vertex  0.931273E+02  0.102900E+02  0.105748E+02
  vertex  0.908478E+02  0.102899E+02  0.133478E+02
 endloop
endfacet
facet normal  0.167071E-01 -0.999654E+00  0.203239E-01
 outer loop
  vertex  0.880748E+02  0.102900E+02  0.156273E+02
  vertex  0.834937E+02  0.100758E+02  0.885750E+01
  vertex  0.850654E+02  0.100758E+02  0.756550E+01
 endloop
endfacet
facet normal  0.167340E-01 -0.999654E+00  0.203136E-01
 outer loop
  vertex  0.850653E+02  0.100757E+02  0.756540E+01
  vertex  0.908478E+02  0.102900E+02  0.133478E+02
  vertex  0.880747E+02  0.102899E+02  0.156273E+02
 endloop
endfacet
facet normal  0.124540E-01 -0.999653E+00  0.232018E-01
 outer loop
  vertex  0.848789E+02  0.102900E+02  0.173428E+02
  vertex  0.816823E+02  0.100758E+02  0.982980E+01
  vertex  0.834937E+02  0.100758E+02  0.885750E+01
 endloop
endfacet
facet normal  0.124827E-01 -0.999653E+00  0.231971E-01
 outer loop
  vertex  0.834936E+02  0.100757E+02  0.885750E+01
  vertex  0.880748E+02  0.102900E+02  0.156273E+02
  vertex  0.848788E+02  0.102899E+02  0.173428E+02
 endloop
endfacet
facet normal  0.768592E-02 -0.999652E+00  0.252304E-01
 outer loop
  vertex  0.813304E+02  0.102900E+02  0.184238E+02
  vertex  0.796710E+02  0.100758E+02  0.104425E+02
  vertex  0.816823E+02  0.100758E+02  0.982980E+01
 endloop
endfacet
facet normal  0.771371E-02 -0.999652E+00  0.252315E-01
 outer loop
  vertex  0.816822E+02  0.100757E+02  0.982970E+01
  vertex  0.848789E+02  0.102900E+02  0.173428E+02
  vertex  0.813303E+02  0.102899E+02  0.184237E+02
 endloop
endfacet
facet normal  0.258073E-02 -0.999651E+00  0.262917E-01
 outer loop
  vertex  0.775000E+02  0.102900E+02  0.187998E+02
  vertex  0.775000E+02  0.100758E+02  0.106556E+02
  vertex  0.796710E+02  0.100758E+02  0.104425E+02
 endloop
endfacet
facet normal  0.260768E-02 -0.999651E+00  0.262987E-01
 outer loop
  vertex  0.796709E+02  0.100757E+02  0.104425E+02
  vertex  0.813304E+02  0.102900E+02  0.184238E+02
  vertex  0.775000E+02  0.102899E+02  0.187998E+02
 endloop
endfacet
facet normal  0.556852E-01 -0.998433E+00  0.546616E-02
 outer loop
  vertex  0.101773E+03  0.106229E+02  0.504660E+01
  vertex  0.959238E+02  0.102900E+02  0.383040E+01
  vertex  0.962998E+02  0.102900E+02  0.000000E+00
 endloop
endfacet
facet normal  0.557017E-01 -0.998433E+00  0.546697E-02
 outer loop
  vertex  0.962997E+02  0.102899E+02  0.000000E+00
  vertex  0.102269E+03  0.106229E+02  0.000000E+00
  vertex  0.101773E+03  0.106229E+02  0.504650E+01
 endloop
endfacet
facet normal  0.534373E-01 -0.998438E+00  0.162789E-01
 outer loop
  vertex  0.100349E+03  0.106229E+02  0.972170E+01
  vertex  0.948428E+02  0.102900E+02  0.737890E+01
  vertex  0.959238E+02  0.102900E+02  0.383040E+01
 endloop
endfacet
facet normal  0.534520E-01 -0.998438E+00  0.162849E-01
 outer loop
  vertex  0.959237E+02  0.102899E+02  0.383030E+01
  vertex  0.101773E+03  0.106229E+02  0.504660E+01
  vertex  0.100349E+03  0.106229E+02  0.972160E+01
 endloop
endfacet
facet normal  0.491410E-01 -0.998443E+00  0.263780E-01
 outer loop
  vertex  0.980889E+02  0.106229E+02  0.139323E+02
  vertex  0.931273E+02  0.102900E+02  0.105748E+02
  vertex  0.948428E+02  0.102900E+02  0.737890E+01
 endloop
endfacet
facet normal  0.491540E-01 -0.998443E+00  0.263871E-01
 outer loop
  vertex  0.948427E+02  0.102899E+02  0.737890E+01
  vertex  0.100349E+03  0.106229E+02  0.972170E+01
  vertex  0.980888E+02  0.106229E+02  0.139322E+02
 endloop
endfacet
facet normal  0.430459E-01 -0.998446E+00  0.353851E-01
 outer loop
  vertex  0.950857E+02  0.106229E+02  0.175857E+02
  vertex  0.908478E+02  0.102900E+02  0.133478E+02
  vertex  0.931273E+02  0.102900E+02  0.105748E+02
 endloop
endfacet
facet normal  0.430575E-01 -0.998445E+00  0.353955E-01
 outer loop
  vertex  0.931272E+02  0.102899E+02  0.105747E+02
  vertex  0.980889E+02  0.106229E+02  0.139323E+02
  vertex  0.950857E+02  0.106229E+02  0.175856E+02
 endloop
endfacet
facet normal  0.353852E-01 -0.998446E+00  0.430460E-01
 outer loop
  vertex  0.914323E+02  0.106229E+02  0.205889E+02
  vertex  0.880748E+02  0.102900E+02  0.156273E+02
  vertex  0.908478E+02  0.102900E+02  0.133478E+02
 endloop
endfacet
facet normal  0.353945E-01 -0.998445E+00  0.430601E-01
 outer loop
  vertex  0.908478E+02  0.102899E+02  0.133478E+02
  vertex  0.950857E+02  0.106229E+02  0.175857E+02
  vertex  0.914322E+02  0.106229E+02  0.205888E+02
 endloop
endfacet
facet normal  0.263778E-01 -0.998443E+00  0.491408E-01
 outer loop
  vertex  0.872217E+02  0.106229E+02  0.228491E+02
  vertex  0.848789E+02  0.102900E+02  0.173428E+02
  vertex  0.880748E+02  0.102900E+02  0.156273E+02
 endloop
endfacet
facet normal  0.263859E-01 -0.998443E+00  0.491551E-01
 outer loop
  vertex  0.880747E+02  0.102899E+02  0.156273E+02
  vertex  0.914323E+02  0.106229E+02  0.205889E+02
  vertex  0.872217E+02  0.106229E+02  0.228491E+02
 endloop
endfacet
facet normal  0.162789E-01 -0.998438E+00  0.534373E-01
 outer loop
  vertex  0.825466E+02  0.106229E+02  0.242733E+02
  vertex  0.813304E+02  0.102900E+02  0.184238E+02
  vertex  0.848789E+02  0.102900E+02  0.173428E+02
 endloop
endfacet
facet normal  0.162837E-01 -0.998438E+00  0.534531E-01
 outer loop
  vertex  0.848788E+02  0.102899E+02  0.173428E+02
  vertex  0.872217E+02  0.106229E+02  0.228491E+02
  vertex  0.825466E+02  0.106229E+02  0.242733E+02
 endloop
endfacet
facet normal  0.546627E-02 -0.998433E+00  0.556860E-01
 outer loop
  vertex  0.775000E+02  0.106229E+02  0.247686E+02
  vertex  0.775000E+02  0.102900E+02  0.187998E+02
  vertex  0.813304E+02  0.102900E+02  0.184238E+02
 endloop
endfacet
facet normal  0.546680E-02 -0.998433E+00  0.557011E-01
 outer loop
  vertex  0.813303E+02  0.102899E+02  0.184237E+02
  vertex  0.825466E+02  0.106229E+02  0.242733E+02
  vertex  0.775000E+02  0.106229E+02  0.247686E+02
 endloop
endfacet
facet normal  0.103964E+00 -0.994529E+00  0.102036E-01
 outer loop
  vertex  0.105820E+03  0.110546E+02  0.588800E+01
  vertex  0.101773E+03  0.106229E+02  0.504660E+01
  vertex  0.102269E+03  0.106229E+02  0.000000E+00
 endloop
endfacet
facet normal  0.103961E+00 -0.994529E+00  0.101903E-01
 outer loop
  vertex  0.102269E+03  0.106229E+02  0.000000E+00
  vertex  0.106398E+03  0.110546E+02  0.000000E+00
  vertex  0.105820E+03  0.110545E+02  0.588800E+01
 endloop
endfacet
facet normal  0.997670E-01 -0.994547E+00  0.303926E-01
 outer loop
  vertex  0.104159E+03  0.110546E+02  0.113426E+02
  vertex  0.100349E+03  0.106229E+02  0.972170E+01
  vertex  0.101773E+03  0.106229E+02  0.504660E+01
 endloop
endfacet
facet normal  0.997712E-01 -0.994547E+00  0.303767E-01
 outer loop
  vertex  0.101773E+03  0.106229E+02  0.504650E+01
  vertex  0.105820E+03  0.110546E+02  0.588800E+01
  vertex  0.104159E+03  0.110545E+02  0.113425E+02
 endloop
endfacet
facet normal  0.917449E-01 -0.994564E+00  0.492476E-01
 outer loop
  vertex  0.101522E+03  0.110546E+02  0.162553E+02
  vertex  0.980889E+02  0.106229E+02  0.139323E+02
  vertex  0.100349E+03  0.106229E+02  0.972170E+01
 endloop
endfacet
facet normal  0.917503E-01 -0.994564E+00  0.492306E-01
 outer loop
  vertex  0.100349E+03  0.106229E+02  0.972160E+01
  vertex  0.104159E+03  0.110546E+02  0.113426E+02
  vertex  0.101522E+03  0.110545E+02  0.162553E+02
 endloop
endfacet
facet normal  0.803683E-01 -0.994573E+00  0.660650E-01
 outer loop
  vertex  0.980178E+02  0.110546E+02  0.205178E+02
  vertex  0.950857E+02  0.106229E+02  0.175857E+02
  vertex  0.980889E+02  0.106229E+02  0.139323E+02
 endloop
endfacet
facet normal  0.803719E-01 -0.994574E+00  0.660500E-01
 outer loop
  vertex  0.980888E+02  0.106229E+02  0.139322E+02
  vertex  0.101522E+03  0.110546E+02  0.162553E+02
  vertex  0.980177E+02  0.110545E+02  0.205177E+02
 endloop
endfacet
facet normal  0.660637E-01 -0.994574E+00  0.803667E-01
 outer loop
  vertex  0.937553E+02  0.110546E+02  0.240218E+02
  vertex  0.914323E+02  0.106229E+02  0.205889E+02
  vertex  0.950857E+02  0.106229E+02  0.175857E+02
 endloop
endfacet
facet normal  0.660767E-01 -0.994574E+00  0.803540E-01
 outer loop
  vertex  0.950857E+02  0.106229E+02  0.175856E+02
  vertex  0.980178E+02  0.110546E+02  0.205178E+02
  vertex  0.937553E+02  0.110545E+02  0.240217E+02
 endloop
endfacet
facet normal  0.492485E-01 -0.994564E+00  0.917464E-01
 outer loop
  vertex  0.888426E+02  0.110546E+02  0.266588E+02
  vertex  0.872217E+02  0.106229E+02  0.228491E+02
  vertex  0.914323E+02  0.106229E+02  0.205889E+02
 endloop
endfacet
facet normal  0.492590E-01 -0.994564E+00  0.917331E-01
 outer loop
  vertex  0.914322E+02  0.106229E+02  0.205888E+02
  vertex  0.937553E+02  0.110546E+02  0.240218E+02
  vertex  0.888425E+02  0.110545E+02  0.266588E+02
 endloop
endfacet
facet normal  0.303930E-01 -0.994546E+00  0.997684E-01
 outer loop
  vertex  0.833880E+02  0.110546E+02  0.283204E+02
  vertex  0.825466E+02  0.106229E+02  0.242733E+02
  vertex  0.872217E+02  0.106229E+02  0.228491E+02
 endloop
endfacet
facet normal  0.304077E-01 -0.994547E+00  0.997606E-01
 outer loop
  vertex  0.872217E+02  0.106229E+02  0.228491E+02
  vertex  0.888426E+02  0.110546E+02  0.266588E+02
  vertex  0.833880E+02  0.110545E+02  0.283204E+02
 endloop
endfacet
facet normal  0.102033E-01 -0.994529E+00  0.103961E+00
 outer loop
  vertex  0.775000E+02  0.110546E+02  0.288984E+02
  vertex  0.775000E+02  0.106229E+02  0.247686E+02
  vertex  0.825466E+02  0.106229E+02  0.242733E+02
 endloop
endfacet
facet normal  0.102205E-01 -0.994529E+00  0.103960E+00
 outer loop
  vertex  0.825466E+02  0.106229E+02  0.242733E+02
  vertex  0.833880E+02  0.110546E+02  0.283204E+02
  vertex  0.775000E+02  0.110545E+02  0.288983E+02
 endloop
endfacet
facet normal  0.190881E+00 -0.981434E+00  0.187381E-01
 outer loop
  vertex  0.108395E+03  0.115655E+02  0.642320E+01
  vertex  0.105820E+03  0.110546E+02  0.588800E+01
  vertex  0.106398E+03  0.110546E+02  0.000000E+00
 endloop
endfacet
facet normal  0.190913E+00 -0.981428E+00  0.187430E-01
 outer loop
  vertex  0.106398E+03  0.110545E+02  0.000000E+00
  vertex  0.109025E+03  0.115655E+02  0.000000E+00
  vertex  0.108395E+03  0.115655E+02  0.642320E+01
 endloop
endfacet
facet normal  0.183192E+00 -0.981492E+00  0.558044E-01
 outer loop
  vertex  0.106582E+03  0.115655E+02  0.123736E+02
  vertex  0.104159E+03  0.110546E+02  0.113426E+02
  vertex  0.105820E+03  0.110546E+02  0.588800E+01
 endloop
endfacet
facet normal  0.183215E+00 -0.981487E+00  0.558137E-01
 outer loop
  vertex  0.105820E+03  0.110545E+02  0.588800E+01
  vertex  0.108395E+03  0.115655E+02  0.642320E+01
  vertex  0.106582E+03  0.115655E+02  0.123736E+02
 endloop
endfacet
facet normal  0.168470E+00 -0.981550E+00  0.904301E-01
 outer loop
  vertex  0.103705E+03  0.115655E+02  0.177329E+02
  vertex  0.101522E+03  0.110546E+02  0.162553E+02
  vertex  0.104159E+03  0.110546E+02  0.113426E+02
 endloop
endfacet
facet normal  0.168494E+00 -0.981544E+00  0.904453E-01
 outer loop
  vertex  0.104159E+03  0.110545E+02  0.113425E+02
  vertex  0.106582E+03  0.115655E+02  0.123736E+02
  vertex  0.103705E+03  0.115655E+02  0.177329E+02
 endloop
endfacet
facet normal  0.147571E+00 -0.981584E+00  0.121311E+00
 outer loop
  vertex  0.998829E+02  0.115655E+02  0.223829E+02
  vertex  0.980178E+02  0.110546E+02  0.205178E+02
  vertex  0.101522E+03  0.110546E+02  0.162553E+02
 endloop
endfacet
facet normal  0.147601E+00 -0.981576E+00  0.121335E+00
 outer loop
  vertex  0.101522E+03  0.110545E+02  0.162553E+02
  vertex  0.103705E+03  0.115655E+02  0.177329E+02
  vertex  0.998828E+02  0.115655E+02  0.223829E+02
 endloop
endfacet
facet normal  0.121316E+00 -0.981582E+00  0.147577E+00
 outer loop
  vertex  0.952329E+02  0.115655E+02  0.262053E+02
  vertex  0.937553E+02  0.110546E+02  0.240218E+02
  vertex  0.980178E+02  0.110546E+02  0.205178E+02
 endloop
endfacet
facet normal  0.121324E+00 -0.981578E+00  0.147595E+00
 outer loop
  vertex  0.980177E+02  0.110545E+02  0.205177E+02
  vertex  0.998829E+02  0.115655E+02  0.223829E+02
  vertex  0.952329E+02  0.115655E+02  0.262052E+02
 endloop
endfacet
facet normal  0.904307E-01 -0.981550E+00  0.168472E+00
 outer loop
  vertex  0.898736E+02  0.115655E+02  0.290820E+02
  vertex  0.888426E+02  0.110546E+02  0.266588E+02
  vertex  0.937553E+02  0.110546E+02  0.240218E+02
 endloop
endfacet
facet normal  0.904425E-01 -0.981544E+00  0.168498E+00
 outer loop
  vertex  0.937553E+02  0.110545E+02  0.240217E+02
  vertex  0.952329E+02  0.115655E+02  0.262053E+02
  vertex  0.898735E+02  0.115655E+02  0.290820E+02
 endloop
endfacet
facet normal  0.558032E-01 -0.981493E+00  0.183187E+00
 outer loop
  vertex  0.839232E+02  0.115655E+02  0.308947E+02
  vertex  0.833880E+02  0.110546E+02  0.283204E+02
  vertex  0.888426E+02  0.110546E+02  0.266588E+02
 endloop
endfacet
facet normal  0.558136E-01 -0.981485E+00  0.183225E+00
 outer loop
  vertex  0.888425E+02  0.110545E+02  0.266588E+02
  vertex  0.898736E+02  0.115655E+02  0.290820E+02
  vertex  0.839232E+02  0.115655E+02  0.308946E+02
 endloop
endfacet
facet normal  0.187383E-01 -0.981434E+00  0.190884E+00
 outer loop
  vertex  0.775000E+02  0.115655E+02  0.315252E+02
  vertex  0.775000E+02  0.110546E+02  0.288984E+02
  vertex  0.833880E+02  0.110546E+02  0.283204E+02
 endloop
endfacet
facet normal  0.187376E-01 -0.981427E+00  0.190919E+00
 outer loop
  vertex  0.833880E+02  0.110545E+02  0.283204E+02
  vertex  0.839232E+02  0.115655E+02  0.308947E+02
  vertex  0.775000E+02  0.115655E+02  0.315251E+02
 endloop
endfacet
facet normal  0.363534E+00 -0.930897E+00  0.356845E-01
 outer loop
  vertex  0.109826E+03  0.121357E+02  0.672070E+01
  vertex  0.108395E+03  0.115655E+02  0.642320E+01
  vertex  0.109025E+03  0.115655E+02  0.000000E+00
 endloop
endfacet
facet normal  0.363514E+00 -0.930905E+00  0.356881E-01
 outer loop
  vertex  0.109025E+03  0.115655E+02  0.000000E+00
  vertex  0.110485E+03  0.121357E+02  0.000000E+00
  vertex  0.109826E+03  0.121357E+02  0.672060E+01
 endloop
endfacet
facet normal  0.348942E+00 -0.931096E+00  0.106300E+00
 outer loop
  vertex  0.107929E+03  0.121357E+02  0.129467E+02
  vertex  0.106582E+03  0.115655E+02  0.123736E+02
  vertex  0.108395E+03  0.115655E+02  0.642320E+01
 endloop
endfacet
facet normal  0.348914E+00 -0.931107E+00  0.106294E+00
 outer loop
  vertex  0.108395E+03  0.115655E+02  0.642320E+01
  vertex  0.109826E+03  0.121357E+02  0.672070E+01
  vertex  0.107929E+03  0.121357E+02  0.129467E+02
 endloop
endfacet
facet normal  0.320949E+00 -0.931296E+00  0.172275E+00
 outer loop
  vertex  0.104919E+03  0.121357E+02  0.185542E+02
  vertex  0.103705E+03  0.115655E+02  0.177329E+02
  vertex  0.106582E+03  0.115655E+02  0.123736E+02
 endloop
endfacet
facet normal  0.320950E+00 -0.931294E+00  0.172283E+00
 outer loop
  vertex  0.106582E+03  0.115655E+02  0.123736E+02
  vertex  0.107929E+03  0.121357E+02  0.129467E+02
  vertex  0.104919E+03  0.121357E+02  0.185541E+02
 endloop
endfacet
facet normal  0.281175E+00 -0.931407E+00  0.231132E+00
 outer loop
  vertex  0.100920E+03  0.121357E+02  0.234195E+02
  vertex  0.998829E+02  0.115655E+02  0.223829E+02
  vertex  0.103705E+03  0.115655E+02  0.177329E+02
 endloop
endfacet
facet normal  0.281161E+00 -0.931414E+00  0.231121E+00
 outer loop
  vertex  0.103705E+03  0.115655E+02  0.177329E+02
  vertex  0.104919E+03  0.121357E+02  0.185542E+02
  vertex  0.100920E+03  0.121357E+02  0.234195E+02
 endloop
endfacet
facet normal  0.231131E+00 -0.931407E+00  0.281174E+00
 outer loop
  vertex  0.960542E+02  0.121357E+02  0.274190E+02
  vertex  0.952329E+02  0.115655E+02  0.262053E+02
  vertex  0.998829E+02  0.115655E+02  0.223829E+02
 endloop
endfacet
facet normal  0.231124E+00 -0.931411E+00  0.281169E+00
 outer loop
  vertex  0.998828E+02  0.115655E+02  0.223829E+02
  vertex  0.100920E+03  0.121357E+02  0.234195E+02
  vertex  0.960541E+02  0.121357E+02  0.274190E+02
 endloop
endfacet
facet normal  0.172277E+00 -0.931295E+00  0.320953E+00
 outer loop
  vertex  0.904467E+02  0.121357E+02  0.304289E+02
  vertex  0.898736E+02  0.115655E+02  0.290820E+02
  vertex  0.952329E+02  0.115655E+02  0.262053E+02
 endloop
endfacet
facet normal  0.172261E+00 -0.931304E+00  0.320936E+00
 outer loop
  vertex  0.952329E+02  0.115655E+02  0.262052E+02
  vertex  0.960542E+02  0.121357E+02  0.274190E+02
  vertex  0.904467E+02  0.121357E+02  0.304288E+02
 endloop
endfacet
facet normal  0.106297E+00 -0.931099E+00  0.348934E+00
 outer loop
  vertex  0.842207E+02  0.121357E+02  0.323256E+02
  vertex  0.839232E+02  0.115655E+02  0.308947E+02
  vertex  0.898736E+02  0.115655E+02  0.290820E+02
 endloop
endfacet
facet normal  0.106295E+00 -0.931098E+00  0.348937E+00
 outer loop
  vertex  0.898735E+02  0.115655E+02  0.290820E+02
  vertex  0.904467E+02  0.121357E+02  0.304289E+02
  vertex  0.842207E+02  0.121357E+02  0.323255E+02
 endloop
endfacet
facet normal  0.356846E-01 -0.930897E+00  0.363535E+00
 outer loop
  vertex  0.775000E+02  0.121357E+02  0.329853E+02
  vertex  0.775000E+02  0.115655E+02  0.315252E+02
  vertex  0.839232E+02  0.115655E+02  0.308947E+02
 endloop
endfacet
facet normal  0.356769E-01 -0.930905E+00  0.363514E+00
 outer loop
  vertex  0.839232E+02  0.115655E+02  0.308946E+02
  vertex  0.842207E+02  0.121357E+02  0.323256E+02
  vertex  0.775000E+02  0.121357E+02  0.329852E+02
 endloop
endfacet
facet normal  0.694108E+00 -0.716639E+00  0.681331E-01
 outer loop
  vertex  0.110442E+03  0.127454E+02  0.684900E+01
  vertex  0.109826E+03  0.121357E+02  0.672070E+01
  vertex  0.110485E+03  0.121357E+02  0.000000E+00
 endloop
endfacet
facet normal  0.694046E+00 -0.716699E+00  0.681390E-01
 outer loop
  vertex  0.110485E+03  0.121357E+02  0.000000E+00
  vertex  0.111115E+03  0.127454E+02  0.000000E+00
  vertex  0.110442E+03  0.127454E+02  0.684890E+01
 endloop
endfacet
facet normal  0.666562E+00 -0.717259E+00  0.203063E+00
 outer loop
  vertex  0.108510E+03  0.127454E+02  0.131938E+02
  vertex  0.107929E+03  0.121357E+02  0.129467E+02
  vertex  0.109826E+03  0.121357E+02  0.672070E+01
 endloop
endfacet
facet normal  0.666540E+00 -0.717280E+00  0.203060E+00
 outer loop
  vertex  0.109826E+03  0.121357E+02  0.672060E+01
  vertex  0.110442E+03  0.127454E+02  0.684900E+01
  vertex  0.108510E+03  0.127454E+02  0.131937E+02
 endloop
endfacet
facet normal  0.613475E+00 -0.717785E+00  0.329291E+00
 outer loop
  vertex  0.105442E+03  0.127454E+02  0.189083E+02
  vertex  0.104919E+03  0.121357E+02  0.185542E+02
  vertex  0.107929E+03  0.121357E+02  0.129467E+02
 endloop
endfacet
facet normal  0.613442E+00 -0.717814E+00  0.329290E+00
 outer loop
  vertex  0.107929E+03  0.121357E+02  0.129467E+02
  vertex  0.108510E+03  0.127454E+02  0.131938E+02
  vertex  0.105442E+03  0.127454E+02  0.189083E+02
 endloop
endfacet
facet normal  0.537628E+00 -0.718082E+00  0.441944E+00
 outer loop
  vertex  0.101367E+03  0.127454E+02  0.238665E+02
  vertex  0.100920E+03  0.121357E+02  0.234195E+02
  vertex  0.104919E+03  0.121357E+02  0.185542E+02
 endloop
endfacet
facet normal  0.537553E+00 -0.718174E+00  0.441886E+00
 outer loop
  vertex  0.104919E+03  0.121357E+02  0.185541E+02
  vertex  0.105442E+03  0.127454E+02  0.189083E+02
  vertex  0.101367E+03  0.127454E+02  0.238665E+02
 endloop
endfacet
facet normal  0.441935E+00 -0.718098E+00  0.537615E+00
 outer loop
  vertex  0.964083E+02  0.127454E+02  0.279423E+02
  vertex  0.960542E+02  0.121357E+02  0.274190E+02
  vertex  0.100920E+03  0.121357E+02  0.234195E+02
 endloop
endfacet
facet normal  0.441941E+00 -0.718090E+00  0.537620E+00
 outer loop
  vertex  0.100920E+03  0.121357E+02  0.234195E+02
  vertex  0.101367E+03  0.127454E+02  0.238665E+02
  vertex  0.964083E+02  0.127454E+02  0.279423E+02
 endloop
endfacet
facet normal  0.329275E+00 -0.717818E+00  0.613445E+00
 outer loop
  vertex  0.906938E+02  0.127454E+02  0.310097E+02
  vertex  0.904467E+02  0.121357E+02  0.304289E+02
  vertex  0.960542E+02  0.121357E+02  0.274190E+02
 endloop
endfacet
facet normal  0.329283E+00 -0.717812E+00  0.613448E+00
 outer loop
  vertex  0.960541E+02  0.121357E+02  0.274190E+02
  vertex  0.964083E+02  0.127454E+02  0.279423E+02
  vertex  0.906938E+02  0.127454E+02  0.310097E+02
 endloop
endfacet
facet normal  0.203077E+00 -0.717213E+00  0.666607E+00
 outer loop
  vertex  0.843490E+02  0.127454E+02  0.329425E+02
  vertex  0.842207E+02  0.121357E+02  0.323256E+02
  vertex  0.904467E+02  0.121357E+02  0.304289E+02
 endloop
endfacet
facet normal  0.203034E+00 -0.717314E+00  0.666511E+00
 outer loop
  vertex  0.904467E+02  0.121357E+02  0.304288E+02
  vertex  0.906938E+02  0.127454E+02  0.310097E+02
  vertex  0.843489E+02  0.127454E+02  0.329425E+02
 endloop
endfacet
facet normal  0.681325E-01 -0.716645E+00  0.694103E+00
 outer loop
  vertex  0.775000E+02  0.127454E+02  0.336148E+02
  vertex  0.775000E+02  0.121357E+02  0.329853E+02
  vertex  0.842207E+02  0.121357E+02  0.323256E+02
 endloop
endfacet
facet normal  0.681181E-01 -0.716696E+00  0.694051E+00
 outer loop
  vertex  0.842207E+02  0.121357E+02  0.323255E+02
  vertex  0.843490E+02  0.127454E+02  0.329425E+02
  vertex  0.775000E+02  0.127454E+02  0.336147E+02
 endloop
endfacet
facet normal  0.973271E+00 -0.208845E+00  0.955369E-01
 outer loop
  vertex  0.110575E+03  0.133750E+02  0.687650E+01
  vertex  0.110442E+03  0.127454E+02  0.684900E+01
  vertex  0.111115E+03  0.127454E+02  0.000000E+00
 endloop
endfacet
facet normal  0.973206E+00 -0.209140E+00  0.955588E-01
 outer loop
  vertex  0.111115E+03  0.127454E+02  0.000000E+00
  vertex  0.111250E+03  0.133750E+02  0.000000E+00
  vertex  0.110575E+03  0.133750E+02  0.687650E+01
 endloop
endfacet
facet normal  0.935449E+00 -0.209122E+00  0.284963E+00
 outer loop
  vertex  0.108634E+03  0.133750E+02  0.132468E+02
  vertex  0.108510E+03  0.127454E+02  0.131938E+02
  vertex  0.110442E+03  0.127454E+02  0.684900E+01
 endloop
endfacet
facet normal  0.935401E+00 -0.209348E+00  0.284953E+00
 outer loop
  vertex  0.110442E+03  0.127454E+02  0.684890E+01
  vertex  0.110575E+03  0.133750E+02  0.687650E+01
  vertex  0.108634E+03  0.133750E+02  0.132468E+02
 endloop
endfacet
facet normal  0.861538E+00 -0.209500E+00  0.462452E+00
 outer loop
  vertex  0.105555E+03  0.133750E+02  0.189843E+02
  vertex  0.105442E+03  0.127454E+02  0.189083E+02
  vertex  0.108510E+03  0.127454E+02  0.131938E+02
 endloop
endfacet
facet normal  0.861515E+00 -0.209639E+00  0.462432E+00
 outer loop
  vertex  0.108510E+03  0.127454E+02  0.131937E+02
  vertex  0.108634E+03  0.133750E+02  0.132468E+02
  vertex  0.105555E+03  0.133750E+02  0.189843E+02
 endloop
endfacet
facet normal  0.755315E+00 -0.209743E+00  0.620893E+00
 outer loop
  vertex  0.101463E+03  0.133750E+02  0.239624E+02
  vertex  0.101367E+03  0.127454E+02  0.238665E+02
  vertex  0.105442E+03  0.127454E+02  0.189083E+02
 endloop
endfacet
facet normal  0.755310E+00 -0.209795E+00  0.620881E+00
 outer loop
  vertex  0.105442E+03  0.127454E+02  0.189083E+02
  vertex  0.105555E+03  0.133750E+02  0.189843E+02
  vertex  0.101463E+03  0.133750E+02  0.239624E+02
 endloop
endfacet
facet normal  0.620903E+00 -0.209671E+00  0.755326E+00
 outer loop
  vertex  0.964843E+02  0.133750E+02  0.280546E+02
  vertex  0.964083E+02  0.127454E+02  0.279423E+02
  vertex  0.101367E+03  0.127454E+02  0.238665E+02
 endloop
endfacet
facet normal  0.620875E+00 -0.209722E+00  0.755335E+00
 outer loop
  vertex  0.101367E+03  0.127454E+02  0.238665E+02
  vertex  0.101463E+03  0.133750E+02  0.239624E+02
  vertex  0.964842E+02  0.133750E+02  0.280545E+02
 endloop
endfacet
facet normal  0.462459E+00 -0.209434E+00  0.861551E+00
 outer loop
  vertex  0.907468E+02  0.133750E+02  0.311343E+02
  vertex  0.906938E+02  0.127454E+02  0.310097E+02
  vertex  0.964083E+02  0.127454E+02  0.279423E+02
 endloop
endfacet
facet normal  0.462448E+00 -0.209490E+00  0.861543E+00
 outer loop
  vertex  0.964083E+02  0.127454E+02  0.279423E+02
  vertex  0.964843E+02  0.133750E+02  0.280546E+02
  vertex  0.907468E+02  0.133750E+02  0.311343E+02
 endloop
endfacet
facet normal  0.284952E+00 -0.209306E+00  0.935411E+00
 outer loop
  vertex  0.843765E+02  0.133750E+02  0.330750E+02
  vertex  0.843490E+02  0.127454E+02  0.329425E+02
  vertex  0.906938E+02  0.127454E+02  0.310097E+02
 endloop
endfacet
facet normal  0.284981E+00 -0.209117E+00  0.935444E+00
 outer loop
  vertex  0.906938E+02  0.127454E+02  0.310097E+02
  vertex  0.907468E+02  0.133750E+02  0.311343E+02
  vertex  0.843765E+02  0.133750E+02  0.330750E+02
 endloop
endfacet
facet normal  0.955333E-01 -0.208994E+00  0.973239E+00
 outer loop
  vertex  0.775000E+02  0.133750E+02  0.337500E+02
  vertex  0.775000E+02  0.127454E+02  0.336148E+02
  vertex  0.843490E+02  0.127454E+02  0.329425E+02
 endloop
endfacet
facet normal  0.955332E-01 -0.209007E+00  0.973237E+00
 outer loop
  vertex  0.843489E+02  0.127454E+02  0.329425E+02
  vertex  0.843765E+02  0.133750E+02  0.330750E+02
  vertex  0.775000E+02  0.133750E+02  0.337500E+02
 endloop
endfacet
facet normal  0.429263E+00  0.902196E+00  0.421380E-01
 outer loop
  vertex  0.820000E+02  0.707500E+02  0.000000E+00
  vertex  0.819100E+02  0.707500E+02  0.916800E+00
  vertex  0.842183E+02  0.696293E+02  0.139670E+01
 endloop
endfacet
facet normal  0.429263E+00  0.902195E+00  0.421670E-01
 outer loop
  vertex  0.842182E+02  0.696293E+02  0.139670E+01
  vertex  0.843554E+02  0.696293E+02  0.000000E+00
  vertex  0.820000E+02  0.707500E+02  0.000000E+00
 endloop
endfacet
facet normal  0.412045E+00  0.902473E+00  0.125546E+00
 outer loop
  vertex  0.819100E+02  0.707500E+02  0.916800E+00
  vertex  0.816512E+02  0.707500E+02  0.176620E+01
  vertex  0.838241E+02  0.696293E+02  0.269070E+01
 endloop
endfacet
facet normal  0.412052E+00  0.902468E+00  0.125559E+00
 outer loop
  vertex  0.838240E+02  0.696293E+02  0.269070E+01
  vertex  0.842183E+02  0.696293E+02  0.139670E+01
  vertex  0.819100E+02  0.707500E+02  0.916800E+00
 endloop
endfacet
facet normal  0.379012E+00  0.902755E+00  0.203427E+00
 outer loop
  vertex  0.816512E+02  0.707500E+02  0.176620E+01
  vertex  0.812406E+02  0.707500E+02  0.253120E+01
  vertex  0.831986E+02  0.696294E+02  0.385610E+01
 endloop
endfacet
facet normal  0.379051E+00  0.902752E+00  0.203368E+00
 outer loop
  vertex  0.831986E+02  0.696294E+02  0.385610E+01
  vertex  0.838241E+02  0.696293E+02  0.269070E+01
  vertex  0.816511E+02  0.707500E+02  0.176610E+01
 endloop
endfacet
facet normal  0.332037E+00  0.902895E+00  0.273004E+00
 outer loop
  vertex  0.812406E+02  0.707500E+02  0.253120E+01
  vertex  0.806949E+02  0.707500E+02  0.319490E+01
  vertex  0.823673E+02  0.696293E+02  0.486730E+01
 endloop
endfacet
facet normal  0.331995E+00  0.902907E+00  0.273019E+00
 outer loop
  vertex  0.823673E+02  0.696293E+02  0.486730E+01
  vertex  0.831986E+02  0.696294E+02  0.385610E+01
  vertex  0.812406E+02  0.707500E+02  0.253110E+01
 endloop
endfacet
facet normal  0.273006E+00  0.902893E+00  0.332041E+00
 outer loop
  vertex  0.806949E+02  0.707500E+02  0.319490E+01
  vertex  0.800312E+02  0.707500E+02  0.374060E+01
  vertex  0.813562E+02  0.696293E+02  0.569860E+01
 endloop
endfacet
facet normal  0.272979E+00  0.902894E+00  0.332061E+00
 outer loop
  vertex  0.813562E+02  0.696293E+02  0.569850E+01
  vertex  0.823673E+02  0.696293E+02  0.486730E+01
  vertex  0.806949E+02  0.707500E+02  0.319490E+01
 endloop
endfacet
facet normal  0.203443E+00  0.902740E+00  0.379040E+00
 outer loop
  vertex  0.800312E+02  0.707500E+02  0.374060E+01
  vertex  0.792662E+02  0.707500E+02  0.415120E+01
  vertex  0.801907E+02  0.696293E+02  0.632410E+01
 endloop
endfacet
facet normal  0.203407E+00  0.902746E+00  0.379045E+00
 outer loop
  vertex  0.801906E+02  0.696293E+02  0.632410E+01
  vertex  0.813562E+02  0.696293E+02  0.569860E+01
  vertex  0.800311E+02  0.707500E+02  0.374060E+01
 endloop
endfacet
facet normal  0.125498E+00  0.902477E+00  0.412050E+00
 outer loop
  vertex  0.792662E+02  0.707500E+02  0.415120E+01
  vertex  0.784168E+02  0.707500E+02  0.440990E+01
  vertex  0.788967E+02  0.696293E+02  0.671830E+01
 endloop
endfacet
facet normal  0.125484E+00  0.902479E+00  0.412049E+00
 outer loop
  vertex  0.788966E+02  0.696293E+02  0.671820E+01
  vertex  0.801907E+02  0.696293E+02  0.632410E+01
  vertex  0.792661E+02  0.707500E+02  0.415110E+01
 endloop
endfacet
facet normal  0.421381E-01  0.902203E+00  0.429249E+00
 outer loop
  vertex  0.784168E+02  0.707500E+02  0.440990E+01
  vertex  0.775000E+02  0.707500E+02  0.449990E+01
  vertex  0.775000E+02  0.696293E+02  0.685540E+01
 endloop
endfacet
facet normal  0.421351E-01  0.902203E+00  0.429248E+00
 outer loop
  vertex  0.775000E+02  0.696293E+02  0.685540E+01
  vertex  0.788967E+02  0.696293E+02  0.671830E+01
  vertex  0.784168E+02  0.707500E+02  0.440990E+01
 endloop
endfacet
facet normal  0.250666E+00  0.967761E+00  0.246054E-01
 outer loop
  vertex  0.843554E+02  0.696293E+02  0.000000E+00
  vertex  0.842183E+02  0.696293E+02  0.139670E+01
  vertex  0.875603E+02  0.687460E+02  0.209160E+01
 endloop
endfacet
facet normal  0.250667E+00  0.967761E+00  0.246052E-01
 outer loop
  vertex  0.875603E+02  0.687460E+02  0.209150E+01
  vertex  0.877656E+02  0.687460E+02  0.000000E+00
  vertex  0.843554E+02  0.696293E+02  0.000000E+00
 endloop
endfacet
facet normal  0.240572E+00  0.967861E+00  0.732877E-01
 outer loop
  vertex  0.842183E+02  0.696293E+02  0.139670E+01
  vertex  0.838241E+02  0.696293E+02  0.269070E+01
  vertex  0.869700E+02  0.687460E+02  0.402920E+01
 endloop
endfacet
facet normal  0.240563E+00  0.967863E+00  0.732889E-01
 outer loop
  vertex  0.869700E+02  0.687460E+02  0.402920E+01
  vertex  0.875603E+02  0.687460E+02  0.209160E+01
  vertex  0.842182E+02  0.696293E+02  0.139670E+01
 endloop
endfacet
facet normal  0.221320E+00  0.967950E+00  0.118705E+00
 outer loop
  vertex  0.838241E+02  0.696293E+02  0.269070E+01
  vertex  0.831986E+02  0.696294E+02  0.385610E+01
  vertex  0.860333E+02  0.687460E+02  0.577440E+01
 endloop
endfacet
facet normal  0.221250E+00  0.967960E+00  0.118751E+00
 outer loop
  vertex  0.860333E+02  0.687460E+02  0.577440E+01
  vertex  0.869700E+02  0.687460E+02  0.402920E+01
  vertex  0.838240E+02  0.696293E+02  0.269070E+01
 endloop
endfacet
facet normal  0.193764E+00  0.968014E+00  0.159387E+00
 outer loop
  vertex  0.831986E+02  0.696294E+02  0.385610E+01
  vertex  0.823673E+02  0.696293E+02  0.486730E+01
  vertex  0.847885E+02  0.687460E+02  0.728850E+01
 endloop
endfacet
facet normal  0.193819E+00  0.968006E+00  0.159370E+00
 outer loop
  vertex  0.847884E+02  0.687460E+02  0.728840E+01
  vertex  0.860333E+02  0.687460E+02  0.577440E+01
  vertex  0.831986E+02  0.696294E+02  0.385610E+01
 endloop
endfacet
facet normal  0.159348E+00  0.968011E+00  0.193813E+00
 outer loop
  vertex  0.823673E+02  0.696293E+02  0.486730E+01
  vertex  0.813562E+02  0.696293E+02  0.569860E+01
  vertex  0.832744E+02  0.687460E+02  0.853320E+01
 endloop
endfacet
facet normal  0.159327E+00  0.968012E+00  0.193823E+00
 outer loop
  vertex  0.832743E+02  0.687460E+02  0.853320E+01
  vertex  0.847885E+02  0.687460E+02  0.728850E+01
  vertex  0.823673E+02  0.696293E+02  0.486730E+01
 endloop
endfacet
facet normal  0.118745E+00  0.967959E+00  0.221259E+00
 outer loop
  vertex  0.813562E+02  0.696293E+02  0.569860E+01
  vertex  0.801907E+02  0.696293E+02  0.632410E+01
  vertex  0.815292E+02  0.687460E+02  0.947000E+01
 endloop
endfacet
facet normal  0.118760E+00  0.967958E+00  0.221255E+00
 outer loop
  vertex  0.815291E+02  0.687460E+02  0.947000E+01
  vertex  0.832744E+02  0.687460E+02  0.853320E+01
  vertex  0.813562E+02  0.696293E+02  0.569850E+01
 endloop
endfacet
facet normal  0.732866E-01  0.967861E+00  0.240570E+00
 outer loop
  vertex  0.801907E+02  0.696293E+02  0.632410E+01
  vertex  0.788967E+02  0.696293E+02  0.671830E+01
  vertex  0.795916E+02  0.687460E+02  0.100603E+02
 endloop
endfacet
facet normal  0.732762E-01  0.967861E+00  0.240575E+00
 outer loop
  vertex  0.795915E+02  0.687460E+02  0.100602E+02
  vertex  0.815292E+02  0.687460E+02  0.947000E+01
  vertex  0.801906E+02  0.696293E+02  0.632410E+01
 endloop
endfacet
facet normal  0.246055E-01  0.967761E+00  0.250667E+00
 outer loop
  vertex  0.788967E+02  0.696293E+02  0.671830E+01
  vertex  0.775000E+02  0.696293E+02  0.685540E+01
  vertex  0.775000E+02  0.687460E+02  0.102656E+02
 endloop
endfacet
facet normal  0.246033E-01  0.967763E+00  0.250659E+00
 outer loop
  vertex  0.775000E+02  0.687460E+02  0.102656E+02
  vertex  0.795916E+02  0.687460E+02  0.100603E+02
  vertex  0.788966E+02  0.696293E+02  0.671820E+01
 endloop
endfacet
facet normal  0.176507E+00  0.984147E+00  0.173249E-01
 outer loop
  vertex  0.877656E+02  0.687460E+02  0.000000E+00
  vertex  0.875603E+02  0.687460E+02  0.209160E+01
  vertex  0.915224E+02  0.680209E+02  0.291530E+01
 endloop
endfacet
facet normal  0.176509E+00  0.984146E+00  0.173624E-01
 outer loop
  vertex  0.915223E+02  0.680208E+02  0.291520E+01
  vertex  0.918085E+02  0.680209E+02  0.000000E+00
  vertex  0.877656E+02  0.687460E+02  0.000000E+00
 endloop
endfacet
facet normal  0.169389E+00  0.984197E+00  0.516055E-01
 outer loop
  vertex  0.875603E+02  0.687460E+02  0.209160E+01
  vertex  0.869700E+02  0.687460E+02  0.402920E+01
  vertex  0.906996E+02  0.680209E+02  0.561610E+01
 endloop
endfacet
facet normal  0.169381E+00  0.984197E+00  0.516401E-01
 outer loop
  vertex  0.906996E+02  0.680208E+02  0.561600E+01
  vertex  0.915224E+02  0.680209E+02  0.291530E+01
  vertex  0.875603E+02  0.687460E+02  0.209150E+01
 endloop
endfacet
facet normal  0.155783E+00  0.984246E+00  0.836130E-01
 outer loop
  vertex  0.869700E+02  0.687460E+02  0.402920E+01
  vertex  0.860333E+02  0.687460E+02  0.577440E+01
  vertex  0.893940E+02  0.680209E+02  0.804850E+01
 endloop
endfacet
facet normal  0.155763E+00  0.984246E+00  0.836530E-01
 outer loop
  vertex  0.893939E+02  0.680208E+02  0.804850E+01
  vertex  0.906996E+02  0.680209E+02  0.561610E+01
  vertex  0.869700E+02  0.687460E+02  0.402920E+01
 endloop
endfacet
facet normal  0.136449E+00  0.984275E+00  0.112180E+00
 outer loop
  vertex  0.860333E+02  0.687460E+02  0.577440E+01
  vertex  0.847885E+02  0.687460E+02  0.728850E+01
  vertex  0.876591E+02  0.680209E+02  0.101590E+02
 endloop
endfacet
facet normal  0.136441E+00  0.984273E+00  0.112205E+00
 outer loop
  vertex  0.876591E+02  0.680208E+02  0.101590E+02
  vertex  0.893940E+02  0.680209E+02  0.804850E+01
  vertex  0.860333E+02  0.687460E+02  0.577440E+01
 endloop
endfacet
facet normal  0.112177E+00  0.984274E+00  0.136456E+00
 outer loop
  vertex  0.847885E+02  0.687460E+02  0.728850E+01
  vertex  0.832744E+02  0.687460E+02  0.853320E+01
  vertex  0.855485E+02  0.680209E+02  0.118940E+02
 endloop
endfacet
facet normal  0.112144E+00  0.984275E+00  0.136477E+00
 outer loop
  vertex  0.855485E+02  0.680208E+02  0.118940E+02
  vertex  0.876591E+02  0.680209E+02  0.101590E+02
  vertex  0.847884E+02  0.687460E+02  0.728840E+01
 endloop
endfacet
facet normal  0.836191E-01  0.984247E+00  0.155777E+00
 outer loop
  vertex  0.832744E+02  0.687460E+02  0.853320E+01
  vertex  0.815292E+02  0.687460E+02  0.947000E+01
  vertex  0.831161E+02  0.680209E+02  0.131996E+02
 endloop
endfacet
facet normal  0.835810E-01  0.984247E+00  0.155797E+00
 outer loop
  vertex  0.831160E+02  0.680208E+02  0.131996E+02
  vertex  0.855485E+02  0.680209E+02  0.118940E+02
  vertex  0.832743E+02  0.687460E+02  0.853320E+01
 endloop
endfacet
facet normal  0.516055E-01  0.984197E+00  0.169390E+00
 outer loop
  vertex  0.815292E+02  0.687460E+02  0.947000E+01
  vertex  0.795916E+02  0.687460E+02  0.100603E+02
  vertex  0.804153E+02  0.680209E+02  0.140224E+02
 endloop
endfacet
facet normal  0.515650E-01  0.984197E+00  0.169405E+00
 outer loop
  vertex  0.804152E+02  0.680208E+02  0.140223E+02
  vertex  0.831161E+02  0.680209E+02  0.131996E+02
  vertex  0.815291E+02  0.687460E+02  0.947000E+01
 endloop
endfacet
facet normal  0.173252E-01  0.984146E+00  0.176509E+00
 outer loop
  vertex  0.795916E+02  0.687460E+02  0.100603E+02
  vertex  0.775000E+02  0.687460E+02  0.102656E+02
  vertex  0.775000E+02  0.680209E+02  0.143085E+02
 endloop
endfacet
facet normal  0.172888E-01  0.984147E+00  0.176510E+00
 outer loop
  vertex  0.775000E+02  0.680208E+02  0.143085E+02
  vertex  0.804153E+02  0.680209E+02  0.140224E+02
  vertex  0.795915E+02  0.687460E+02  0.100602E+02
 endloop
endfacet
facet normal  0.150101E+00  0.988561E+00  0.147306E-01
 outer loop
  vertex  0.918085E+02  0.680209E+02  0.000000E+00
  vertex  0.915224E+02  0.680209E+02  0.291530E+01
  vertex  0.956912E+02  0.673750E+02  0.378210E+01
 endloop
endfacet
facet normal  0.150074E+00  0.988565E+00  0.147336E-01
 outer loop
  vertex  0.956912E+02  0.673750E+02  0.378200E+01
  vertex  0.960625E+02  0.673750E+02  0.000000E+00
  vertex  0.918085E+02  0.680208E+02  0.000000E+00
 endloop
endfacet
facet normal  0.144042E+00  0.988598E+00  0.438826E-01
 outer loop
  vertex  0.915224E+02  0.680209E+02  0.291530E+01
  vertex  0.906996E+02  0.680209E+02  0.561610E+01
  vertex  0.946239E+02  0.673750E+02  0.728570E+01
 endloop
endfacet
facet normal  0.144019E+00  0.988602E+00  0.438738E-01
 outer loop
  vertex  0.946239E+02  0.673750E+02  0.728560E+01
  vertex  0.956912E+02  0.673750E+02  0.378210E+01
  vertex  0.915223E+02  0.680208E+02  0.291520E+01
 endloop
endfacet
facet normal  0.132469E+00  0.988633E+00  0.711035E-01
 outer loop
  vertex  0.906996E+02  0.680209E+02  0.561610E+01
  vertex  0.893940E+02  0.680209E+02  0.804850E+01
  vertex  0.929300E+02  0.673750E+02  0.104414E+02
 endloop
endfacet
facet normal  0.132445E+00  0.988637E+00  0.710952E-01
 outer loop
  vertex  0.929300E+02  0.673750E+02  0.104413E+02
  vertex  0.946239E+02  0.673750E+02  0.728570E+01
  vertex  0.906996E+02  0.680208E+02  0.561600E+01
 endloop
endfacet
facet normal  0.116041E+00  0.988653E+00  0.953888E-01
 outer loop
  vertex  0.893940E+02  0.680209E+02  0.804850E+01
  vertex  0.876591E+02  0.680209E+02  0.101590E+02
  vertex  0.906793E+02  0.673750E+02  0.131793E+02
 endloop
endfacet
facet normal  0.116017E+00  0.988657E+00  0.953762E-01
 outer loop
  vertex  0.906792E+02  0.673750E+02  0.131793E+02
  vertex  0.929300E+02  0.673750E+02  0.104414E+02
  vertex  0.893939E+02  0.680208E+02  0.804850E+01
 endloop
endfacet
facet normal  0.953885E-01  0.988654E+00  0.116039E+00
 outer loop
  vertex  0.876591E+02  0.680209E+02  0.101590E+02
  vertex  0.855485E+02  0.680209E+02  0.118940E+02
  vertex  0.879414E+02  0.673750E+02  0.154300E+02
 endloop
endfacet
facet normal  0.953738E-01  0.988657E+00  0.116023E+00
 outer loop
  vertex  0.879413E+02  0.673750E+02  0.154300E+02
  vertex  0.906793E+02  0.673750E+02  0.131793E+02
  vertex  0.876591E+02  0.680208E+02  0.101590E+02
 endloop
endfacet
facet normal  0.711024E-01  0.988634E+00  0.132468E+00
 outer loop
  vertex  0.855485E+02  0.680209E+02  0.118940E+02
  vertex  0.831161E+02  0.680209E+02  0.131996E+02
  vertex  0.847857E+02  0.673750E+02  0.171239E+02
 endloop
endfacet
facet normal  0.710901E-01  0.988637E+00  0.132451E+00
 outer loop
  vertex  0.847856E+02  0.673750E+02  0.171238E+02
  vertex  0.879414E+02  0.673750E+02  0.154300E+02
  vertex  0.855485E+02  0.680208E+02  0.118940E+02
 endloop
endfacet
facet normal  0.438833E-01  0.988598E+00  0.144045E+00
 outer loop
  vertex  0.831161E+02  0.680209E+02  0.131996E+02
  vertex  0.804153E+02  0.680209E+02  0.140224E+02
  vertex  0.812821E+02  0.673750E+02  0.181912E+02
 endloop
endfacet
facet normal  0.438720E-01  0.988602E+00  0.144022E+00
 outer loop
  vertex  0.812820E+02  0.673750E+02  0.181912E+02
  vertex  0.847857E+02  0.673750E+02  0.171239E+02
  vertex  0.831160E+02  0.680208E+02  0.131996E+02
 endloop
endfacet
facet normal  0.147304E-01  0.988561E+00  0.150100E+00
 outer loop
  vertex  0.804153E+02  0.680209E+02  0.140224E+02
  vertex  0.775000E+02  0.680209E+02  0.143085E+02
  vertex  0.775000E+02  0.673750E+02  0.185624E+02
 endloop
endfacet
facet normal  0.147293E-01  0.988565E+00  0.150074E+00
 outer loop
  vertex  0.775000E+02  0.673750E+02  0.185624E+02
  vertex  0.812821E+02  0.673750E+02  0.181912E+02
  vertex  0.804152E+02  0.680208E+02  0.140223E+02
 endloop
endfacet
facet normal  0.157764E+00  0.987355E+00  0.154882E-01
 outer loop
  vertex  0.960625E+02  0.673750E+02  0.000000E+00
  vertex  0.956912E+02  0.673750E+02  0.378210E+01
  vertex  0.996533E+02  0.667290E+02  0.460580E+01
 endloop
endfacet
facet normal  0.157767E+00  0.987355E+00  0.155109E-01
 outer loop
  vertex  0.996532E+02  0.667289E+02  0.460580E+01
  vertex  0.100105E+03  0.667290E+02  0.000000E+00
  vertex  0.960625E+02  0.673750E+02  0.000000E+00
 endloop
endfacet
facet normal  0.151403E+00  0.987396E+00  0.461216E-01
 outer loop
  vertex  0.956912E+02  0.673750E+02  0.378210E+01
  vertex  0.946239E+02  0.673750E+02  0.728570E+01
  vertex  0.983535E+02  0.667290E+02  0.887260E+01
 endloop
endfacet
facet normal  0.151397E+00  0.987395E+00  0.461440E-01
 outer loop
  vertex  0.983535E+02  0.667289E+02  0.887250E+01
  vertex  0.996533E+02  0.667290E+02  0.460580E+01
  vertex  0.956912E+02  0.673750E+02  0.378200E+01
 endloop
endfacet
facet normal  0.139235E+00  0.987435E+00  0.747376E-01
 outer loop
  vertex  0.946239E+02  0.673750E+02  0.728570E+01
  vertex  0.929300E+02  0.673750E+02  0.104414E+02
  vertex  0.962907E+02  0.667290E+02  0.127155E+02
 endloop
endfacet
facet normal  0.139222E+00  0.987435E+00  0.747594E-01
 outer loop
  vertex  0.962907E+02  0.667289E+02  0.127154E+02
  vertex  0.983535E+02  0.667290E+02  0.887260E+01
  vertex  0.946239E+02  0.673750E+02  0.728560E+01
 endloop
endfacet
facet normal  0.121965E+00  0.987457E+00  0.100262E+00
 outer loop
  vertex  0.929300E+02  0.673750E+02  0.104414E+02
  vertex  0.906793E+02  0.673750E+02  0.131793E+02
  vertex  0.935498E+02  0.667290E+02  0.160498E+02
 endloop
endfacet
facet normal  0.121951E+00  0.987457E+00  0.100281E+00
 outer loop
  vertex  0.935497E+02  0.667289E+02  0.160498E+02
  vertex  0.962907E+02  0.667290E+02  0.127155E+02
  vertex  0.929300E+02  0.673750E+02  0.104413E+02
 endloop
endfacet
facet normal  0.100263E+00  0.987457E+00  0.121966E+00
 outer loop
  vertex  0.906793E+02  0.673750E+02  0.131793E+02
  vertex  0.879414E+02  0.673750E+02  0.154300E+02
  vertex  0.902155E+02  0.667290E+02  0.187907E+02
 endloop
endfacet
facet normal  0.100241E+00  0.987457E+00  0.121982E+00
 outer loop
  vertex  0.902154E+02  0.667289E+02  0.187907E+02
  vertex  0.935498E+02  0.667290E+02  0.160498E+02
  vertex  0.906792E+02  0.673750E+02  0.131793E+02
 endloop
endfacet
facet normal  0.747371E-01  0.987435E+00  0.139234E+00
 outer loop
  vertex  0.879414E+02  0.673750E+02  0.154300E+02
  vertex  0.847857E+02  0.673750E+02  0.171239E+02
  vertex  0.863726E+02  0.667290E+02  0.208535E+02
 endloop
endfacet
facet normal  0.747173E-01  0.987435E+00  0.139246E+00
 outer loop
  vertex  0.863725E+02  0.667289E+02  0.208535E+02
  vertex  0.902155E+02  0.667290E+02  0.187907E+02
  vertex  0.879413E+02  0.673750E+02  0.154300E+02
 endloop
endfacet
facet normal  0.461216E-01  0.987396E+00  0.151402E+00
 outer loop
  vertex  0.847857E+02  0.673750E+02  0.171239E+02
  vertex  0.812821E+02  0.673750E+02  0.181912E+02
  vertex  0.821058E+02  0.667290E+02  0.221533E+02
 endloop
endfacet
facet normal  0.460961E-01  0.987396E+00  0.151408E+00
 outer loop
  vertex  0.821057E+02  0.667289E+02  0.221532E+02
  vertex  0.863726E+02  0.667290E+02  0.208535E+02
  vertex  0.847856E+02  0.673750E+02  0.171238E+02
 endloop
endfacet
facet normal  0.154839E-01  0.987356E+00  0.157763E+00
 outer loop
  vertex  0.812821E+02  0.673750E+02  0.181912E+02
  vertex  0.775000E+02  0.673750E+02  0.185624E+02
  vertex  0.775000E+02  0.667290E+02  0.226054E+02
 endloop
endfacet
facet normal  0.154652E-01  0.987355E+00  0.157769E+00
 outer loop
  vertex  0.775000E+02  0.667289E+02  0.226054E+02
  vertex  0.821058E+02  0.667290E+02  0.221533E+02
  vertex  0.812820E+02  0.673750E+02  0.181912E+02
 endloop
endfacet
facet normal  0.207933E+00  0.977930E+00  0.204106E-01
 outer loop
  vertex  0.100105E+03  0.667290E+02  0.000000E+00
  vertex  0.996533E+02  0.667290E+02  0.460580E+01
  vertex  0.102995E+03  0.660039E+02  0.530060E+01
 endloop
endfacet
facet normal  0.207906E+00  0.977935E+00  0.204262E-01
 outer loop
  vertex  0.102995E+03  0.660038E+02  0.530060E+01
  vertex  0.103516E+03  0.660039E+02  0.000000E+00
  vertex  0.100105E+03  0.667289E+02  0.000000E+00
 endloop
endfacet
facet normal  0.199554E+00  0.977999E+00  0.607903E-01
 outer loop
  vertex  0.996533E+02  0.667290E+02  0.460580E+01
  vertex  0.983535E+02  0.667290E+02  0.887260E+01
  vertex  0.101499E+03  0.660039E+02  0.102111E+02
 endloop
endfacet
facet normal  0.199517E+00  0.978006E+00  0.608046E-01
 outer loop
  vertex  0.101499E+03  0.660038E+02  0.102110E+02
  vertex  0.102995E+03  0.660039E+02  0.530060E+01
  vertex  0.996532E+02  0.667289E+02  0.460580E+01
 endloop
endfacet
facet normal  0.183522E+00  0.978067E+00  0.985114E-01
 outer loop
  vertex  0.983535E+02  0.667290E+02  0.887260E+01
  vertex  0.962907E+02  0.667290E+02  0.127155E+02
  vertex  0.991254E+02  0.660039E+02  0.146337E+02
 endloop
endfacet
facet normal  0.183485E+00  0.978073E+00  0.985186E-01
 outer loop
  vertex  0.991253E+02  0.660038E+02  0.146337E+02
  vertex  0.101499E+03  0.660039E+02  0.102111E+02
  vertex  0.983535E+02  0.667289E+02  0.887250E+01
 endloop
endfacet
facet normal  0.160766E+00  0.978105E+00  0.132155E+00
 outer loop
  vertex  0.962907E+02  0.667290E+02  0.127155E+02
  vertex  0.935498E+02  0.667290E+02  0.160498E+02
  vertex  0.959710E+02  0.660039E+02  0.184710E+02
 endloop
endfacet
facet normal  0.160731E+00  0.978111E+00  0.132152E+00
 outer loop
  vertex  0.959710E+02  0.660038E+02  0.184710E+02
  vertex  0.991254E+02  0.660039E+02  0.146337E+02
  vertex  0.962907E+02  0.667289E+02  0.127154E+02
 endloop
endfacet
facet normal  0.132155E+00  0.978105E+00  0.160766E+00
 outer loop
  vertex  0.935498E+02  0.667290E+02  0.160498E+02
  vertex  0.902155E+02  0.667290E+02  0.187907E+02
  vertex  0.921337E+02  0.660039E+02  0.216254E+02
 endloop
endfacet
facet normal  0.132120E+00  0.978111E+00  0.160758E+00
 outer loop
  vertex  0.921336E+02  0.660038E+02  0.216254E+02
  vertex  0.959710E+02  0.660039E+02  0.184710E+02
  vertex  0.935497E+02  0.667289E+02  0.160498E+02
 endloop
endfacet
facet normal  0.985106E-01  0.978067E+00  0.183521E+00
 outer loop
  vertex  0.902155E+02  0.667290E+02  0.187907E+02
  vertex  0.863726E+02  0.667290E+02  0.208535E+02
  vertex  0.877111E+02  0.660039E+02  0.239994E+02
 endloop
endfacet
facet normal  0.984772E-01  0.978073E+00  0.183509E+00
 outer loop
  vertex  0.877110E+02  0.660038E+02  0.239993E+02
  vertex  0.921337E+02  0.660039E+02  0.216254E+02
  vertex  0.902154E+02  0.667289E+02  0.187907E+02
 endloop
endfacet
facet normal  0.607902E-01  0.977999E+00  0.199554E+00
 outer loop
  vertex  0.863726E+02  0.667290E+02  0.208535E+02
  vertex  0.821058E+02  0.667290E+02  0.221533E+02
  vertex  0.828006E+02  0.660039E+02  0.254953E+02
 endloop
endfacet
facet normal  0.607637E-01  0.978005E+00  0.199534E+00
 outer loop
  vertex  0.828005E+02  0.660038E+02  0.254953E+02
  vertex  0.877111E+02  0.660039E+02  0.239994E+02
  vertex  0.863725E+02  0.667289E+02  0.208535E+02
 endloop
endfacet
facet normal  0.204106E-01  0.977930E+00  0.207933E+00
 outer loop
  vertex  0.821058E+02  0.667290E+02  0.221533E+02
  vertex  0.775000E+02  0.667290E+02  0.226054E+02
  vertex  0.775000E+02  0.660039E+02  0.260156E+02
 endloop
endfacet
facet normal  0.203892E-01  0.977937E+00  0.207903E+00
 outer loop
  vertex  0.775000E+02  0.660038E+02  0.260156E+02
  vertex  0.828006E+02  0.660039E+02  0.254953E+02
  vertex  0.821057E+02  0.667289E+02  0.221532E+02
 endloop
endfacet
facet normal  0.350922E+00  0.935771E+00  0.344462E-01
 outer loop
  vertex  0.103516E+03  0.660039E+02  0.000000E+00
  vertex  0.102995E+03  0.660039E+02  0.530060E+01
  vertex  0.105304E+03  0.651206E+02  0.578060E+01
 endloop
endfacet
facet normal  0.350889E+00  0.935783E+00  0.344643E-01
 outer loop
  vertex  0.105303E+03  0.651205E+02  0.578060E+01
  vertex  0.105871E+03  0.651206E+02  0.000000E+00
  vertex  0.103516E+03  0.660038E+02  0.000000E+00
 endloop
endfacet
facet normal  0.336819E+00  0.935962E+00  0.102606E+00
 outer loop
  vertex  0.102995E+03  0.660039E+02  0.530060E+01
  vertex  0.101499E+03  0.660039E+02  0.102111E+02
  vertex  0.103672E+03  0.651206E+02  0.111356E+02
 endloop
endfacet
facet normal  0.336785E+00  0.935974E+00  0.102612E+00
 outer loop
  vertex  0.103672E+03  0.651205E+02  0.111356E+02
  vertex  0.105304E+03  0.651206E+02  0.578060E+01
  vertex  0.102995E+03  0.660038E+02  0.530060E+01
 endloop
endfacet
facet normal  0.309789E+00  0.936151E+00  0.166291E+00
 outer loop
  vertex  0.101499E+03  0.660039E+02  0.102111E+02
  vertex  0.991254E+02  0.660039E+02  0.146337E+02
  vertex  0.101083E+03  0.651206E+02  0.159587E+02
 endloop
endfacet
facet normal  0.309744E+00  0.936166E+00  0.166287E+00
 outer loop
  vertex  0.101083E+03  0.651205E+02  0.159587E+02
  vertex  0.103672E+03  0.651206E+02  0.111356E+02
  vertex  0.101499E+03  0.660038E+02  0.102110E+02
 endloop
endfacet
facet normal  0.271397E+00  0.936254E+00  0.223098E+00
 outer loop
  vertex  0.991254E+02  0.660039E+02  0.146337E+02
  vertex  0.959710E+02  0.660039E+02  0.184710E+02
  vertex  0.976434E+02  0.651206E+02  0.201434E+02
 endloop
endfacet
facet normal  0.271350E+00  0.936271E+00  0.223083E+00
 outer loop
  vertex  0.976434E+02  0.651205E+02  0.201434E+02
  vertex  0.101083E+03  0.651206E+02  0.159587E+02
  vertex  0.991253E+02  0.660038E+02  0.146337E+02
 endloop
endfacet
facet normal  0.223096E+00  0.936255E+00  0.271395E+00
 outer loop
  vertex  0.959710E+02  0.660039E+02  0.184710E+02
  vertex  0.921337E+02  0.660039E+02  0.216254E+02
  vertex  0.934587E+02  0.651206E+02  0.235834E+02
 endloop
endfacet
facet normal  0.223065E+00  0.936266E+00  0.271381E+00
 outer loop
  vertex  0.934587E+02  0.651205E+02  0.235834E+02
  vertex  0.976434E+02  0.651206E+02  0.201434E+02
  vertex  0.959710E+02  0.660038E+02  0.184710E+02
 endloop
endfacet
facet normal  0.166296E+00  0.936147E+00  0.309797E+00
 outer loop
  vertex  0.921337E+02  0.660039E+02  0.216254E+02
  vertex  0.877111E+02  0.660039E+02  0.239994E+02
  vertex  0.886356E+02  0.651206E+02  0.261723E+02
 endloop
endfacet
facet normal  0.166251E+00  0.936165E+00  0.309767E+00
 outer loop
  vertex  0.886355E+02  0.651205E+02  0.261723E+02
  vertex  0.934587E+02  0.651206E+02  0.235834E+02
  vertex  0.921336E+02  0.660038E+02  0.216254E+02
 endloop
endfacet
facet normal  0.102607E+00  0.935961E+00  0.336821E+00
 outer loop
  vertex  0.877111E+02  0.660039E+02  0.239994E+02
  vertex  0.828006E+02  0.660039E+02  0.254953E+02
  vertex  0.832806E+02  0.651206E+02  0.278036E+02
 endloop
endfacet
facet normal  0.102576E+00  0.935980E+00  0.336778E+00
 outer loop
  vertex  0.832806E+02  0.651205E+02  0.278036E+02
  vertex  0.886356E+02  0.651206E+02  0.261723E+02
  vertex  0.877110E+02  0.660038E+02  0.239993E+02
 endloop
endfacet
facet normal  0.344463E-01  0.935770E+00  0.350924E+00
 outer loop
  vertex  0.828006E+02  0.660039E+02  0.254953E+02
  vertex  0.775000E+02  0.660039E+02  0.260156E+02
  vertex  0.775000E+02  0.651206E+02  0.283710E+02
 endloop
endfacet
facet normal  0.344258E-01  0.935784E+00  0.350889E+00
 outer loop
  vertex  0.775000E+02  0.651205E+02  0.283710E+02
  vertex  0.832806E+02  0.651206E+02  0.278036E+02
  vertex  0.828005E+02  0.660038E+02  0.254953E+02
 endloop
endfacet
facet normal  0.784492E+00  0.615340E+00  0.770033E-01
 outer loop
  vertex  0.105871E+03  0.651206E+02  0.000000E+00
  vertex  0.105304E+03  0.651206E+02  0.578060E+01
  vertex  0.106165E+03  0.640000E+02  0.595960E+01
 endloop
endfacet
facet normal  0.784457E+00  0.615383E+00  0.770043E-01
 outer loop
  vertex  0.106165E+03  0.640000E+02  0.595950E+01
  vertex  0.106750E+03  0.640000E+02  0.000000E+00
  vertex  0.105871E+03  0.651205E+02  0.000000E+00
 endloop
endfacet
facet normal  0.753602E+00  0.615940E+00  0.229570E+00
 outer loop
  vertex  0.105304E+03  0.651206E+02  0.578060E+01
  vertex  0.103672E+03  0.651206E+02  0.111356E+02
  vertex  0.104483E+03  0.640000E+02  0.114806E+02
 endloop
endfacet
facet normal  0.753533E+00  0.616030E+00  0.229554E+00
 outer loop
  vertex  0.104483E+03  0.640000E+02  0.114806E+02
  vertex  0.106165E+03  0.640000E+02  0.595960E+01
  vertex  0.105303E+03  0.651205E+02  0.578060E+01
 endloop
endfacet
facet normal  0.693694E+00  0.616555E+00  0.372356E+00
 outer loop
  vertex  0.103672E+03  0.651206E+02  0.111356E+02
  vertex  0.101083E+03  0.651206E+02  0.159587E+02
  vertex  0.101814E+03  0.640000E+02  0.164531E+02
 endloop
endfacet
facet normal  0.693671E+00  0.616588E+00  0.372343E+00
 outer loop
  vertex  0.101814E+03  0.640000E+02  0.164531E+02
  vertex  0.104483E+03  0.640000E+02  0.114806E+02
  vertex  0.103672E+03  0.651205E+02  0.111356E+02
 endloop
endfacet
facet normal  0.607980E+00  0.616908E+00  0.499784E+00
 outer loop
  vertex  0.101083E+03  0.651206E+02  0.159587E+02
  vertex  0.976434E+02  0.651206E+02  0.201434E+02
  vertex  0.982675E+02  0.640000E+02  0.207674E+02
 endloop
endfacet
facet normal  0.607948E+00  0.616965E+00  0.499754E+00
 outer loop
  vertex  0.982675E+02  0.640000E+02  0.207674E+02
  vertex  0.101814E+03  0.640000E+02  0.164531E+02
  vertex  0.101083E+03  0.651205E+02  0.159587E+02
 endloop
endfacet
facet normal  0.499791E+00  0.616895E+00  0.607987E+00
 outer loop
  vertex  0.976434E+02  0.651206E+02  0.201434E+02
  vertex  0.934587E+02  0.651206E+02  0.235834E+02
  vertex  0.939531E+02  0.640000E+02  0.243140E+02
 endloop
endfacet
facet normal  0.499761E+00  0.616935E+00  0.607971E+00
 outer loop
  vertex  0.939531E+02  0.640000E+02  0.243139E+02
  vertex  0.982675E+02  0.640000E+02  0.207674E+02
  vertex  0.976434E+02  0.651205E+02  0.201434E+02
 endloop
endfacet
facet normal  0.372355E+00  0.616555E+00  0.693694E+00
 outer loop
  vertex  0.934587E+02  0.651206E+02  0.235834E+02
  vertex  0.886356E+02  0.651206E+02  0.261723E+02
  vertex  0.889806E+02  0.640000E+02  0.269831E+02
 endloop
endfacet
facet normal  0.372339E+00  0.616585E+00  0.693676E+00
 outer loop
  vertex  0.889805E+02  0.640000E+02  0.269831E+02
  vertex  0.939531E+02  0.640000E+02  0.243140E+02
  vertex  0.934587E+02  0.651205E+02  0.235834E+02
 endloop
endfacet
facet normal  0.229577E+00  0.615912E+00  0.753623E+00
 outer loop
  vertex  0.886356E+02  0.651206E+02  0.261723E+02
  vertex  0.832806E+02  0.651206E+02  0.278036E+02
  vertex  0.834596E+02  0.640000E+02  0.286649E+02
 endloop
endfacet
facet normal  0.229539E+00  0.615986E+00  0.753573E+00
 outer loop
  vertex  0.834596E+02  0.640000E+02  0.286648E+02
  vertex  0.889806E+02  0.640000E+02  0.269831E+02
  vertex  0.886355E+02  0.651205E+02  0.261723E+02
 endloop
endfacet
facet normal  0.770049E-01  0.615308E+00  0.784517E+00
 outer loop
  vertex  0.832806E+02  0.651206E+02  0.278036E+02
  vertex  0.775000E+02  0.651206E+02  0.283710E+02
  vertex  0.775000E+02  0.640000E+02  0.292499E+02
 endloop
endfacet
facet normal  0.770074E-01  0.615328E+00  0.784501E+00
 outer loop
  vertex  0.775000E+02  0.640000E+02  0.292499E+02
  vertex  0.834596E+02  0.640000E+02  0.286649E+02
  vertex  0.832806E+02  0.651205E+02  0.278036E+02
 endloop
endfacet
facet normal  0.900064E+00  0.426705E+00  0.883640E-01
 outer loop
  vertex  0.111250E+03  0.640000E+02  0.000000E+00
  vertex  0.110575E+03  0.640000E+02  0.687650E+01
  vertex  0.112631E+03  0.595736E+02  0.730410E+01
 endloop
endfacet
facet normal  0.900080E+00  0.426675E+00  0.883427E-01
 outer loop
  vertex  0.112631E+03  0.595736E+02  0.730410E+01
  vertex  0.113348E+03  0.595736E+02  0.000000E+00
  vertex  0.111250E+03  0.640000E+02  0.000000E+00
 endloop
endfacet
facet normal  0.864886E+00  0.427264E+00  0.263472E+00
 outer loop
  vertex  0.110575E+03  0.640000E+02  0.687650E+01
  vertex  0.108634E+03  0.640000E+02  0.132468E+02
  vertex  0.110570E+03  0.595736E+02  0.140704E+02
 endloop
endfacet
facet normal  0.864868E+00  0.427290E+00  0.263488E+00
 outer loop
  vertex  0.110570E+03  0.595736E+02  0.140704E+02
  vertex  0.112631E+03  0.595736E+02  0.730410E+01
  vertex  0.110575E+03  0.640000E+02  0.687650E+01
 endloop
endfacet
facet normal  0.796387E+00  0.427825E+00  0.427474E+00
 outer loop
  vertex  0.108634E+03  0.640000E+02  0.132468E+02
  vertex  0.105555E+03  0.640000E+02  0.189843E+02
  vertex  0.107299E+03  0.595736E+02  0.201647E+02
 endloop
endfacet
facet normal  0.796380E+00  0.427822E+00  0.427489E+00
 outer loop
  vertex  0.107299E+03  0.595736E+02  0.201646E+02
  vertex  0.110570E+03  0.595736E+02  0.140704E+02
  vertex  0.108634E+03  0.640000E+02  0.132468E+02
 endloop
endfacet
facet normal  0.698123E+00  0.428130E+00  0.573872E+00
 outer loop
  vertex  0.105555E+03  0.640000E+02  0.189843E+02
  vertex  0.101463E+03  0.640000E+02  0.239624E+02
  vertex  0.102952E+03  0.595736E+02  0.254523E+02
 endloop
endfacet
facet normal  0.698109E+00  0.428140E+00  0.573882E+00
 outer loop
  vertex  0.102952E+03  0.595736E+02  0.254522E+02
  vertex  0.107299E+03  0.595736E+02  0.201647E+02
  vertex  0.105555E+03  0.640000E+02  0.189843E+02
 endloop
endfacet
facet normal  0.573869E+00  0.428142E+00  0.698118E+00
 outer loop
  vertex  0.101463E+03  0.640000E+02  0.239624E+02
  vertex  0.964843E+02  0.640000E+02  0.280546E+02
  vertex  0.976647E+02  0.595736E+02  0.297989E+02
 endloop
endfacet
facet normal  0.573878E+00  0.428133E+00  0.698117E+00
 outer loop
  vertex  0.976647E+02  0.595736E+02  0.297989E+02
  vertex  0.102952E+03  0.595736E+02  0.254523E+02
  vertex  0.101463E+03  0.640000E+02  0.239624E+02
 endloop
endfacet
facet normal  0.427475E+00  0.427822E+00  0.796388E+00
 outer loop
  vertex  0.964843E+02  0.640000E+02  0.280546E+02
  vertex  0.907468E+02  0.640000E+02  0.311343E+02
  vertex  0.915704E+02  0.595736E+02  0.330701E+02
 endloop
endfacet
facet normal  0.427451E+00  0.427848E+00  0.796387E+00
 outer loop
  vertex  0.915703E+02  0.595736E+02  0.330700E+02
  vertex  0.976647E+02  0.595736E+02  0.297989E+02
  vertex  0.964842E+02  0.640000E+02  0.280545E+02
 endloop
endfacet
facet normal  0.263472E+00  0.427270E+00  0.864883E+00
 outer loop
  vertex  0.907468E+02  0.640000E+02  0.311343E+02
  vertex  0.843765E+02  0.640000E+02  0.330749E+02
  vertex  0.848040E+02  0.595736E+02  0.351314E+02
 endloop
endfacet
facet normal  0.263477E+00  0.427264E+00  0.864885E+00
 outer loop
  vertex  0.848040E+02  0.595736E+02  0.351314E+02
  vertex  0.915704E+02  0.595736E+02  0.330701E+02
  vertex  0.907468E+02  0.640000E+02  0.311343E+02
 endloop
endfacet
facet normal  0.883512E-01  0.426692E+00  0.900071E+00
 outer loop
  vertex  0.843765E+02  0.640000E+02  0.330749E+02
  vertex  0.775000E+02  0.640000E+02  0.337499E+02
  vertex  0.775000E+02  0.595736E+02  0.358483E+02
 endloop
endfacet
facet normal  0.883431E-01  0.426702E+00  0.900067E+00
 outer loop
  vertex  0.775000E+02  0.595736E+02  0.358483E+02
  vertex  0.848040E+02  0.595736E+02  0.351314E+02
  vertex  0.843765E+02  0.640000E+02  0.330749E+02
 endloop
endfacet
facet normal  0.904485E+00  0.417163E+00  0.887751E-01
 outer loop
  vertex  0.113348E+03  0.595736E+02  0.000000E+00
  vertex  0.112631E+03  0.595736E+02  0.730410E+01
  vertex  0.114623E+03  0.551669E+02  0.771820E+01
 endloop
endfacet
facet normal  0.904472E+00  0.417190E+00  0.887922E-01
 outer loop
  vertex  0.114623E+03  0.551669E+02  0.771820E+01
  vertex  0.115381E+03  0.551669E+02  0.000000E+00
  vertex  0.113348E+03  0.595736E+02  0.000000E+00
 endloop
endfacet
facet normal  0.869138E+00  0.417724E+00  0.264776E+00
 outer loop
  vertex  0.112631E+03  0.595736E+02  0.730410E+01
  vertex  0.110570E+03  0.595736E+02  0.140704E+02
  vertex  0.112445E+03  0.551669E+02  0.148682E+02
 endloop
endfacet
facet normal  0.869134E+00  0.417725E+00  0.264788E+00
 outer loop
  vertex  0.112445E+03  0.551669E+02  0.148682E+02
  vertex  0.114623E+03  0.551669E+02  0.771820E+01
  vertex  0.112631E+03  0.595736E+02  0.730410E+01
 endloop
endfacet
facet normal  0.800314E+00  0.418280E+00  0.429580E+00
 outer loop
  vertex  0.110570E+03  0.595736E+02  0.140704E+02
  vertex  0.107299E+03  0.595736E+02  0.201647E+02
  vertex  0.108988E+03  0.551669E+02  0.213079E+02
 endloop
endfacet
facet normal  0.800306E+00  0.418294E+00  0.429582E+00
 outer loop
  vertex  0.108988E+03  0.551669E+02  0.213078E+02
  vertex  0.112445E+03  0.551669E+02  0.148682E+02
  vertex  0.110570E+03  0.595736E+02  0.140704E+02
 endloop
endfacet
facet normal  0.701557E+00  0.418603E+00  0.576705E+00
 outer loop
  vertex  0.107299E+03  0.595736E+02  0.201647E+02
  vertex  0.102952E+03  0.595736E+02  0.254523E+02
  vertex  0.104395E+03  0.551669E+02  0.268954E+02
 endloop
endfacet
facet normal  0.701557E+00  0.418611E+00  0.576700E+00
 outer loop
  vertex  0.104395E+03  0.551669E+02  0.268953E+02
  vertex  0.108988E+03  0.551669E+02  0.213079E+02
  vertex  0.107299E+03  0.595736E+02  0.201646E+02
 endloop
endfacet
facet normal  0.576711E+00  0.418586E+00  0.701563E+00
 outer loop
  vertex  0.102952E+03  0.595736E+02  0.254523E+02
  vertex  0.976647E+02  0.595736E+02  0.297989E+02
  vertex  0.988079E+02  0.551669E+02  0.314884E+02
 endloop
endfacet
facet normal  0.576679E+00  0.418615E+00  0.701572E+00
 outer loop
  vertex  0.988078E+02  0.551669E+02  0.314883E+02
  vertex  0.104395E+03  0.551669E+02  0.268954E+02
  vertex  0.102952E+03  0.595736E+02  0.254522E+02
 endloop
endfacet
facet normal  0.429579E+00  0.418279E+00  0.800315E+00
 outer loop
  vertex  0.976647E+02  0.595736E+02  0.297989E+02
  vertex  0.915704E+02  0.595736E+02  0.330701E+02
  vertex  0.923682E+02  0.551669E+02  0.349450E+02
 endloop
endfacet
facet normal  0.429571E+00  0.418278E+00  0.800320E+00
 outer loop
  vertex  0.923682E+02  0.551669E+02  0.349449E+02
  vertex  0.988079E+02  0.551669E+02  0.314884E+02
  vertex  0.976647E+02  0.595736E+02  0.297989E+02
 endloop
endfacet
facet normal  0.264772E+00  0.417730E+00  0.869136E+00
 outer loop
  vertex  0.915704E+02  0.595736E+02  0.330701E+02
  vertex  0.848040E+02  0.595736E+02  0.351314E+02
  vertex  0.852182E+02  0.551669E+02  0.371232E+02
 endloop
endfacet
facet normal  0.264763E+00  0.417745E+00  0.869132E+00
 outer loop
  vertex  0.852182E+02  0.551669E+02  0.371231E+02
  vertex  0.923682E+02  0.551669E+02  0.349450E+02
  vertex  0.915703E+02  0.595736E+02  0.330700E+02
 endloop
endfacet
facet normal  0.887763E-01  0.417173E+00  0.904481E+00
 outer loop
  vertex  0.848040E+02  0.595736E+02  0.351314E+02
  vertex  0.775000E+02  0.595736E+02  0.358483E+02
  vertex  0.775000E+02  0.551669E+02  0.378808E+02
 endloop
endfacet
facet normal  0.887703E-01  0.417165E+00  0.904485E+00
 outer loop
  vertex  0.775000E+02  0.551669E+02  0.378807E+02
  vertex  0.852182E+02  0.551669E+02  0.371232E+02
  vertex  0.848040E+02  0.595736E+02  0.351314E+02
 endloop
endfacet
facet normal  0.913232E+00  0.397457E+00  0.896405E-01
 outer loop
  vertex  0.115381E+03  0.551669E+02  0.000000E+00
  vertex  0.114623E+03  0.551669E+02  0.771820E+01
  vertex  0.116486E+03  0.507999E+02  0.810540E+01
 endloop
endfacet
facet normal  0.913225E+00  0.397474E+00  0.896393E-01
 outer loop
  vertex  0.116486E+03  0.507999E+02  0.810540E+01
  vertex  0.117281E+03  0.507999E+02  0.000000E+00
  vertex  0.115381E+03  0.551669E+02  0.000000E+00
 endloop
endfacet
facet normal  0.877558E+00  0.398019E+00  0.267342E+00
 outer loop
  vertex  0.114623E+03  0.551669E+02  0.771820E+01
  vertex  0.112445E+03  0.551669E+02  0.148682E+02
  vertex  0.114198E+03  0.507999E+02  0.156142E+02
 endloop
endfacet
facet normal  0.877561E+00  0.398018E+00  0.267334E+00
 outer loop
  vertex  0.114198E+03  0.507999E+02  0.156141E+02
  vertex  0.116486E+03  0.507999E+02  0.810540E+01
  vertex  0.114623E+03  0.551669E+02  0.771820E+01
 endloop
endfacet
facet normal  0.808096E+00  0.398543E+00  0.433757E+00
 outer loop
  vertex  0.112445E+03  0.551669E+02  0.148682E+02
  vertex  0.108988E+03  0.551669E+02  0.213079E+02
  vertex  0.110568E+03  0.507999E+02  0.223770E+02
 endloop
endfacet
facet normal  0.808077E+00  0.398570E+00  0.433767E+00
 outer loop
  vertex  0.110568E+03  0.507999E+02  0.223770E+02
  vertex  0.114198E+03  0.507999E+02  0.156142E+02
  vertex  0.112445E+03  0.551669E+02  0.148682E+02
 endloop
endfacet
facet normal  0.708405E+00  0.398832E+00  0.582319E+00
 outer loop
  vertex  0.108988E+03  0.551669E+02  0.213079E+02
  vertex  0.104395E+03  0.551669E+02  0.268954E+02
  vertex  0.105745E+03  0.507999E+02  0.282448E+02
 endloop
endfacet
facet normal  0.708386E+00  0.398855E+00  0.582326E+00
 outer loop
  vertex  0.105745E+03  0.507999E+02  0.282448E+02
  vertex  0.110568E+03  0.507999E+02  0.223770E+02
  vertex  0.108988E+03  0.551669E+02  0.213078E+02
 endloop
endfacet
facet normal  0.582315E+00  0.398845E+00  0.708401E+00
 outer loop
  vertex  0.104395E+03  0.551669E+02  0.268954E+02
  vertex  0.988079E+02  0.551669E+02  0.314884E+02
  vertex  0.998770E+02  0.507999E+02  0.330683E+02
 endloop
endfacet
facet normal  0.582308E+00  0.398846E+00  0.708406E+00
 outer loop
  vertex  0.998769E+02  0.507999E+02  0.330682E+02
  vertex  0.105745E+03  0.507999E+02  0.282448E+02
  vertex  0.104395E+03  0.551669E+02  0.268953E+02
 endloop
endfacet
facet normal  0.433755E+00  0.398554E+00  0.808091E+00
 outer loop
  vertex  0.988079E+02  0.551669E+02  0.314884E+02
  vertex  0.923682E+02  0.551669E+02  0.349450E+02
  vertex  0.931142E+02  0.507999E+02  0.366984E+02
 endloop
endfacet
facet normal  0.433744E+00  0.398567E+00  0.808091E+00
 outer loop
  vertex  0.931141E+02  0.507999E+02  0.366983E+02
  vertex  0.998770E+02  0.507999E+02  0.330683E+02
  vertex  0.988078E+02  0.551669E+02  0.314883E+02
 endloop
endfacet
facet normal  0.267345E+00  0.398001E+00  0.877566E+00
 outer loop
  vertex  0.923682E+02  0.551669E+02  0.349450E+02
  vertex  0.852182E+02  0.551669E+02  0.371232E+02
  vertex  0.856054E+02  0.507999E+02  0.389858E+02
 endloop
endfacet
facet normal  0.267329E+00  0.398035E+00  0.877555E+00
 outer loop
  vertex  0.856054E+02  0.507999E+02  0.389858E+02
  vertex  0.931142E+02  0.507999E+02  0.366984E+02
  vertex  0.923682E+02  0.551669E+02  0.349449E+02
 endloop
endfacet
facet normal  0.896406E-01  0.397456E+00  0.913232E+00
 outer loop
  vertex  0.852182E+02  0.551669E+02  0.371232E+02
  vertex  0.775000E+02  0.551669E+02  0.378808E+02
  vertex  0.775000E+02  0.507999E+02  0.397814E+02
 endloop
endfacet
facet normal  0.896278E-01  0.397474E+00  0.913226E+00
 outer loop
  vertex  0.775000E+02  0.507999E+02  0.397813E+02
  vertex  0.856054E+02  0.507999E+02  0.389858E+02
  vertex  0.852182E+02  0.551669E+02  0.371231E+02
 endloop
endfacet
facet normal  0.926127E+00  0.366095E+00  0.909057E-01
 outer loop
  vertex  0.117281E+03  0.507999E+02  0.000000E+00
  vertex  0.116486E+03  0.507999E+02  0.810540E+01
  vertex  0.118155E+03  0.464921E+02  0.845240E+01
 endloop
endfacet
facet normal  0.926123E+00  0.366101E+00  0.909136E-01
 outer loop
  vertex  0.118155E+03  0.464920E+02  0.845240E+01
  vertex  0.118984E+03  0.464921E+02  0.000000E+00
  vertex  0.117281E+03  0.507999E+02  0.000000E+00
 endloop
endfacet
facet normal  0.889993E+00  0.366615E+00  0.271118E+00
 outer loop
  vertex  0.116486E+03  0.507999E+02  0.810540E+01
  vertex  0.114198E+03  0.507999E+02  0.156142E+02
  vertex  0.115769E+03  0.464921E+02  0.162826E+02
 endloop
endfacet
facet normal  0.889993E+00  0.366614E+00  0.271122E+00
 outer loop
  vertex  0.115769E+03  0.464920E+02  0.162826E+02
  vertex  0.118155E+03  0.464921E+02  0.845240E+01
  vertex  0.116486E+03  0.507999E+02  0.810540E+01
 endloop
endfacet
facet normal  0.819566E+00  0.367125E+00  0.439922E+00
 outer loop
  vertex  0.114198E+03  0.507999E+02  0.156142E+02
  vertex  0.110568E+03  0.507999E+02  0.223770E+02
  vertex  0.111984E+03  0.464921E+02  0.233349E+02
 endloop
endfacet
facet normal  0.819558E+00  0.367133E+00  0.439930E+00
 outer loop
  vertex  0.111984E+03  0.464920E+02  0.233348E+02
  vertex  0.115769E+03  0.464921E+02  0.162826E+02
  vertex  0.114198E+03  0.507999E+02  0.156141E+02
 endloop
endfacet
facet normal  0.718465E+00  0.367425E+00  0.590599E+00
 outer loop
  vertex  0.110568E+03  0.507999E+02  0.223770E+02
  vertex  0.105745E+03  0.507999E+02  0.282448E+02
  vertex  0.106954E+03  0.464921E+02  0.294539E+02
 endloop
endfacet
facet normal  0.718463E+00  0.367425E+00  0.590602E+00
 outer loop
  vertex  0.106954E+03  0.464920E+02  0.294538E+02
  vertex  0.111984E+03  0.464921E+02  0.233349E+02
  vertex  0.110568E+03  0.507999E+02  0.223770E+02
 endloop
endfacet
facet normal  0.590602E+00  0.367411E+00  0.718469E+00
 outer loop
  vertex  0.105745E+03  0.507999E+02  0.282448E+02
  vertex  0.998770E+02  0.507999E+02  0.330683E+02
  vertex  0.100835E+03  0.464921E+02  0.344838E+02
 endloop
endfacet
facet normal  0.590573E+00  0.367435E+00  0.718481E+00
 outer loop
  vertex  0.100835E+03  0.464920E+02  0.344837E+02
  vertex  0.106954E+03  0.464921E+02  0.294539E+02
  vertex  0.105745E+03  0.507999E+02  0.282448E+02
 endloop
endfacet
facet normal  0.439922E+00  0.367125E+00  0.819566E+00
 outer loop
  vertex  0.998770E+02  0.507999E+02  0.330683E+02
  vertex  0.931142E+02  0.507999E+02  0.366984E+02
  vertex  0.937826E+02  0.464921E+02  0.382693E+02
 endloop
endfacet
facet normal  0.439905E+00  0.367149E+00  0.819564E+00
 outer loop
  vertex  0.937826E+02  0.464920E+02  0.382692E+02
  vertex  0.100835E+03  0.464921E+02  0.344838E+02
  vertex  0.998769E+02  0.507999E+02  0.330682E+02
 endloop
endfacet
facet normal  0.271119E+00  0.366613E+00  0.889994E+00
 outer loop
  vertex  0.931142E+02  0.507999E+02  0.366984E+02
  vertex  0.856054E+02  0.507999E+02  0.389858E+02
  vertex  0.859524E+02  0.464921E+02  0.406546E+02
 endloop
endfacet
facet normal  0.271100E+00  0.366638E+00  0.889989E+00
 outer loop
  vertex  0.859524E+02  0.464920E+02  0.406545E+02
  vertex  0.937826E+02  0.464921E+02  0.382693E+02
  vertex  0.931141E+02  0.507999E+02  0.366983E+02
 endloop
endfacet
facet normal  0.909050E-01  0.366102E+00  0.926124E+00
 outer loop
  vertex  0.856054E+02  0.507999E+02  0.389858E+02
  vertex  0.775000E+02  0.507999E+02  0.397814E+02
  vertex  0.775000E+02  0.464921E+02  0.414843E+02
 endloop
endfacet
facet normal  0.908950E-01  0.366094E+00  0.926128E+00
 outer loop
  vertex  0.775000E+02  0.464920E+02  0.414842E+02
  vertex  0.859524E+02  0.464921E+02  0.406546E+02
  vertex  0.856054E+02  0.507999E+02  0.389858E+02
 endloop
endfacet
facet normal  0.942605E+00  0.320833E+00  0.925272E-01
 outer loop
  vertex  0.118984E+03  0.464921E+02  0.000000E+00
  vertex  0.118155E+03  0.464921E+02  0.845240E+01
  vertex  0.119565E+03  0.422635E+02  0.874560E+01
 endloop
endfacet
facet normal  0.942602E+00  0.320844E+00  0.925194E-01
 outer loop
  vertex  0.119565E+03  0.422635E+02  0.874550E+01
  vertex  0.120424E+03  0.422635E+02  0.000000E+00
  vertex  0.118984E+03  0.464920E+02  0.000000E+00
 endloop
endfacet
facet normal  0.905880E+00  0.321294E+00  0.275957E+00
 outer loop
  vertex  0.118155E+03  0.464921E+02  0.845240E+01
  vertex  0.115769E+03  0.464921E+02  0.162826E+02
  vertex  0.117097E+03  0.422635E+02  0.168475E+02
 endloop
endfacet
facet normal  0.905874E+00  0.321307E+00  0.275962E+00
 outer loop
  vertex  0.117097E+03  0.422635E+02  0.168474E+02
  vertex  0.119565E+03  0.422635E+02  0.874560E+01
  vertex  0.118155E+03  0.464920E+02  0.845240E+01
 endloop
endfacet
facet normal  0.834234E+00  0.321764E+00  0.447796E+00
 outer loop
  vertex  0.115769E+03  0.464921E+02  0.162826E+02
  vertex  0.111984E+03  0.464921E+02  0.233349E+02
  vertex  0.113180E+03  0.422635E+02  0.241445E+02
 endloop
endfacet
facet normal  0.834232E+00  0.321762E+00  0.447801E+00
 outer loop
  vertex  0.113180E+03  0.422635E+02  0.241445E+02
  vertex  0.117097E+03  0.422635E+02  0.168475E+02
  vertex  0.115769E+03  0.464920E+02  0.162826E+02
 endloop
endfacet
facet normal  0.731361E+00  0.321997E+00  0.601189E+00
 outer loop
  vertex  0.111984E+03  0.464921E+02  0.233349E+02
  vertex  0.106954E+03  0.464921E+02  0.294539E+02
  vertex  0.107976E+03  0.422635E+02  0.304757E+02
 endloop
endfacet
facet normal  0.731340E+00  0.322042E+00  0.601191E+00
 outer loop
  vertex  0.107976E+03  0.422635E+02  0.304757E+02
  vertex  0.113180E+03  0.422635E+02  0.241445E+02
  vertex  0.111984E+03  0.464920E+02  0.233348E+02
 endloop
endfacet
facet normal  0.601183E+00  0.322024E+00  0.731355E+00
 outer loop
  vertex  0.106954E+03  0.464921E+02  0.294539E+02
  vertex  0.100835E+03  0.464921E+02  0.344838E+02
  vertex  0.101645E+03  0.422635E+02  0.356802E+02
 endloop
endfacet
facet normal  0.601189E+00  0.322020E+00  0.731352E+00
 outer loop
  vertex  0.101645E+03  0.422635E+02  0.356801E+02
  vertex  0.107976E+03  0.422635E+02  0.304757E+02
  vertex  0.106954E+03  0.464920E+02  0.294538E+02
 endloop
endfacet
facet normal  0.447797E+00  0.321756E+00  0.834236E+00
 outer loop
  vertex  0.100835E+03  0.464921E+02  0.344838E+02
  vertex  0.937826E+02  0.464921E+02  0.382693E+02
  vertex  0.943475E+02  0.422635E+02  0.395970E+02
 endloop
endfacet
facet normal  0.447787E+00  0.321798E+00  0.834226E+00
 outer loop
  vertex  0.943475E+02  0.422635E+02  0.395970E+02
  vertex  0.101645E+03  0.422635E+02  0.356802E+02
  vertex  0.100835E+03  0.464920E+02  0.344837E+02
 endloop
endfacet
facet normal  0.275956E+00  0.321301E+00  0.905877E+00
 outer loop
  vertex  0.937826E+02  0.464921E+02  0.382693E+02
  vertex  0.859524E+02  0.464921E+02  0.406546E+02
  vertex  0.862456E+02  0.422635E+02  0.420651E+02
 endloop
endfacet
facet normal  0.275954E+00  0.321321E+00  0.905871E+00
 outer loop
  vertex  0.862455E+02  0.422635E+02  0.420651E+02
  vertex  0.943475E+02  0.422635E+02  0.395970E+02
  vertex  0.937826E+02  0.464920E+02  0.382692E+02
 endloop
endfacet
facet normal  0.925281E-01  0.320817E+00  0.942611E+00
 outer loop
  vertex  0.859524E+02  0.464921E+02  0.406546E+02
  vertex  0.775000E+02  0.464921E+02  0.414843E+02
  vertex  0.775000E+02  0.422635E+02  0.429235E+02
 endloop
endfacet
facet normal  0.925179E-01  0.320860E+00  0.942597E+00
 outer loop
  vertex  0.775000E+02  0.422635E+02  0.429235E+02
  vertex  0.862456E+02  0.422635E+02  0.420651E+02
  vertex  0.859524E+02  0.464920E+02  0.406545E+02
 endloop
endfacet
facet normal  0.961440E+00  0.258318E+00  0.943673E-01
 outer loop
  vertex  0.120424E+03  0.422635E+02  0.000000E+00
  vertex  0.119565E+03  0.422635E+02  0.874560E+01
  vertex  0.120652E+03  0.381337E+02  0.897170E+01
 endloop
endfacet
facet normal  0.961431E+00  0.258343E+00  0.943905E-01
 outer loop
  vertex  0.120652E+03  0.381337E+02  0.897160E+01
  vertex  0.121533E+03  0.381337E+02  0.000000E+00
  vertex  0.120424E+03  0.422635E+02  0.000000E+00
 endloop
endfacet
facet normal  0.924030E+00  0.258711E+00  0.281490E+00
 outer loop
  vertex  0.119565E+03  0.422635E+02  0.874560E+01
  vertex  0.117097E+03  0.422635E+02  0.168475E+02
  vertex  0.118121E+03  0.381337E+02  0.172830E+02
 endloop
endfacet
facet normal  0.924025E+00  0.258719E+00  0.281500E+00
 outer loop
  vertex  0.118120E+03  0.381337E+02  0.172830E+02
  vertex  0.120652E+03  0.381337E+02  0.897170E+01
  vertex  0.119565E+03  0.422635E+02  0.874550E+01
 endloop
endfacet
facet normal  0.851003E+00  0.259105E+00  0.456792E+00
 outer loop
  vertex  0.117097E+03  0.422635E+02  0.168475E+02
  vertex  0.113180E+03  0.422635E+02  0.241445E+02
  vertex  0.114103E+03  0.381337E+02  0.247686E+02
 endloop
endfacet
facet normal  0.851004E+00  0.259108E+00  0.456788E+00
 outer loop
  vertex  0.114103E+03  0.381337E+02  0.247686E+02
  vertex  0.118121E+03  0.381337E+02  0.172830E+02
  vertex  0.117097E+03  0.422635E+02  0.168474E+02
 endloop
endfacet
facet normal  0.746070E+00  0.259312E+00  0.613299E+00
 outer loop
  vertex  0.113180E+03  0.422635E+02  0.241445E+02
  vertex  0.107976E+03  0.422635E+02  0.304757E+02
  vertex  0.108763E+03  0.381337E+02  0.312635E+02
 endloop
endfacet
facet normal  0.746058E+00  0.259335E+00  0.613305E+00
 outer loop
  vertex  0.108763E+03  0.381337E+02  0.312635E+02
  vertex  0.114103E+03  0.381337E+02  0.247686E+02
  vertex  0.113180E+03  0.422635E+02  0.241445E+02
 endloop
endfacet
facet normal  0.613298E+00  0.259319E+00  0.746069E+00
 outer loop
  vertex  0.107976E+03  0.422635E+02  0.304757E+02
  vertex  0.101645E+03  0.422635E+02  0.356802E+02
  vertex  0.102269E+03  0.381337E+02  0.366026E+02
 endloop
endfacet
facet normal  0.613302E+00  0.259313E+00  0.746068E+00
 outer loop
  vertex  0.102269E+03  0.381337E+02  0.366026E+02
  vertex  0.108763E+03  0.381337E+02  0.312635E+02
  vertex  0.107976E+03  0.422635E+02  0.304757E+02
 endloop
endfacet
facet normal  0.456793E+00  0.259097E+00  0.851005E+00
 outer loop
  vertex  0.101645E+03  0.422635E+02  0.356802E+02
  vertex  0.943475E+02  0.422635E+02  0.395970E+02
  vertex  0.947830E+02  0.381337E+02  0.406206E+02
 endloop
endfacet
facet normal  0.456782E+00  0.259123E+00  0.851003E+00
 outer loop
  vertex  0.947829E+02  0.381337E+02  0.406206E+02
  vertex  0.102269E+03  0.381337E+02  0.366026E+02
  vertex  0.101645E+03  0.422635E+02  0.356801E+02
 endloop
endfacet
facet normal  0.281489E+00  0.258714E+00  0.924030E+00
 outer loop
  vertex  0.943475E+02  0.422635E+02  0.395970E+02
  vertex  0.862456E+02  0.422635E+02  0.420651E+02
  vertex  0.864717E+02  0.381337E+02  0.431525E+02
 endloop
endfacet
facet normal  0.281491E+00  0.258711E+00  0.924030E+00
 outer loop
  vertex  0.864717E+02  0.381337E+02  0.431525E+02
  vertex  0.947830E+02  0.381337E+02  0.406206E+02
  vertex  0.943475E+02  0.422635E+02  0.395970E+02
 endloop
endfacet
facet normal  0.943667E-01  0.258342E+00  0.961433E+00
 outer loop
  vertex  0.862456E+02  0.422635E+02  0.420651E+02
  vertex  0.775000E+02  0.422635E+02  0.429235E+02
  vertex  0.775000E+02  0.381337E+02  0.440332E+02
 endloop
endfacet
facet normal  0.943682E-01  0.258321E+00  0.961439E+00
 outer loop
  vertex  0.775000E+02  0.381337E+02  0.440331E+02
  vertex  0.864717E+02  0.381337E+02  0.431525E+02
  vertex  0.862455E+02  0.422635E+02  0.420651E+02
 endloop
endfacet
facet normal  0.979954E+00  0.174460E+00  0.961972E-01
 outer loop
  vertex  0.121533E+03  0.381337E+02  0.000000E+00
  vertex  0.120652E+03  0.381337E+02  0.897170E+01
  vertex  0.121352E+03  0.341226E+02  0.911720E+01
 endloop
endfacet
facet normal  0.979954E+00  0.174461E+00  0.961989E-01
 outer loop
  vertex  0.121352E+03  0.341226E+02  0.911710E+01
  vertex  0.122247E+03  0.341226E+02  0.000000E+00
  vertex  0.121533E+03  0.381337E+02  0.000000E+00
 endloop
endfacet
facet normal  0.941878E+00  0.174750E+00  0.286927E+00
 outer loop
  vertex  0.120652E+03  0.381337E+02  0.897170E+01
  vertex  0.118121E+03  0.381337E+02  0.172830E+02
  vertex  0.118779E+03  0.341226E+02  0.175633E+02
 endloop
endfacet
facet normal  0.941877E+00  0.174765E+00  0.286923E+00
 outer loop
  vertex  0.118779E+03  0.341226E+02  0.175632E+02
  vertex  0.121352E+03  0.341226E+02  0.911720E+01
  vertex  0.120652E+03  0.381337E+02  0.897160E+01
 endloop
endfacet
facet normal  0.867496E+00  0.175012E+00  0.465640E+00
 outer loop
  vertex  0.118121E+03  0.381337E+02  0.172830E+02
  vertex  0.114103E+03  0.381337E+02  0.247686E+02
  vertex  0.114696E+03  0.341226E+02  0.251703E+02
 endloop
endfacet
facet normal  0.867482E+00  0.175042E+00  0.465655E+00
 outer loop
  vertex  0.114696E+03  0.341226E+02  0.251702E+02
  vertex  0.118779E+03  0.341226E+02  0.175633E+02
  vertex  0.118120E+03  0.381337E+02  0.172830E+02
 endloop
endfacet
facet normal  0.760550E+00  0.175159E+00  0.625207E+00
 outer loop
  vertex  0.114103E+03  0.381337E+02  0.247686E+02
  vertex  0.108763E+03  0.381337E+02  0.312635E+02
  vertex  0.109271E+03  0.341226E+02  0.317705E+02
 endloop
endfacet
facet normal  0.760547E+00  0.175165E+00  0.625208E+00
 outer loop
  vertex  0.109271E+03  0.341226E+02  0.317705E+02
  vertex  0.114696E+03  0.341226E+02  0.251703E+02
  vertex  0.114103E+03  0.381337E+02  0.247686E+02
 endloop
endfacet
facet normal  0.625206E+00  0.175166E+00  0.760549E+00
 outer loop
  vertex  0.108763E+03  0.381337E+02  0.312635E+02
  vertex  0.102269E+03  0.381337E+02  0.366026E+02
  vertex  0.102670E+03  0.341226E+02  0.371962E+02
 endloop
endfacet
facet normal  0.625208E+00  0.175174E+00  0.760546E+00
 outer loop
  vertex  0.102670E+03  0.341226E+02  0.371962E+02
  vertex  0.109271E+03  0.341226E+02  0.317705E+02
  vertex  0.108763E+03  0.381337E+02  0.312635E+02
 endloop
endfacet
facet normal  0.465642E+00  0.175000E+00  0.867498E+00
 outer loop
  vertex  0.102269E+03  0.381337E+02  0.366026E+02
  vertex  0.947830E+02  0.381337E+02  0.406206E+02
  vertex  0.950633E+02  0.341226E+02  0.412793E+02
 endloop
endfacet
facet normal  0.465635E+00  0.175013E+00  0.867499E+00
 outer loop
  vertex  0.950633E+02  0.341226E+02  0.412793E+02
  vertex  0.102670E+03  0.341226E+02  0.371962E+02
  vertex  0.102269E+03  0.381337E+02  0.366026E+02
 endloop
endfacet
facet normal  0.286929E+00  0.174734E+00  0.941881E+00
 outer loop
  vertex  0.947830E+02  0.381337E+02  0.406206E+02
  vertex  0.864717E+02  0.381337E+02  0.431525E+02
  vertex  0.866172E+02  0.341226E+02  0.438523E+02
 endloop
endfacet
facet normal  0.286922E+00  0.174733E+00  0.941883E+00
 outer loop
  vertex  0.866172E+02  0.341226E+02  0.438522E+02
  vertex  0.950633E+02  0.341226E+02  0.412793E+02
  vertex  0.947829E+02  0.381337E+02  0.406206E+02
 endloop
endfacet
facet normal  0.961963E-01  0.174462E+00  0.979954E+00
 outer loop
  vertex  0.864717E+02  0.381337E+02  0.431525E+02
  vertex  0.775000E+02  0.381337E+02  0.440332E+02
  vertex  0.775000E+02  0.341226E+02  0.447473E+02
 endloop
endfacet
facet normal  0.961878E-01  0.174458E+00  0.979955E+00
 outer loop
  vertex  0.775000E+02  0.341226E+02  0.447472E+02
  vertex  0.866172E+02  0.341226E+02  0.438523E+02
  vertex  0.864717E+02  0.381337E+02  0.431525E+02
 endloop
endfacet
facet normal  0.993125E+00  0.647925E-01  0.974909E-01
 outer loop
  vertex  0.122247E+03  0.341226E+02  0.000000E+00
  vertex  0.121352E+03  0.341226E+02  0.911720E+01
  vertex  0.121600E+03  0.302500E+02  0.916870E+01
 endloop
endfacet
facet normal  0.993121E+00  0.648301E-01  0.975065E-01
 outer loop
  vertex  0.121600E+03  0.302500E+02  0.916870E+01
  vertex  0.122500E+03  0.302500E+02  0.000000E+00
  vertex  0.122247E+03  0.341226E+02  0.000000E+00
 endloop
endfacet
facet normal  0.954585E+00  0.648737E-01  0.290791E+00
 outer loop
  vertex  0.121352E+03  0.341226E+02  0.911720E+01
  vertex  0.118779E+03  0.341226E+02  0.175633E+02
  vertex  0.119012E+03  0.302500E+02  0.176624E+02
 endloop
endfacet
facet normal  0.954575E+00  0.649062E-01  0.290814E+00
 outer loop
  vertex  0.119012E+03  0.302500E+02  0.176623E+02
  vertex  0.121600E+03  0.302500E+02  0.916870E+01
  vertex  0.121352E+03  0.341226E+02  0.911710E+01
 endloop
endfacet
facet normal  0.879229E+00  0.650074E-01  0.471943E+00
 outer loop
  vertex  0.118779E+03  0.341226E+02  0.175633E+02
  vertex  0.114696E+03  0.341226E+02  0.251703E+02
  vertex  0.114906E+03  0.302500E+02  0.253125E+02
 endloop
endfacet
facet normal  0.879232E+00  0.649879E-01  0.471940E+00
 outer loop
  vertex  0.114906E+03  0.302500E+02  0.253125E+02
  vertex  0.119012E+03  0.302500E+02  0.176624E+02
  vertex  0.118779E+03  0.341226E+02  0.175632E+02
 endloop
endfacet
facet normal  0.770853E+00  0.650816E-01  0.633680E+00
 outer loop
  vertex  0.114696E+03  0.341226E+02  0.251703E+02
  vertex  0.109271E+03  0.341226E+02  0.317705E+02
  vertex  0.109450E+03  0.302500E+02  0.319500E+02
 endloop
endfacet
facet normal  0.770850E+00  0.651053E-01  0.633682E+00
 outer loop
  vertex  0.109450E+03  0.302500E+02  0.319500E+02
  vertex  0.114906E+03  0.302500E+02  0.253125E+02
  vertex  0.114696E+03  0.341226E+02  0.251702E+02
 endloop
endfacet
facet normal  0.633681E+00  0.650689E-01  0.770853E+00
 outer loop
  vertex  0.109271E+03  0.341226E+02  0.317705E+02
  vertex  0.102670E+03  0.341226E+02  0.371962E+02
  vertex  0.102813E+03  0.302500E+02  0.374062E+02
 endloop
endfacet
facet normal  0.633675E+00  0.650852E-01  0.770857E+00
 outer loop
  vertex  0.102813E+03  0.302500E+02  0.374062E+02
  vertex  0.109450E+03  0.302500E+02  0.319500E+02
  vertex  0.109271E+03  0.341226E+02  0.317705E+02
 endloop
endfacet
facet normal  0.471933E+00  0.650222E-01  0.879233E+00
 outer loop
  vertex  0.102670E+03  0.341226E+02  0.371962E+02
  vertex  0.950633E+02  0.341226E+02  0.412793E+02
  vertex  0.951624E+02  0.302500E+02  0.415125E+02
 endloop
endfacet
facet normal  0.471935E+00  0.650069E-01  0.879233E+00
 outer loop
  vertex  0.951623E+02  0.302500E+02  0.415125E+02
  vertex  0.102813E+03  0.302500E+02  0.374062E+02
  vertex  0.102670E+03  0.341226E+02  0.371962E+02
 endloop
endfacet
facet normal  0.290801E+00  0.648996E-01  0.954580E+00
 outer loop
  vertex  0.950633E+02  0.341226E+02  0.412793E+02
  vertex  0.866172E+02  0.341226E+02  0.438523E+02
  vertex  0.866687E+02  0.302500E+02  0.440999E+02
 endloop
endfacet
facet normal  0.290780E+00  0.649241E-01  0.954585E+00
 outer loop
  vertex  0.866687E+02  0.302500E+02  0.440998E+02
  vertex  0.951624E+02  0.302500E+02  0.415125E+02
  vertex  0.950633E+02  0.341226E+02  0.412793E+02
 endloop
endfacet
facet normal  0.974912E-01  0.648049E-01  0.993124E+00
 outer loop
  vertex  0.866172E+02  0.341226E+02  0.438523E+02
  vertex  0.775000E+02  0.341226E+02  0.447473E+02
  vertex  0.775000E+02  0.302500E+02  0.450000E+02
 endloop
endfacet
facet normal  0.974959E-01  0.648188E-01  0.993123E+00
 outer loop
  vertex  0.775000E+02  0.302500E+02  0.450000E+02
  vertex  0.866687E+02  0.302500E+02  0.440999E+02
  vertex  0.866172E+02  0.341226E+02  0.438522E+02
 endloop
endfacet
facet normal  0.986267E+00 -0.133805E+00  0.968228E-01
 outer loop
  vertex  0.122500E+03  0.302500E+02  0.000000E+00
  vertex  0.121600E+03  0.302500E+02  0.916870E+01
  vertex  0.121126E+03  0.266871E+02  0.907020E+01
 endloop
endfacet
facet normal  0.986265E+00 -0.133812E+00  0.968301E-01
 outer loop
  vertex  0.121126E+03  0.266870E+02  0.907010E+01
  vertex  0.122017E+03  0.266871E+02  0.000000E+00
  vertex  0.122500E+03  0.302500E+02  0.000000E+00
 endloop
endfacet
facet normal  0.947967E+00 -0.134015E+00  0.288787E+00
 outer loop
  vertex  0.121600E+03  0.302500E+02  0.916870E+01
  vertex  0.119012E+03  0.302500E+02  0.176624E+02
  vertex  0.118566E+03  0.266871E+02  0.174727E+02
 endloop
endfacet
facet normal  0.947968E+00 -0.133994E+00  0.288794E+00
 outer loop
  vertex  0.118566E+03  0.266870E+02  0.174727E+02
  vertex  0.121126E+03  0.266871E+02  0.907020E+01
  vertex  0.121600E+03  0.302500E+02  0.916870E+01
 endloop
endfacet
facet normal  0.873124E+00 -0.134241E+00  0.468651E+00
 outer loop
  vertex  0.119012E+03  0.302500E+02  0.176624E+02
  vertex  0.114906E+03  0.302500E+02  0.253125E+02
  vertex  0.114504E+03  0.266871E+02  0.250405E+02
 endloop
endfacet
facet normal  0.873128E+00 -0.134188E+00  0.468659E+00
 outer loop
  vertex  0.114504E+03  0.266870E+02  0.250405E+02
  vertex  0.118566E+03  0.266871E+02  0.174727E+02
  vertex  0.119012E+03  0.302500E+02  0.176623E+02
 endloop
endfacet
facet normal  0.765489E+00 -0.134369E+00  0.629263E+00
 outer loop
  vertex  0.114906E+03  0.302500E+02  0.253125E+02
  vertex  0.109450E+03  0.302500E+02  0.319500E+02
  vertex  0.109107E+03  0.266871E+02  0.316067E+02
 endloop
endfacet
facet normal  0.765486E+00 -0.134344E+00  0.629272E+00
 outer loop
  vertex  0.109107E+03  0.266870E+02  0.316067E+02
  vertex  0.114504E+03  0.266871E+02  0.250405E+02
  vertex  0.114906E+03  0.302500E+02  0.253125E+02
 endloop
endfacet
facet normal  0.629262E+00 -0.134367E+00  0.765490E+00
 outer loop
  vertex  0.109450E+03  0.302500E+02  0.319500E+02
  vertex  0.102813E+03  0.302500E+02  0.374062E+02
  vertex  0.102540E+03  0.266871E+02  0.370044E+02
 endloop
endfacet
facet normal  0.629254E+00 -0.134355E+00  0.765499E+00
 outer loop
  vertex  0.102540E+03  0.266870E+02  0.370043E+02
  vertex  0.109107E+03  0.266871E+02  0.316067E+02
  vertex  0.109450E+03  0.302500E+02  0.319500E+02
 endloop
endfacet
facet normal  0.468659E+00 -0.134248E+00  0.873119E+00
 outer loop
  vertex  0.102813E+03  0.302500E+02  0.374062E+02
  vertex  0.951624E+02  0.302500E+02  0.415125E+02
  vertex  0.949727E+02  0.266871E+02  0.410665E+02
 endloop
endfacet
facet normal  0.468659E+00 -0.134244E+00  0.873119E+00
 outer loop
  vertex  0.949727E+02  0.266870E+02  0.410665E+02
  vertex  0.102540E+03  0.266871E+02  0.370044E+02
  vertex  0.102813E+03  0.302500E+02  0.374062E+02
 endloop
endfacet
facet normal  0.288776E+00 -0.134019E+00  0.947970E+00
 outer loop
  vertex  0.951624E+02  0.302500E+02  0.415125E+02
  vertex  0.866687E+02  0.302500E+02  0.440999E+02
  vertex  0.865702E+02  0.266871E+02  0.436262E+02
 endloop
endfacet
facet normal  0.288782E+00 -0.134033E+00  0.947966E+00
 outer loop
  vertex  0.865701E+02  0.266870E+02  0.436262E+02
  vertex  0.949727E+02  0.266871E+02  0.410665E+02
  vertex  0.951623E+02  0.302500E+02  0.415125E+02
 endloop
endfacet
facet normal  0.968227E-01 -0.133812E+00  0.986266E+00
 outer loop
  vertex  0.866687E+02  0.302500E+02  0.440999E+02
  vertex  0.775000E+02  0.302500E+02  0.450000E+02
  vertex  0.775000E+02  0.266871E+02  0.445166E+02
 endloop
endfacet
facet normal  0.968213E-01 -0.133777E+00  0.986270E+00
 outer loop
  vertex  0.775000E+02  0.266870E+02  0.445166E+02
  vertex  0.865702E+02  0.266871E+02  0.436262E+02
  vertex  0.866687E+02  0.302500E+02  0.440998E+02
 endloop
endfacet
facet normal  0.921447E+00 -0.377827E+00  0.904566E-01
 outer loop
  vertex  0.122017E+03  0.266871E+02  0.000000E+00
  vertex  0.121126E+03  0.266871E+02  0.907020E+01
  vertex  0.119877E+03  0.235791E+02  0.881050E+01
 endloop
endfacet
facet normal  0.921432E+00 -0.377864E+00  0.904506E-01
 outer loop
  vertex  0.119877E+03  0.235790E+02  0.881050E+01
  vertex  0.120742E+03  0.235791E+02  0.000000E+00
  vertex  0.122017E+03  0.266870E+02  0.000000E+00
 endloop
endfacet
facet normal  0.885487E+00 -0.378348E+00  0.269751E+00
 outer loop
  vertex  0.121126E+03  0.266871E+02  0.907020E+01
  vertex  0.118566E+03  0.266871E+02  0.174727E+02
  vertex  0.117391E+03  0.235791E+02  0.169725E+02
 endloop
endfacet
facet normal  0.885490E+00 -0.378336E+00  0.269757E+00
 outer loop
  vertex  0.117391E+03  0.235790E+02  0.169724E+02
  vertex  0.119877E+03  0.235791E+02  0.881050E+01
  vertex  0.121126E+03  0.266870E+02  0.907010E+01
 endloop
endfacet
facet normal  0.815405E+00 -0.378883E+00  0.437677E+00
 outer loop
  vertex  0.118566E+03  0.266871E+02  0.174727E+02
  vertex  0.114504E+03  0.266871E+02  0.250405E+02
  vertex  0.113445E+03  0.235791E+02  0.243237E+02
 endloop
endfacet
facet normal  0.815407E+00 -0.378856E+00  0.437698E+00
 outer loop
  vertex  0.113445E+03  0.235790E+02  0.243236E+02
  vertex  0.117391E+03  0.235791E+02  0.169725E+02
  vertex  0.118566E+03  0.266870E+02  0.174727E+02
 endloop
endfacet
facet normal  0.714812E+00 -0.379160E+00  0.587607E+00
 outer loop
  vertex  0.114504E+03  0.266871E+02  0.250405E+02
  vertex  0.109107E+03  0.266871E+02  0.316067E+02
  vertex  0.108202E+03  0.235791E+02  0.307019E+02
 endloop
endfacet
facet normal  0.714806E+00 -0.379182E+00  0.587600E+00
 outer loop
  vertex  0.108202E+03  0.235790E+02  0.307019E+02
  vertex  0.113445E+03  0.235791E+02  0.243237E+02
  vertex  0.114504E+03  0.266870E+02  0.250405E+02
 endloop
endfacet
facet normal  0.587604E+00 -0.379170E+00  0.714809E+00
 outer loop
  vertex  0.109107E+03  0.266871E+02  0.316067E+02
  vertex  0.102540E+03  0.266871E+02  0.370044E+02
  vertex  0.101824E+03  0.235791E+02  0.359450E+02
 endloop
endfacet
facet normal  0.587596E+00 -0.379154E+00  0.714824E+00
 outer loop
  vertex  0.101824E+03  0.235790E+02  0.359449E+02
  vertex  0.108202E+03  0.235791E+02  0.307019E+02
  vertex  0.109107E+03  0.266870E+02  0.316067E+02
 endloop
endfacet
facet normal  0.437681E+00 -0.378869E+00  0.815410E+00
 outer loop
  vertex  0.102540E+03  0.266871E+02  0.370044E+02
  vertex  0.949727E+02  0.266871E+02  0.410665E+02
  vertex  0.944725E+02  0.235791E+02  0.398909E+02
 endloop
endfacet
facet normal  0.437684E+00 -0.378858E+00  0.815414E+00
 outer loop
  vertex  0.944725E+02  0.235790E+02  0.398908E+02
  vertex  0.101824E+03  0.235791E+02  0.359450E+02
  vertex  0.102540E+03  0.266870E+02  0.370043E+02
 endloop
endfacet
facet normal  0.269750E+00 -0.378357E+00  0.885483E+00
 outer loop
  vertex  0.949727E+02  0.266871E+02  0.410665E+02
  vertex  0.865702E+02  0.266871E+02  0.436262E+02
  vertex  0.863105E+02  0.235791E+02  0.423773E+02
 endloop
endfacet
facet normal  0.269750E+00 -0.378359E+00  0.885482E+00
 outer loop
  vertex  0.863105E+02  0.235790E+02  0.423773E+02
  vertex  0.944725E+02  0.235791E+02  0.398909E+02
  vertex  0.949727E+02  0.266870E+02  0.410665E+02
 endloop
endfacet
facet normal  0.904552E-01 -0.377854E+00  0.921436E+00
 outer loop
  vertex  0.865702E+02  0.266871E+02  0.436262E+02
  vertex  0.775000E+02  0.266871E+02  0.445166E+02
  vertex  0.775000E+02  0.235791E+02  0.432421E+02
 endloop
endfacet
facet normal  0.904389E-01 -0.377835E+00  0.921446E+00
 outer loop
  vertex  0.775000E+02  0.235790E+02  0.432420E+02
  vertex  0.863105E+02  0.235791E+02  0.423773E+02
  vertex  0.865701E+02  0.266870E+02  0.436262E+02
 endloop
endfacet
facet normal  0.826482E+00 -0.557087E+00  0.811245E-01
 outer loop
  vertex  0.120742E+03  0.235791E+02  0.000000E+00
  vertex  0.119877E+03  0.235791E+02  0.881050E+01
  vertex  0.118112E+03  0.209061E+02  0.844340E+01
 endloop
endfacet
facet normal  0.826476E+00 -0.557097E+00  0.811196E-01
 outer loop
  vertex  0.118112E+03  0.209060E+02  0.844340E+01
  vertex  0.118940E+03  0.209061E+02  0.000000E+00
  vertex  0.120742E+03  0.235790E+02  0.000000E+00
 endloop
endfacet
facet normal  0.793994E+00 -0.557737E+00  0.241875E+00
 outer loop
  vertex  0.119877E+03  0.235791E+02  0.881050E+01
  vertex  0.117391E+03  0.235791E+02  0.169725E+02
  vertex  0.115729E+03  0.209061E+02  0.162653E+02
 endloop
endfacet
facet normal  0.794009E+00 -0.557707E+00  0.241894E+00
 outer loop
  vertex  0.115729E+03  0.209060E+02  0.162653E+02
  vertex  0.118112E+03  0.209061E+02  0.844340E+01
  vertex  0.119877E+03  0.235790E+02  0.881050E+01
 endloop
endfacet
facet normal  0.730969E+00 -0.558334E+00  0.392362E+00
 outer loop
  vertex  0.117391E+03  0.235791E+02  0.169725E+02
  vertex  0.113445E+03  0.235791E+02  0.243237E+02
  vertex  0.111947E+03  0.209061E+02  0.233102E+02
 endloop
endfacet
facet normal  0.730972E+00 -0.558338E+00  0.392351E+00
 outer loop
  vertex  0.111947E+03  0.209060E+02  0.233101E+02
  vertex  0.115729E+03  0.209061E+02  0.162653E+02
  vertex  0.117391E+03  0.235790E+02  0.169724E+02
 endloop
endfacet
facet normal  0.640703E+00 -0.558666E+00  0.526680E+00
 outer loop
  vertex  0.113445E+03  0.235791E+02  0.243237E+02
  vertex  0.108202E+03  0.235791E+02  0.307019E+02
  vertex  0.106923E+03  0.209061E+02  0.294227E+02
 endloop
endfacet
facet normal  0.640707E+00 -0.558665E+00  0.526676E+00
 outer loop
  vertex  0.106923E+03  0.209060E+02  0.294227E+02
  vertex  0.111947E+03  0.209061E+02  0.233102E+02
  vertex  0.113445E+03  0.235790E+02  0.243236E+02
 endloop
endfacet
facet normal  0.526674E+00 -0.558680E+00  0.640696E+00
 outer loop
  vertex  0.108202E+03  0.235791E+02  0.307019E+02
  vertex  0.101824E+03  0.235791E+02  0.359450E+02
  vertex  0.100810E+03  0.209061E+02  0.344473E+02
 endloop
endfacet
facet normal  0.526674E+00 -0.558667E+00  0.640708E+00
 outer loop
  vertex  0.100810E+03  0.209060E+02  0.344472E+02
  vertex  0.106923E+03  0.209061E+02  0.294227E+02
  vertex  0.108202E+03  0.235790E+02  0.307019E+02
 endloop
endfacet
facet normal  0.392356E+00 -0.558352E+00  0.730958E+00
 outer loop
  vertex  0.101824E+03  0.235791E+02  0.359450E+02
  vertex  0.944725E+02  0.235791E+02  0.398909E+02
  vertex  0.937653E+02  0.209061E+02  0.382287E+02
 endloop
endfacet
facet normal  0.392353E+00 -0.558319E+00  0.730985E+00
 outer loop
  vertex  0.937652E+02  0.209060E+02  0.382286E+02
  vertex  0.100810E+03  0.209061E+02  0.344473E+02
  vertex  0.101824E+03  0.235790E+02  0.359449E+02
 endloop
endfacet
facet normal  0.241879E+00 -0.557716E+00  0.794007E+00
 outer loop
  vertex  0.944725E+02  0.235791E+02  0.398909E+02
  vertex  0.863105E+02  0.235791E+02  0.423773E+02
  vertex  0.859434E+02  0.209061E+02  0.406116E+02
 endloop
endfacet
facet normal  0.241881E+00 -0.557732E+00  0.793996E+00
 outer loop
  vertex  0.859433E+02  0.209060E+02  0.406115E+02
  vertex  0.937653E+02  0.209061E+02  0.382287E+02
  vertex  0.944725E+02  0.235790E+02  0.398908E+02
 endloop
endfacet
facet normal  0.811241E-01 -0.557082E+00  0.826486E+00
 outer loop
  vertex  0.863105E+02  0.235791E+02  0.423773E+02
  vertex  0.775000E+02  0.235791E+02  0.432421E+02
  vertex  0.775000E+02  0.209061E+02  0.414404E+02
 endloop
endfacet
facet normal  0.811229E-01 -0.557103E+00  0.826471E+00
 outer loop
  vertex  0.775000E+02  0.209060E+02  0.414403E+02
  vertex  0.859434E+02  0.209061E+02  0.406116E+02
  vertex  0.863105E+02  0.235790E+02  0.423773E+02
 endloop
endfacet
facet normal  0.735902E+00 -0.673224E+00  0.722355E-01
 outer loop
  vertex  0.118940E+03  0.209061E+02  0.000000E+00
  vertex  0.118112E+03  0.209061E+02  0.844340E+01
  vertex  0.116088E+03  0.186484E+02  0.802260E+01
 endloop
endfacet
facet normal  0.735905E+00 -0.673221E+00  0.722281E-01
 outer loop
  vertex  0.116088E+03  0.186483E+02  0.802260E+01
  vertex  0.116875E+03  0.186484E+02  0.000000E+00
  vertex  0.118940E+03  0.209060E+02  0.000000E+00
 endloop
endfacet
facet normal  0.706825E+00 -0.673818E+00  0.215331E+00
 outer loop
  vertex  0.118112E+03  0.209061E+02  0.844340E+01
  vertex  0.115729E+03  0.209061E+02  0.162653E+02
  vertex  0.113823E+03  0.186484E+02  0.154546E+02
 endloop
endfacet
facet normal  0.706810E+00 -0.673839E+00  0.215315E+00
 outer loop
  vertex  0.113823E+03  0.186483E+02  0.154546E+02
  vertex  0.116088E+03  0.186484E+02  0.802260E+01
  vertex  0.118112E+03  0.209060E+02  0.844340E+01
 endloop
endfacet
facet normal  0.650558E+00 -0.674419E+00  0.349191E+00
 outer loop
  vertex  0.115729E+03  0.209061E+02  0.162653E+02
  vertex  0.111947E+03  0.209061E+02  0.233102E+02
  vertex  0.110230E+03  0.186484E+02  0.221484E+02
 endloop
endfacet
facet normal  0.650564E+00 -0.674409E+00  0.349196E+00
 outer loop
  vertex  0.110230E+03  0.186483E+02  0.221483E+02
  vertex  0.113823E+03  0.186484E+02  0.154546E+02
  vertex  0.115729E+03  0.209060E+02  0.162653E+02
 endloop
endfacet
facet normal  0.570136E+00 -0.674758E+00  0.468664E+00
 outer loop
  vertex  0.111947E+03  0.209061E+02  0.233102E+02
  vertex  0.106923E+03  0.209061E+02  0.294227E+02
  vertex  0.105456E+03  0.186484E+02  0.279562E+02
 endloop
endfacet
facet normal  0.570133E+00 -0.674753E+00  0.468674E+00
 outer loop
  vertex  0.105456E+03  0.186483E+02  0.279561E+02
  vertex  0.110230E+03  0.186484E+02  0.221484E+02
  vertex  0.111947E+03  0.209060E+02  0.233101E+02
 endloop
endfacet
facet normal  0.468669E+00 -0.674749E+00  0.570143E+00
 outer loop
  vertex  0.106923E+03  0.209061E+02  0.294227E+02
  vertex  0.100810E+03  0.209061E+02  0.344473E+02
  vertex  0.996484E+02  0.186484E+02  0.327304E+02
 endloop
endfacet
facet normal  0.468667E+00 -0.674763E+00  0.570128E+00
 outer loop
  vertex  0.996483E+02  0.186483E+02  0.327304E+02
  vertex  0.105456E+03  0.186484E+02  0.279562E+02
  vertex  0.106923E+03  0.209060E+02  0.294227E+02
 endloop
endfacet
facet normal  0.349195E+00 -0.674409E+00  0.650565E+00
 outer loop
  vertex  0.100810E+03  0.209061E+02  0.344473E+02
  vertex  0.937653E+02  0.209061E+02  0.382287E+02
  vertex  0.929546E+02  0.186484E+02  0.363234E+02
 endloop
endfacet
facet normal  0.349191E+00 -0.674419E+00  0.650557E+00
 outer loop
  vertex  0.929545E+02  0.186483E+02  0.363233E+02
  vertex  0.996484E+02  0.186484E+02  0.327304E+02
  vertex  0.100810E+03  0.209060E+02  0.344472E+02
 endloop
endfacet
facet normal  0.215330E+00 -0.673822E+00  0.706822E+00
 outer loop
  vertex  0.937653E+02  0.209061E+02  0.382287E+02
  vertex  0.859434E+02  0.209061E+02  0.406116E+02
  vertex  0.855226E+02  0.186484E+02  0.385875E+02
 endloop
endfacet
facet normal  0.215336E+00 -0.673813E+00  0.706828E+00
 outer loop
  vertex  0.855225E+02  0.186483E+02  0.385875E+02
  vertex  0.929546E+02  0.186484E+02  0.363234E+02
  vertex  0.937652E+02  0.209060E+02  0.382286E+02
 endloop
endfacet
facet normal  0.722359E-01 -0.673222E+00  0.735903E+00
 outer loop
  vertex  0.859434E+02  0.209061E+02  0.406116E+02
  vertex  0.775000E+02  0.209061E+02  0.414404E+02
  vertex  0.775000E+02  0.186484E+02  0.393750E+02
 endloop
endfacet
facet normal  0.722447E-01 -0.673220E+00  0.735904E+00
 outer loop
  vertex  0.775000E+02  0.186483E+02  0.393750E+02
  vertex  0.855226E+02  0.186484E+02  0.385875E+02
  vertex  0.859433E+02  0.209060E+02  0.406115E+02
 endloop
endfacet
facet normal  0.668167E+00 -0.741115E+00  0.655873E-01
 outer loop
  vertex  0.116875E+03  0.186484E+02  0.000000E+00
  vertex  0.116088E+03  0.186484E+02  0.802260E+01
  vertex  0.114063E+03  0.167862E+02  0.760180E+01
 endloop
endfacet
facet normal  0.668149E+00 -0.741132E+00  0.655774E-01
 outer loop
  vertex  0.114063E+03  0.167861E+02  0.760170E+01
  vertex  0.114810E+03  0.167862E+02  0.000000E+00
  vertex  0.116875E+03  0.186483E+02  0.000000E+00
 endloop
endfacet
facet normal  0.641672E+00 -0.741650E+00  0.195480E+00
 outer loop
  vertex  0.116088E+03  0.186484E+02  0.802260E+01
  vertex  0.113823E+03  0.186484E+02  0.154546E+02
  vertex  0.111918E+03  0.167862E+02  0.146440E+02
 endloop
endfacet
facet normal  0.641647E+00 -0.741675E+00  0.195467E+00
 outer loop
  vertex  0.111918E+03  0.167861E+02  0.146440E+02
  vertex  0.114063E+03  0.167862E+02  0.760180E+01
  vertex  0.116088E+03  0.186483E+02  0.802260E+01
 endloop
endfacet
facet normal  0.590507E+00 -0.742183E+00  0.316964E+00
 outer loop
  vertex  0.113823E+03  0.186484E+02  0.154546E+02
  vertex  0.110230E+03  0.186484E+02  0.221484E+02
  vertex  0.108513E+03  0.167862E+02  0.209866E+02
 endloop
endfacet
facet normal  0.590492E+00 -0.742199E+00  0.316955E+00
 outer loop
  vertex  0.108513E+03  0.167861E+02  0.209866E+02
  vertex  0.111918E+03  0.167862E+02  0.146440E+02
  vertex  0.113823E+03  0.186483E+02  0.154546E+02
 endloop
endfacet
facet normal  0.517463E+00 -0.742490E+00  0.425371E+00
 outer loop
  vertex  0.110230E+03  0.186484E+02  0.221484E+02
  vertex  0.105456E+03  0.186484E+02  0.279562E+02
  vertex  0.103990E+03  0.167862E+02  0.264897E+02
 endloop
endfacet
facet normal  0.517467E+00 -0.742489E+00  0.425368E+00
 outer loop
  vertex  0.103990E+03  0.167861E+02  0.264897E+02
  vertex  0.108513E+03  0.167862E+02  0.209866E+02
  vertex  0.110230E+03  0.186483E+02  0.221483E+02
 endloop
endfacet
facet normal  0.425378E+00 -0.742481E+00  0.517471E+00
 outer loop
  vertex  0.105456E+03  0.186484E+02  0.279562E+02
  vertex  0.996484E+02  0.186484E+02  0.327304E+02
  vertex  0.984866E+02  0.167862E+02  0.310135E+02
 endloop
endfacet
facet normal  0.425386E+00 -0.742486E+00  0.517456E+00
 outer loop
  vertex  0.984866E+02  0.167861E+02  0.310135E+02
  vertex  0.103990E+03  0.167862E+02  0.264897E+02
  vertex  0.105456E+03  0.186483E+02  0.279561E+02
 endloop
endfacet
facet normal  0.316965E+00 -0.742180E+00  0.590510E+00
 outer loop
  vertex  0.996484E+02  0.186484E+02  0.327304E+02
  vertex  0.929546E+02  0.186484E+02  0.363234E+02
  vertex  0.921440E+02  0.167862E+02  0.344180E+02
 endloop
endfacet
facet normal  0.316958E+00 -0.742192E+00  0.590499E+00
 outer loop
  vertex  0.921439E+02  0.167861E+02  0.344179E+02
  vertex  0.984866E+02  0.167862E+02  0.310135E+02
  vertex  0.996483E+02  0.186483E+02  0.327304E+02
 endloop
endfacet
facet normal  0.195478E+00 -0.741657E+00  0.641664E+00
 outer loop
  vertex  0.929546E+02  0.186484E+02  0.363234E+02
  vertex  0.855226E+02  0.186484E+02  0.385875E+02
  vertex  0.851018E+02  0.167862E+02  0.365633E+02
 endloop
endfacet
facet normal  0.195484E+00 -0.741647E+00  0.641674E+00
 outer loop
  vertex  0.851017E+02  0.167861E+02  0.365633E+02
  vertex  0.921440E+02  0.167862E+02  0.344180E+02
  vertex  0.929545E+02  0.186483E+02  0.363233E+02
 endloop
endfacet
facet normal  0.655875E-01 -0.741113E+00  0.668169E+00
 outer loop
  vertex  0.855226E+02  0.186484E+02  0.385875E+02
  vertex  0.775000E+02  0.186484E+02  0.393750E+02
  vertex  0.775000E+02  0.167862E+02  0.373095E+02
 endloop
endfacet
facet normal  0.655958E-01 -0.741131E+00  0.668148E+00
 outer loop
  vertex  0.775000E+02  0.167861E+02  0.373095E+02
  vertex  0.851018E+02  0.167862E+02  0.365633E+02
  vertex  0.855225E+02  0.186483E+02  0.385875E+02
 endloop
endfacet
facet normal  0.635137E+00 -0.769880E+00  0.623457E-01
 outer loop
  vertex  0.114810E+03  0.167862E+02  0.000000E+00
  vertex  0.114063E+03  0.167862E+02  0.760180E+01
  vertex  0.112298E+03  0.152998E+02  0.723470E+01
 endloop
endfacet
facet normal  0.635118E+00 -0.769895E+00  0.623447E-01
 outer loop
  vertex  0.112298E+03  0.152997E+02  0.723470E+01
  vertex  0.113008E+03  0.152998E+02  0.000000E+00
  vertex  0.114810E+03  0.167861E+02  0.000000E+00
 endloop
endfacet
facet normal  0.609899E+00 -0.770391E+00  0.185797E+00
 outer loop
  vertex  0.114063E+03  0.167862E+02  0.760180E+01
  vertex  0.111918E+03  0.167862E+02  0.146440E+02
  vertex  0.110256E+03  0.152998E+02  0.139368E+02
 endloop
endfacet
facet normal  0.609882E+00 -0.770406E+00  0.185790E+00
 outer loop
  vertex  0.110256E+03  0.152997E+02  0.139368E+02
  vertex  0.112298E+03  0.152998E+02  0.723470E+01
  vertex  0.114063E+03  0.167861E+02  0.760170E+01
 endloop
endfacet
facet normal  0.561224E+00 -0.770894E+00  0.301247E+00
 outer loop
  vertex  0.111918E+03  0.167862E+02  0.146440E+02
  vertex  0.108513E+03  0.167862E+02  0.209866E+02
  vertex  0.107016E+03  0.152998E+02  0.199731E+02
 endloop
endfacet
facet normal  0.561224E+00 -0.770899E+00  0.301234E+00
 outer loop
  vertex  0.107016E+03  0.152997E+02  0.199731E+02
  vertex  0.110256E+03  0.152998E+02  0.139368E+02
  vertex  0.111918E+03  0.167861E+02  0.146440E+02
 endloop
endfacet
facet normal  0.491797E+00 -0.771164E+00  0.404279E+00
 outer loop
  vertex  0.108513E+03  0.167862E+02  0.209866E+02
  vertex  0.103990E+03  0.167862E+02  0.264897E+02
  vertex  0.102711E+03  0.152998E+02  0.252105E+02
 endloop
endfacet
facet normal  0.491790E+00 -0.771184E+00  0.404251E+00
 outer loop
  vertex  0.102711E+03  0.152997E+02  0.252105E+02
  vertex  0.107016E+03  0.152998E+02  0.199731E+02
  vertex  0.108513E+03  0.167861E+02  0.209866E+02
 endloop
endfacet
facet normal  0.404270E+00 -0.771176E+00  0.491785E+00
 outer loop
  vertex  0.103990E+03  0.167862E+02  0.264897E+02
  vertex  0.984866E+02  0.167862E+02  0.310135E+02
  vertex  0.974731E+02  0.152998E+02  0.295158E+02
 endloop
endfacet
facet normal  0.404263E+00 -0.771185E+00  0.491777E+00
 outer loop
  vertex  0.974730E+02  0.152997E+02  0.295158E+02
  vertex  0.102711E+03  0.152998E+02  0.252105E+02
  vertex  0.103990E+03  0.167861E+02  0.264897E+02
 endloop
endfacet
facet normal  0.301247E+00 -0.770893E+00  0.561226E+00
 outer loop
  vertex  0.984866E+02  0.167862E+02  0.310135E+02
  vertex  0.921440E+02  0.167862E+02  0.344180E+02
  vertex  0.914368E+02  0.152998E+02  0.327559E+02
 endloop
endfacet
facet normal  0.301241E+00 -0.770916E+00  0.561197E+00
 outer loop
  vertex  0.914367E+02  0.152997E+02  0.327559E+02
  vertex  0.974731E+02  0.152998E+02  0.295158E+02
  vertex  0.984866E+02  0.167861E+02  0.310135E+02
 endloop
endfacet
facet normal  0.185797E+00 -0.770390E+00  0.609900E+00
 outer loop
  vertex  0.921440E+02  0.167862E+02  0.344180E+02
  vertex  0.851018E+02  0.167862E+02  0.365633E+02
  vertex  0.847347E+02  0.152998E+02  0.347976E+02
 endloop
endfacet
facet normal  0.185800E+00 -0.770390E+00  0.609900E+00
 outer loop
  vertex  0.847347E+02  0.152997E+02  0.347975E+02
  vertex  0.914368E+02  0.152998E+02  0.327559E+02
  vertex  0.921439E+02  0.167861E+02  0.344179E+02
 endloop
endfacet
facet normal  0.623464E-01 -0.769873E+00  0.635144E+00
 outer loop
  vertex  0.851018E+02  0.167862E+02  0.365633E+02
  vertex  0.775000E+02  0.167862E+02  0.373095E+02
  vertex  0.775000E+02  0.152998E+02  0.355078E+02
 endloop
endfacet
facet normal  0.623569E-01 -0.769899E+00  0.635111E+00
 outer loop
  vertex  0.775000E+02  0.152997E+02  0.355078E+02
  vertex  0.847347E+02  0.152998E+02  0.347976E+02
  vertex  0.851017E+02  0.167861E+02  0.365633E+02
 endloop
endfacet
facet normal  0.662207E+00 -0.746496E+00  0.650058E-01
 outer loop
  vertex  0.113008E+03  0.152998E+02  0.000000E+00
  vertex  0.112298E+03  0.152998E+02  0.723470E+01
  vertex  0.111049E+03  0.141693E+02  0.697500E+01
 endloop
endfacet
facet normal  0.662173E+00 -0.746526E+00  0.650031E-01
 outer loop
  vertex  0.111049E+03  0.141693E+02  0.697490E+01
  vertex  0.111733E+03  0.141693E+02  0.000000E+00
  vertex  0.113008E+03  0.152997E+02  0.000000E+00
 endloop
endfacet
facet normal  0.635940E+00 -0.747027E+00  0.193730E+00
 outer loop
  vertex  0.112298E+03  0.152998E+02  0.723470E+01
  vertex  0.110256E+03  0.152998E+02  0.139368E+02
  vertex  0.109080E+03  0.141693E+02  0.134366E+02
 endloop
endfacet
facet normal  0.635923E+00 -0.747041E+00  0.193734E+00
 outer loop
  vertex  0.109080E+03  0.141693E+02  0.134365E+02
  vertex  0.111049E+03  0.141693E+02  0.697500E+01
  vertex  0.112298E+03  0.152997E+02  0.723470E+01
 endloop
endfacet
facet normal  0.585216E+00 -0.747561E+00  0.314126E+00
 outer loop
  vertex  0.110256E+03  0.152998E+02  0.139368E+02
  vertex  0.107016E+03  0.152998E+02  0.199731E+02
  vertex  0.105956E+03  0.141693E+02  0.192562E+02
 endloop
endfacet
facet normal  0.585210E+00 -0.747562E+00  0.314135E+00
 outer loop
  vertex  0.105956E+03  0.141693E+02  0.192562E+02
  vertex  0.109080E+03  0.141693E+02  0.134366E+02
  vertex  0.110256E+03  0.152997E+02  0.139368E+02
 endloop
endfacet
facet normal  0.512835E+00 -0.747852E+00  0.421566E+00
 outer loop
  vertex  0.107016E+03  0.152998E+02  0.199731E+02
  vertex  0.102711E+03  0.152998E+02  0.252105E+02
  vertex  0.101806E+03  0.141693E+02  0.243057E+02
 endloop
endfacet
facet normal  0.512804E+00 -0.747890E+00  0.421536E+00
 outer loop
  vertex  0.101806E+03  0.141693E+02  0.243057E+02
  vertex  0.105956E+03  0.141693E+02  0.192562E+02
  vertex  0.107016E+03  0.152997E+02  0.199731E+02
 endloop
endfacet
facet normal  0.421560E+00 -0.747859E+00  0.512829E+00
 outer loop
  vertex  0.102711E+03  0.152998E+02  0.252105E+02
  vertex  0.974731E+02  0.152998E+02  0.295158E+02
  vertex  0.967562E+02  0.141693E+02  0.284565E+02
 endloop
endfacet
facet normal  0.421537E+00 -0.747881E+00  0.512817E+00
 outer loop
  vertex  0.967562E+02  0.141693E+02  0.284564E+02
  vertex  0.101806E+03  0.141693E+02  0.243057E+02
  vertex  0.102711E+03  0.152997E+02  0.252105E+02
 endloop
endfacet
facet normal  0.314128E+00 -0.747557E+00  0.585220E+00
 outer loop
  vertex  0.974731E+02  0.152998E+02  0.295158E+02
  vertex  0.914368E+02  0.152998E+02  0.327559E+02
  vertex  0.909366E+02  0.141693E+02  0.315803E+02
 endloop
endfacet
facet normal  0.314107E+00 -0.747577E+00  0.585206E+00
 outer loop
  vertex  0.909365E+02  0.141693E+02  0.315802E+02
  vertex  0.967562E+02  0.141693E+02  0.284565E+02
  vertex  0.974730E+02  0.152997E+02  0.295158E+02
 endloop
endfacet
facet normal  0.193727E+00 -0.747037E+00  0.635929E+00
 outer loop
  vertex  0.914368E+02  0.152998E+02  0.327559E+02
  vertex  0.847347E+02  0.152998E+02  0.347976E+02
  vertex  0.844750E+02  0.141693E+02  0.335487E+02
 endloop
endfacet
facet normal  0.193708E+00 -0.747048E+00  0.635921E+00
 outer loop
  vertex  0.844749E+02  0.141693E+02  0.335486E+02
  vertex  0.909366E+02  0.141693E+02  0.315803E+02
  vertex  0.914367E+02  0.152997E+02  0.327559E+02
 endloop
endfacet
facet normal  0.650031E-01 -0.746523E+00  0.662176E+00
 outer loop
  vertex  0.847347E+02  0.152998E+02  0.347976E+02
  vertex  0.775000E+02  0.152998E+02  0.355078E+02
  vertex  0.775000E+02  0.141693E+02  0.342333E+02
 endloop
endfacet
facet normal  0.649865E-01 -0.746498E+00  0.662206E+00
 outer loop
  vertex  0.775000E+02  0.141693E+02  0.342332E+02
  vertex  0.844750E+02  0.141693E+02  0.335487E+02
  vertex  0.847347E+02  0.152997E+02  0.347975E+02
 endloop
endfacet
facet normal  0.851221E+00 -0.518115E+00  0.835479E-01
 outer loop
  vertex  0.111733E+03  0.141693E+02  0.000000E+00
  vertex  0.111049E+03  0.141693E+02  0.697500E+01
  vertex  0.110575E+03  0.133750E+02  0.687650E+01
 endloop
endfacet
facet normal  0.851345E+00 -0.517903E+00  0.835933E-01
 outer loop
  vertex  0.110575E+03  0.133750E+02  0.687650E+01
  vertex  0.111250E+03  0.133750E+02  0.000000E+00
  vertex  0.111733E+03  0.141693E+02  0.000000E+00
 endloop
endfacet
facet normal  0.817827E+00 -0.518740E+00  0.249135E+00
 outer loop
  vertex  0.111049E+03  0.141693E+02  0.697500E+01
  vertex  0.109080E+03  0.141693E+02  0.134366E+02
  vertex  0.108634E+03  0.133750E+02  0.132468E+02
 endloop
endfacet
facet normal  0.817888E+00 -0.518634E+00  0.249155E+00
 outer loop
  vertex  0.108634E+03  0.133750E+02  0.132468E+02
  vertex  0.110575E+03  0.133750E+02  0.687650E+01
  vertex  0.111049E+03  0.141693E+02  0.697490E+01
 endloop
endfacet
facet normal  0.752959E+00 -0.519328E+00  0.404168E+00
 outer loop
  vertex  0.109080E+03  0.141693E+02  0.134366E+02
  vertex  0.105956E+03  0.141693E+02  0.192562E+02
  vertex  0.105555E+03  0.133750E+02  0.189843E+02
 endloop
endfacet
facet normal  0.753004E+00 -0.519248E+00  0.404187E+00
 outer loop
  vertex  0.105555E+03  0.133750E+02  0.189843E+02
  vertex  0.108634E+03  0.133750E+02  0.132468E+02
  vertex  0.109080E+03  0.141693E+02  0.134365E+02
 endloop
endfacet
facet normal  0.660004E+00 -0.519661E+00  0.542537E+00
 outer loop
  vertex  0.105956E+03  0.141693E+02  0.192562E+02
  vertex  0.101806E+03  0.141693E+02  0.243057E+02
  vertex  0.101463E+03  0.133750E+02  0.239624E+02
 endloop
endfacet
facet normal  0.660032E+00 -0.519602E+00  0.542560E+00
 outer loop
  vertex  0.101463E+03  0.133750E+02  0.239624E+02
  vertex  0.105555E+03  0.133750E+02  0.189843E+02
  vertex  0.105956E+03  0.141693E+02  0.192562E+02
 endloop
endfacet
facet normal  0.542535E+00 -0.519667E+00  0.660001E+00
 outer loop
  vertex  0.101806E+03  0.141693E+02  0.243057E+02
  vertex  0.967562E+02  0.141693E+02  0.284565E+02
  vertex  0.964843E+02  0.133750E+02  0.280546E+02
 endloop
endfacet
facet normal  0.542520E+00 -0.519671E+00  0.660011E+00
 outer loop
  vertex  0.964842E+02  0.133750E+02  0.280545E+02
  vertex  0.101463E+03  0.133750E+02  0.239624E+02
  vertex  0.101806E+03  0.141693E+02  0.243057E+02
 endloop
endfacet
facet normal  0.404160E+00 -0.519352E+00  0.752946E+00
 outer loop
  vertex  0.967562E+02  0.141693E+02  0.284565E+02
  vertex  0.909366E+02  0.141693E+02  0.315803E+02
  vertex  0.907468E+02  0.133750E+02  0.311343E+02
 endloop
endfacet
facet normal  0.404183E+00 -0.519265E+00  0.752994E+00
 outer loop
  vertex  0.907468E+02  0.133750E+02  0.311343E+02
  vertex  0.964843E+02  0.133750E+02  0.280546E+02
  vertex  0.967562E+02  0.141693E+02  0.284564E+02
 endloop
endfacet
facet normal  0.249150E+00 -0.518654E+00  0.817877E+00
 outer loop
  vertex  0.909366E+02  0.141693E+02  0.315803E+02
  vertex  0.844750E+02  0.141693E+02  0.335487E+02
  vertex  0.843765E+02  0.133750E+02  0.330750E+02
 endloop
endfacet
facet normal  0.249165E+00 -0.518643E+00  0.817879E+00
 outer loop
  vertex  0.843765E+02  0.133750E+02  0.330750E+02
  vertex  0.907468E+02  0.133750E+02  0.311343E+02
  vertex  0.909365E+02  0.141693E+02  0.315802E+02
 endloop
endfacet
facet normal  0.835558E-01 -0.517982E+00  0.851301E+00
 outer loop
  vertex  0.844750E+02  0.141693E+02  0.335487E+02
  vertex  0.775000E+02  0.141693E+02  0.342333E+02
  vertex  0.775000E+02  0.133750E+02  0.337500E+02
 endloop
endfacet
facet normal  0.835658E-01 -0.517948E+00  0.851320E+00
 outer loop
  vertex  0.775000E+02  0.133750E+02  0.337500E+02
  vertex  0.843765E+02  0.133750E+02  0.330750E+02
  vertex  0.844749E+02  0.141693E+02  0.335486E+02
 endloop
endfacet
facet normal -0.572185E-01  0.998346E+00  0.556855E-02
 outer loop
  vertex  0.775000E+02  0.808750E+02  0.000000E+00
  vertex  0.723232E+02  0.805783E+02  0.000000E+00
  vertex  0.724262E+02  0.805783E+02  0.105840E+01
 endloop
endfacet
facet normal -0.549121E-01  0.998353E+00  0.166269E-01
 outer loop
  vertex  0.775000E+02  0.808750E+02  0.000000E+00
  vertex  0.724262E+02  0.805783E+02  0.105840E+01
  vertex  0.727226E+02  0.805783E+02  0.203730E+01
 endloop
endfacet
facet normal -0.504911E-01  0.998360E+00  0.269949E-01
 outer loop
  vertex  0.775000E+02  0.808750E+02  0.000000E+00
  vertex  0.727226E+02  0.805783E+02  0.203730E+01
  vertex  0.731932E+02  0.805783E+02  0.291750E+01
 endloop
endfacet
facet normal -0.441922E-01  0.998364E+00  0.362940E-01
 outer loop
  vertex  0.775000E+02  0.808750E+02  0.000000E+00
  vertex  0.731933E+02  0.805783E+02  0.291760E+01
  vertex  0.738196E+02  0.805783E+02  0.368020E+01
 endloop
endfacet
facet normal -0.362846E-01  0.998364E+00  0.442008E-01
 outer loop
  vertex  0.775000E+02  0.808750E+02  0.000000E+00
  vertex  0.738196E+02  0.805783E+02  0.368030E+01
  vertex  0.745823E+02  0.805783E+02  0.430640E+01
 endloop
endfacet
facet normal -0.270004E-01  0.998360E+00  0.504903E-01
 outer loop
  vertex  0.775000E+02  0.808750E+02  0.000000E+00
  vertex  0.745824E+02  0.805783E+02  0.430650E+01
  vertex  0.754626E+02  0.805783E+02  0.477720E+01
 endloop
endfacet
facet normal -0.166235E-01  0.998353E+00  0.549143E-01
 outer loop
  vertex  0.775000E+02  0.808750E+02  0.000000E+00
  vertex  0.754626E+02  0.805783E+02  0.477730E+01
  vertex  0.764414E+02  0.805783E+02  0.507360E+01
 endloop
endfacet
facet normal -0.556790E-02  0.998346E+00  0.572196E-01
 outer loop
  vertex  0.775000E+02  0.808750E+02  0.000000E+00
  vertex  0.764415E+02  0.805783E+02  0.507370E+01
  vertex  0.775000E+02  0.805783E+02  0.517670E+01
 endloop
endfacet
facet normal -0.309784E+00  0.950329E+00  0.301485E-01
 outer loop
  vertex  0.699884E+02  0.797675E+02  0.156700E+01
  vertex  0.724262E+02  0.805783E+02  0.105840E+01
  vertex  0.723232E+02  0.805783E+02  0.000000E+00
 endloop
endfacet
facet normal -0.309795E+00  0.950325E+00  0.301500E-01
 outer loop
  vertex  0.723231E+02  0.805783E+02  0.000000E+00
  vertex  0.698359E+02  0.797675E+02  0.000000E+00
  vertex  0.699884E+02  0.797675E+02  0.156700E+01
 endloop
endfacet
facet normal -0.297354E+00  0.950513E+00  0.900361E-01
 outer loop
  vertex  0.704272E+02  0.797675E+02  0.301610E+01
  vertex  0.727226E+02  0.805783E+02  0.203730E+01
  vertex  0.724262E+02  0.805783E+02  0.105840E+01
 endloop
endfacet
facet normal -0.297349E+00  0.950513E+00  0.900456E-01
 outer loop
  vertex  0.724262E+02  0.805783E+02  0.105840E+01
  vertex  0.699884E+02  0.797675E+02  0.156700E+01
  vertex  0.704272E+02  0.797675E+02  0.301600E+01
 endloop
endfacet
facet normal -0.273479E+00  0.950698E+00  0.146229E+00
 outer loop
  vertex  0.711242E+02  0.797675E+02  0.431930E+01
  vertex  0.731933E+02  0.805783E+02  0.291760E+01
  vertex  0.727226E+02  0.805783E+02  0.203730E+01
 endloop
endfacet
facet normal -0.273457E+00  0.950703E+00  0.146234E+00
 outer loop
  vertex  0.727226E+02  0.805783E+02  0.203730E+01
  vertex  0.704272E+02  0.797675E+02  0.301610E+01
  vertex  0.711241E+02  0.797675E+02  0.431930E+01
 endloop
endfacet
facet normal -0.239388E+00  0.950816E+00  0.196578E+00
 outer loop
  vertex  0.720513E+02  0.797675E+02  0.544860E+01
  vertex  0.738196E+02  0.805783E+02  0.368030E+01
  vertex  0.731933E+02  0.805783E+02  0.291760E+01
 endloop
endfacet
facet normal -0.239421E+00  0.950809E+00  0.196571E+00
 outer loop
  vertex  0.731932E+02  0.805783E+02  0.291750E+01
  vertex  0.711242E+02  0.797675E+02  0.431930E+01
  vertex  0.720513E+02  0.797675E+02  0.544850E+01
 endloop
endfacet
facet normal -0.196545E+00  0.950815E+00  0.239418E+00
 outer loop
  vertex  0.731806E+02  0.797675E+02  0.637570E+01
  vertex  0.745824E+02  0.805783E+02  0.430650E+01
  vertex  0.738196E+02  0.805783E+02  0.368030E+01
 endloop
endfacet
facet normal -0.196532E+00  0.950817E+00  0.239422E+00
 outer loop
  vertex  0.738196E+02  0.805783E+02  0.368020E+01
  vertex  0.720513E+02  0.797675E+02  0.544860E+01
  vertex  0.731806E+02  0.797675E+02  0.637560E+01
 endloop
endfacet
facet normal -0.146260E+00  0.950702E+00  0.273446E+00
 outer loop
  vertex  0.744838E+02  0.797675E+02  0.707270E+01
  vertex  0.754626E+02  0.805783E+02  0.477730E+01
  vertex  0.745824E+02  0.805783E+02  0.430650E+01
 endloop
endfacet
facet normal -0.146248E+00  0.950705E+00  0.273443E+00
 outer loop
  vertex  0.745823E+02  0.805783E+02  0.430640E+01
  vertex  0.731806E+02  0.797675E+02  0.637570E+01
  vertex  0.744838E+02  0.797675E+02  0.707270E+01
 endloop
endfacet
facet normal -0.900350E-01  0.950513E+00  0.297351E+00
 outer loop
  vertex  0.759329E+02  0.797675E+02  0.751150E+01
  vertex  0.764415E+02  0.805783E+02  0.507370E+01
  vertex  0.754626E+02  0.805783E+02  0.477730E+01
 endloop
endfacet
facet normal -0.900252E-01  0.950516E+00  0.297347E+00
 outer loop
  vertex  0.754626E+02  0.805783E+02  0.477720E+01
  vertex  0.744838E+02  0.797675E+02  0.707270E+01
  vertex  0.759328E+02  0.797675E+02  0.751140E+01
 endloop
endfacet
facet normal -0.301443E-01  0.950329E+00  0.309784E+00
 outer loop
  vertex  0.775000E+02  0.797675E+02  0.766400E+01
  vertex  0.775000E+02  0.805783E+02  0.517670E+01
  vertex  0.764415E+02  0.805783E+02  0.507370E+01
 endloop
endfacet
facet normal -0.301453E-01  0.950332E+00  0.309774E+00
 outer loop
  vertex  0.764414E+02  0.805783E+02  0.507360E+01
  vertex  0.759329E+02  0.797675E+02  0.751150E+01
  vertex  0.775000E+02  0.797675E+02  0.766400E+01
 endloop
endfacet
facet normal -0.924477E+00  0.370470E+00  0.899721E-01
 outer loop
  vertex  0.695146E+02  0.785612E+02  0.166570E+01
  vertex  0.699884E+02  0.797675E+02  0.156700E+01
  vertex  0.698359E+02  0.797675E+02  0.000000E+00
 endloop
endfacet
facet normal -0.924505E+00  0.370399E+00  0.899759E-01
 outer loop
  vertex  0.698358E+02  0.797675E+02  0.000000E+00
  vertex  0.693525E+02  0.785612E+02  0.000000E+00
  vertex  0.695146E+02  0.785612E+02  0.166560E+01
 endloop
endfacet
facet normal -0.888750E+00  0.371077E+00  0.269119E+00
 outer loop
  vertex  0.699811E+02  0.785612E+02  0.320620E+01
  vertex  0.704272E+02  0.797675E+02  0.301610E+01
  vertex  0.699884E+02  0.797675E+02  0.156700E+01
 endloop
endfacet
facet normal -0.888735E+00  0.371092E+00  0.269147E+00
 outer loop
  vertex  0.699884E+02  0.797675E+02  0.156700E+01
  vertex  0.695146E+02  0.785612E+02  0.166570E+01
  vertex  0.699811E+02  0.785612E+02  0.320610E+01
 endloop
endfacet
facet normal -0.818642E+00  0.371648E+00  0.437839E+00
 outer loop
  vertex  0.707222E+02  0.785612E+02  0.459160E+01
  vertex  0.711242E+02  0.797675E+02  0.431930E+01
  vertex  0.704272E+02  0.797675E+02  0.301610E+01
 endloop
endfacet
facet normal -0.818582E+00  0.371756E+00  0.437860E+00
 outer loop
  vertex  0.704272E+02  0.797675E+02  0.301600E+01
  vertex  0.699811E+02  0.785612E+02  0.320620E+01
  vertex  0.707221E+02  0.785612E+02  0.459150E+01
 endloop
endfacet
facet normal -0.717435E+00  0.372008E+00  0.588980E+00
 outer loop
  vertex  0.717078E+02  0.785612E+02  0.579210E+01
  vertex  0.720513E+02  0.797675E+02  0.544860E+01
  vertex  0.711242E+02  0.797675E+02  0.431930E+01
 endloop
endfacet
facet normal -0.717405E+00  0.371981E+00  0.589034E+00
 outer loop
  vertex  0.711241E+02  0.797675E+02  0.431930E+01
  vertex  0.707222E+02  0.785612E+02  0.459160E+01
  vertex  0.717078E+02  0.785612E+02  0.579200E+01
 endloop
endfacet
facet normal -0.588972E+00  0.372033E+00  0.717428E+00
 outer loop
  vertex  0.729083E+02  0.785612E+02  0.677770E+01
  vertex  0.731806E+02  0.797675E+02  0.637570E+01
  vertex  0.720513E+02  0.797675E+02  0.544860E+01
 endloop
endfacet
facet normal -0.588948E+00  0.372058E+00  0.717435E+00
 outer loop
  vertex  0.720513E+02  0.797675E+02  0.544850E+01
  vertex  0.717078E+02  0.785612E+02  0.579210E+01
  vertex  0.729083E+02  0.785612E+02  0.677760E+01
 endloop
endfacet
facet normal -0.437825E+00  0.371728E+00  0.818613E+00
 outer loop
  vertex  0.742937E+02  0.785612E+02  0.751880E+01
  vertex  0.744838E+02  0.797675E+02  0.707270E+01
  vertex  0.731806E+02  0.797675E+02  0.637570E+01
 endloop
endfacet
facet normal -0.437846E+00  0.371707E+00  0.818612E+00
 outer loop
  vertex  0.731806E+02  0.797675E+02  0.637560E+01
  vertex  0.729083E+02  0.785612E+02  0.677770E+01
  vertex  0.742937E+02  0.785612E+02  0.751870E+01
 endloop
endfacet
facet normal -0.269120E+00  0.371093E+00  0.888743E+00
 outer loop
  vertex  0.758342E+02  0.785612E+02  0.798530E+01
  vertex  0.759329E+02  0.797675E+02  0.751150E+01
  vertex  0.744838E+02  0.797675E+02  0.707270E+01
 endloop
endfacet
facet normal -0.269150E+00  0.371079E+00  0.888740E+00
 outer loop
  vertex  0.744838E+02  0.797675E+02  0.707270E+01
  vertex  0.742937E+02  0.785612E+02  0.751880E+01
  vertex  0.758341E+02  0.785612E+02  0.798530E+01
 endloop
endfacet
facet normal -0.899643E-01  0.370466E+00  0.924479E+00
 outer loop
  vertex  0.775000E+02  0.785612E+02  0.814740E+01
  vertex  0.775000E+02  0.797675E+02  0.766400E+01
  vertex  0.759329E+02  0.797675E+02  0.751150E+01
 endloop
endfacet
facet normal -0.899040E-01  0.370527E+00  0.924460E+00
 outer loop
  vertex  0.759328E+02  0.797675E+02  0.751140E+01
  vertex  0.758342E+02  0.785612E+02  0.798530E+01
  vertex  0.775000E+02  0.785612E+02  0.814730E+01
 endloop
endfacet
facet normal -0.868260E+00 -0.488861E+00  0.844969E-01
 outer loop
  vertex  0.703330E+02  0.770781E+02  0.149470E+01
  vertex  0.695146E+02  0.785612E+02  0.166570E+01
  vertex  0.693525E+02  0.785612E+02  0.000000E+00
 endloop
endfacet
facet normal -0.868267E+00 -0.488842E+00  0.845263E-01
 outer loop
  vertex  0.693525E+02  0.785612E+02  0.000000E+00
  vertex  0.701875E+02  0.770781E+02  0.000000E+00
  vertex  0.703330E+02  0.770781E+02  0.149460E+01
 endloop
endfacet
facet normal -0.834473E+00 -0.489693E+00  0.252698E+00
 outer loop
  vertex  0.707518E+02  0.770781E+02  0.287720E+01
  vertex  0.699811E+02  0.785612E+02  0.320620E+01
  vertex  0.695146E+02  0.785612E+02  0.166570E+01
 endloop
endfacet
facet normal -0.834486E+00 -0.489613E+00  0.252809E+00
 outer loop
  vertex  0.695146E+02  0.785612E+02  0.166560E+01
  vertex  0.703330E+02  0.770781E+02  0.149470E+01
  vertex  0.707518E+02  0.770781E+02  0.287710E+01
 endloop
endfacet
facet normal -0.768399E+00 -0.490517E+00  0.411042E+00
 outer loop
  vertex  0.714170E+02  0.770781E+02  0.412060E+01
  vertex  0.707222E+02  0.785612E+02  0.459160E+01
  vertex  0.699811E+02  0.785612E+02  0.320620E+01
 endloop
endfacet
facet normal -0.768431E+00 -0.490472E+00  0.411037E+00
 outer loop
  vertex  0.699811E+02  0.785612E+02  0.320610E+01
  vertex  0.707518E+02  0.770781E+02  0.287720E+01
  vertex  0.714169E+02  0.770781E+02  0.412060E+01
 endloop
endfacet
facet normal -0.673317E+00 -0.490986E+00  0.552790E+00
 outer loop
  vertex  0.723017E+02  0.770781E+02  0.519820E+01
  vertex  0.717078E+02  0.785612E+02  0.579210E+01
  vertex  0.707222E+02  0.785612E+02  0.459160E+01
 endloop
endfacet
facet normal -0.673345E+00 -0.490996E+00  0.552747E+00
 outer loop
  vertex  0.707221E+02  0.785612E+02  0.459150E+01
  vertex  0.714170E+02  0.770781E+02  0.412060E+01
  vertex  0.723016E+02  0.770781E+02  0.519820E+01
 endloop
endfacet
facet normal -0.552788E+00 -0.490988E+00  0.673318E+00
 outer loop
  vertex  0.733793E+02  0.770781E+02  0.608290E+01
  vertex  0.729083E+02  0.785612E+02  0.677770E+01
  vertex  0.717078E+02  0.785612E+02  0.579210E+01
 endloop
endfacet
facet normal -0.552799E+00 -0.490951E+00  0.673335E+00
 outer loop
  vertex  0.717078E+02  0.785612E+02  0.579200E+01
  vertex  0.723017E+02  0.770781E+02  0.519820E+01
  vertex  0.733793E+02  0.770781E+02  0.608290E+01
 endloop
endfacet
facet normal -0.411050E+00 -0.490493E+00  0.768410E+00
 outer loop
  vertex  0.746227E+02  0.770781E+02  0.674810E+01
  vertex  0.742937E+02  0.785612E+02  0.751880E+01
  vertex  0.729083E+02  0.785612E+02  0.677770E+01
 endloop
endfacet
facet normal -0.411036E+00 -0.490476E+00  0.768429E+00
 outer loop
  vertex  0.729083E+02  0.785612E+02  0.677760E+01
  vertex  0.733793E+02  0.770781E+02  0.608290E+01
  vertex  0.746227E+02  0.770781E+02  0.674800E+01
 endloop
endfacet
facet normal -0.252709E+00 -0.489632E+00  0.834505E+00
 outer loop
  vertex  0.760052E+02  0.770781E+02  0.716690E+01
  vertex  0.758342E+02  0.785612E+02  0.798530E+01
  vertex  0.742937E+02  0.785612E+02  0.751880E+01
 endloop
endfacet
facet normal -0.252785E+00 -0.489655E+00  0.834468E+00
 outer loop
  vertex  0.742937E+02  0.785612E+02  0.751870E+01
  vertex  0.746227E+02  0.770781E+02  0.674810E+01
  vertex  0.760052E+02  0.770781E+02  0.716690E+01
 endloop
endfacet
facet normal -0.844917E-01 -0.488844E+00  0.868270E+00
 outer loop
  vertex  0.775000E+02  0.770781E+02  0.731240E+01
  vertex  0.775000E+02  0.785612E+02  0.814740E+01
  vertex  0.758342E+02  0.785612E+02  0.798530E+01
 endloop
endfacet
facet normal -0.844565E-01 -0.488865E+00  0.868262E+00
 outer loop
  vertex  0.758341E+02  0.785612E+02  0.798530E+01
  vertex  0.760052E+02  0.770781E+02  0.716690E+01
  vertex  0.775000E+02  0.770781E+02  0.731230E+01
 endloop
endfacet
facet normal -0.743461E+00 -0.664852E+00  0.723715E-01
 outer loop
  vertex  0.717716E+02  0.754367E+02  0.119420E+01
  vertex  0.703330E+02  0.770781E+02  0.149470E+01
  vertex  0.701875E+02  0.770781E+02  0.000000E+00
 endloop
endfacet
facet normal -0.743497E+00 -0.664814E+00  0.723535E-01
 outer loop
  vertex  0.701875E+02  0.770781E+02  0.000000E+00
  vertex  0.716552E+02  0.754367E+02  0.000000E+00
  vertex  0.717715E+02  0.754366E+02  0.119420E+01
 endloop
endfacet
facet normal -0.714201E+00 -0.665664E+00  0.216353E+00
 outer loop
  vertex  0.721065E+02  0.754367E+02  0.229900E+01
  vertex  0.707518E+02  0.770781E+02  0.287720E+01
  vertex  0.703330E+02  0.770781E+02  0.149470E+01
 endloop
endfacet
facet normal -0.714249E+00 -0.665601E+00  0.216388E+00
 outer loop
  vertex  0.703330E+02  0.770781E+02  0.149460E+01
  vertex  0.717716E+02  0.754367E+02  0.119420E+01
  vertex  0.721064E+02  0.754366E+02  0.229900E+01
 endloop
endfacet
facet normal -0.657347E+00 -0.666500E+00  0.351670E+00
 outer loop
  vertex  0.726384E+02  0.754367E+02  0.329280E+01
  vertex  0.714170E+02  0.770781E+02  0.412060E+01
  vertex  0.707518E+02  0.770781E+02  0.287720E+01
 endloop
endfacet
facet normal -0.657376E+00 -0.666434E+00  0.351742E+00
 outer loop
  vertex  0.707518E+02  0.770781E+02  0.287710E+01
  vertex  0.721065E+02  0.754367E+02  0.229900E+01
  vertex  0.726383E+02  0.754366E+02  0.329270E+01
 endloop
endfacet
facet normal -0.575863E+00 -0.666981E+00  0.472777E+00
 outer loop
  vertex  0.733457E+02  0.754367E+02  0.415420E+01
  vertex  0.723017E+02  0.770781E+02  0.519820E+01
  vertex  0.714170E+02  0.770781E+02  0.412060E+01
 endloop
endfacet
facet normal -0.575867E+00 -0.666979E+00  0.472774E+00
 outer loop
  vertex  0.714169E+02  0.770781E+02  0.412060E+01
  vertex  0.726384E+02  0.754367E+02  0.329280E+01
  vertex  0.733457E+02  0.754366E+02  0.415420E+01
 endloop
endfacet
facet normal -0.472788E+00 -0.666960E+00  0.575878E+00
 outer loop
  vertex  0.742071E+02  0.754367E+02  0.486150E+01
  vertex  0.733793E+02  0.770781E+02  0.608290E+01
  vertex  0.723017E+02  0.770781E+02  0.519820E+01
 endloop
endfacet
facet normal -0.472845E+00 -0.667001E+00  0.575784E+00
 outer loop
  vertex  0.723016E+02  0.770781E+02  0.519820E+01
  vertex  0.733457E+02  0.754367E+02  0.415420E+01
  vertex  0.742070E+02  0.754366E+02  0.486140E+01
 endloop
endfacet
facet normal -0.351692E+00 -0.666448E+00  0.657388E+00
 outer loop
  vertex  0.752009E+02  0.754367E+02  0.539340E+01
  vertex  0.746227E+02  0.770781E+02  0.674810E+01
  vertex  0.733793E+02  0.770781E+02  0.608290E+01
 endloop
endfacet
facet normal -0.351865E+00 -0.666512E+00  0.657231E+00
 outer loop
  vertex  0.733793E+02  0.770781E+02  0.608290E+01
  vertex  0.742071E+02  0.754367E+02  0.486150E+01
  vertex  0.752008E+02  0.754366E+02  0.539340E+01
 endloop
endfacet
facet normal -0.216367E+00 -0.665610E+00  0.714247E+00
 outer loop
  vertex  0.763057E+02  0.754367E+02  0.572830E+01
  vertex  0.760052E+02  0.770781E+02  0.716690E+01
  vertex  0.746227E+02  0.770781E+02  0.674810E+01
 endloop
endfacet
facet normal -0.216542E+00 -0.665650E+00  0.714157E+00
 outer loop
  vertex  0.746227E+02  0.770781E+02  0.674800E+01
  vertex  0.752009E+02  0.754367E+02  0.539340E+01
  vertex  0.763057E+02  0.754366E+02  0.572830E+01
 endloop
endfacet
facet normal -0.723699E-01 -0.664814E+00  0.743495E+00
 outer loop
  vertex  0.775000E+02  0.754367E+02  0.584470E+01
  vertex  0.775000E+02  0.770781E+02  0.731240E+01
  vertex  0.760052E+02  0.770781E+02  0.716690E+01
 endloop
endfacet
facet normal -0.724519E-01 -0.664856E+00  0.743449E+00
 outer loop
  vertex  0.760052E+02  0.770781E+02  0.716690E+01
  vertex  0.763057E+02  0.754367E+02  0.572830E+01
  vertex  0.775000E+02  0.754366E+02  0.584460E+01
 endloop
endfacet
facet normal -0.762847E+00 -0.642290E+00  0.743566E-01
 outer loop
  vertex  0.731586E+02  0.737558E+02  0.904300E+00
  vertex  0.717716E+02  0.754367E+02  0.119420E+01
  vertex  0.716552E+02  0.754367E+02  0.000000E+00
 endloop
endfacet
facet normal -0.762842E+00 -0.642297E+00  0.743437E-01
 outer loop
  vertex  0.716551E+02  0.754366E+02  0.000000E+00
  vertex  0.730703E+02  0.737558E+02  0.000000E+00
  vertex  0.731585E+02  0.737557E+02  0.904200E+00
 endloop
endfacet
facet normal -0.732808E+00 -0.643154E+00  0.222137E+00
 outer loop
  vertex  0.734127E+02  0.737558E+02  0.174130E+01
  vertex  0.721065E+02  0.754367E+02  0.229900E+01
  vertex  0.717716E+02  0.754367E+02  0.119420E+01
 endloop
endfacet
facet normal -0.732800E+00 -0.643098E+00  0.222327E+00
 outer loop
  vertex  0.717715E+02  0.754366E+02  0.119420E+01
  vertex  0.731586E+02  0.737558E+02  0.904300E+00
  vertex  0.734126E+02  0.737557E+02  0.174120E+01
 endloop
endfacet
facet normal -0.674474E+00 -0.644027E+00  0.360990E+00
 outer loop
  vertex  0.738161E+02  0.737558E+02  0.249440E+01
  vertex  0.726384E+02  0.754367E+02  0.329280E+01
  vertex  0.721065E+02  0.754367E+02  0.229900E+01
 endloop
endfacet
facet normal -0.674416E+00 -0.643986E+00  0.361172E+00
 outer loop
  vertex  0.721064E+02  0.754366E+02  0.229900E+01
  vertex  0.734127E+02  0.737558E+02  0.174130E+01
  vertex  0.738161E+02  0.737557E+02  0.249440E+01
 endloop
endfacet
facet normal -0.590897E+00 -0.644538E+00  0.485192E+00
 outer loop
  vertex  0.743525E+02  0.737558E+02  0.314740E+01
  vertex  0.733457E+02  0.754367E+02  0.415420E+01
  vertex  0.726384E+02  0.754367E+02  0.329280E+01
 endloop
endfacet
facet normal -0.590829E+00 -0.644514E+00  0.485307E+00
 outer loop
  vertex  0.726383E+02  0.754366E+02  0.329270E+01
  vertex  0.738161E+02  0.737558E+02  0.249440E+01
  vertex  0.743525E+02  0.737557E+02  0.314730E+01
 endloop
endfacet
facet normal -0.485215E+00 -0.644494E+00  0.590927E+00
 outer loop
  vertex  0.750055E+02  0.737558E+02  0.368380E+01
  vertex  0.742071E+02  0.754367E+02  0.486150E+01
  vertex  0.733457E+02  0.754367E+02  0.415420E+01
 endloop
endfacet
facet normal -0.485296E+00 -0.644568E+00  0.590778E+00
 outer loop
  vertex  0.733457E+02  0.754366E+02  0.415420E+01
  vertex  0.743525E+02  0.737558E+02  0.314740E+01
  vertex  0.750055E+02  0.737557E+02  0.368370E+01
 endloop
endfacet
facet normal -0.361023E+00 -0.643949E+00  0.674531E+00
 outer loop
  vertex  0.757586E+02  0.737558E+02  0.408720E+01
  vertex  0.752009E+02  0.754367E+02  0.539340E+01
  vertex  0.742071E+02  0.754367E+02  0.486150E+01
 endloop
endfacet
facet normal -0.361310E+00 -0.644057E+00  0.674274E+00
 outer loop
  vertex  0.742070E+02  0.754366E+02  0.486140E+01
  vertex  0.750055E+02  0.737558E+02  0.368380E+01
  vertex  0.757585E+02  0.737557E+02  0.408720E+01
 endloop
endfacet
facet normal -0.222160E+00 -0.643058E+00  0.732886E+00
 outer loop
  vertex  0.765956E+02  0.737558E+02  0.434130E+01
  vertex  0.763057E+02  0.754367E+02  0.572830E+01
  vertex  0.752009E+02  0.754367E+02  0.539340E+01
 endloop
endfacet
facet normal -0.222522E+00 -0.643207E+00  0.732645E+00
 outer loop
  vertex  0.752008E+02  0.754366E+02  0.539340E+01
  vertex  0.757586E+02  0.737558E+02  0.408720E+01
  vertex  0.765955E+02  0.737557E+02  0.434130E+01
 endloop
endfacet
facet normal -0.743527E-01 -0.642248E+00  0.762882E+00
 outer loop
  vertex  0.775000E+02  0.737558E+02  0.442960E+01
  vertex  0.775000E+02  0.754367E+02  0.584470E+01
  vertex  0.763057E+02  0.754367E+02  0.572830E+01
 endloop
endfacet
facet normal -0.744622E-01 -0.642317E+00  0.762813E+00
 outer loop
  vertex  0.763057E+02  0.754366E+02  0.572830E+01
  vertex  0.765956E+02  0.737558E+02  0.434130E+01
  vertex  0.775000E+02  0.737557E+02  0.442950E+01
 endloop
endfacet
facet normal -0.917407E+00 -0.387737E+00  0.895825E-01
 outer loop
  vertex  0.738220E+02  0.721540E+02  0.765100E+00
  vertex  0.731586E+02  0.737558E+02  0.904300E+00
  vertex  0.730703E+02  0.737558E+02  0.000000E+00
 endloop
endfacet
facet normal -0.917422E+00 -0.387660E+00  0.897587E-01
 outer loop
  vertex  0.730702E+02  0.737557E+02  0.000000E+00
  vertex  0.737470E+02  0.721540E+02  0.000000E+00
  vertex  0.738219E+02  0.721539E+02  0.765100E+00
 endloop
endfacet
facet normal -0.881653E+00 -0.388652E+00  0.267653E+00
 outer loop
  vertex  0.740376E+02  0.721540E+02  0.147380E+01
  vertex  0.734127E+02  0.737558E+02  0.174130E+01
  vertex  0.731586E+02  0.737558E+02  0.904300E+00
 endloop
endfacet
facet normal -0.881605E+00 -0.388481E+00  0.268060E+00
 outer loop
  vertex  0.731585E+02  0.737557E+02  0.904200E+00
  vertex  0.738220E+02  0.721540E+02  0.765100E+00
  vertex  0.740375E+02  0.721539E+02  0.147370E+01
 endloop
endfacet
facet normal -0.811856E+00 -0.389578E+00  0.434877E+00
 outer loop
  vertex  0.743798E+02  0.721540E+02  0.211180E+01
  vertex  0.738161E+02  0.737558E+02  0.249440E+01
  vertex  0.734127E+02  0.737558E+02  0.174130E+01
 endloop
endfacet
facet normal -0.811729E+00 -0.389411E+00  0.435265E+00
 outer loop
  vertex  0.734126E+02  0.737557E+02  0.174120E+01
  vertex  0.740376E+02  0.721540E+02  0.147380E+01
  vertex  0.743797E+02  0.721539E+02  0.211170E+01
 endloop
endfacet
facet normal -0.711493E+00 -0.390126E+00  0.584448E+00
 outer loop
  vertex  0.748347E+02  0.721540E+02  0.266520E+01
  vertex  0.743525E+02  0.737558E+02  0.314740E+01
  vertex  0.738161E+02  0.737558E+02  0.249440E+01
 endloop
endfacet
facet normal -0.711311E+00 -0.390015E+00  0.584743E+00
 outer loop
  vertex  0.738161E+02  0.737557E+02  0.249440E+01
  vertex  0.743798E+02  0.721540E+02  0.211180E+01
  vertex  0.748347E+02  0.721539E+02  0.266510E+01
 endloop
endfacet
facet normal -0.584481E+00 -0.390006E+00  0.711532E+00
 outer loop
  vertex  0.753881E+02  0.721540E+02  0.312010E+01
  vertex  0.750055E+02  0.737558E+02  0.368380E+01
  vertex  0.743525E+02  0.737558E+02  0.314740E+01
 endloop
endfacet
facet normal -0.584796E+00 -0.390124E+00  0.711208E+00
 outer loop
  vertex  0.743525E+02  0.737557E+02  0.314730E+01
  vertex  0.748347E+02  0.721540E+02  0.266520E+01
  vertex  0.753880E+02  0.721539E+02  0.312010E+01
 endloop
endfacet
facet normal -0.434914E+00 -0.389384E+00  0.811930E+00
 outer loop
  vertex  0.760261E+02  0.721540E+02  0.346230E+01
  vertex  0.757586E+02  0.737558E+02  0.408720E+01
  vertex  0.750055E+02  0.737558E+02  0.368380E+01
 endloop
endfacet
facet normal -0.435369E+00 -0.389577E+00  0.811593E+00
 outer loop
  vertex  0.750055E+02  0.737557E+02  0.368370E+01
  vertex  0.753881E+02  0.721540E+02  0.312010E+01
  vertex  0.760261E+02  0.721539E+02  0.346230E+01
 endloop
endfacet
facet normal -0.267682E+00 -0.388442E+00  0.881736E+00
 outer loop
  vertex  0.767348E+02  0.721540E+02  0.367790E+01
  vertex  0.765956E+02  0.737558E+02  0.434130E+01
  vertex  0.757586E+02  0.737558E+02  0.408720E+01
 endloop
endfacet
facet normal -0.268210E+00 -0.388710E+00  0.881458E+00
 outer loop
  vertex  0.757585E+02  0.737557E+02  0.408720E+01
  vertex  0.760261E+02  0.721540E+02  0.346230E+01
  vertex  0.767348E+02  0.721539E+02  0.367790E+01
 endloop
endfacet
facet normal -0.895752E-01 -0.387595E+00  0.917467E+00
 outer loop
  vertex  0.775000E+02  0.721540E+02  0.375290E+01
  vertex  0.775000E+02  0.737558E+02  0.442960E+01
  vertex  0.765956E+02  0.737558E+02  0.434130E+01
 endloop
endfacet
facet normal -0.898448E-01 -0.387773E+00  0.917366E+00
 outer loop
  vertex  0.765955E+02  0.737557E+02  0.434130E+01
  vertex  0.767348E+02  0.721540E+02  0.367790E+01
  vertex  0.775000E+02  0.721539E+02  0.375280E+01
 endloop
endfacet
facet normal -0.879543E+00  0.467944E+00  0.862149E-01
 outer loop
  vertex  0.730899E+02  0.707500E+02  0.916800E+00
  vertex  0.738220E+02  0.721540E+02  0.765100E+00
  vertex  0.737470E+02  0.721540E+02  0.000000E+00
 endloop
endfacet
facet normal -0.879526E+00  0.467987E+00  0.861471E-01
 outer loop
  vertex  0.737470E+02  0.721539E+02  0.000000E+00
  vertex  0.730000E+02  0.707500E+02  0.000000E+00
  vertex  0.730898E+02  0.707500E+02  0.916800E+00
 endloop
endfacet
facet normal -0.845308E+00  0.468321E+00  0.257158E+00
 outer loop
  vertex  0.733487E+02  0.707500E+02  0.176620E+01
  vertex  0.740376E+02  0.721540E+02  0.147380E+01
  vertex  0.738220E+02  0.721540E+02  0.765100E+00
 endloop
endfacet
facet normal -0.845111E+00  0.468473E+00  0.257528E+00
 outer loop
  vertex  0.738219E+02  0.721539E+02  0.765100E+00
  vertex  0.730899E+02  0.707500E+02  0.916800E+00
  vertex  0.733487E+02  0.707500E+02  0.176610E+01
 endloop
endfacet
facet normal -0.778428E+00  0.468748E+00  0.417522E+00
 outer loop
  vertex  0.737593E+02  0.707500E+02  0.253120E+01
  vertex  0.743798E+02  0.721540E+02  0.211180E+01
  vertex  0.740376E+02  0.721540E+02  0.147380E+01
 endloop
endfacet
facet normal -0.778233E+00  0.468864E+00  0.417756E+00
 outer loop
  vertex  0.740375E+02  0.721539E+02  0.147370E+01
  vertex  0.733487E+02  0.707500E+02  0.176620E+01
  vertex  0.737593E+02  0.707500E+02  0.253110E+01
 endloop
endfacet
facet normal -0.682274E+00  0.469001E+00  0.560839E+00
 outer loop
  vertex  0.743050E+02  0.707500E+02  0.319490E+01
  vertex  0.748347E+02  0.721540E+02  0.266520E+01
  vertex  0.743798E+02  0.721540E+02  0.211180E+01
 endloop
endfacet
facet normal -0.682182E+00  0.469066E+00  0.560896E+00
 outer loop
  vertex  0.743797E+02  0.721539E+02  0.211170E+01
  vertex  0.737593E+02  0.707500E+02  0.253120E+01
  vertex  0.743050E+02  0.707500E+02  0.319490E+01
 endloop
endfacet
facet normal -0.560821E+00  0.469052E+00  0.682254E+00
 outer loop
  vertex  0.749687E+02  0.707500E+02  0.374060E+01
  vertex  0.753881E+02  0.721540E+02  0.312010E+01
  vertex  0.748347E+02  0.721540E+02  0.266520E+01
 endloop
endfacet
facet normal -0.560946E+00  0.469072E+00  0.682137E+00
 outer loop
  vertex  0.748347E+02  0.721539E+02  0.266510E+01
  vertex  0.743050E+02  0.707500E+02  0.319490E+01
  vertex  0.749686E+02  0.707500E+02  0.374060E+01
 endloop
endfacet
facet normal -0.417490E+00  0.468870E+00  0.778372E+00
 outer loop
  vertex  0.757337E+02  0.707500E+02  0.415120E+01
  vertex  0.760261E+02  0.721540E+02  0.346230E+01
  vertex  0.753881E+02  0.721540E+02  0.312010E+01
 endloop
endfacet
facet normal -0.417659E+00  0.468759E+00  0.778348E+00
 outer loop
  vertex  0.753880E+02  0.721539E+02  0.312010E+01
  vertex  0.749687E+02  0.707500E+02  0.374060E+01
  vertex  0.757337E+02  0.707500E+02  0.415110E+01
 endloop
endfacet
facet normal -0.257136E+00  0.468463E+00  0.845236E+00
 outer loop
  vertex  0.765831E+02  0.707500E+02  0.440990E+01
  vertex  0.767348E+02  0.721540E+02  0.367790E+01
  vertex  0.760261E+02  0.721540E+02  0.346230E+01
 endloop
endfacet
facet normal -0.257451E+00  0.468362E+00  0.845196E+00
 outer loop
  vertex  0.760261E+02  0.721539E+02  0.346230E+01
  vertex  0.757337E+02  0.707500E+02  0.415120E+01
  vertex  0.765830E+02  0.707500E+02  0.440990E+01
 endloop
endfacet
facet normal -0.862065E-01  0.467958E+00  0.879536E+00
 outer loop
  vertex  0.775000E+02  0.707500E+02  0.449990E+01
  vertex  0.775000E+02  0.721540E+02  0.375290E+01
  vertex  0.767348E+02  0.721540E+02  0.367790E+01
 endloop
endfacet
facet normal -0.862381E-01  0.467921E+00  0.879552E+00
 outer loop
  vertex  0.767348E+02  0.721539E+02  0.367790E+01
  vertex  0.765831E+02  0.707500E+02  0.440990E+01
  vertex  0.775000E+02  0.707500E+02  0.449980E+01
 endloop
endfacet
facet normal -0.931940E+00 -0.350883E+00 -0.914788E-01
 outer loop
  vertex  0.109000E+03  0.640000E+02  0.000000E+00
  vertex  0.108370E+03  0.640000E+02  0.641810E+01
  vertex  0.108012E+03  0.649689E+02  0.634380E+01
 endloop
endfacet
facet normal -0.931939E+00 -0.350882E+00 -0.914931E-01
 outer loop
  vertex  0.108012E+03  0.649689E+02  0.634380E+01
  vertex  0.108635E+03  0.649689E+02  0.000000E+00
  vertex  0.109000E+03  0.640000E+02  0.000000E+00
 endloop
endfacet
facet normal -0.895611E+00 -0.351337E+00 -0.272844E+00
 outer loop
  vertex  0.108370E+03  0.640000E+02  0.641810E+01
  vertex  0.106559E+03  0.640000E+02  0.123637E+02
  vertex  0.106222E+03  0.649690E+02  0.122205E+02
 endloop
endfacet
facet normal -0.895601E+00 -0.351355E+00 -0.272853E+00
 outer loop
  vertex  0.106222E+03  0.649690E+02  0.122204E+02
  vertex  0.108012E+03  0.649689E+02  0.634380E+01
  vertex  0.108370E+03  0.640000E+02  0.641800E+01
 endloop
endfacet
facet normal -0.824763E+00 -0.351817E+00 -0.442707E+00
 outer loop
  vertex  0.106559E+03  0.640000E+02  0.123637E+02
  vertex  0.103684E+03  0.640000E+02  0.177187E+02
  vertex  0.103381E+03  0.649690E+02  0.175135E+02
 endloop
endfacet
facet normal -0.824773E+00 -0.351794E+00 -0.442709E+00
 outer loop
  vertex  0.103381E+03  0.649690E+02  0.175135E+02
  vertex  0.106222E+03  0.649690E+02  0.122205E+02
  vertex  0.106559E+03  0.640000E+02  0.123636E+02
 endloop
endfacet
facet normal -0.723045E+00 -0.352025E+00 -0.594378E+00
 outer loop
  vertex  0.103684E+03  0.640000E+02  0.177187E+02
  vertex  0.998649E+02  0.640000E+02  0.223649E+02
  vertex  0.996060E+02  0.649689E+02  0.221060E+02
 endloop
endfacet
facet normal -0.723032E+00 -0.352098E+00 -0.594350E+00
 outer loop
  vertex  0.996060E+02  0.649689E+02  0.221060E+02
  vertex  0.103381E+03  0.649690E+02  0.175135E+02
  vertex  0.103684E+03  0.640000E+02  0.177187E+02
 endloop
endfacet
facet normal -0.594352E+00 -0.352129E+00 -0.723015E+00
 outer loop
  vertex  0.998649E+02  0.640000E+02  0.223649E+02
  vertex  0.952187E+02  0.640000E+02  0.261843E+02
  vertex  0.950135E+02  0.649689E+02  0.258811E+02
 endloop
endfacet
facet normal -0.594358E+00 -0.351970E+00 -0.723087E+00
 outer loop
  vertex  0.950134E+02  0.649689E+02  0.258810E+02
  vertex  0.996060E+02  0.649689E+02  0.221060E+02
  vertex  0.998648E+02  0.640000E+02  0.223649E+02
 endloop
endfacet
facet normal -0.442699E+00 -0.351866E+00 -0.824747E+00
 outer loop
  vertex  0.952187E+02  0.640000E+02  0.261843E+02
  vertex  0.898637E+02  0.640000E+02  0.290587E+02
  vertex  0.897205E+02  0.649689E+02  0.287222E+02
 endloop
endfacet
facet normal -0.442714E+00 -0.351735E+00 -0.824795E+00
 outer loop
  vertex  0.897204E+02  0.649689E+02  0.287222E+02
  vertex  0.950135E+02  0.649689E+02  0.258811E+02
  vertex  0.952186E+02  0.640000E+02  0.261842E+02
 endloop
endfacet
facet normal -0.272835E+00 -0.351292E+00 -0.895631E+00
 outer loop
  vertex  0.898637E+02  0.640000E+02  0.290587E+02
  vertex  0.839181E+02  0.640000E+02  0.308699E+02
  vertex  0.838438E+02  0.649689E+02  0.305125E+02
 endloop
endfacet
facet normal -0.272839E+00 -0.351368E+00 -0.895600E+00
 outer loop
  vertex  0.838438E+02  0.649689E+02  0.305125E+02
  vertex  0.897205E+02  0.649689E+02  0.287222E+02
  vertex  0.898637E+02  0.640000E+02  0.290587E+02
 endloop
endfacet
facet normal -0.914824E-01 -0.350799E+00 -0.931971E+00
 outer loop
  vertex  0.839181E+02  0.640000E+02  0.308699E+02
  vertex  0.775000E+02  0.640000E+02  0.314999E+02
  vertex  0.775000E+02  0.649689E+02  0.311352E+02
 endloop
endfacet
facet normal -0.914848E-01 -0.350700E+00 -0.932009E+00
 outer loop
  vertex  0.775000E+02  0.649689E+02  0.311352E+02
  vertex  0.838438E+02  0.649689E+02  0.305125E+02
  vertex  0.839180E+02  0.640000E+02  0.308698E+02
 endloop
endfacet
facet normal -0.989527E+00 -0.106784E+00 -0.971313E-01
 outer loop
  vertex  0.108635E+03  0.649689E+02  0.000000E+00
  vertex  0.108012E+03  0.649689E+02  0.634380E+01
  vertex  0.107939E+03  0.656611E+02  0.632850E+01
 endloop
endfacet
facet normal -0.989526E+00 -0.106786E+00 -0.971327E-01
 outer loop
  vertex  0.107939E+03  0.656611E+02  0.632840E+01
  vertex  0.108561E+03  0.656611E+02  0.000000E+00
  vertex  0.108635E+03  0.649689E+02  0.000000E+00
 endloop
endfacet
facet normal -0.951109E+00 -0.106953E+00 -0.289747E+00
 outer loop
  vertex  0.108012E+03  0.649689E+02  0.634380E+01
  vertex  0.106222E+03  0.649690E+02  0.122205E+02
  vertex  0.106153E+03  0.656611E+02  0.121912E+02
 endloop
endfacet
facet normal -0.951116E+00 -0.106844E+00 -0.289762E+00
 outer loop
  vertex  0.106153E+03  0.656611E+02  0.121912E+02
  vertex  0.107939E+03  0.656611E+02  0.632850E+01
  vertex  0.108012E+03  0.649689E+02  0.634380E+01
 endloop
endfacet
facet normal -0.876023E+00 -0.107142E+00 -0.470218E+00
 outer loop
  vertex  0.106222E+03  0.649690E+02  0.122205E+02
  vertex  0.103381E+03  0.649690E+02  0.175135E+02
  vertex  0.103319E+03  0.656611E+02  0.174715E+02
 endloop
endfacet
facet normal -0.876042E+00 -0.106927E+00 -0.470231E+00
 outer loop
  vertex  0.103319E+03  0.656611E+02  0.174715E+02
  vertex  0.106153E+03  0.656611E+02  0.121912E+02
  vertex  0.106222E+03  0.649690E+02  0.122204E+02
 endloop
endfacet
facet normal -0.768039E+00 -0.107350E+00 -0.631341E+00
 outer loop
  vertex  0.103381E+03  0.649690E+02  0.175135E+02
  vertex  0.996060E+02  0.649689E+02  0.221060E+02
  vertex  0.995529E+02  0.656611E+02  0.220529E+02
 endloop
endfacet
facet normal -0.768040E+00 -0.107231E+00 -0.631360E+00
 outer loop
  vertex  0.995529E+02  0.656611E+02  0.220529E+02
  vertex  0.103319E+03  0.656611E+02  0.174715E+02
  vertex  0.103381E+03  0.649690E+02  0.175135E+02
 endloop
endfacet
facet normal -0.631349E+00 -0.107212E+00 -0.768052E+00
 outer loop
  vertex  0.996060E+02  0.649689E+02  0.221060E+02
  vertex  0.950135E+02  0.649689E+02  0.258811E+02
  vertex  0.949715E+02  0.656611E+02  0.258190E+02
 endloop
endfacet
facet normal -0.631344E+00 -0.107350E+00 -0.768037E+00
 outer loop
  vertex  0.949714E+02  0.656611E+02  0.258190E+02
  vertex  0.995529E+02  0.656611E+02  0.220529E+02
  vertex  0.996060E+02  0.649689E+02  0.221060E+02
 endloop
endfacet
facet normal -0.470221E+00 -0.107101E+00 -0.876026E+00
 outer loop
  vertex  0.950135E+02  0.649689E+02  0.258811E+02
  vertex  0.897205E+02  0.649689E+02  0.287222E+02
  vertex  0.896912E+02  0.656611E+02  0.286533E+02
 endloop
endfacet
facet normal -0.470219E+00 -0.106931E+00 -0.876048E+00
 outer loop
  vertex  0.896912E+02  0.656611E+02  0.286532E+02
  vertex  0.949715E+02  0.656611E+02  0.258190E+02
  vertex  0.950134E+02  0.649689E+02  0.258810E+02
 endloop
endfacet
facet normal -0.289748E+00 -0.106986E+00 -0.951105E+00
 outer loop
  vertex  0.897205E+02  0.649689E+02  0.287222E+02
  vertex  0.838438E+02  0.649689E+02  0.305125E+02
  vertex  0.838285E+02  0.656611E+02  0.304393E+02
 endloop
endfacet
facet normal -0.289741E+00 -0.106895E+00 -0.951117E+00
 outer loop
  vertex  0.838284E+02  0.656611E+02  0.304393E+02
  vertex  0.896912E+02  0.656611E+02  0.286533E+02
  vertex  0.897204E+02  0.649689E+02  0.287222E+02
 endloop
endfacet
facet normal -0.971306E-01 -0.106788E+00 -0.989526E+00
 outer loop
  vertex  0.838438E+02  0.649689E+02  0.305125E+02
  vertex  0.775000E+02  0.649689E+02  0.311352E+02
  vertex  0.775000E+02  0.656611E+02  0.310605E+02
 endloop
endfacet
facet normal -0.971154E-01 -0.106790E+00 -0.989527E+00
 outer loop
  vertex  0.775000E+02  0.656611E+02  0.310604E+02
  vertex  0.838285E+02  0.656611E+02  0.304393E+02
  vertex  0.838438E+02  0.649689E+02  0.305125E+02
 endloop
endfacet
facet normal -0.927337E+00  0.362988E+00 -0.910266E-01
 outer loop
  vertex  0.108561E+03  0.656611E+02  0.000000E+00
  vertex  0.107939E+03  0.656611E+02  0.632850E+01
  vertex  0.108099E+03  0.660764E+02  0.636170E+01
 endloop
endfacet
facet normal -0.927309E+00  0.363060E+00 -0.910293E-01
 outer loop
  vertex  0.108099E+03  0.660764E+02  0.636170E+01
  vertex  0.108723E+03  0.660764E+02  0.000000E+00
  vertex  0.108561E+03  0.656611E+02  0.000000E+00
 endloop
endfacet
facet normal -0.891133E+00  0.363573E+00 -0.271473E+00
 outer loop
  vertex  0.107939E+03  0.656611E+02  0.632850E+01
  vertex  0.106153E+03  0.656611E+02  0.121912E+02
  vertex  0.106303E+03  0.660764E+02  0.122550E+02
 endloop
endfacet
facet normal -0.891123E+00  0.363589E+00 -0.271482E+00
 outer loop
  vertex  0.106303E+03  0.660764E+02  0.122550E+02
  vertex  0.108099E+03  0.660764E+02  0.636170E+01
  vertex  0.107939E+03  0.656611E+02  0.632840E+01
 endloop
endfacet
facet normal -0.820585E+00  0.364186E+00 -0.440464E+00
 outer loop
  vertex  0.106153E+03  0.656611E+02  0.121912E+02
  vertex  0.103319E+03  0.656611E+02  0.174715E+02
  vertex  0.103454E+03  0.660764E+02  0.175630E+02
 endloop
endfacet
facet normal -0.820567E+00  0.364240E+00 -0.440452E+00
 outer loop
  vertex  0.103454E+03  0.660764E+02  0.175629E+02
  vertex  0.106303E+03  0.660764E+02  0.122550E+02
  vertex  0.106153E+03  0.656611E+02  0.121912E+02
 endloop
endfacet
facet normal -0.719344E+00  0.364518E+00 -0.591330E+00
 outer loop
  vertex  0.103319E+03  0.656611E+02  0.174715E+02
  vertex  0.995529E+02  0.656611E+02  0.220529E+02
  vertex  0.996684E+02  0.660764E+02  0.221684E+02
 endloop
endfacet
facet normal -0.719354E+00  0.364472E+00 -0.591346E+00
 outer loop
  vertex  0.996684E+02  0.660764E+02  0.221683E+02
  vertex  0.103454E+03  0.660764E+02  0.175630E+02
  vertex  0.103319E+03  0.656611E+02  0.174715E+02
 endloop
endfacet
facet normal -0.591339E+00  0.364482E+00 -0.719355E+00
 outer loop
  vertex  0.995529E+02  0.656611E+02  0.220529E+02
  vertex  0.949715E+02  0.656611E+02  0.258190E+02
  vertex  0.950630E+02  0.660764E+02  0.259542E+02
 endloop
endfacet
facet normal -0.591328E+00  0.364517E+00 -0.719346E+00
 outer loop
  vertex  0.950630E+02  0.660764E+02  0.259542E+02
  vertex  0.996684E+02  0.660764E+02  0.221684E+02
  vertex  0.995529E+02  0.656611E+02  0.220529E+02
 endloop
endfacet
facet normal -0.440486E+00  0.364068E+00 -0.820626E+00
 outer loop
  vertex  0.949715E+02  0.656611E+02  0.258190E+02
  vertex  0.896912E+02  0.656611E+02  0.286533E+02
  vertex  0.897550E+02  0.660764E+02  0.288033E+02
 endloop
endfacet
facet normal -0.440431E+00  0.364283E+00 -0.820560E+00
 outer loop
  vertex  0.897549E+02  0.660764E+02  0.288033E+02
  vertex  0.950630E+02  0.660764E+02  0.259542E+02
  vertex  0.949714E+02  0.656611E+02  0.258190E+02
 endloop
endfacet
facet normal -0.271478E+00  0.363531E+00 -0.891148E+00
 outer loop
  vertex  0.896912E+02  0.656611E+02  0.286533E+02
  vertex  0.838285E+02  0.656611E+02  0.304393E+02
  vertex  0.838617E+02  0.660764E+02  0.305986E+02
 endloop
endfacet
facet normal -0.271449E+00  0.363756E+00 -0.891065E+00
 outer loop
  vertex  0.838617E+02  0.660764E+02  0.305986E+02
  vertex  0.897550E+02  0.660764E+02  0.288033E+02
  vertex  0.896912E+02  0.656611E+02  0.286532E+02
 endloop
endfacet
facet normal -0.910234E-01  0.363067E+00 -0.927306E+00
 outer loop
  vertex  0.838285E+02  0.656611E+02  0.304393E+02
  vertex  0.775000E+02  0.656611E+02  0.310605E+02
  vertex  0.775000E+02  0.660764E+02  0.312231E+02
 endloop
endfacet
facet normal -0.910319E-01  0.363004E+00 -0.927330E+00
 outer loop
  vertex  0.775000E+02  0.660764E+02  0.312231E+02
  vertex  0.838617E+02  0.660764E+02  0.305986E+02
  vertex  0.838284E+02  0.656611E+02  0.304393E+02
 endloop
endfacet
facet normal -0.369994E+00  0.928324E+00 -0.363205E-01
 outer loop
  vertex  0.108723E+03  0.660764E+02  0.000000E+00
  vertex  0.108099E+03  0.660764E+02  0.636170E+01
  vertex  0.108439E+03  0.662148E+02  0.643240E+01
 endloop
endfacet
facet normal -0.369943E+00  0.928345E+00 -0.362987E-01
 outer loop
  vertex  0.108439E+03  0.662147E+02  0.643240E+01
  vertex  0.109070E+03  0.662148E+02  0.000000E+00
  vertex  0.108723E+03  0.660764E+02  0.000000E+00
 endloop
endfacet
facet normal -0.355163E+00  0.928522E+00 -0.108195E+00
 outer loop
  vertex  0.108099E+03  0.660764E+02  0.636170E+01
  vertex  0.106303E+03  0.660764E+02  0.122550E+02
  vertex  0.106624E+03  0.662148E+02  0.123913E+02
 endloop
endfacet
facet normal -0.355148E+00  0.928529E+00 -0.108182E+00
 outer loop
  vertex  0.106623E+03  0.662147E+02  0.123913E+02
  vertex  0.108439E+03  0.662148E+02  0.643240E+01
  vertex  0.108099E+03  0.660764E+02  0.636170E+01
 endloop
endfacet
facet normal -0.326738E+00  0.928700E+00 -0.175379E+00
 outer loop
  vertex  0.106303E+03  0.660764E+02  0.122550E+02
  vertex  0.103454E+03  0.660764E+02  0.175630E+02
  vertex  0.103743E+03  0.662148E+02  0.177582E+02
 endloop
endfacet
facet normal -0.326607E+00  0.928760E+00 -0.175305E+00
 outer loop
  vertex  0.103743E+03  0.662147E+02  0.177581E+02
  vertex  0.106624E+03  0.662148E+02  0.123913E+02
  vertex  0.106303E+03  0.660764E+02  0.122550E+02
 endloop
endfacet
facet normal -0.286215E+00  0.928830E+00 -0.235278E+00
 outer loop
  vertex  0.103454E+03  0.660764E+02  0.175630E+02
  vertex  0.996684E+02  0.660764E+02  0.221684E+02
  vertex  0.999149E+02  0.662148E+02  0.224149E+02
 endloop
endfacet
facet normal -0.286218E+00  0.928833E+00 -0.235262E+00
 outer loop
  vertex  0.999149E+02  0.662147E+02  0.224148E+02
  vertex  0.103743E+03  0.662148E+02  0.177582E+02
  vertex  0.103454E+03  0.660764E+02  0.175629E+02
 endloop
endfacet
facet normal -0.235274E+00  0.928833E+00 -0.286209E+00
 outer loop
  vertex  0.996684E+02  0.660764E+02  0.221684E+02
  vertex  0.950630E+02  0.660764E+02  0.259542E+02
  vertex  0.952583E+02  0.662148E+02  0.262428E+02
 endloop
endfacet
facet normal -0.235241E+00  0.928859E+00 -0.286152E+00
 outer loop
  vertex  0.952583E+02  0.662147E+02  0.262427E+02
  vertex  0.999149E+02  0.662148E+02  0.224149E+02
  vertex  0.996684E+02  0.660764E+02  0.221683E+02
 endloop
endfacet
facet normal -0.175345E+00  0.928729E+00 -0.326676E+00
 outer loop
  vertex  0.950630E+02  0.660764E+02  0.259542E+02
  vertex  0.897550E+02  0.660764E+02  0.288033E+02
  vertex  0.898913E+02  0.662148E+02  0.291236E+02
 endloop
endfacet
facet normal -0.175369E+00  0.928719E+00 -0.326692E+00
 outer loop
  vertex  0.898912E+02  0.662147E+02  0.291236E+02
  vertex  0.952583E+02  0.662148E+02  0.262428E+02
  vertex  0.950630E+02  0.660764E+02  0.259542E+02
 endloop
endfacet
facet normal -0.108190E+00  0.928528E+00 -0.355147E+00
 outer loop
  vertex  0.897550E+02  0.660764E+02  0.288033E+02
  vertex  0.838617E+02  0.660764E+02  0.305986E+02
  vertex  0.839324E+02  0.662148E+02  0.309389E+02
 endloop
endfacet
facet normal -0.108196E+00  0.928533E+00 -0.355133E+00
 outer loop
  vertex  0.839324E+02  0.662147E+02  0.309388E+02
  vertex  0.898913E+02  0.662148E+02  0.291236E+02
  vertex  0.897549E+02  0.660764E+02  0.288033E+02
 endloop
endfacet
facet normal -0.363246E-01  0.928308E+00 -0.370034E+00
 outer loop
  vertex  0.838617E+02  0.660764E+02  0.305986E+02
  vertex  0.775000E+02  0.660764E+02  0.312231E+02
  vertex  0.775000E+02  0.662148E+02  0.315703E+02
 endloop
endfacet
facet normal -0.363270E-01  0.928323E+00 -0.369995E+00
 outer loop
  vertex  0.775000E+02  0.662147E+02  0.315702E+02
  vertex  0.839324E+02  0.662148E+02  0.309389E+02
  vertex  0.838617E+02  0.660764E+02  0.305986E+02
 endloop
endfacet
facet normal  0.277484E+00  0.960344E+00  0.272374E-01
 outer loop
  vertex  0.109070E+03  0.662148E+02  0.000000E+00
  vertex  0.108439E+03  0.662148E+02  0.643240E+01
  vertex  0.108908E+03  0.660764E+02  0.653000E+01
 endloop
endfacet
facet normal  0.277234E+00  0.960417E+00  0.272139E-01
 outer loop
  vertex  0.108908E+03  0.660764E+02  0.653000E+01
  vertex  0.109549E+03  0.660764E+02  0.000000E+00
  vertex  0.109070E+03  0.662147E+02  0.000000E+00
 endloop
endfacet
facet normal  0.266342E+00  0.960457E+00  0.811379E-01
 outer loop
  vertex  0.108439E+03  0.662148E+02  0.643240E+01
  vertex  0.106624E+03  0.662148E+02  0.123913E+02
  vertex  0.107065E+03  0.660764E+02  0.125793E+02
 endloop
endfacet
facet normal  0.266137E+00  0.960519E+00  0.810835E-01
 outer loop
  vertex  0.107065E+03  0.660764E+02  0.125792E+02
  vertex  0.108908E+03  0.660764E+02  0.653000E+01
  vertex  0.108439E+03  0.662147E+02  0.643240E+01
 endloop
endfacet
facet normal  0.244936E+00  0.960584E+00  0.131475E+00
 outer loop
  vertex  0.106624E+03  0.662148E+02  0.123913E+02
  vertex  0.103743E+03  0.662148E+02  0.177582E+02
  vertex  0.104141E+03  0.660764E+02  0.180277E+02
 endloop
endfacet
facet normal  0.244751E+00  0.960644E+00  0.131378E+00
 outer loop
  vertex  0.104141E+03  0.660764E+02  0.180277E+02
  vertex  0.107065E+03  0.660764E+02  0.125793E+02
  vertex  0.106623E+03  0.662147E+02  0.123913E+02
 endloop
endfacet
facet normal  0.214555E+00  0.960656E+00  0.176369E+00
 outer loop
  vertex  0.103743E+03  0.662148E+02  0.177582E+02
  vertex  0.999149E+02  0.662148E+02  0.224149E+02
  vertex  0.100255E+03  0.660764E+02  0.227550E+02
 endloop
endfacet
facet normal  0.214361E+00  0.960727E+00  0.176216E+00
 outer loop
  vertex  0.100255E+03  0.660764E+02  0.227549E+02
  vertex  0.104141E+03  0.660764E+02  0.180277E+02
  vertex  0.103743E+03  0.662147E+02  0.177581E+02
 endloop
endfacet
facet normal  0.176400E+00  0.960643E+00  0.214589E+00
 outer loop
  vertex  0.999149E+02  0.662148E+02  0.224149E+02
  vertex  0.952583E+02  0.662148E+02  0.262428E+02
  vertex  0.955277E+02  0.660764E+02  0.266409E+02
 endloop
endfacet
facet normal  0.176223E+00  0.960721E+00  0.214385E+00
 outer loop
  vertex  0.955277E+02  0.660764E+02  0.266408E+02
  vertex  0.100255E+03  0.660764E+02  0.227550E+02
  vertex  0.999149E+02  0.662147E+02  0.224148E+02
 endloop
endfacet
facet normal  0.131483E+00  0.960577E+00  0.244957E+00
 outer loop
  vertex  0.952583E+02  0.662148E+02  0.262428E+02
  vertex  0.898913E+02  0.662148E+02  0.291236E+02
  vertex  0.900793E+02  0.660764E+02  0.295654E+02
 endloop
endfacet
facet normal  0.131371E+00  0.960642E+00  0.244760E+00
 outer loop
  vertex  0.900792E+02  0.660764E+02  0.295653E+02
  vertex  0.955277E+02  0.660764E+02  0.266409E+02
  vertex  0.952583E+02  0.662147E+02  0.262427E+02
 endloop
endfacet
facet normal  0.811292E-01  0.960466E+00  0.266314E+00
 outer loop
  vertex  0.898913E+02  0.662148E+02  0.291236E+02
  vertex  0.839324E+02  0.662148E+02  0.309389E+02
  vertex  0.840300E+02  0.660764E+02  0.314083E+02
 endloop
endfacet
facet normal  0.810811E-01  0.960515E+00  0.266152E+00
 outer loop
  vertex  0.840299E+02  0.660764E+02  0.314083E+02
  vertex  0.900793E+02  0.660764E+02  0.295654E+02
  vertex  0.898912E+02  0.662147E+02  0.291236E+02
 endloop
endfacet
facet normal  0.272364E-01  0.960348E+00  0.277472E+00
 outer loop
  vertex  0.839324E+02  0.662148E+02  0.309389E+02
  vertex  0.775000E+02  0.662148E+02  0.315703E+02
  vertex  0.775000E+02  0.660764E+02  0.320493E+02
 endloop
endfacet
facet normal  0.272152E-01  0.960413E+00  0.277247E+00
 outer loop
  vertex  0.775000E+02  0.660764E+02  0.320493E+02
  vertex  0.840300E+02  0.660764E+02  0.314083E+02
  vertex  0.839324E+02  0.662147E+02  0.309388E+02
 endloop
endfacet
facet normal  0.595987E+00  0.800860E+00  0.585034E-01
 outer loop
  vertex  0.109549E+03  0.660764E+02  0.000000E+00
  vertex  0.108908E+03  0.660764E+02  0.653000E+01
  vertex  0.109455E+03  0.656611E+02  0.664370E+01
 endloop
endfacet
facet normal  0.595960E+00  0.800880E+00  0.585042E-01
 outer loop
  vertex  0.109455E+03  0.656611E+02  0.664370E+01
  vertex  0.110107E+03  0.656611E+02  0.000000E+00
  vertex  0.109549E+03  0.660764E+02  0.000000E+00
 endloop
endfacet
facet normal  0.572189E+00  0.801382E+00  0.174316E+00
 outer loop
  vertex  0.108908E+03  0.660764E+02  0.653000E+01
  vertex  0.107065E+03  0.660764E+02  0.125793E+02
  vertex  0.107580E+03  0.656611E+02  0.127984E+02
 endloop
endfacet
facet normal  0.572260E+00  0.801327E+00  0.174339E+00
 outer loop
  vertex  0.107580E+03  0.656611E+02  0.127983E+02
  vertex  0.109455E+03  0.656611E+02  0.664370E+01
  vertex  0.108908E+03  0.660764E+02  0.653000E+01
 endloop
endfacet
facet normal  0.526494E+00  0.801835E+00  0.282603E+00
 outer loop
  vertex  0.107065E+03  0.660764E+02  0.125793E+02
  vertex  0.104141E+03  0.660764E+02  0.180277E+02
  vertex  0.104605E+03  0.656611E+02  0.183416E+02
 endloop
endfacet
facet normal  0.526399E+00  0.801912E+00  0.282562E+00
 outer loop
  vertex  0.104605E+03  0.656611E+02  0.183416E+02
  vertex  0.107580E+03  0.656611E+02  0.127984E+02
  vertex  0.107065E+03  0.660764E+02  0.125792E+02
 endloop
endfacet
facet normal  0.461406E+00  0.802029E+00  0.379282E+00
 outer loop
  vertex  0.104141E+03  0.660764E+02  0.180277E+02
  vertex  0.100255E+03  0.660764E+02  0.227550E+02
  vertex  0.100651E+03  0.656611E+02  0.231512E+02
 endloop
endfacet
facet normal  0.461292E+00  0.802124E+00  0.379219E+00
 outer loop
  vertex  0.100651E+03  0.656611E+02  0.231511E+02
  vertex  0.104605E+03  0.656611E+02  0.183416E+02
  vertex  0.104141E+03  0.660764E+02  0.180277E+02
 endloop
endfacet
facet normal  0.379233E+00  0.802086E+00  0.461347E+00
 outer loop
  vertex  0.100255E+03  0.660764E+02  0.227550E+02
  vertex  0.955277E+02  0.660764E+02  0.266409E+02
  vertex  0.958416E+02  0.656611E+02  0.271049E+02
 endloop
endfacet
facet normal  0.379224E+00  0.802101E+00  0.461328E+00
 outer loop
  vertex  0.958415E+02  0.656611E+02  0.271049E+02
  vertex  0.100651E+03  0.656611E+02  0.231512E+02
  vertex  0.100255E+03  0.660764E+02  0.227549E+02
 endloop
endfacet
facet normal  0.282597E+00  0.801843E+00  0.526485E+00
 outer loop
  vertex  0.955277E+02  0.660764E+02  0.266409E+02
  vertex  0.900793E+02  0.660764E+02  0.295654E+02
  vertex  0.902984E+02  0.656611E+02  0.300803E+02
 endloop
endfacet
facet normal  0.282568E+00  0.801880E+00  0.526444E+00
 outer loop
  vertex  0.902984E+02  0.656611E+02  0.300802E+02
  vertex  0.958416E+02  0.656611E+02  0.271049E+02
  vertex  0.955277E+02  0.660764E+02  0.266408E+02
 endloop
endfacet
facet normal  0.174337E+00  0.801328E+00  0.572259E+00
 outer loop
  vertex  0.900793E+02  0.660764E+02  0.295654E+02
  vertex  0.840300E+02  0.660764E+02  0.314083E+02
  vertex  0.841437E+02  0.656611E+02  0.319552E+02
 endloop
endfacet
facet normal  0.174279E+00  0.801446E+00  0.572112E+00
 outer loop
  vertex  0.841436E+02  0.656611E+02  0.319552E+02
  vertex  0.902984E+02  0.656611E+02  0.300803E+02
  vertex  0.900792E+02  0.660764E+02  0.295653E+02
 endloop
endfacet
facet normal  0.585009E-01  0.800880E+00  0.595960E+00
 outer loop
  vertex  0.840300E+02  0.660764E+02  0.314083E+02
  vertex  0.775000E+02  0.660764E+02  0.320493E+02
  vertex  0.775000E+02  0.656611E+02  0.326074E+02
 endloop
endfacet
facet normal  0.584973E-01  0.800866E+00  0.595980E+00
 outer loop
  vertex  0.775000E+02  0.656611E+02  0.326073E+02
  vertex  0.841437E+02  0.656611E+02  0.319552E+02
  vertex  0.840299E+02  0.660764E+02  0.314083E+02
 endloop
endfacet
facet normal  0.761908E+00  0.643353E+00  0.747949E-01
 outer loop
  vertex  0.110107E+03  0.656611E+02  0.000000E+00
  vertex  0.109455E+03  0.656611E+02  0.664370E+01
  vertex  0.110028E+03  0.649689E+02  0.676280E+01
 endloop
endfacet
facet normal  0.761901E+00  0.643360E+00  0.747956E-01
 outer loop
  vertex  0.110028E+03  0.649689E+02  0.676280E+01
  vertex  0.110692E+03  0.649689E+02  0.000000E+00
  vertex  0.110107E+03  0.656611E+02  0.000000E+00
 endloop
endfacet
facet normal  0.731848E+00  0.643969E+00  0.222942E+00
 outer loop
  vertex  0.109455E+03  0.656611E+02  0.664370E+01
  vertex  0.107580E+03  0.656611E+02  0.127984E+02
  vertex  0.108119E+03  0.649689E+02  0.130278E+02
 endloop
endfacet
facet normal  0.731844E+00  0.643968E+00  0.222956E+00
 outer loop
  vertex  0.108119E+03  0.649689E+02  0.130277E+02
  vertex  0.110028E+03  0.649689E+02  0.676280E+01
  vertex  0.109455E+03  0.656611E+02  0.664370E+01
 endloop
endfacet
facet normal  0.673654E+00  0.644546E+00  0.361595E+00
 outer loop
  vertex  0.107580E+03  0.656611E+02  0.127984E+02
  vertex  0.104605E+03  0.656611E+02  0.183416E+02
  vertex  0.105091E+03  0.649689E+02  0.186704E+02
 endloop
endfacet
facet normal  0.673564E+00  0.644657E+00  0.361564E+00
 outer loop
  vertex  0.105091E+03  0.649689E+02  0.186704E+02
  vertex  0.108119E+03  0.649689E+02  0.130278E+02
  vertex  0.107580E+03  0.656611E+02  0.127983E+02
 endloop
endfacet
facet normal  0.590378E+00  0.644921E+00  0.485316E+00
 outer loop
  vertex  0.104605E+03  0.656611E+02  0.183416E+02
  vertex  0.100651E+03  0.656611E+02  0.231512E+02
  vertex  0.101066E+03  0.649689E+02  0.235662E+02
 endloop
endfacet
facet normal  0.590368E+00  0.644940E+00  0.485301E+00
 outer loop
  vertex  0.101066E+03  0.649689E+02  0.235662E+02
  vertex  0.105091E+03  0.649689E+02  0.186704E+02
  vertex  0.104605E+03  0.656611E+02  0.183416E+02
 endloop
endfacet
facet normal  0.485332E+00  0.644891E+00  0.590397E+00
 outer loop
  vertex  0.100651E+03  0.656611E+02  0.231512E+02
  vertex  0.958416E+02  0.656611E+02  0.271049E+02
  vertex  0.961704E+02  0.649689E+02  0.275907E+02
 endloop
endfacet
facet normal  0.485264E+00  0.645010E+00  0.590323E+00
 outer loop
  vertex  0.961704E+02  0.649689E+02  0.275907E+02
  vertex  0.101066E+03  0.649689E+02  0.235662E+02
  vertex  0.100651E+03  0.656611E+02  0.231511E+02
 endloop
endfacet
facet normal  0.361585E+00  0.644571E+00  0.673636E+00
 outer loop
  vertex  0.958416E+02  0.656611E+02  0.271049E+02
  vertex  0.902984E+02  0.656611E+02  0.300803E+02
  vertex  0.905278E+02  0.649689E+02  0.306195E+02
 endloop
endfacet
facet normal  0.361577E+00  0.644576E+00  0.673634E+00
 outer loop
  vertex  0.905278E+02  0.649689E+02  0.306194E+02
  vertex  0.961704E+02  0.649689E+02  0.275907E+02
  vertex  0.958415E+02  0.656611E+02  0.271049E+02
 endloop
endfacet
facet normal  0.222942E+00  0.643969E+00  0.731848E+00
 outer loop
  vertex  0.902984E+02  0.656611E+02  0.300803E+02
  vertex  0.841437E+02  0.656611E+02  0.319552E+02
  vertex  0.842628E+02  0.649689E+02  0.325280E+02
 endloop
endfacet
facet normal  0.222917E+00  0.644030E+00  0.731802E+00
 outer loop
  vertex  0.842628E+02  0.649689E+02  0.325279E+02
  vertex  0.905278E+02  0.649689E+02  0.306195E+02
  vertex  0.902984E+02  0.656611E+02  0.300802E+02
 endloop
endfacet
facet normal  0.747998E-01  0.643294E+00  0.761957E+00
 outer loop
  vertex  0.841437E+02  0.656611E+02  0.319552E+02
  vertex  0.775000E+02  0.656611E+02  0.326074E+02
  vertex  0.775000E+02  0.649689E+02  0.331918E+02
 endloop
endfacet
facet normal  0.747732E-01  0.643358E+00  0.761905E+00
 outer loop
  vertex  0.775000E+02  0.649689E+02  0.331917E+02
  vertex  0.842628E+02  0.649689E+02  0.325280E+02
  vertex  0.841436E+02  0.656611E+02  0.319552E+02
 endloop
endfacet
facet normal  0.863426E+00  0.497307E+00  0.847496E-01
 outer loop
  vertex  0.110692E+03  0.649689E+02  0.000000E+00
  vertex  0.110028E+03  0.649689E+02  0.676280E+01
  vertex  0.110575E+03  0.640000E+02  0.687650E+01
 endloop
endfacet
facet normal  0.863370E+00  0.497398E+00  0.847741E-01
 outer loop
  vertex  0.110575E+03  0.640000E+02  0.687650E+01
  vertex  0.111250E+03  0.640000E+02  0.000000E+00
  vertex  0.110692E+03  0.649689E+02  0.000000E+00
 endloop
endfacet
facet normal  0.829593E+00  0.497904E+00  0.252718E+00
 outer loop
  vertex  0.110028E+03  0.649689E+02  0.676280E+01
  vertex  0.108119E+03  0.649689E+02  0.130278E+02
  vertex  0.108634E+03  0.640000E+02  0.132468E+02
 endloop
endfacet
facet normal  0.829551E+00  0.497981E+00  0.252708E+00
 outer loop
  vertex  0.108634E+03  0.640000E+02  0.132468E+02
  vertex  0.110575E+03  0.640000E+02  0.687650E+01
  vertex  0.110028E+03  0.649689E+02  0.676280E+01
 endloop
endfacet
facet normal  0.763795E+00  0.498526E+00  0.409985E+00
 outer loop
  vertex  0.108119E+03  0.649689E+02  0.130278E+02
  vertex  0.105091E+03  0.649689E+02  0.186704E+02
  vertex  0.105555E+03  0.640000E+02  0.189843E+02
 endloop
endfacet
facet normal  0.763765E+00  0.498591E+00  0.409963E+00
 outer loop
  vertex  0.105555E+03  0.640000E+02  0.189843E+02
  vertex  0.108634E+03  0.640000E+02  0.132468E+02
  vertex  0.108119E+03  0.649689E+02  0.130277E+02
 endloop
endfacet
facet normal  0.669499E+00  0.498886E+00  0.550349E+00
 outer loop
  vertex  0.105091E+03  0.649689E+02  0.186704E+02
  vertex  0.101066E+03  0.649689E+02  0.235662E+02
  vertex  0.101463E+03  0.640000E+02  0.239624E+02
 endloop
endfacet
facet normal  0.669491E+00  0.498912E+00  0.550335E+00
 outer loop
  vertex  0.101463E+03  0.640000E+02  0.239624E+02
  vertex  0.105555E+03  0.640000E+02  0.189843E+02
  vertex  0.105091E+03  0.649689E+02  0.186704E+02
 endloop
endfacet
facet normal  0.550360E+00  0.498856E+00  0.669512E+00
 outer loop
  vertex  0.101066E+03  0.649689E+02  0.235662E+02
  vertex  0.961704E+02  0.649689E+02  0.275907E+02
  vertex  0.964843E+02  0.640000E+02  0.280546E+02
 endloop
endfacet
facet normal  0.550335E+00  0.498875E+00  0.669518E+00
 outer loop
  vertex  0.964842E+02  0.640000E+02  0.280545E+02
  vertex  0.101463E+03  0.640000E+02  0.239624E+02
  vertex  0.101066E+03  0.649689E+02  0.235662E+02
 endloop
endfacet
facet normal  0.409992E+00  0.498501E+00  0.763809E+00
 outer loop
  vertex  0.961704E+02  0.649689E+02  0.275907E+02
  vertex  0.905278E+02  0.649689E+02  0.306195E+02
  vertex  0.907468E+02  0.640000E+02  0.311343E+02
 endloop
endfacet
facet normal  0.409983E+00  0.498521E+00  0.763800E+00
 outer loop
  vertex  0.907468E+02  0.640000E+02  0.311343E+02
  vertex  0.964843E+02  0.640000E+02  0.280546E+02
  vertex  0.961704E+02  0.649689E+02  0.275907E+02
 endloop
endfacet
facet normal  0.252716E+00  0.497919E+00  0.829585E+00
 outer loop
  vertex  0.905278E+02  0.649689E+02  0.306195E+02
  vertex  0.842628E+02  0.649689E+02  0.325280E+02
  vertex  0.843765E+02  0.640000E+02  0.330749E+02
 endloop
endfacet
facet normal  0.252710E+00  0.497969E+00  0.829557E+00
 outer loop
  vertex  0.843765E+02  0.640000E+02  0.330749E+02
  vertex  0.907468E+02  0.640000E+02  0.311343E+02
  vertex  0.905278E+02  0.649689E+02  0.306194E+02
 endloop
endfacet
facet normal  0.847474E-01  0.497336E+00  0.863409E+00
 outer loop
  vertex  0.842628E+02  0.649689E+02  0.325280E+02
  vertex  0.775000E+02  0.649689E+02  0.331918E+02
  vertex  0.775000E+02  0.640000E+02  0.337499E+02
 endloop
endfacet
facet normal  0.847501E-01  0.497376E+00  0.863386E+00
 outer loop
  vertex  0.775000E+02  0.640000E+02  0.337499E+02
  vertex  0.843765E+02  0.640000E+02  0.330749E+02
  vertex  0.842628E+02  0.649689E+02  0.325279E+02
 endloop
endfacet
 endsolid TEATEST 
```

### Code 

![File_Code](src/File_Code.jpg)

- Have a look at tha actual file content
  - This is also the view the markdown files are edited in
  - https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax 
- Click on the line number to
  - Open a new issue
  - Open a new discussion
  - Switch to GIT blame

### Blame

![File_Blame](src/File_Blame.jpg)

- Have a look at which commit made which lines
- Use this view to find out which change made the document as it currently is
- Click on the line number to
  - Open a new issue
  - Open a new discussion

## Local Toolchain

### Version Control System

#### Git Desktop

https://desktop.github.com/

### Code Editor

#### Visual Studio Code

https://code.visualstudio.com/

## Conclude Training
- Lets have a look at our working model


-  Lets have a look at the new Network graph
  -  https://github.com/ClosedSourcerer/ExpertGroupGitHubTraining/network  
- Lets create a Repository we can work on
  - https://github.com/orgs/catenax-eV/repositories 
Lets create Feature-Branches if applicable
 - Lets create a new team within catena-X ev
  - https://github.com/orgs/catenax-eV/teams
    - DCM Expert Group
- Lets create a new project within catena-x ev
  - https://github.com/orgs/catenax-eV/projects 
    - DCM Expert Group

### How do these things interlink with each other?

![Organisation](src/Organisation.svg)

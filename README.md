<!--
author:   Bruna Piereck, Alexander Botzki, James Collier, Tuur Muyldermans
email:    trainingandconferences@vib.be
version:  1.0.0
language: en
narrator: UK English Female

icon:     https://vib.be/sites/vib.sites.vib.be/files/logo_VIB_noTagline.svg

comment:  This document shall provide an entire compendium and course on the
          development of Open-courSes with [LiaScript](https://LiaScript.github.io).
          As the language and the systems grows, also this document will be updated.
          Feel free to fork or copy it, translations are very welcome...

script:   https://cdn.jsdelivr.net/chartist.js/latest/chartist.min.js
          https://felixhao28.github.io/JSCPP/dist/JSCPP.es5.min.js

link:     https://cdn.jsdelivr.net/chartist.js/latest/chartist.min.css
link:     https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css
link:     https://raw.githubusercontent.com/vib-tcp/material-liascript/master/img/org.css
link:     https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.11.2/css/all.min.css
link:     https://fonts.googleapis.com/css2?family=Saira+Condensed:wght@300&display=swap
link:     https://fonts.googleapis.com/css2?family=Open+Sans&display=swap

link:  https://raw.githubusercontent.com/vib-tcp/material-liascript/master/vib-styles.css

@orcid: [@0](@1)<!--class="orcid-logo-for-author-list" -->

@edition: 10th 
@CourseTitle: Versioning code and documentation with Git & GitHub

@JSONLD
<script run-once>
  let json = @0 

  const script = document.createElement('script');
  script.type = 'application/ld+json';
  script.text = JSON.stringify(json);

  document.head.appendChild(script);

  // this is only needed to prevent and output,
  // as long as the result of a script is undefined,
  // it is not shown or rendered within LiaScript
  console.debug("added json to head")
</script>
@end

-->

# Versioning code and documentation with Git & GitHub

Lesson overview
---------------

> <i class="fa fa-lock"></i> **License:** [Creative Commons Attribution 4.0 International  License](https://creativecommons.org/licenses/by/4.0/deed.en)
>
> [<img src="https://raw.githubusercontent.com/vibbits/introduction-github/master/images/logos/CC-by.png" title="" alt="" width="80">](https://creativecommons.org/licenses/by/4.0/)
>
> <i class="fa fa-user"></i> **Target Audience:** Researchers, trainers, training providers
>
> <svg xmlns="http://www.w3.org/2000/svg" height="14" width="16" viewBox="0 0 576 512"><!--!Font Awesome Free 6.5.1 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free Copyright 2023 Fonticons, Inc.--><path d="M384 64c0-17.7 14.3-32 32-32H544c17.7 0 32 14.3 32 32s-14.3 32-32 32H448v96c0 17.7-14.3 32-32 32H320v96c0 17.7-14.3 32-32 32H192v96c0 17.7-14.3 32-32 32H32c-17.7 0-32-14.3-32-32s14.3-32 32-32h96V320c0-17.7 14.3-32 32-32h96V192c0-17.7 14.3-32 32-32h96V64z"/></svg> **Level:** Beginner  
>
> <i class="fa fa-arrow-left"></i> **Prerequisites**  
> To be able to follow this course, learners should:
>
> Have BASH/Linux/Unix command-line skills. 
>
>If you lack command-line experience, you can prepare by following this [e-learning or Linux introduction](https://www.vibtrainingandconferences.be/events?f%5B0%5D=status%3Aupcoming&text=linux).
>
> <i class="fa fa-bookmark"></i> **Description**  
> This hands-on course introduces Git and GitHub to researchers, trainers, support staff, and anyone interested in version control. Git and GitHub are essential tools for ensuring reproducibility and efficient collaboration in computational projects. You will learn how to configure Git, manage project history, and work with local and remote repositories. 
>
>Through practical exercises, you will gain confidence in creating and managing repositories, applying core Git operations, and collaborating through branching and pull requests. 
>
> The **presentation** which goes alongside this material can be found [here](./docs/presentation/).
>
> <i class="fa fa-arrow-right"></i> **Learning Outcomes:**  
> By the end of the course, learners will be able to:
>
> 1. Configure Git on a local machine for version control.
> 2. Create and manage repositories to track changes and maintain project history.
> 3. Apply essential Git operations (staging, committing, pushing) for effective workflow locally and remotely.
> 4. Connect and synchronize local repositories with GitHub.
> 5. Implement branching and pull request workflows for collaborative development.
> 6. Interpret Git history and logs to monitor project evolution and resolve issues.
> 7. Troubleshoot common version control problems using basic debugging techniques.
>
> <i class="fa fa-hourglass"></i> **Time estimation**: 16 hours (2 days)
>
> <i class="fa fa-asterisk"></i> **Requirements:** The (technical) installation requirements are described in the chapter ["Get ready"](./docs/tutorials/1_Get_ready_for_the_course/tutorial.md).
>
> <i class="fa fa-envelope-open-text"></i> **Supporting Materials**:
> 
> 1. [Exercises](./exercises/)
> 2. [Slides](./docs/presentations/)  
>
> ## Proposed Schedule
>
> |Time | Day 1 | Time | Day 2 |
> |:--- | :---  |:---  | :---  |
> |09h30|Configurations & Introduction|09h30 | Solving Conflicts |
> |11h00|Coffee break  |10h30 | Coffee break | 
> |11h15|Routine usage part 1 (status-stage-commit) |10h30 | Experimenting Risk Free: Working with Branchs |
> |13h00|Lunch |12h30 | Lunch |
> |14h00|History & Comparing Versions |13h00 | Tagging & Forking |
> |14h40|Coffee break   |15h00 | Coffee break |
> |14h55|Collaborating in GitHub  |15h00 | Using the browser |
> |17h00|End of the day  | 17h00 | End of the day |
> 
> <i class="fa fa-life-ring"></i> **Acknowledgement**:
>
> * [ELIXIR Belgium](https://www.elixir-belgium.org/)
> * [VIB Technologies](https://www.vib.be/)
>
> <i class="fa fa-money-bill"></i> **Funding:** This project has received funding from VIB and ELIXIR-BE.
>
> <i class="fa fa-anchor"></i> **PURL**:  [<img src="https://zenodo.org/badge/DOI/10.5281/zenodo.20761246.svg" width="200"/>](https://zenodo.org/records/20761246)
>
> # Authors and Contributors
>
> Authors
>
> [<img src="https://raw.githubusercontent.com/vib-training-conferences/training_material_template/refs/heads/main/docs/images/ORCID-iD_icon_vector.svg" width="20"/>](http://orcid.org/00000-0001-5958-0669) Bruna Piereck
>
> [<img src="https://raw.githubusercontent.com/vib-training-conferences/training_material_template/refs/heads/main/docs/images/ORCID-iD_icon_vector.svg" width="20"/>](http://orcid.org/0000-0002-0020-421X) James Collier
>
> [<img src="https://raw.githubusercontent.com/vib-training-conferences/training_material_template/refs/heads/main/docs/images/ORCID-iD_icon_vector.svg" width="20"/>](http://orcid.org/0000-0002-3926-7293) Tuur Muyldermans
>
> [<img src="https://raw.githubusercontent.com/vib-training-conferences/training_material_template/refs/heads/main/docs/images/ORCID-iD_icon_vector.svg" width="20"/>](http://orcid.org/0000-0001-6691-4233) Alexander Botzki
>
> Contributors
>
>**We welcome contributors for these materials**
>
>## Citing this lesson
>
> Please cite as:
>
> Piereck Moura, B., Botzki, A., Collier, J.& Muyldermans, T. (2026, June 19). Versioning code and documentation with Git & GitHub. Zenodo. https://doi.org/10.5281/zenodo.20761246
>
> # Chapters List
>
> | Chapter | Title | Summary | 
> | :---    |:---   |:---     |
> |1        | [Get Ready for the course](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/master/docs/tutorials/01_Get_ready_for_the_course.md#1) | <br>In this chapter you will find the step-by-step of what you need to get ready for this course. |
> |2        | [Introduction](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/master/docs/tutorials/02_introduction.md#1) | Find out the differences between Git and GitHub and Why is Git in several cases the best approach for versioning? |
> |3        |[Get started with Git](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/master/docs/tutorials/03_getting_started.md#1)  | Understand how Git is structured, make your first commit, learn the basic routine to get one version saved and managed with Git.|
> |4        |[A travel in Time: Check your versions](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/master/docs/tutorials/04_time-travel_my_versions.md#1) |Moving towards becoming more confident and using some of the power of Git. Learn to compare versions.|
> |5        |[Connect to GitHub](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/master/docs/tutorials/05_Connecting_2_GitHub.md#1)|Connect your local repository to GitHub, make a remote backup of all your versions.|
>
> | Chapter | Title | Summary | 
> | :---    |:---   |:---     |
> |6        |[README.md & .gitignore - Important files](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/master/docs/tutorials/06_gitignore%26README.md#1)| Learn about README files and .gitignore files. These are essential for a good project development.|
> |7        |[Collaborating](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/master/docs/tutorials/07_collaborating_GitHub.md#1) | In this chapter we teach you how to start the collaboration, best practices when working in a team and last but not least ... HOW TO SOLVE CONFLICTS! |
> |8         |[Branches](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/master/docs/tutorials/08_branches.md#1) | To work in collaboration or experiment with new code or documentation desing you can creat parallel developing areas. Learn more about the application of Branchs, it will add more flexibility and better organization.|
>|9           |[Forks](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/master/docs/tutorials/09_forks.md#1)|You find a nice repo that you want to work on a new idea, or you want your collaborators to work separatelly before their changed is reviewd and approved for merging. Here it is an strategy for you.|
>| 10         | [Aliases](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/master/docs/tutorials/10_Git_aliases.md#1) | Create commands shortcut for your favorite commands. |
>| 11         |[GitHub & RStudio](https://github.com/vib-tcp/introduction-github/refs/heads/master/docs/tutorials/11_github_rstudio.md) | <br>A big developer of R ? <br> Integrate Git, GitHub and RStudio, use buttons avoiding extra command line.|

# Workshop and Material organization

> We are using the interactive Open Educational Resource online/offline course infrastructure called LiaScript.
> It is a distributed way of creating and sharing educational content hosted on github.
> To see this document as an interactive LiaScript rendered version, click on the
> following link/badge: [LiaScript](https://liascript.github.io/course/)


# About us

*About ELIXIR Training Platform*

The ELIXIR Training Platform was established to develop a training community that spans all ELIXIR member states (see the list of Training Coordinators). It aims to strengthen national training programmes, grow bioinformatics training capacity and competence across Europe, and empower researchers to use ELIXIR's services and tools.

One service offered by the Training Platform is TeSS, the training registry for the ELIXIR community. Together with ELIXIR France and ELIXIR Slovenia, VIB as lead node for ELIXIR Belgium is engaged in consolidating quality and impact of the TeSS training resources (2022-23) (https://elixir-europe.org/internal-projects/commissioned-services/2022-trp3).

The Training eSupport System was developed to help trainees, trainers and their institutions to have a one-stop shop where they can share and find information about training and events, including training material. This way we can create a catalogue that can be shared within the community. How it works is what we are going to find out in this course.

*About VIB and VIB Technologies*

VIB is an entrepreneurial non-profit research institute, with a clear focus on groundbreaking strategic basic research in life sciences and operates in close partnership with the five universities in Flanders – Ghent University, KU Leuven, University of Antwerp, Vrije Universiteit Brussel and Hasselt University.

As part of the VIB Technologies, the 12 VIB Core Facilities, provide support in a wide array of research fields and housing specialized scientific equipment for each discipline. Science and technology go hand in hand. New technologies advance science and often accelerate breakthroughs in scientific research. VIB has a visionary approach to science and technology, founded on its ability to identify and foster new innovations in life sciences.

The goal of VIB Technology Training is to up-skill life scientists to excel in the domains of VIB Technologies, Bioinformatics & AI, Software Development, and Research Data Management.

--------------------------------------------

*Editorial team for this course*

Authors: @[orcid(Alexander Botzki)](https://orcid.org/0000-0001-6691-4233), @[orcid(Bruna Piereck)](https://orcid.org/0000-0001-5958-0669)

Technical Editors: Alexander Botzki

License: [![CC BY SA](docs/images.png)](https://creativecommons.org/licenses/by-sa/4.0/deed.en)


```json   @JSONLD
{
  "@context": "https://schema.org/",
  "@type": "LearningResource",
  "@id": "https://elixir-europe-training.github.io/ELIXIR-TrP-TeSS/",
  "http://purl.org/dc/terms/conformsTo": {
    "@type": "CreativeWork",
    "@id": "https://bioschemas.org/profiles/TrainingMaterial/1.0-RELEASE"
  },
  "description": "track the versions of your code and your documentation, make your research more reproducible and more impactifull",
  "keywords": "FAIR, Reproducibility, RDM, code, data analysis",
  "name": "Versioning code and documentation with Git & GitHub",
  "license": "https://creativecommons.org/licenses/by/4.0/",
  "educationalLevel": "beginner",
  "competencyRequired": "Unix command line basic knowledge",
  "teaches": [
    "1. Configure Git on a local machine to prepare for version control in research projects.",
    "2. Create and manage repositories using Git commands to track changes and maintain project history.",
    "3. Apply basic Git operations (e.g., staging, committing, pushing) to work effectively with local and remote repositories.",
    "4. Implement branching and pull request workflows to collaborate with others on shared codebases.",
    "5. Interpret Git logs and history to understand project evolution and troubleshoot issues.",
    "6. Collaborate with other people in your project."
  ],
  "audience": "life scientists",
  "inLanguage": "en-US",
  "learningResourceType": [
    "tutorial"
  ],
  "author": [
    {
      "@type": "Person",
      "name": "Bruna Piereck"
    },
    {
      "@type": "Person",
      "name": "James Collier"
    },
    {
      "@type": "Person",
      "name": "Alexander Botzki"
    },
    {
      "@type": "Person",
      "name": "Tuur Muyldermans"
    }
   ]
}
```









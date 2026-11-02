# 10. Aliases (Extra)

The configuration file is also a place where we can make our own aliases, like creating a shortcut for lines of git commands that are used frequently. In other words, creating **a new command tailored to your wishes**. It often consists of an existing Git command (e.g. `git log`) followed by a bunch of variables. This omits that we have to type a long command the whole time. Here are some useful aliases for a structured history overview:

```
git config --global alias.hist "log --pretty=format:'%h %ad | %s%d [%an]' --graph --date=short"
git config --global alias.oneline "log --graph --decorate --pretty=oneline --abbrev-commit --all"
git config --global alias.mylog1 "log --pretty=format:'%h %s [%an]' --graph"
git config --global alias.mylog2 "log --pretty=format:'%Cgreen%h%Creset %ai | %s %Cblue[%an] %Cred%d' --date=short -n 10 --color"
git config --global alias.mylog3 "log --decorate --pretty='format:%C(auto) %h %d %s %Cgreen(%cr by %cn)%Creset' --graph --all"
```
Once they are set, you can use them whenever you like. E.g.: running `git hist` gives us the same result as `git log --pretty=format:'%h %ad | %s%d [%an]' --graph --date=short`. 


If at some point we are not happy any more about an alias, we can delete it with the following command:
```
git config --global --unset alias.<command>
```

In this course we are not using any aliases, but you can create your own or use the examples above if you think they are useful!

---


You can access the next chapter

[<img src="../images/PNGs/button_nextChapter.png" alt="next chapter" width="200">](https://github.com/vibbits/introduction-github/blob/master/tutorials/11_github_rstudio/tutorial.md)!

### All chapters

| Chapter | Title | Summary | 
| :---    |:---   |:---     |
|1        | [Get Ready for the course](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/master/docs/tutorials/01_Get_ready_for_the_course.md#1) | <br>In this chapter you will find the step-by-step of what you need to get ready for this course. |
|2        | [Introduction](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/master/docs/tutorials/02_introduction.md#1) | Find out the differences between Git and GitHub and Why is Git in several cases the best approach for versioning? |
|3        |[Get started with Git](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/master/docs/tutorials/03_getting_started.md#1)  | Understand how Git is structured, make your first commit, learn the basic routine to get one version saved and managed with Git.|
|4        |[A travel in Time: Check your versions](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/master/docs/tutorials/04_time-travel_my_versions.md#1) |Moving towards becoming more confident and using some of the power of Git. Learn to compare versions.|
|5        |[Connect to GitHub](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/master/docs/tutorials/05_Connecting_2_GitHub.md#1)|Connect your local repository to GitHub, make a remote backup of all your versions.|

| Chapter | Title | Summary | 
| :---    |:---   |:---     |
|6        |[README.md & .gitignore - Important files](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/master/docs/tutorials/06_gitignore%26README.md#1)| Learn about README files and .gitignore files. These are essential for a good project development.|
|7        |[Collaborating](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/master/docs/tutorials/07_collaborating_GitHub.md#1) | In this chapter we teach you how to start the collaboration, best practices when working in a team and last but not least ... HOW TO SOLVE CONFLICTS! |
|8         |[Branches](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/master/docs/tutorials/08_branches.md#1) | To work in collaboration or experiment with new code or documentation desing you can creat parallel developing areas. Learn more about the application of Branchs, it will add more flexibility and better organization.|
|9           |[Forks](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/master/docs/tutorials/09_forks.md#1)|You find a nice repo that you want to work on a new idea, or you want your collaborators to work separatelly before their changed is reviewd and approved for merging. Here it is an strategy for you.|
| 10         | [Aliases](https://liascript.github.io/course/?https://raw.githubusercontent.com/vib-tcp/introduction-github/refs/heads/master/docs/tutorials/10_Git_aliases.md#1) | Create commands shortcut for your favorite commands. |
| 11         |[GitHub & RStudio](https://github.com/vib-tcp/introduction-github/refs/heads/master/docs/tutorials/11_github_rstudio.md) | <br>A big developer of R ? <br> Integrate Git, GitHub and RStudio, use buttons avoiding extra command line.|

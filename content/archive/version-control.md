---
date: 2021-01-07T10:47:11+01:00
featured_image: git.svg
title: "Version Control & Code Reviews"
summary: "In which we talk about git, git's role in team/deployment workflows, how to perform a code review."
---
<div class="body-spacer--small"></div>
<p style="margin-bottom: 1rem;" class="col">{{< param summary>}}</p>
<section class="col">
    <h2 class="text-center">Table of Contents</h2>
    <ul>
        <li><a href="#what-is-version-control">What is Version Control?</a>
            <ul class="post-only">
                <li><a href="#git-basics">Git Basics</a>
                    <ul class="post-only">
                        <li><a href="#what-is-a-git-repo">What is a git repository?</a></li>
                        <li><a href="#how-do-i-get-a-copy">How do I get a copy?</a></li>
                        <li><a href="#gitignore">Ignoring files and folders</a></li>
                        <li><a href="#how-do-i-make-changes">How do I make changes?</a>
                            <ul>
                                <li><a href="#git-status">Git status</a></li>
                                <li><a href="#git-add">Adding files to git tracking</a></li>
                                <li><a href="#git-commit">Committing changes</a></li>
                                <li><a href="#git-pull">Pulling changes from remote</a></li>
                                <li><a href="#git-push">Pushing changes to remote</a></li>
                                <li><a href="#git-conflict">Resolving merge conflicts</a></li>
                            </ul>
                        </li>
                    </ul>
                </li>
                <li><a href="#git-branching">Git branching</a>
                    <ul class="post-only">
                        <li><a href="#create-branch">Creating a branch</a></li>
                        <li><a href="#checkout">Checking out a branch</a></li>
                        <li><a href="#remote-branch">Creating a remote branch</a></li>
                    </ul>
                </li>
            </ul>
        </li>
        <li><a href="#how-do-teams-use-git">How Do Teams Use Git?</a>
            <ul class="post-only">
                <li><a href="#git-workflows">Git workflows</a>
                    <ul class="post-only">
                        <li><a href="#gitlab">GitLab Flow</a></li>
                    </ul>
                </li>
                <li><a href="#git-and-pipeline">Git and the deployment pipeline</a>
                    <ul class="post-only">
                        <li><a href="#continuous-integration">Continuous Integration</a></li>
                        <li><a href="#continuous-deployment">Continuous Deployment</a></li>
                    </ul>
                </li>
            </ul>
        </li>
        <li><a href="#what-is-code-review">What is Code Review?</a>
            <ul class="post-only">
                <li><a href="#pr">Creating a PR (pull request)</a></li>
                <li><a href="#cr">Requesting a code review</a></li>
                <li><a href="#cr-response">Responding to a code review request</a></li>
                <li><a href="#commenting">Adding comments to lines of code</a></li>
                <li><a href="#cr-submit">Submitting your code review</a></li>
            </ul>
        </li>
        <li><a href="#giving-good-feedback">Giving good feedback</a>
            <ul class="post-only">
                <li><a href="#understand">Review to understand</a></li>
                <li><a href="#succeed">Review for success</a></li>
                <li><a href="#process-improvement">Recognize where process needs&nbsp;improvement</a></li>
            </ul>
        </li>
        <li><a href="#getting-good-feedback">Getting good feedback</a></li>
    </ul>
</section>
<div class="body-spacer"></div>
<section id="what-is-version-control" class="col"><img class="body-icon" alt="" src="/images/versions.svg">
    <h2>What is Version Control?</h2>
    <p>You might also be familiar with version control from applications like <a href="https://support.microsoft.com/en-us/topic/view-previous-versions-of-office-files-5c1e076f-a9c9-41b8-8ace-f77b9642e2c2" target="_blank" rel="noopener noreferrer">MS Word<span class="show-for-sr"> Opens in a new window</span></a>, or from trying to manually manage versions.</p>
</section>
<section class="col">
    <figure>
        <img src="/images/version-control--manual.png" alt="Multiple versions of a Photoshop file">
        <figcaption>Maybe time to give Figma a try.</figcaption>
    </figure>
</section>
<section class="col">
    <p>One of the most magical things about computers is the time-travel afforded to us by the concept of <code>undo</code> and <code>redo</code>. Extending this magic to <strong>every change made to a file</strong>, indefinitely, is a really powerful idea.</p>
    <p>Version control not only lets us step backwards and forwards in time, but with the concept of "<strong>branching</strong>", allows us to explore alternate timelines that diverge from, and then merge with, the main timeline.</p>
</section>
<section class="col">
    <figure>
        <img src="/images/back-to-the-future.jpeg" alt="Still from Back to the Future">
        <figcaption>I do not foresee any complications with this simple concept.</figcaption>
    </figure>
</section>
<section class="col">
    <p>The standard in software development today is to use a <strong>distributed version control system</strong>, where each contributor has a copy of the whole codebase, including the full history, on their machine.</p>
    <p>There are a <a href="https://www.mercurial-scm.org/" target="_blank" rel="noopener noreferrer">few<span class="show-for-sr"> Opens in a new window</span></a> <a href="https://www.fossil-scm.org/home/doc/trunk/www/index.wiki" target="_blank" rel="noopener noreferrer">other<span class="show-for-sr"> Opens in a new window</span></a> other distributed version control systems out there besides git, but they work pretty much like git, and basically <a href="https://insights.stackoverflow.com/survey/2020#technology-collaboration-tools" target="_blank" rel="noopener noreferrer">everybody uses git<span class="show-for-sr"> Opens in a new window</span></a>.</p>
</section>
<section class="col">
    <div class="callout primary">
        <p><strong>Notice I'm saying 'git' and not 'Github'</strong> (despite the fact that pretty much everybody uses Github, too).</p>
        <p>That's because git is a piece of open-source software. Git<em>hub</em> is a company owned by Microsoft that lets you host your remote git repositories with them. You don't need Github to use git - you can host your own repositories, or host them with a Github competitor like <a href="https://about.gitlab.com/features/" target="_blank" rel="noopener noreferrer">GitLab<span class="show-for-sr"> Opens in a new window</span></a> or <a href="https://bitbucket.org/product/features" target="_blank" rel="noopener noreferrer">Bitbucket<span class="show-for-sr"> Opens in a new window</span></a>.</p>
    </div>
</section>
<section class="col">
    <figure>
            <img src="/images/xkcd-git.png" alt="[Cueball points to a computer on a desk while Ponytail and Hairy are standing further away behind an office chair.] Cueball: This is git. It tracks collaborative work on projects through a beautiful distributed graph theory tree model. Ponytail: Cool. How do we use it? Cueball: No idea. Just memorize these shell commands and type them to sync up. If you get errors, save your work elsewhere, delete the project, and download a fresh copy.">
        <figcaption>If that doesn't fix it, git.txt contains the phone number of a friend of mine who understands git. Just wait through a few minutes of 'It's really pretty simple, just think of branches as...' and eventually you'll learn the commands that will fix everything.</figcaption>
    </figure>
</section>
<section class="col">
    <p>Git is a truly <strong>brilliant piece of software</strong> with pretty <strong>terrible user experience</strong>. I'm going to teach you the absolute basics today, but the absolute basics are enough for most developers.</p>
    <p>If you want to know more, let me recommend the excellent (and free!) book <a href="https://git-scm.com/book/en/v2" target="_blank" rel="noopener noreferrer">'Pro Git'<span class="show-for-sr"> Opens in a new window</span></a> by Scott Chacon and Ben Straub.</p>
</section>
<div class="body-spacer--small"></div>
<section id="git-basics" class="col">
    <h3 class="text-center">Git Basics</h3>
</section>
<section id="what-is-a-git-repo" class="col">
    <h4>What is a git repository?</h4>
    <p>A git repository, or "repo" for short, is a <strong>software project that uses git to keep track of its changes</strong>.</p>
    <p>Typically, you'll have a copy on your local machine (the "<strong>local repo</strong>"), and another copy on a server somewhere (the "<strong>remote repo</strong>").</p>
</section>
<section id="how-do-i-get-a-copy" class="col">
    <h4>How do I get a copy?</h4>
    <ol>
        <li>Open your terminal/command prompt, and <strong>change directories</strong> into the folder where you keep your projects, using the <code>cd</code> command for Mac/Linux or <code>Set-Location</code> for Windows.</li>
    </ol>
</section>
<section class="col">
    <div class="callout alert">Ok, I'm not super familiar with Powershell, but from what I understand, most basic Linux commands are used as aliases in Powershell, so I'm going to start writing out most command-line instructions using just the Linux commands. If you're using Powershell, and the commands I'm providing aren't working for you, <strong>please let me know</strong>.</div>
</section>
<div class="body-spacer--small" style="margin-top: 2rem;"></div>
<div class="col">
    <details class="callout">
        <summary>
            <h5 style="margin-top: 0;">Command line basics</h5>
        </summary>
        <dl>
            <dt>Where am I?</dt>
            <dd><code>pwd</code> ("print working directory")</dd>
            <dt>What else is in here (in terms of files and folders)?</dt>
            <dd><code>ls</code> ("list")</dd>
            <dt>Go into "projects" directory</dt>
            <dd><code>cd projects</code> ("change directory")</dd>
            <dt>Go "up" one directory</dt>
            <dd><code>cd ../</code></dd>
            <dt>Go to my home directory</dt>
            <dd><code>cd ~</code></dd>
        </dl>
    </details>
</div>
<section class="slide-only" aria-hidden="true">
    <h5>Command line basics</h5>
    <dl>
        <dt>Where am I?</dt>
        <dd><code>pwd</code> ("print working directory")</dd>
        <dt>What else is in here (in terms of files and folders)?</dt>
        <dd><code>ls</code> ("list")</dd>
        <dt>Go into "projects" directory</dt>
        <dd><code>cd projects</code> ("change directory")</dd>
        <dt>Go "up" one directory</dt>
        <dd><code>cd ../</code></dd>
        <dt>Go to my home directory</dt>
        <dd><code>cd ~</code></dd>
    </dl>
</section>
<section class="col">
    <ol start="2">
        <li>Run the command <br class="slide-only"><code>git clone git@github.com:HTTP5105/emilio-estevez.git</code></li>
    </ol>
</section>
<section class="col">
    <div class="callout primary">
        <strong>Wait, where did that URL thing come from?</strong>
        <figure>
            <img src="/images/emilio-ssh.png" alt="">
            <figcaption>If you're cloning a repo from github, you can click on the dropdown from the green "code" button to get the URL.</figcaption>
        </figure>
    </div>
</section>
<section class="col">
    <ol start="3">
        <li>There's no step three! The repo has been <strong>downloaded onto your computer</strong> and you now have a <strong>full copy of the files, folders and git history</strong>.</li>
    </ol>
</section>
<div class="body-spacer--small"></div>
<div class="body-spacer--small" style="margin-top: 2rem;"></div>
<div class="col">
<details class="callout alert" id="gitignore">
    <summary>
        <h4 style="margin-top: 0;">Ignoring files and folders</h4>
    </summary>
    <p>I want you to take note of a file in this repo that you've just downloaded: <code>.gitignore</code>.</p>
    <p>The dot at the beginning of the file name means that it will be "hidden" in most file system viewers, but if you're using a modern code editor, you should be able to see it when you open the repo's folder with your code editor.</p>
    <p>This file contains a list of files and folders that <strong>will not</strong> be tracked by git.</p>
    <p><strong>If git is so great, why would we want to <em>not</em> use it with some files and folders?</strong></p>
    <p>Three reasons:</p>
    <ul>
        <li>Any files containing <strong>sensitive information</strong> like database passwords <strong>should be ignored</strong></li>
        <li>Any files that are <strong>too big</strong> (i.e. 20mb+ - git will reject any files bigger than 100mb)</li>
        <li>Any "dependencies" that can be installed separately. I'll leave this one vague, but we'll definitely learn more about this during our lesson on NodeJS.</li>
    </ul>
</details>
</div>
<section class="slide-only" aria-hidden="true">
        <h4>Ignoring files and folders</h4>
    <p>I want you to <strong>take note of a file</strong> in this repo that you've just downloaded: <code>.gitignore</code>.</p>
    <p>The dot at the beginning of the file name means that it will be "hidden" in most file system viewers, but if you're using a modern code editor, you should be able to see it when you open the repo's folder with your code editor.</p>
</section>
<section class="col">
    <p>This file contains a list of files and folders that <strong>will not</strong> be tracked by git.</p>
    <p><strong>If git is so great, why would we want to <em>not</em> use it with some files and folders?</strong></p>
</section>
<section class="col">
    <p>Three reasons:</p>
    <ul>
        <li>Any files containing <strong>sensitive information</strong> like database passwords <strong>should be ignored</strong></li>
        <li>Any files that are <strong>too big</strong> (i.e. 20mb+ - git will reject any files bigger than 100mb)</li>
        <li>Any "dependencies" that can be <strong>installed separately</strong>. I'll leave this one vague, but we'll definitely learn more about this during our lesson on NodeJS.</li>
    </ul>
</section>
<div class="body-spacer--small"></div>
<section id="#how-do-i-make-changes" class="col">
    <h4>How do I make changes?</h4>
    <p>At this point, you can <strong>edit the files as you normally would</strong> in any project.</p>
    <p>For our purposes, let's add a new file called <code>harry-dean-stanton.md</code>, and write some stuff in it.</p>
    <figure>
        <img src="/images/harry.png" alt="A text file with some info about Harry Dean Stanton">
    </figure>
</section>
<section class="col">
    <p>Git <wtrong>doesn't automatically start tracking</wtrong> anything that happens to be in the same folder. You have to <strong>explicitly add the file</strong> to the repo.</p>
</section>
<section id="git-status" class="col">
    <h5>Git status</h5>
    <p>Before we start adding files, though, let's check on git's status:</p>
    <pre><code class="language-console">git status</code></pre>
    <figure>
        <img src="/images/git-status.png" alt="The output of the command 'git status'">
        <figcaption>Well that's good to know.</figcaption>
    </figure>
</section>
<section id="git-add" class="col">
    <h5>Adding files to git tracking</h5>
    <pre><code class="language-console">git add harry-dean-stanton.md</code></pre>
    <figure>
        <div class="match-iterm"><img src="/images/git-status-added.png" alt="The output of the command 'git status' after adding a file"></div>
        <figcaption>Now we're getting somewhere! Not somewhere exciting, but somewhere!</figcaption>
    </figure>
</section>
<section class="col">
    <p>Alright, so now we've added the file to the git repo, and it's telling us to commit? <strong>Why do we have to commit it if we've already added it?</strong></p>
    <p>It's best to think of your repo having a "rough draft" stage. You work on stuff in your <strong>working directory</strong>, add it to your "<strong>rough draft</strong>", and when it's ready to be sync'd up with the remote repo (which, remember, other developers are working with), then you <strong>make your commits</strong>.</p>
</section>
<section id="git-commit" class="col">
    <h5>Committing changes</h5>
    <pre><code class="language-console">git commit -m 'Message about what you did'</code></pre>
    <figure>
        <img src="/images/git-commit.png" alt="Output of the git commit command">
        <figcaption>I am committed to this Repo Man bit.</figcaption>
    </figure>
    <p>Notice the use of the <code>-m</code> "flag" to allow us to type out the (<strong>required</strong>) message that goes along with our commit.</p>
</section>
<section class="col">
    <p>Let's check our status again and see if we're ready to sync up our commits with the remote repository.</p>
    <figure>
        <img src="/images/git-status-commit.png" alt="Git status prompting a push">
        <figcaption>Pushed to commit? Or committed to push? I don't know, it's way too late in the evening to be writing snarky&nbsp;captions.</figcaption>
    </figure>
</section>
<section id="git-pull" class="col">
    <h5>Pulling changes from remote</h5>
    <p><code>git status</code> is telling us we're ready to push! It's time to synchronize with our remote repo.</p>
    <p>Before we <code>push</code>, it's a good idea to <code>pull</code>.</p>
    <pre><code class="language-console">git pull</code></pre>
    <p>This tries to <strong>merge any code that might've been updated</strong> on the remote repo with your local repo. Best to <strong>resolve conflicts locally</strong> before you push.</p>
    <figure>
        <div class="match-iterm"><img src="/images/git-pull.png" alt="Git pull"></div>
        <figcaption>"If you want to go fast, go alone"</figcaption>
    </figure>
</section>
<section id="git-push" class="col">
    <h5>Pushing changes to remote</h5>
    <p>Once you're all up-to-date, you can push your commits to the remote repository!</p>
    <pre><code class="language-console">git push</code></pre>
    <figure>
        <img src="/images/git-push-it.png" alt="Git push output">
        <figcaption>Done deal.</figcaption>
    </figure>
</section>
<section class="col">
    <p>What would've happened if there had been <strong>changes in the remote repository</strong> before we pulled?</p>
    <figure>
        <img src="/images/git-pull-with-changes.png" alt="Output from a git pull with changes.">
        <figcaption>We'd see a few more lines of output, and download the new files, but everything's fine!</figcaption>
    </figure>
</section>
<section class="col">
    <p>What's amazing is that even if you're working on the <strong>same file</strong> as somebody else, you can still pull their changes into your local repo without there being a problem.</p>
    <p>You really only run into an issue with you've made a change on the <strong>same line</strong> where there's been a change on the remote.</p>
    <img src="/images/git-conflict.png" alt="Console output from a conflict">
</section>
<section id="git-conflict" class="col">
    <h5>Resolving merge conflicts</h5>
    <p>Let's say there is a change on the remote that is on the same line of the same file in the same branch (more on branches later) as your work.</p>
    <p>At that point, git will have <strong>injected some content</strong> into your file. You then have to edit the file, which now contains both your changes and the changes to the remote.</p>
</section>
<section class="col">
    <p><strong>On top will be your changes</strong> (the "HEAD"), and underneath, separated by a row of equal signs, will be the <strong>alternate changes from the remote repo</strong>. Finally, there will we a row of "greater than" symbols.</p>
    <img src="/images/git-resolve.png" alt="File with conflicts">
</section>
<section class="col">
    <p>All you have to do to resolve the conflict is <strong>decide what changes to keep, and what changes to discard</strong>. Edit the file so that it looks the way you think it should, deleting the added lines (like the equal signs and whatnot). Finally, <code>git add</code> the file, commit and push your changes.</p>
    <img src="/images/git-push-resolution.png" alt="Output from pushing a resolved merge conflict">
</section>
<div class="body-spacer--small"></div>
<section id="git-branching" class="col">
    <h3 class="text-center">Git branching</h3>
    <p>Remember earlier when I said that git didn't just give us the option to time travel, but also to branch off into <strong>different timelines</strong>?</p>
    <p>With "branches", git allows us to <strong>split off temporarily</strong> from the existing repo, do our work, and push it to the remote repository without it affecting other developers.</p>
    <p>When your work is ready to be re-integrated with whatever other developers have been working on, you can <strong>merge your work back into the main branch</strong>.</p>
</section>
<section class="col">
    <p>Git branching is often a major part of how a team structures their workflow. There might not be a single "main" branch, but <strong>multiple branches that represent the development, testing and production versions</strong> of the application. Merging into different branches <strong>may trigger automated processes</strong>, like testing (which you've seen with our Github Classroom lab exercises), but also code compilation, optimization, deployments - all kinds of things.</p>
    <p>We'll look at how a team might structure their git workflow later in this lesson, but first, let's look at how git branching is done.</p>
</section>
<section id="create-branch" class="col">
    <h4>Creating a branch</h4>
    <p>Creating a branch in git is easy - just use the following command:</p>
    <pre><code class="language-console">git branch [some-name-for-your-branch]</code></pre>
</section>
<section class="col">
    <figure>
        <div class="match-iterm"><img src="/images/git-branch.png" alt="Output of git branch commands"></div>
        <figcaption>You can see what branches are available, and which branch you're currently "on" with the command <code>git branch --list</code>, or simply <code>git branch</code></figcaption>
    </figure>
    <p>Notice the asterisk (<code>*</code>) in the screenshot? That's indicating <strong>the branch that we're currently "on"</strong>. If you open the files in your code editor, <strong>the code you see will be the code stored in the branch with the asterisk</strong>. If we make changes to the code, we'll be making changes to, adding to, and committing to the code in the branch with the asterisk.</p>
</section>
<section id="checkout" class="col">
    <h4>Checking out a branch</h4>
    <p>To change which branch you're working on, you need to "<strong>check out</strong>" the branch that you want to switch to.</p>
    <pre><code class="language-console">git checkout [some-name-for-your-branch]</code></pre>
    <figure>
        <div class="match-iterm"><img src="/images/git-checkout.png" alt="Output of git checkout command"></div>
        <figcaption>Look at that little asterisk go!</figcaption>
    </figure>
</section>
<section id="remote-branch" class="col">
    <h4>Creating a remote branch</h4>
    <p>Once you've created a branch and switched to it, you can add and commit files as usual. However, when it's time to push to the remote repository, the branch <strong>has to exist in the remote repo</strong> before you can push to it.</p>
</section>
<section class="col">
    <p>We can do <strong>simultaneously create the remote branch and push our code</strong> in one line by writing the following command:</p>
    <pre><code class="language-console">git push -u origin [some-name-for-your-branch]</code></pre>
    <figure>
        <a href="/images/git-branch-push.png" target="_blank"><img src="/images/git-branch-push.png" alt="Output of git push when the branch hasn't been created on the remote"></a>
        <figcaption>Git's pretty good at telling you the commands you need to run to make stuff work. Not great, but pretty&nbsp;good.</figcaption>
    </figure>
</section>
<section class="col">
    <p>That's it! When you're ready, <strong>go to your remote repo and create a pull request</strong>, and <strong>get someone to code review it</strong>.</p>
</section>
<section class="col">
    <p>If you're at this point, it's probably time to run the following commands to get started on your next task:</p>
    <pre><code class="language-console">git checkout main
git pull
git branch [another-branch-name]
git checkout [another-branch-name]</code></pre>
    <p>This will <strong>put you back on your main branch</strong>, <strong>make sure your code is up-to-date</strong> with the remote repo, and <strong>put you on a whole new branch</strong> to begin your next piece of work.</p>
</section>
<hr>
<div class="further-reading col">
<strong>Further Reading:</strong>
<ul>
    <li><a href="https://rogerdudler.github.io/git-guide/" target="_blank" rel="noopener noreferrer">git - the simple guide<span class="show-for-sr"> Opens in a new window</span></a>, <em>Roger Dudler</em></li>
    <li><a href="https://ohshitgit.com/" target="_blank" rel="noopener noreferrer">Oh Sh*t, Git!?!<span class="show-for-sr"> Opens in a new window</span></a>, <em>Katie Sylor-Miller</em></li>
    <li><a href="https://wizardzines.com/zines/oh-shit-git/" target="_blank" rel="noopener noreferrer">Oh sh*t, git!<span class="show-for-sr"> Opens in a new window</span></a> (like the above, but expanded, illustrated and in 'zine form), <em>Katie Sylor-Miller & Julia Evans</em></li>
    <li><a href="https://www.freecodecamp.org/news/learn-the-basics-of-git-in-under-10-minutes-da548267cc91/" target="_blank" rel="noreferrer">Learn the Basics of Git in Under 10 Minutes<span class="show-for-sr"> Opens in a new window</span></a>, <em>Gowtham Venkatesan</em></li>
    <li><a href="https://rachelcarmena.github.io/2018/12/12/how-to-teach-git.html" target="_blank" rel="noopener noreferrer">How to teach Git<span class="show-for-sr"> Opens in a new window</span></a>, <em>Rachel M. Carmena</em></li>
    <li><a href="https://git-scm.com/book/en/v2" target="_blank" rel="noopener noreferrer">Pro Git<span class="show-for-sr"> Opens in a new window</span></a>, <em>Scott Chacon and Ben Straub</em></li>
</ul>
</div>
<div class="body-spacer"></div>
<section id="how-do-teams-use-git" class="col"><img class="body-icon" alt="" src="/images/collab.svg">
    <h2>How Do Teams Use Git?</h2>
    <p>As we talked about, git branching can be used to <strong>manage collaboration</strong>, and also to trigger <strong>powerful commands</strong> and <strong>deployment strategies</strong>. Let's talk about it!</p>
</section>
<div class="body-spacer--small"></div>
<section id="git-workflows" class="col">
    <h3 class="text-center">Git workflows</h3>
    <p>A git workflow (or "branching model") is a <a href="/posts/methodologies-and-design-patterns/#why" target="_blank">team standard<span class="show-for-sr"> Opens in a new window</span></a>. Like other team standards, the most important thing is <strong>consistency</strong>.</p>
    <p>There are <a href="http://scottchacon.com/2011/08/31/github-flow.html" target="_blank" rel="noopener noreferrer">many<span class="show-for-sr"> Opens in a new window</span></a> <a href="https://www.endoflineblog.com/oneflow-a-git-branching-model-and-workflow" target="_blank" rel="noopener noreferrer">branching<span class="show-for-sr"> Opens in a new window</span></a> <a href="https://nvie.com/posts/a-successful-git-branching-model/" target="_blank" rel="noopener noreferrer">models<span class="show-for-sr"> Opens in a new window</span></a> out there.</p>
    <p>I'm going to show you one today - GitLab Flow. It's one of the <strong>best-known git workflows</strong>, but expect different teams to use alternatives, or to have their own modified version of this one.</p>
</section>
<section class="col">
    <h4>The precursor to GitLab Flow</h4>
    <p>The best-known git branching model is <a href="https://nvie.com/posts/a-successful-git-branching-model/" target="_blank" rel="noopener noreferrer">gitflow<span class="show-for-sr"> Opens in a new window</span></a>, first described by Vincent Driessen in 2010.</p><p>Gitflow was based on an older software development model where you <strong>released slowly</strong> and <strong>supported multiple versions</strong> of a piece of software. It involved a number of different types of branches, including multiple "main" branches, feature branches, "hotfix" branches for bug fixes that need to 'skip the queue', and so on. Since that software development lifecycle doesn't reflect most work on the web today, <strong>Driessen himself no longer recommends Gitflow</strong> for most web applications.</p>
</section>
<section class="col">
    <h4>The (too?) simple competitor of GitLab Flow</h4>
    <p><a href="http://scottchacon.com/2011/08/31/github-flow.html" target="_blank" rel="noopener noreferrer">Github Flow<span class="show-for-sr"> Opens in a new window</span></a> was introduced a few years later as a lightweight alternative. Github Flow is <strong>essentially the simple workflow I described</strong> in the first part of this lesson:</p>
    <pre><code class="language-console">main [remote]
    → main [local] 
    → feature-branch [local] 
    → feature-branch [remote] 
    → pull request 
→ main [remote]</code></pre>
</section>
<section id="gitlab" class="col">
    <h4>GitLab Flow</h4>
    <p>GitLab Flow is what I consider a "<strong>happy medium</strong>" between these two.</p>
    <p>It allows for multiple "environment" branches - branches that reflect a staged deployment through QA, UAT, and production - without the complications of reflecting an outdated software development paradigm.</p>
</section>
<section class="col">
    <img src="/images/gitlab-environment-branches.png" alt="GitLab Workflow environment branches.">
    <p>Developers still use a <strong>feature branching model</strong> (like Github Flow), working off a shared main branch, but <strong>other environments can be represented</strong> as "downstream" branches, in order to work with a multi-staged deployment.</p>
</section>
<section class="col">
    <p>GitLab also nicely documents smaller details about the workflow, like <strong>when to run tests</strong>, <strong>how to open issues</strong>, and <strong>how to phrase your commit messages</strong>.</p>
    <p>All in all, a pretty nice system!</p>
</section>
<hr>
<div class="further-reading col">
    <strong>Further Reading:</strong>
    <ul>
        <li><a href="https://docs.gitlab.com/ee/topics/gitlab_flow.html" target="_blank" rel="noreferrer">GitLab Flow<span class="show-for-sr"> Opens in a new window</span></a>, <em>GitLab Docs</em></li>
        <li><a href="https://medium.com/@patrickporto/4-branching-workflows-for-git-30d0aaee7bf" target="_blank" rel="noopener noreferrer">4 branching workflows for Git<span class="show-for-sr"> Opens in a new window</span>, <em>Patrick Porto</em></a></li>
    </ul>
</div>
<div class="body-spacer--small"></div>
<section id="git-and-pipeline" class="col">
    <h3 class="text-center">Git and the deployment pipeline</h3>
    <p>A git workflow is often <strong>the basis for continuous integration/continuous deployment operations</strong>, also known as a "CI/CD pipeline".</p>
</section>
<section id="continuous-integration" class="col">
    <h4>Continuous Integration</h4>
    <p>Continuous integration is the practice of <strong>frequently</strong> (at least daily) <strong>merging developers' code</strong>, where <strong>each merge triggers automated testing on the main branch</strong>.</p><p>This prevents a bottleneck - the moment when a deadline comes up, all developers try to merge, and are faced with dozens of failed test and hundreds of merge conflicts.</p>
    </section>
<section id="continuous-deployment" class="col">
    <h4>Continuous Deployment</h4>
    <p>Continuous deployment means that your software is <strong>automatically deployed to production</strong> when it's ready (which is frequently, as continuous integration is a pre-requisite for continuous deployment).</p>
    <p>The definition of "ready" will depend on the workplace, but one simple example of this is in the <a href="/supplemental/netlify/" target="_blank">instructions for deploying via Netlify<span class="show-for-sr"> Opens in a new window</span></a> that I provided to you wherein <strong>the site is made public anytime a commit</strong> (including a merge) <strong>is made</strong> into the main branch.</p>
</section>
<hr>
<div class="further-reading col">
<strong>Further Reading:</strong>
<ul>
    <li><a href="https://www.atlassian.com/continuous-delivery/principles/continuous-integration-vs-delivery-vs-deployment" target="_blank" rel="noreferrer">Continuous integration vs. continuous delivery vs. continuous deployment<span class="show-for-sr"> Opens in a new window</span></a>, <em>Sten Pittet</em></li>
</ul>
</div>
<div class="body-spacer"></div>
<section id="what-is-code-review" class="col"><img class="body-icon" alt="" src="/images/consult.svg">
    <h2>What is Code Review?</h2>
</section>
<section class="col">
    <p>Code review is a common element of a team's workflow. In many teams, <strong>when your branch is ready to be merged into the main branch, you are required to ask for a code review</strong>. After another developer has reviewed your code, they may ask you to make changes to meet with team standards. <strong>When they approve of your code</strong>, <strong>they</strong> (not you) <strong>will then merge it into the main branch</strong>.</p>
</section>
<section class="col">
    <p class="callout warning">Just to reiterate, this is <strong>one possible workflow</strong>. I'm choosing to describe this workflow because it's quite common, but every team is different!</p>
    <p class="post-only">Here is the process for requesting and conducting a code review through Github. Note that you can click any of these screenshots to enlarge them.</p>
</section>
<section id="pr" class="col">
    <h3 class="text-center">Creating a PR (pull request)</h3>
    <figure><a href="/images/git-pull-request.png" target="_blank"><img src="/images/git-pull-request.png" alt="Github interface for creating a pull request."></a>
        <figcaption>When your code is ready, go to your branch on the remote repository and click the "pull&nbsp;request"&nbsp;button.</figcaption>
    </figure>
</section>
<section id="cr" class="col">
    <h3 class="text-center">Requesting a code review</h3>
    <figure><a href="/images/git-pr-tag.png" target="_blank"><img src="/images/git-pr-tag.png" alt="Github interface for tagging another user and requesting a code review."></a><figcaption>Request a code review by tagging another user (with the @ symbol) in the pull request comment&nbsp;section.</figcaption></figure>
</section>
<section id="cr-response" class="col">
    <h3 class="text-center">Responding to a code review request</h3>
    <figure><a href="/images/git-pr-see-changes.png" target="_blank"><img src="/images/git-pr-see-changes.png" alt="Github interface for reviewing code file-by-file"></a><figcaption>When someone requests a code review from you, click on the "Files Changed" tab to see the code that would be added to the main branch by merging this pull request.</figcaption></figure>
</section>
<section id="commenting" class="col">
    <h3 class="text-center">Adding comments to lines of code</h3>
    <figure><a href="/images/git-pr-line-comments.png" target="_blank"><img src="/images/git-pr-line-comments.png" alt="Github interface for adding comments to individual lines of code"></a><figcaption>Hover over a line of code - a blue "+" button will appear. Click this button to create a comment about this specific line of code. Do so wherever you have comments or change requests for a particular section of code. Repeat this for all files that have updated code.</figcaption></figure>
</section>
<section id="cr-submit" class="col">
    <h3 class="text-center">Submitting your code review</h3>
    <figure><a href="/images/git-pr-finish-review.png" target="_blank"><img src="/images/git-pr-finish-review.png" alt="Github interface for submitting a code review."></a><figcaption>When you have finished your review, you can write a final comment, and then choose to simply comment, request changes, or approve & merge the pull request.</figcaption></figure>
</section>
<hr>
<div class="further-reading col">
    <strong>Further Reading:</strong>
    <ul>
        <li><a href="https://github.com/features/code-review/" target="_blank" rel="noreferrer">Write better code (Code Review Features)<span class="show-for-sr"> Opens in a new window</span></a>, <em>Github.com</em></li>
    </ul>
</div>
<div class="body-spacer"></div>
<section id="giving-good-feedback" class="col"><img class="body-icon" alt="" src="/images/conversation.svg">
    <h2>Giving good feedback</h2>
    <p>A code review isn't a movie review! Movie reviewers aren't <strong>on the same team</strong> as the filmmakers, don't get to <strong>ask for changes</strong>, and don't have to <strong>sit next to them at team lunches</strong>. <strong>Code reviews are part of a collaborative process</strong>.</p>
    <p>To quote Springsteen paraphrasing civil rights badass <a href="https://www.youtube.com/watch?v=IRCUUzpfV7k" target="_blank" rel="noopener noreferrer">Fannie Lou Hamer<span class="show-for-sr"> Opens in a new window</span></a>, "nobody wins unless everybody wins".</p>
</section>
<section id="understand" class="col">
    <h3 class="text-center">Review to understand.</h3>
    <p>Use your own ability to understand the code you're reviewing as a benchmark for how well-written the code is. <strong>Don't let your <a href="https://codeinstitute.net/blog/impostor-syndrome-in-web-development/" target="_blank" rel="noopener noreferrer">impostor syndrome<span class="show-for-sr"> Opens in a new window</span></a> be responsible for letting bad code into the code base!</strong> If the code isn't properly commented, uses non-standard syntax, or is badly convoluted, it probably isn't going to be much use to the team in the long run.</p>
    <p>On the other hand, <strong>maybe you're right and you're a total dummy</strong>. Code review is a great chance to fix that! On most teams I've worked on, most other developers knew more than me about some aspect of coding, and I got to <strong>learn really cool stuff</strong> by asking questions during code review.</p>
</section>
<section id="succeed" class="col">
    <h3 class="text-center">Review for success.</h3>
    <p><strong>Be positive in your code reviews!</strong> When someone does something cool, <strong>let them know</strong>. Your goal is not to point out mistakes, your goal is to <strong>have your team write great code</strong>.</p>
    <p>When you do need to request changes, <strong>be specific</strong>, and, where possible, <strong>point them in the direction of the resources they need</strong> - preferably internal team documentation.</p>
</section>
<section id="process-improvement" class="col">
    <h3 class="text-center">Recognize where process needs&nbsp;improvement.</h3>
    <p>Code review should be your team's <strong>last line of defense</strong> before your code heads to the QA team.</p>
    <p>Syntax and style errors should be caught <strong>by the code author with automated testing</strong>. Anything not automated should be clearly described in the documentation. Only when automation and documentation falls short should you be requesting changes in code review.</p>
    <p>If you find yourself catching (or, heaven help you, discussing in the comments) things that <em>should</em> be caught by automation or documentation, it may not be an issue that should be resolved in a single code review - it should be <strong>logged and resolved as a team effort</strong>.</p>
</section>
<hr>
<div class="further-reading col">
<strong>Further Reading:</strong>
<ul>
    <li><a href="https://mtlynch.io/human-code-reviews-1/" target="_blank" rel="noreferrer">How to Do Code Reviews Like a Human (Part One)<span class="show-for-sr"> Opens in a new window</span></a>, <em>Michael Lynch</em></li>
</ul>
</div>
<div class="body-spacer"></div>
<section id="getting-good-feedback" class="col"><img class="body-icon" alt="" src="/images/love.svg"><h2>Getting good feedback</h2>
</section>
<section class="col">
    <p>The best way to get good feedback isn't to write good code - it's to make reviewing your code as easy as possible.</p>
    <ul>
        <li><strong>Keep PRs small</strong> and focussed (break them up if you need to)</li>
        <li>Write out a <strong>list of changes</strong></li>
        <li><strong>Pass your tests</strong> first</li>
        <li>Be <strong>grateful</strong> they caught your mistakes</li>
    </ul>
</section>
<hr>
<div class="further-reading col">
<strong>Further Reading:</strong>
<ul>
    <li><a href="https://mtlynch.io/code-review-love/" target="_blank" rel="noreferrer">How to Make Your Code Reviewer Fall in Love with You<span class="show-for-sr"> Opens in a new window</span></a>, <em>Michael Lynch</em></li>
</ul>
</div>
<div class="body-spacer"></div>
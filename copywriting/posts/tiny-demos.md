       Mostly meetings, git workflow, tiny demos   

Mostly meetings, git workflow, tiny demos
=========================================

[Slides](/slides//posts/tiny-demos/)

Here is our agenda for today:

*   [Git workflow // 10:45-10:55](#gitflow)
*   [Tiny Demos](#demo) // 10:55-11:00
*   [Stand-up](#standup) // 11:00-11:15
*   [Team time!](#teamTime) // 11:15-11:45
*   [Retrospective meeting](#retro) // 11:45-12:10
*   [Sprint planning](#sprintPlanning) // 12:10-12:30

Documenting a git workflow
--------------------------

You're about to have your first team-lead "retrospective" meeting.

Before you do, I want to set a goal for you - document your git workflow.

I will be checking in with your groups in the weeks to come, and this is one of the things I'm going to ask to see.

All you need to do is to agree on, and write down, the following:

*   When you'll create a new branch
*   How you'll name your branches
*   When you'll ask to merge your branch

However, you should discuss the following (and if you agree on something, document it):

*   Acceptance criteria (i.e. no conflicts, good code commenting, good description in the pull request, etc.)
*   What to write in commit messages
*   How to handle merge conflicts
*   Whether everybody feels they fully understand the basics of git in general, and if not, what you can do about it as a team
*   Anything else that might make things run smoothly

A tiny demo
-----------

As your teams become more self-governing, I'm going to have less "shepherding" to do. I will be checking in with different teams each week, but I'd also like to do a small code/tech demo each week.

If you're interested in having me show you a particular thing, you can request it in the `[demo-requests Opens in a new window](https://discord.com/channels/1065627378950340619/1072227905549123716)` channel I have set up in Discord.

### A little background

"**dotfiles**" are files on your computer used for configuration. Your computer probably has a bunch of them already.

You may never have seen them, however. By default, both Mac & Windows hide any files whose name begins with a dot, i.e. .mySecretFile.

This is just the default, though. If you want to see them, it's as simple as changing your [Windows Opens in a new window](https://support.microsoft.com/en-us/windows/view-hidden-files-and-folders-in-windows-97fbc472-c603-9d90-91d0-1166d1d9f4b5) or [Mac Opens in a new window](https://www.pcmag.com/how-to/how-to-access-your-macs-hidden-files) file finder settings.

As you might suspect, these files are editable, and you can set just about any configuration for the system or an individual application. A lot of developers will store their dotfiles in github so whenever they set up at a new computer, it's as simple as cloning their dotfiles repo.

![Nigel Ng](/images/NigelNg.jpeg)

Photo by Albin Olsson - [Own work Opens in a new window](https://commons.wikimedia.org/w/index.php?curid=96131198), CC BY-SA 4.0

Fun little side story:

I had a student a few semesters ago (when everything was online) whose avatar for everything was 'Uncle Roger' (a comic character that my wife enjoyed a lot, as he reminded her of more than a couple relatives, and who cared about rice as much as she did).

Before Uncle Roger became Uncle Roger, he (comedian Nigel Ng) wrote code! I found his github profile, and [his dotfiles repo Opens in a new window](https://github.com/nigeljyng/dotfiles). It felt like I'd found his wallet in the street.

### The most common dotfile

Probably the world's most common dotfile is `.bashrc`.

This file sets the configuration for when you interact with `bash`.

Typically, it's saved in the root folder on your computer at `~/.bashrc`.

Most people use it for just two things: aliases (shortcuts for command line commands) and bash functions.

Let's take a look at a few of mine:

    alias cddb='cd /Volumes/sg/Projects/dbcourse'

An alias is a shortcut for a command. In this case, when I type "`cddb` \+ Enter" into the command line, it takes me to the folder where I keep the website for our 'Databases' course. From I can open it in my editor (using the command `subl .`) and fire up my local development server (using the command `hugo server -D`), and I'm off to the races.

If I'm feeling impatient, I can chain these commands together with double ampersands:

    cddb && subl . && hugo server -D

And if I ever got sick of typing those commands entirely, I can add them to _another_ alias:

~/.bashrc

    alias dbserve='cddb && subl . && hugo server -D'

Aliases are great for creating a shorthand for long file paths, or long commands with a bunch of required arguments that no one would ever remember.

Those commands you were typing in for git? A lot of people will alias them to something really short, like `alias gp='git pull'`

### Functions

What aliases _can't_ do is accept an argument.

    function multiFile()
    {
        langs=(en fr)
        PROJ="$1"
        if [ "$#" -gt 1 ]; then
            for file in "${@:2}"
            do
                for lang in "${langs[@]}"
                do 
                    touch "${PROJ}-${file}-${lang}.html"
                done
            done
        else
            for lang in "${langs[@]}"
            do 
                touch "${PROJ}-${lang}.html"
            done
        fi
    }

This is a little function I have left over from when I was doing some HTML email work. Often I'd get a project that needed, say, six versions of an email, with a french and english version of each.

This little function lets me type something into my terminal like…

    multiFile McDonalds fries nofries pickles nopickles shake noshake

and it'll create the following files:

*   McDonalds-fries-en.html
*   McDonalds-nofries-en.html
*   McDonalds-pickles-en.html
*   McDonalds-nopickles-en.html
*   McDonalds-shake-en.html
*   McDonalds-noshake-en.html
*   McDonalds-fries-fr.html
*   McDonalds-nofries-fr.html
*   McDonalds-pickles-fr.html
*   McDonalds-nopickles-fr.html
*   McDonalds-shake-fr.html
*   McDonalds-noshake-fr.html

Not only that, but I can now use this script in _other_ automations I might write.

Little timesavers like this can really add up, and help you be consistent and organized in your work. The more you automate, the more you can focus on problems that _actually_ require your attention.

Stand-up
--------

**Step 1**: Choose a scrum master and someone to keep notes.

**Step 2**: Stand in a circle, and make sure any remote attendees can attend your meeting virtually.

As a reminder, this is a short (<15 minutes) team meeting in which you go around the circle and say…

*   what **team-related work you did** since the last stand-up,
*   what you're **gonna do** now,
*   anything that's preventing them from working (a '**blocker**').

…so that everyone knows what everyone else is working on, and if they can help.

When you speak, you or the scrum master can update your feature tracking (i.e. Kanban board).

**Step 3**: If any issues (i.e. blockers) were raised, and can be resolved quickly, great. Otherwise, capture that information in your notes with someone taking responsibility for resolving the issue.

Reminder for the Scrum Master: it is your responsibility to make sure the **meeting stays short**, the **feature tracking gets updated** properly, and **blockers get resolved**.

Note for this week: you will have more team meetings today, so **scrum masters be warned**.

Team time!
----------

Now, you can contine working on your research!

Again, I encourage you to **keep your research and meeting notes in your team repo**.

Retrospective
-------------

It's time for your first retrospective meeting!

This is where you look at _how you're working together_ - not the work itself, but the **processes** you're using - your git workflow, your feature tracking, your communication, etc.

As I've mentioned in the past, there are a number of formats you could choose, but for your first retrospective, I'm going to suggest "**start/stop/continue**".

Go around the circle and have each team member list one of each of the following:

*   A work practice you'd like to see the team **start** doing,
*   a work practice you'd like the team to **stop**,
*   a work practice you'd like the team to **continue** doing.

After everyone has spoken, at the discretion of the scrum master, discuss your practices, and if the team agrees they would be willing to start or stop doing something, discuss _how_ it would happen and _who_ would take responsibility for it.

#### The scrum master's role in a sprint retrospective

The scrum master's role today is to…

1.  keep the meeting to 25 minutes,
2.  remind everyone that the meeting is a safe space to speak without interruption or judgement,
3.  keep things positive and friendly,
4.  make sure everyone is heard from,
5.  bring up topics for discussion after everyone says their piece,
6.  if a team member takes on a responsibility, put it in your feature tracking,
7.  make sure someone documents the meeting.

Sprint Planning
---------------

It's time to start planning your second sprint.

Since we only work on this class while we're in this class, you'll need to base your sprint planning on the time we have available to us in this "sprint". This sprint will consist of **one hour and 15 minutes of working time next week, and 45 minutes the following week**.

(Don't worry, I promise your working time is only going to get longer as we go.)

Did you finish everything you planned to do in the last sprint? Don't worry, those items can either stay on your board (to work on this sprint), or get moved into the backlog.

Now it's time to have your next sprint planning session!

In your groups…

1.  Decide who will take notes
2.  Create notes for any new tasks - either generated by your research, or action items from your retrospective. Include the time you estimate the task would take.
3.  Along with these new tasks, look at the tasks that were not 'Done' last week. Based on priority, you can keep them in the sprint, or move them to the 'Backlog'.
4.  Make sure each task is assigned to an individual. Does anyone have more than 2 hours worth of work to do? Either re-assign the excess work to another person, or move it into the backlog.
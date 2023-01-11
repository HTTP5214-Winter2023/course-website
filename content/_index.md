---
title: "Workshops in Web Development 2"
date: 2022-06-21T08:47:11+01:00
featured_image: meet.svg
summary: ""
toc: 
---
<div class="body-spacer--small"></div>
<h2 class="col">Table of Contents</h2>
<nav>
    <ul class="toc col">
        <li><a href="#missionStatement">Mission Statement</a></li>
        <li><a href="#description">Course Description</a>
            <ul>
                <li><a href="#agile">Agile</a>
                    <ul>
                        <li><a href="#kanban">Kanban</a></li>
                        <li><a href="#scrum">Scrum</a>
                            <ul>
                                <li><a href="#standup">Stand-ups</a></li>
                                <li><a href="#sprintPlan">Sprint Planning</a></li>
                                <li><a href="#retro">Retrospectives</a></li>
                            </ul>
                        </li>
                    </ul>
                </li>
            </ul>
        </li>
        <li><a href="#weeklyBreakdown">Weekly Breakdown</a></li>
        <li><a href="#passingCriteria">Passing Criteria</a></li>
        <li><a href="#potentialProjects">Project Examples</a></li>
        <li><a href="#git">Git workflow</a></li>
        <li><a href="#review">Review</a></li>
        <li><a href="#agileTeams">Agile workflow</a>
            <ul>
                <li><a href="#standUps">How to run a stand-up</a></li>
                <li><a href="#sprintPlanning">How to run a sprint planning session</a></li>
                <li><a href="#retrospectives">How to run a retrospective</a></li>
            </ul>
        </li>
    </ul>
</nav>
<section id="missionStatement" class="col">
    <h2>Mission statement</h2>
    <p>The point of the course will be to build stuff that makes everyone's dev work easier. This means both <strong>creating value for other developers</strong> and <strong>flattening the learning curve</strong> of your tool as much as reasonably possible.</p>
    <p>The "stuff" you build is up to you. It just has to be&hellip;</p>
    <ul>
        <li>&hellip;coded, and</li>
        <li>&hellip;potentially useful to your classmates.</li>
    </ul>
</section>
<section class="col">
    <h2>Real talk</h2>
    <p>This is the first time I've run this course, and this is the first time this course has been run with this content.</p>
    <p>What I'm about to describe may not end up being the final shape of the course, because we will work together to further define it in the way that works best for you. Thanks to agile project management practices, the direction of this course is a <strong>collaboration between me and you</strong>.</p>
    <p>My main hope for this course is that you will make cool stuff, and also get a sense of how software projects are run in most workplaces.</p>
</section>
<section class="col">
    <p>Also, there will be a lot of meetings, and meetings can be boring sometimes, but I promise where you're headed, there will be <strong>lots of meetings</strong>. I think it's really valuable that you learn <strong>how to shape your workplace practices</strong> so that <em>your team</em> can get the most value out of them.</p>
</section>
<section id="description" class="col">
    <h2>Description</h2>
    <p>This course will be conducted using <a href="#agile">Agile principles</a>. This means a flexible workflow that responds to the needs of the team. As a starting point, we will be&hellip;</p>
    <ul>
        <li>using a virtual <a href="#kanban">Kanban board</a> (via <a href="https://trello.com/b/39FoPmFO/kanban-board" target="_blank">Trello</a>) to assign and track feature progress,</li>
        <li>conducting <a href="#scrum">Scrum</a> ceremonies, including sprint planning, stand-ups, reviews and retrospectives.</li>
    </ul>
</section>
<section class="col">
    <p>Per Agile, any and all tools (including ceremonies) are subject to reassessment based on the needs of the team.</p>
</section>
<section class="col">
    <p>I will serve as the product owner. The product will be a suite of internal tools developed to resolve pain points identified by the team. These tools will be stored and maintained in a <a href="https://github.com/HTTP5214-Winter2023" target="_blank">git repository</a>.</p>
</section>
<section class="col">
    <p>Each tool must be <strong>user-tested</strong> by five other students (who have not contributed to the tool). User-testing results must be <strong>documented</strong>, including any instructions that had to be supplied to the user, and any user feedback. These results will be used to improve the tool. While smaller tools (i.e. simple bash scripts) might be ready for testing within the first couple of weeks, no tool should be so large in scope that it cannot be user tested by week 10.</p>
</section>
<section class="col">
    <p>Weeks 2 & 3 I will serve as the scrum master, conducting a single stand-up meeting (time-boxed to 30min) to provide clarity on lines of research that encourages collaboration and minimizes redundancy across the team. Weeks 4+, students will be divided into groups of 5-10 where they are collaborating or working in a similar code/user space. Individual teams will select team member to serve as scrum master in a given week.</p>
    <p>All team members will serve as scrum master for at least one week.</p>
</section>
<section id="agile" class="col">
    <h2>Agile project management</h2>
    <p>Okay, you may have heard the term "agile" thrown around in relation to dev work. Agile can mean a lot of different things, but essentially it means "a set of project management principles that can <strong>respond to what the team needs</strong>". Basically it's a way of working that reflects the software lifecycle that the web introduced - where you can update pieces of the whole, and if something's broken, you can just fix it, rather than, say, recalling ten thousand cars that people are already driving.</p>
    <p>You can <a href="https://en.wikipedia.org/wiki/Agile_software_development" target="_blank">read all about Agile</a> if you want, but we're going to be taking some techniques from two specific Agile methodologies: <a href="#kanban">Kanban</a> and <a href="#scrum">Scrum</a>.</p>
</section>
<section id="kanban" class="col">
    <h3>Kanban</h3>
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 400 300" width="406" height="306" class="illustration styles_illustrationTablet__1DWOa" style="max-width: 100%;">
        <title>Kanban board</title>
        <g id="_174_scrum_board_outline" data-name="#174_scrum_board_outline"><rect x="86.48" y="76.55" width="227.04" height="146.91" rx="5.64" fill="#68e1fd"></rect><path d="M307.88,224.45H92.12a6.65,6.65,0,0,1-6.64-6.64V82.19a6.65,6.65,0,0,1,6.64-6.64H307.88a6.65,6.65,0,0,1,6.64,6.64V217.81A6.65,6.65,0,0,1,307.88,224.45ZM92.12,77.55a4.64,4.64,0,0,0-4.64,4.64V217.81a4.64,4.64,0,0,0,4.64,4.64H307.88a4.64,4.64,0,0,0,4.64-4.64V82.19a4.64,4.64,0,0,0-4.64-4.64Z" fill="#093f68"></path><path d="M86.48,104.13h227a0,0,0,0,1,0,0V217.81a5.64,5.64,0,0,1-5.64,5.64H92.12a5.64,5.64,0,0,1-5.64-5.64V104.13A0,0,0,0,1,86.48,104.13Z" fill="#fff"></path><path d="M307.88,224.45H92.12a6.65,6.65,0,0,1-6.64-6.64V104.13a1,1,0,0,1,1-1h227a1,1,0,0,1,1,1V217.81A6.65,6.65,0,0,1,307.88,224.45ZM87.48,105.13V217.81a4.64,4.64,0,0,0,4.64,4.64H307.88a4.64,4.64,0,0,0,4.64-4.64V105.13Z" fill="#093f68"></path><path d="M139.79,224.45a1,1,0,0,1-1-1V76.55a1,1,0,1,1,2,0v146.9A1,1,0,0,1,139.79,224.45Z" fill="#093f68"></path><path d="M200,224.45a1,1,0,0,1-1-1V76.55a1,1,0,0,1,2,0v146.9A1,1,0,0,1,200,224.45Z" fill="#093f68"></path><path d="M260.21,224.45a1,1,0,0,1-1-1V76.55a1,1,0,0,1,2,0v146.9A1,1,0,0,1,260.21,224.45Z" fill="#093f68"></path><rect x="97.83" y="116.53" width="29.25" height="27.11" fill="#ffbc0e"></rect><path d="M127.08,144.65H97.83a1,1,0,0,1-1-1V116.53a1,1,0,0,1,1-1h29.25a1,1,0,0,1,1,1v27.12A1,1,0,0,1,127.08,144.65Zm-28.25-2h27.25V117.53H98.83Z" fill="#093f68"></path><rect x="156.07" y="116.53" width="29.25" height="27.11" fill="#ffbc0e"></rect><path d="M185.32,144.65H156.07a1,1,0,0,1-1-1V116.53a1,1,0,0,1,1-1h29.25a1,1,0,0,1,1,1v27.12A1,1,0,0,1,185.32,144.65Zm-28.25-2h27.25V117.53H157.07Z" fill="#093f68"></path><rect x="156.07" y="150.24" width="29.25" height="27.11" fill="#f56132"></rect><path d="M185.32,178.35H156.07a1,1,0,0,1-1-1V150.24a1,1,0,0,1,1-1h29.25a1,1,0,0,1,1,1v27.11A1,1,0,0,1,185.32,178.35Zm-28.25-2h27.25V151.24H157.07Z" fill="#093f68"></path><rect x="215.52" y="116.53" width="29.25" height="27.11" fill="#ffbc0e"></rect><path d="M244.78,144.65H215.52a1,1,0,0,1-1-1V116.53a1,1,0,0,1,1-1h29.26a1,1,0,0,1,1,1v27.12A1,1,0,0,1,244.78,144.65Zm-28.26-2h27.26V117.53H216.52Z" fill="#093f68"></path><rect x="215.52" y="150.24" width="29.25" height="27.11" fill="#f56132"></rect><path d="M244.78,178.35H215.52a1,1,0,0,1-1-1V150.24a1,1,0,0,1,1-1h29.26a1,1,0,0,1,1,1v27.11A1,1,0,0,1,244.78,178.35Zm-28.26-2h27.26V151.24H216.52Z" fill="#093f68"></path><rect x="272.01" y="116.53" width="29.25" height="27.11" fill="#70cc40"></rect><path d="M301.26,144.65H272a1,1,0,0,1-1-1V116.53a1,1,0,0,1,1-1h29.25a1,1,0,0,1,1,1v27.12A1,1,0,0,1,301.26,144.65Zm-28.25-2h27.25V117.53H273Z" fill="#093f68"></path><rect x="215.52" y="183.94" width="29.25" height="27.11" fill="#70cc40"></rect><path d="M244.78,212.05H215.52a1,1,0,0,1-1-1V183.94a1,1,0,0,1,1-1h29.26a1,1,0,0,1,1,1v27.11A1,1,0,0,1,244.78,212.05Zm-28.26-2h27.26V184.94H216.52Z" fill="#093f68"></path><path d="M122,124.31H103.06a1,1,0,0,1,0-2H122a1,1,0,0,1,0,2Z" fill="#093f68"></path><path d="M122,130.29H103.06a1,1,0,0,1,0-2H122a1,1,0,0,1,0,2Z" fill="#093f68"></path><path d="M117.78,136.26H103.06a1,1,0,0,1,0-2h14.72a1,1,0,0,1,0,2Z" fill="#093f68"></path><path d="M180.15,158.82H161.24a1,1,0,0,1,0-2h18.91a1,1,0,1,1,0,2Z" fill="#093f68"></path><path d="M180.15,164.79H161.24a1,1,0,0,1,0-2h18.91a1,1,0,0,1,0,2Z" fill="#093f68"></path><path d="M176,170.77H161.24a1,1,0,0,1,0-2H176a1,1,0,0,1,0,2Z" fill="#093f68"></path><path d="M239.6,125.11H220.7a1,1,0,0,1,0-2h18.9a1,1,0,0,1,0,2Z" fill="#093f68"></path><path d="M239.6,131.09H220.7a1,1,0,0,1,0-2h18.9a1,1,0,0,1,0,2Z" fill="#093f68"></path><path d="M235.41,137.07H220.7a1,1,0,0,1,0-2h14.71a1,1,0,1,1,0,2Z" fill="#093f68"></path><path d="M239.6,192.52H220.7a1,1,0,0,1,0-2h18.9a1,1,0,0,1,0,2Z" fill="#093f68"></path><path d="M239.6,198.5H220.7a1,1,0,0,1,0-2h18.9a1,1,0,1,1,0,2Z" fill="#093f68"></path><path d="M235.41,204.47H220.7a1,1,0,0,1,0-2h14.71a1,1,0,0,1,0,2Z" fill="#093f68"></path><path d="M180.15,128.1H161.24a1,1,0,0,1,0-2h18.91a1,1,0,0,1,0,2Z" fill="#093f68"></path><path d="M174.41,134.08H161.24a1,1,0,0,1,0-2h13.17a1,1,0,0,1,0,2Z" fill="#093f68"></path><path d="M296.09,128.1H277.18a1,1,0,0,1,0-2h18.91a1,1,0,0,1,0,2Z" fill="#093f68"></path><path d="M290.34,134.08H277.18a1,1,0,0,1,0-2h13.16a1,1,0,0,1,0,2Z" fill="#093f68"></path><path d="M239.6,161.81H220.7a1,1,0,0,1,0-2h18.9a1,1,0,0,1,0,2Z" fill="#093f68"></path><path d="M233.86,167.78H220.7a1,1,0,0,1,0-2h13.16a1,1,0,0,1,0,2Z" fill="#093f68"></path><path d="M127.08,161.81H99.85a1,1,0,1,1,0-2h27.23a1,1,0,1,1,0,2Z" fill="#dfeaef"></path><path d="M127.08,170.77H99.85a1,1,0,0,1,0-2h27.23a1,1,0,1,1,0,2Z" fill="#dfeaef"></path><path d="M117.78,179.73H99.85a1,1,0,0,1,0-2h17.93a1,1,0,0,1,0,2Z" fill="#dfeaef"></path><path d="M292.14,212.05H275a1,1,0,0,1,0-2h17.12a1,1,0,0,1,0,2Z" fill="#dfeaef"></path><path d="M301.26,202.44H275a1,1,0,0,1,0-2h26.24a1,1,0,0,1,0,2Z" fill="#dfeaef"></path><path d="M183.69,190.31H159.78a1,1,0,0,1,0-2h23.91a1,1,0,0,1,0,2Z" fill="#dfeaef"></path><path d="M121,90.42H102.11a1,1,0,0,1,0-2H121a1,1,0,0,1,0,2Z" fill="#093f68"></path><path d="M176,90.42H162.28a1,1,0,0,1,0-2H176a1,1,0,0,1,0,2Z" fill="#093f68"></path><path d="M245,90.42H215.29a1,1,0,0,1,0-2H245a1,1,0,0,1,0,2Z" fill="#093f68"></path><path d="M302,90.42h-5.86a1,1,0,0,1,0-2H302a1,1,0,0,1,0,2Z" fill="#093f68"></path><path d="M290.34,90.42H275.55a1,1,0,0,1,0-2h14.79a1,1,0,0,1,0,2Z" fill="#093f68"></path></g>
    </svg>
</section>
<section class="col">
    <p><a href="https://en.wikipedia.org/wiki/Kanban_(development)">Kanban</a> is a project management technique often used in software development. It is recognized as an "Agile" development method. Basically, every "thing" (feature, user story) that you're working on you put on a sticky note, and move it to a different corresponding column whenever the status of the work changes.</p>
    <p>The purpose of this is to make it really easy to <strong>visualize the progress</strong> of the team's work.</p>
</section>
<section class="col">
    <p><a href="https://trello.com/b/39FoPmFO/kanban-board" target="_blank">Our board</a> has a pretty typical column layout:</p>
    <dl style="padding-left: 1rem; font-size: 1rem;">
        <dt>Research</dt>
        <dd>Stuff we're looking into doing.</dd>
        <dt>To do</dt>
        <dd>Stuff we're committed to doing next.</dd>
        <dt>Doing</dt>
        <dd>Stuff we're actively working on.</dd>
        <dt>Code Review</dt>
        <dd>Stuff we've finished that needs peer review before it's considered "done".</dd>
        <dt>Done</dt>
        <dd>Stuff that has completed code review.</dd>
        <dt>Backlog</dt>
        <dd>Stuff we want to work on, but we're not sure when we'll get to it.</dd>
    </dl>
</section>
<section class="col">
    <p>Since we're using a virtual board, we can associate a lot of information with each task (sticky note), like&hellip;</p>
    <ul>
        <li>who it's assigned to,</li>
        <li>when we estimate it will be done,</li>
        <li>comments,</li>
        <li>activity history,</li>
        <li>labels,</li>
        <li>etc.</li>
    </ul>
</section>
<section class="col">
    <p>We can also use it remotely, <a href="https://trello.com/b/39FoPmFO/kanban-board/butler/rules" target="_blank">create automations</a> (like notifications), and integrate it with other tools.</p>
    <p>Kanban boards are often updated during stand&#8209;up meetings. <em>What's a stand-up meeting</em>, you ask?</p>
    <p>Well, that brings us to&hellip;</p>
</section>
<section id="scrum" class="col">
    <h3>Scrum</h3>
</section>
<section class="col">
    <p>Scrum is another set of Agile software project management practices.</p>
</section>
<section class="col">
    <p class="callout warning">It has <a href="https://news.ycombinator.com/item?id=28702676" target="_blank">kind of become a dirty word nowadays</a>, because some folks decided to charge money for training and turn it into something kind of cult-like.</p>
    <p><strong>But</strong> the industry still uses a lot of Scrum practices - they're just not dogmatic about them, because the <em>whole point</em> of Agile software is to be flexible. That's what we're gonna do - take some Scrum practices, and change 'em if we don't like 'em.</p>
</section>
<section class="col">
    <p>Here're the ones we're going to use:</p>
</section>
<section class="col" id="standup">
    <h4>Stand-ups</h4>
    <p>A 'stand-up' is a quick meeting where people say three things:</p>
    <ul>
        <li>what they <strong>did</strong> since the last stand-up,</li>
        <li>what they're <strong>gonna do</strong> now,</li>
        <li>anything that's preventing them from working (a '<strong>blocker</strong>').</li>
    </ul>
    <p>If you're using a Kanban board, like we are, this is often when it gets updated, during the stand&#8209;up.</p>
</section>
<section class="col">
    <p>The point of the stand-up meeting is so that everyone knows what everyone else is working on, and if they can help.</p>
    <p>Stand-ups are usually a 10-15 minute meeting around the beginning of each day. Since we're not going to be together every day, we'll do them each class - for the first couple weeks as a whole class, and then in smaller groups.</p>
</section>
<section class="col" id="sprintPlan">
    <h4>Sprint planning</h4>
    <p>A 'sprint' is a <strong>period of time</strong> where you're working fairly uninterrupted on a <strong>set amount of work</strong>. Typically this is two weeks (about ten working days), but since we're not working 8 hours a day, five days a week, <a href="#weeklyBreakdown">our sprints</a> will be a little wonky. A 'sprint planning meeting' is just a meeting where you <strong>figure out what work you're going to try and get done</strong> during that period of time. It's also usually when you <strong>create all the sticky notes</strong> that go on the Kanban board.</p>
</section>
<section class="col" id="retro">
    <h4>Retrospectives</h4>
    <p>A 'retrospective' is a longer discussion about <strong>how the project is being managed</strong> - what's going well, and what could be improved. Usually this is done once every two weeks (every ten working days, i.e. one sprint) - we're going to have them <a href="#weeklyBreakdown">a little more sporadically</a>.</p>
</section>
<section class="col">
    <h4>A scrum thing we're <em>not</em> doing: sprint review</h4>
    <p>There's <em>another</em> meeting type in Scrum called a "sprint review". It's like a retrospective, but a retrospective asks, "is our process working?", whereas a sprint review asks, "how is the work progressing?" Since our work is going to be very fragmented, we'll probably skip the sprint reviews.</p>
</section>
<section class="col">
    <p><strong>OR MAYBE NOT</strong>, because here's the thing:</p>
</section>
<section class="col">
    <h4>We're working agile, which means <strong>we can do whatever we want</strong>.</h4>
    <p>Each time we have a retrospective, it's an opportunity for us to <em>change how we work</em>, meaning we can stop having stand-ups, or start having sprint reviews, or change how often we have stand-ups, or <em>whatever we can agree will help the process</em>.</p>
</section>
<section class="col">
    <p>Now, there are two caveats here:</p>
    <ol>
        <li>You need <strong>buy-in from the product owner</strong>, meaning you have to get me to approve it, and</li>
        <li>I need a way to give 45+ students each a SAT/UNSAT grade in a fair, predictable and manageable way. Since that's a requirement that I have to fulfill, there will be certain things I'll insist on. But we can <a href="#passingCriteria">talk about that later</a>.</li>
    </ol>
</section>
<section id="weeklyBreakdown" class="col">
    <h2>Weekly breakdown</h2>
</section>
<div class="col">
    <table style="table-layout: fixed;">
        <thead>
            <tr>
                <th style="width: 6ch;">Week</th>
                <th>Tasks</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td style="text-align: left; vertical-align: text-top;">1</td>
                <td>
                    <ul style="margin-top:0">
                        <li>Course description</li>
                        <li>Agile (Kanban/Scrum) introduction</li>
                        <li>Description of <a href="#potentialProjects">potential projects</a></li>
                        <li>Description of a <a href="#git">simple git workflow</a> with <a href="#codeReview"></a></li>
                        <li>Break into groups to identify development pain-points</li>
                        <li>Research time</li>
                    </ul>
                </td>
            </tr>
            <tr>
                <td style="text-align: left; vertical-align: text-top;">2</td>
                <td>
                    <ul style="margin-top:0">
                        <li>Jumbo stand-up</li>
                        <li>Research time</li>
                    </ul>
                </td>
            </tr>
            <tr>
                <td style="text-align: left; vertical-align: text-top;">3</td>
                <td>
                    <ul style="margin-top:0">
                        <li>Jumbo stand-up</li>
                        <li>Research time</li>
                        <li>Get into <a href="#agileTeams">teams</a></li>
                        <li>Sprint planning</li>
                    </ul>
                </td>
            </tr>
            <tr>
                <td style="text-align: left; vertical-align: text-top;">4</td>
                <td>
                    <ul style="margin-top:0">
                        <li>Retrospective</li>
                        <li>Stand-up</li>
                    </ul>
                </td>
            </tr>
            <tr>
                <td style="text-align: left; vertical-align: text-top;">5</td>
                <td><ul style="margin-top:0"><li>Stand-up</li></ul></td>
            </tr>
            <tr>
                <td style="text-align: left; vertical-align: text-top;">6</td>
                <td><ul style="margin-top:0"><li>Stand-up</li></ul></td>
            </tr>
            <tr>
                <td style="text-align: left; vertical-align: text-top;">7</td>
                <td>
                    <ul style="margin-top:0">
                        <li>Stand-up</li>
                        <li>Retrospective</li>
                    </ul>
                </td>
            </tr>
            <tr>
                <td style="text-align: left; vertical-align: text-top;">X</td>
                <td><strong>Reading Week</strong></td>
            </tr>
            <tr>
                <td style="text-align: left; vertical-align: text-top;">8</td>
                <td>
                    <ul><li>Stand-up</li><li>Sprint planning</li></ul></td>
            </tr>
            <tr>
                <td style="text-align: left; vertical-align: text-top;">9</td>
                <td><ul style="margin-top:0"><li>Stand-up</li></ul></td>
            </tr>
            <tr>
                <td style="text-align: left; vertical-align: text-top;">10</td>
                <td><ul style="margin-top:0"><li>Stand-up</li><li>Deadline for user testing</li></ul></td>
            </tr>
            <tr>
                <td style="text-align: left; vertical-align: text-top;">11</td>
                <td><ul style="margin-top:0"><li>Stand-up</li><li>Retrospective</li><li>Sprint planning</li></ul></td>
            </tr>
            <tr>
                <td style="text-align: left; vertical-align: text-top;">12</td>
                <td><ul style="margin-top:0"><li>Stand-up</li></ul></td>
            </tr>
            <tr>
                <td style="text-align: left; vertical-align: text-top;">13</td>
                <td><ul style="margin-top:0"><li>Stand-up</li></ul></td>
            </tr>
            <tr>
                <td style="text-align: left; vertical-align: text-top;">14</td>
                <td><ul style="margin-top:0"><li>Retrospective</li></ul></td>
            </tr>
        </tbody>
    </table>
</div>
<section class="slide-only">
    <table style="table-layout: fixed; font-size: 1.2rem;">
    <thead>
        <tr>
            <th style="width: 6ch;">Week</th>
            <th>Tasks</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td style="text-align: left; vertical-align: text-top;">1</td>
            <td>
                <ul style="margin-top:0">
                    <li>Course description</li>
                    <li>Agile (Kanban/Scrum) introduction</li>
                    <li>Description of <a href="#potentialProjects">potential projects</a></li>
                    <li>Description of a <a href="#git">simple git workflow</a> with <a href="#codeReview"></a></li>
                    <li>Break into groups to identify development pain-points</li>
                    <li>Research time</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td style="text-align: left; vertical-align: text-top;">2</td>
            <td>
                <ul style="margin-top:0">
                    <li>Jumbo stand-up</li>
                    <li>Research time</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td style="text-align: left; vertical-align: text-top;">3</td>
            <td>
                <ul style="margin-top:0">
                    <li>Jumbo stand-up</li>
                    <li>Research time</li>
                    <li>Get into <a href="#agileTeams">teams</a></li>
                    <li>Sprint planning</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td style="text-align: left; vertical-align: text-top;">4</td>
            <td>
                <ul style="margin-top:0">
                    <li>Retrospective</li>
                    <li>Stand-up</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td style="text-align: left; vertical-align: text-top;">5</td>
            <td><ul style="margin-top:0"><li>Stand-up</li></ul></td>
        </tr>
        <tr>
            <td style="text-align: left; vertical-align: text-top;">6</td>
            <td><ul style="margin-top:0"><li>Stand-up</li></ul></td>
        </tr>
        <tr>
            <td style="text-align: left; vertical-align: text-top;">7</td>
            <td>
                <ul style="margin-top:0">
                    <li>Stand-up</li>
                    <li>Retrospective</li>
                </ul>
            </td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <td colspan="2"><em>Note: the stars (⭐) indicate level of difficulty. These levels of difficulty are for students' assessment of tasks they might choose, but are in no way reflected in the passing criteria.</em></td>
        </tr>
    </tfoot>
    </table>
</section>
<section class="slide-only">
    <table class="slide-only" style="table-layout: fixed; font-size: 1.2rem;">
        <thead>
            <tr>
                <th style="width: 6ch;">Week</th>
                <th>Tasks</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td style="text-align: left; vertical-align: text-top;">X</td>
                <td><strong>Reading Week</strong></td>
            </tr>
            <tr>
                <td style="text-align: left; vertical-align: text-top;">8</td>
                <td>
                    <ul><li>Stand-up</li><li>Sprint planning</li></ul></td>
            </tr>
            <tr>
                <td style="text-align: left; vertical-align: text-top;">9</td>
                <td><ul style="margin-top:0"><li>Stand-up</li></ul></td>
            </tr>
            <tr>
                <td style="text-align: left; vertical-align: text-top;">10</td>
                <td><ul style="margin-top:0"><li>Stand-up</li><li>Deadline for user testing</li></ul></td>
            </tr>
            <tr>
                <td style="text-align: left; vertical-align: text-top;">11</td>
                <td><ul style="margin-top:0"><li>Stand-up</li><li>Retrospective</li><li>Sprint planning</li></ul></td>
            </tr>
            <tr>
                <td style="text-align: left; vertical-align: text-top;">12</td>
                <td><ul style="margin-top:0"><li>Stand-up</li></ul></td>
            </tr>
            <tr>
                <td style="text-align: left; vertical-align: text-top;">13</td>
                <td><ul style="margin-top:0"><li>Stand-up</li></ul></td>
            </tr>
            <tr>
                <td style="text-align: left; vertical-align: text-top;">14</td>
                <td><ul><li>Retrospective</li></ul></td>
            </tr>
        </tbody>
    </table>
</section>
<section id="passingCriteria" class="col">
    <h2>Passing criteria</h2>
    <ol>
        <li>Each of you will <strong>maintain a markdown (<code>.md</code>) file</strong> in the shared git repository. Each week you will document:
            <ol>
                <li>what you worked on in the last session;</li>
                <li>what you will be working on in your upcoming session;</li>
                <li>any issues blocking your work.</li>
            </ol>
            <strong>10</strong> such entries are required for a pass.
        </li>
        <li>Each person must <strong>lead at least one</strong> agile ceremony (i.e. meeting).</li>
        <li>Each student must create at minimum <strong>one pull request which passes code review</strong>, and which contributes to a project that is user-tested with five classmates (not working on the same project). The results of this user testing must be written down and stored in the git repo.</li>
    </ol>
</section>
<section id="potentialProjects" class="col">
    <h2>Examples of potential projects</h2>
    <ul>
        <li>Library of simple <a href="#shell">shell/bash scripts</a> (⭐)</li>
        <li>Team <a href="#editorConfig">editor config boilerplate</a> (⭐⭐)</li>
        <li>Shared <a href="#sharedDev">dev environment</a> (⭐⭐⭐)</li>
        <li>Boilerplate / <a href="#staticHTML">workflow for deploying static HTML</a> pages (⭐⭐)</li>
        <li><a href="#automatedDocs">Automated documentation</a> (⭐⭐⭐)</li>
        <li><a href="#testSuite">Test suite</a> (from simple unit test examples to visual regression via CI action/webhook) (⭐⭐/⭐)</li>
        <li><a href="#integration">Synchronizing team tools</a>, i.e. Github pull request notification in Slack; git merge triggers card movement in Trello; etc. (⭐/⭐)</li>
    </ul>
    <div><em>Note: the stars (⭐) indicate level of difficulty. These levels of difficulty are for students' assessment of tasks they might choose, but are in no way reflected in the passing criteria.</em></div>
</section>
<section id="shell" class="col">
    <h3>Shell scripting</h3>
</section>
<section class="col">
    <p>Shells are computer interfaces that predate modern Graphical User Interfaces.</p>
    <figure>
        <img src="https://upload.wikimedia.org/wikipedia/commons/2/2f/Apple_Lisa_Computer.jpg" alt="Apple Lisa Computer">
        <figcaption>Imagine before this. <em>Timothy Colegrove, CC BY-SA 4.0, via Wikimedia Commons</em></figcaption>
    </figure>
</section>
<section class="col">
    <p>Shell scripts are simple computer programs that&hellip; make computers do stuff.</p>
    <p>I'd love to be more specific, but they're insanely flexible, so that's about as specific as I can be without excluding something.</p>
</section>
<section class="col">
    <p>Shell scripts are very commonly used on servers, but can also serve to automate tasks on our own computers. Since the majority of web servers run on Linux, the most popular shell scripting language is bash, which is the default shell on most Linux machines.</p>
    <p>Working in the shell is great for creating files and folders, and manipulating their content. For example:</p>
</section>
<section class="col">
    <pre class="small"><code class="language-bash"># delete the file called 'test.html'
rm test.html && 
# download this html file from github & save the contents into 
# a local copy called 'test.html'
curl https://raw.githubusercontent.com/simonborer/Workshops/main/index.html > test.html && 
# In 'test.html', replace every instance of the word 'Scrum' 
# with the word 'Scrumptious'
sed -i '.bak' 's/Scrum/Scrumptious/g' test.html && 
# For every instance of the word 'Scrumptious' in 'test.html', 
# print the line in the terminal with the line number
grep 'Scrumptious' test.html -n</code></pre>
</section>
<section class="col">
    <p>You can type or paste these commands directly into your terminal, or you can save them in a file, called a shell script. For example, I have script called `pwGen.sh`. Whenever I want to generate some secure passwords (say, for a class full of students with their own databases), I can just type `pwGen 42` (if I have 42 students), and it generates 42 secure passwords, and saves them to a file called `output.txt`.</p>
</section>
<section class="col">
    <p>The code in the file looks like this:</p>
    <pre><code class="language-bash">#!/bin/bash
OUTPUTFILE="output.txt"
END=${1:-1}
touch -a $OUTPUTFILE
for ((i=1;i<=$END;i++)); do
    openssl rand -base64 12 >> $OUTPUTFILE
done
echo "Passwords saved to $OUTPUTFILE"</code></pre>
</section>
<section class="col">
    <p>&hellip; but honestly I haven't looked at it in years.</p>
    <p>Creating bash scripts usually goes like this:</p>
    <ol>
        <li>Have an annoying task you do on your computer.</li>
        <li>Google the individual steps "&hellip; in bash".</li>
        <li>Build out your script by doing the individual steps in the command line.</li>
        <li>Save it in a <code>.sh</code> file.</li>
        <li>Go into work at a new job and realize you completely forget how you wrote that script, you're not sure where it is, and you definitely should've thrown it into a repo on Github.</li>
    </ol>
</section>
<section class="col">
    <p>Shell scripting isn't typically a language you "learn", because it's all about automating stuff. Once you write it once, you never have to write it again.</p>
    <p>That being said, there are a bajillion things you can do in the command line, like watch ascii star wars (<code>telnet towel.blinkenlights.nl</code>). I personally love the crazy powerful <code><a href="https://ffmpeg.org/" target="_blank">ffmpeg</a></code> library. Getting familiar with what's <em>possible</em> is what will allow you to look up how to do stuff. Here is an insanely long list of <a href="https://github.com/onceupon/Bash-Oneliner" target="_blank" rel="noopener noreferrer">things you can do in one line of bash code<span class="show-for-sr"> Opens in a new window</span></a>.</p>
</section>
<section id="editorConfig" class="col">
    <h3>Editor Configuration</h3>
    <p>Most popular code editors allow you to store all your settings in a <code>.json</code> file. Having your team use the same configurations (at least as a baseline) can save a lot of headaches, especially when it comes to auto-formatting (different formatting can make code diffs a pain). Being able to share this baseline settings file can make life easier for onboarding, working on a new machine, and working remote.</p>
    <p>Here's the documentation for <a href="https://code.visualstudio.com/docs/getstarted/settings#_settingsjson" target="_blank" rel="noopener noreferrer">VS Code's settings file<span class="show-for-sr"> Opens in a new window</span></a> and how to work with it.</p>
</section>
<section id="sharedDev" class="col">
    <h3>A shared development environment</h3>
    <p>Making sure everyone on the team is essentially working on the same "machine" can save a lot of headaches. Making sure folks are using the same version of software is great, especially if it's as close an approximation to the live environment (i.e. the server) as possible.</p>
    <p>There's a few different ways to accomplish this, including <a href="https://docs.docker.com/desktop/dev-environments/" target="_blank" rel="noopener noreferrer">Docker<span class="show-for-sr"> Opens in a new window</span></a> and <a href="https://developer.hashicorp.com/vagrant/intro" target="_blank" rel="noopener noreferrer">Vagrant<span class="show-for-sr"> Opens in a new window</span></a>.</p>
</section>
<section id="staticHTML" class="col">
    <h3>Boilerplate for static HTML deployment</h3>
    <p>You know what's great? Making web pages. I wonder how fast we could make it to&hellip;</p>
    <ul>
        <li>Create an HTML file with sensible defaults</li>
        <li>Write to that HTML file (something like <a href="https://daringfireball.net/projects/markdown/" target="_blank" rel="noopener noreferrer">markdown<span class="show-for-sr"> Opens in a new window</span></a> might help)</li>
        <li>Deploy that HTML file to the internet (something like <a href="https://www.netlify.com/" target="_blank" rel="noopener noreferrer">Netlify<span class="show-for-sr"> Opens in a new window</span></a> might help).</li>
    </ul>
    <p>Could we use shell scripts to help us? Is there an even easier process that we could document and share with our teammates?</p>
</section>
<section id="automatedDocs" class="col">
    <h3>Automated documentation</h3>
    <p>You know what can take a long time? Documentation.</p>
    <p>Some people, like me, think that taking the time to write good, thorough documentation can help us understand our work better, create better dialogue within the team, and be pleasurable unto itself.</p>
    <p>I understand this is perverse.</p>
</section>
<section class="col">
    <p>But what if I told you it's <strong>possible to generate documentation from the code you're already writing?</strong></p>
    <p>Okay, you <em>do</em> have to write some code comments, but things like <a href="https://jsdoc.app/about-getting-started.html" target="_blank" rel="noopener noreferrer">JSDoc<span class="show-for-sr"> Opens in a new window</span></a>, <a href="https://www.sphinx-doc.org/en/master/index.html" target="_blank" rel="noopener noreferrer">Sphinx<span class="show-for-sr"> Opens in a new window</span></a> (for Python) and <a href="https://storybook.js.org/addons/@storybook/addon-docs" target="_blank" rel="noopener noreferrer">Storybook Docs<span class="show-for-sr"> Opens in a new window</span></a> are really impressive. Or maybe you want a really swell looking documentation site that lets your React components <a href="https://www.docz.site/" target="_blank" rel="noopener noreferrer">basically document themselves</a>?</p>
    <p>There's a lot of good options out there for having your documentation write itself!</p>
</section>
<section id="testSuite" class="col">
    <h3>A boilerplate testing suite</h3>
    <p>The world of software testing is wild, wooly and rich, from simple unit tests that can tell you if <code>2 + 2</code> does, in fact, equal <code>4</code>, to <a href="https://engineering.dollarshaveclub.com/monitor-all-the-things-4b6f88a922e6" target="_blank" rel="noopener noreferrer">monitoring your site 24/7<span class="show-for-sr"> Opens in a new window</span></a>, to visual regression testing that can tell you if a single pixel is out of line.</p>
    <figure><a target="_blank" href="https://webintro.ca/images/vis-diff.jpg"><img src="https://webintro.ca/images/vis-diff.jpg" alt=""></a><figcaption>Visual regression, by <a href="https://markus.oberlehner.net/blog/visual-regression-tests-for-vue-applications-with-jest-and-puppeteer/" target="_blank">Markus Oberlehner<span class="show-for-sr"> Opens in a new window</span></a></figcaption></figure>
</section>
<section class="col">
    <p>As with so many things in our world, the set-up is the hard part. What if you could get things up and running for your teammates so that they could have an easy-to-replicate demo with simple instructions and guidance? <a href="https://jestjs.io/" target="_blank" rel="noopener noreferrer">Jest<span class="show-for-sr"> Opens in a new window</span></a> and <a href="https://mochajs.org/" target="_blank" rel="noopener noreferrer">Mocha<span class="show-for-sr"> Opens in a new window</span></a> are common, popular unit testing libraries. You could start there, and, if you have time, investigate <a href="https://github.com/features/actions" target="_blank" rel="noopener noreferrer">CI actions<span class="show-for-sr"> Opens in a new window</span></a> (testing/linting as part of a pull request), and more advanced types of testing, like <a href="https://www.cypress.io/" target="_blank" rel="noopener noreferrer">end-to-end testing<span class="show-for-sr"> Opens in a new window</span></a> and <a href="https://pptr.dev/" target="_blank" rel="noopener noreferrer">browser automation<span class="show-for-sr"> Opens in a new window</span></a>.</p>
</section>
<section id="integration" class="col">
    <h3>Tooling integration</h3>
    <p>One thing that makes software development tooling popular (or despised) is the ability to automate it and integrate it with other tools. Want to get a Slack message when someone assigns you a JIRA task? Want to move your Trello card automatically from 'Doing' to 'Code Review' when you submit a pull request in Github? These things are just the tip of the iceberg when it comes to integrating dev team tooling. Think about anything that's annoying or repetitive - any digital 'chore'. There's probably a way to automate it!</p>
</section>
<section id="git" class="col">
    <h2>How we'll work in git</h2>
    <p><em>Since some of you are new to git, I'm going to try to keep this as simple as possible. If things start to get messy, that's a great thing for us to work out in our sprint retrospective.</em></p>
    <p>On the first day, run this command in your terminal:</p>
    <pre><code class="language-bash">git clone git@github.com:HTTP5214-Winter2023/starter.git</code></pre>
    <p>This will create a copy of the git repo on your computer.</p>
</section>
<section class="col">
    <p>To start working on your own version of the repo, use the command <code>git branch whateverYouWantToCallIt</code>. A 'branch' is a separate version of the code that can eventually get 'merged' back into the main code base, but keeps things separate while you (and others) are doing your own thing.</p>
    <p>In the folder '<code>starter</code>' that was just created, create a folder for your project.</p>
</section>
<section class="col">
    <p>Add any files or folders you need to in order to work on your project. These could be code files, documentation, etc.</p>
    <p>Whenever you add a file or folder, you'll want to run the command <code>git add .</code>. This gets all the new files and folders 'staged', ready to send to the remote repository (the one we all share, on Github).</p>
</section>
<section class="col">
    <p>Whenever you do something worth saving, run the command <code>git commit -m 'Message about what you did'</code>.</p>
    <p>When you want to save your work to the remote repository, if it's your first time on this particular branch, run the command <code>git push -u origin whateverYouWantToCallIt</code>. This creates the branch in the remote repository, and sends your work there. After you've done it once (for this branch), you can just use the command <code>git push</code>.</p>
</section>
<section class="col">
    <p><strong>If you're the only one working on this branch</strong>, then you can just push the code. <strong>If other people are also working on this branch</strong>, then before you push, run the command <code>git pull</code> to see if they've made any changes that might conflict with yours. If there are conflicts, resolve them, commit your resolutions, and push your work.</p>
</section>
<section class="col">
    <p>When your code is ready to join the main branch of the project, you can go to your remote repo and create a pull request, and get someone to code review it. If the code reviewer wants you to make some changes, they can reject your PR (pull request), or, if they're happy, they can merge your code into the main project.</p>
    <p>Whenever you want to start on something new, switch back to the main branch, and create a new branch from there. (It's possible to branch from a branch, but I don't think you'll want to do that most of the time, unless you're doing some intense collaboration.)</p>
</section>
<section class="col">
    <p>For more information, like how to resolve conflicts and switch branches, I've created <a href="/posts/version-control">a more in-depth git write-up here<span class="show-for-sr"> Opens in a new window</span></a>.</p>
</section>
<section id="codeReview" class="col">
    <h3>Doing a code review</h3>
    <p>Okay, so as we just mentioned, you have to get a classmate to code review your work. How do you do that?</p>
</section>
<section class="col">
    <p>In the workplace, your team will probably have all kinds of requirements, both technical and social, on how to do this.</p>
    <p>We're going to keep it simple, though.</p>
</section>
<section class="col">
    <p>When someone tags you in their PR, requesting a code review, you are going to look at the files that have changed, and <strong>see if you understand their code</strong>.</p>
    <p>If you don't understand their code, it's not because you're dumb, it's because they have formatted their code poorly, or haven't written descriptive comments.</p>
    <p>If you can't understand their code, let them know where you didn't understand stuff, and reject their pull request. This is not a mean thing to do (unless you're mean about it). It's doing the team a favour by making sure any code that makes it into the main branch is easy to work with.</p>
</section>
<section class="col">
    <p>If you <em>can</em> understand their code, make sure there aren't any code conflicts or obvious errors, and that it does something worthwhile. Switch to their branch on your machine and try running their code. Does it work? Great! Does it do something useful? Awesome! Do you have any automated testing set up, and if so, has it passed the tests? Amazing! If it doesn't work, or do something obviously useful, or fails testing, you should reject the pull request (and let them know why), otherwise, you can merge it into the main branch!</p>
    <p>For more on creating and responding to pull requests, including screenshots of which buttons to press in Github, and how to get and give good feedback, <a href="/posts/version-control/#what-is-code-review">check out my PR write-up here<span class="show-for-sr"> Opens in a new window</span></a>.</p>
</section>
<section class="col">
    <h2>Course overview review</h2>
    <p>Okay, here's the plan:</p>
    <ul class="post-only">
        <li>Figure out "pain points" - things about your work (both in this program and in your upcoming workplaces) that we can make less painful using computer scripting.</li>
        <li>Investigate possible solutions, and pick one to work on.</li>
        <li>Get into groups of 5-10 people who are doing similar stuff.</li>
        <li>If one or more classmates are going to help with your solution, break it up into individual parts that you can each work on.</li>
        <li>Put those solutions/parts on virtual sticky notes and assign them to yourselves.</li>
        <li>Create those solutions and store the code in Github.</li>
        <li>In class each week, give us a brief update about how it's going.</li>
        <li>When your solution is pretty much ready, have 5 other people try it out. If you have to give them instructions on how to use it, write down those instructions. If they ask questions while using it, write down those questions. Ask if there's anything you can improve, and write down their feedback.</li>
        <li>If you've made something of value, create a pull request and merge it into the main repository.</li>
        <li>From there, you can work on improving your solution, or move onto a new one.</li>
        <li>Every couple weeks, we'll get into our groups and have a discussion about how we're working together. If there's any changes/improvements you can agree on, make it happen.</li>
        <li>Every couple weeks, we'll get into our groups and have a discussion about what we're going to work on for the new few weeks. This is especially important if you're working on stuff together, but is still helpful just as a way of checking in your work and making commitments.</li>
    </ul>
</section>
<section class="slide-only col"><ol><li>Figure out "pain points" - things about your work (both in this program and in your upcoming workplaces) that we can make less painful using computer scripting.</li></ol></section>
<section class="slide-only col"><ol start="2"><li>Investigate possible solutions, and pick one to work on.</li></ol></section>
<section class="slide-only col"><ol start="3"><li>Get into groups of 5-10 people who are doing similar stuff.</li></ol></section>
<section class="slide-only col"><ol start="4"><li>If one or more classmates are going to help with your solution, break it up into individual parts that you can each work on.</li></ol></section>
<section class="slide-only col"><ol start="5"><li>Put those solutions/parts on virtual sticky notes and assign them to yourselves.</li></ol></section>
<section class="slide-only col"><ol start="6"><li>Create those solutions and store the code in Github.</li></ol></section>
<section class="slide-only col"><ol start="7"><li>In class each week, give us a brief update about how it's going.</li></ol></section>
<section class="slide-only col"><ol start="8"><li>When your solution is pretty much ready, have 5 other people try it out. If you have to give them instructions on how to use it, write down those instructions. If they ask questions while using it, write down those questions. Ask if there's anything you can improve, and write down their feedback.</li></ol></section>
<section class="slide-only col"><ol start="9"><li>If you've made something of value, create a pull request and merge it into the main repository.</li></ol></section>
<section class="slide-only col"><ol start="10"><li>From there, you can work on improving your solution, or move onto a new one.</li></ol></section>
<section class="slide-only col"><ol start="11"><li>Every couple weeks, we'll get into our groups and have a discussion about how we're working together. If there's any changes/improvements you can agree on, make it happen.</li></ol></section>
<section class="slide-only col"><ol start="12"><li>Every couple weeks, we'll get into our groups and have a discussion about what we're going to work on for the new few weeks. This is especially important if you're working on stuff together, but is still helpful just as a way of checking in your work and making commitments.</li></ol></section>
<section id="agileTeams" class="col">
    <h2>Team work in Agile</h2>
    <p>In agile development, teams are meant to be "cross-functional", meaning that each team member has an expertise, but also basic skills in all the jobs the team does.</p>
    <p>In the third week, you'll be broken up into individual teams of 5-10 people, and you'll start to run meetings for yourselves. This means one person in your team will need to be the "scrum master" - the person who runs the meeting. Every person on your team will need to lead at least <em>one meeting</em> over the course of the&hellip; course. (Don't worry too much, these meetings include the weekly stand-ups!) You <em>must</em> keep track of who lead which meeting in a document stored in Github. You can also keep track of any additional meeting notes you want to track in this document.</p>
</section>
<section class="col">
    <p>The scrum master is responsible for conducting these meetings in a timely fashion, and for keeping the team positive and productive. The scrum master is also responsible for documenting meetings (although they can delegate the documentation to another team member).</p>
    <p>Here's how you run these meetings:</p>
</section>
<section id="standUps" class="col">
    <h3>How to run a "stand up"</h3>
    <ol>
        <li>Stand (duh) in a circle</li>
        <li>Go around the circle, with each person stating the following:
            <ol>
                <li>"Last time I worked on&hellip;"</li>
                <li>"This time I'm gonna work on&hellip;"</li>
                <li>"Here are the things preventing me from working&hellip;" (a.k.a. "blockers")</li>
            </ol> 
            <p class="callout primary"><small>Note that the last point should be about specific actions, i.e. "I'm waiting on the design," or "I'm waiting on code review". The goal is to make your team mates aware of how they can help.</small></p>
            <p>If this person can move a sticky note to a new column, they should do so now.</p>
        </li>
    </ol>
</section>
<section class="col">
    <h4>The scrum master's role in a stand-up</h4>
    <p>The scrum master's role is to&hellip;<ol><li>call the meeting,</li><li>assist in updating the Kanban board,</li><li>document the meeting,</li><li>co-ordinate with the product owner if the team identifies resources they need,</li><li>and help remove blockers.</li></ol></p>
</section>
<section id="sprintPlanning" class="col">
    <h3>How to run a sprint planning session</h3>
    <p>In your group&hellip;</p>
    <ol>
        <li>Look at the work that needs doing, including anything in the backlog, and any proposed new work.</li>
        <li>Look at how much time you have available in the sprint.</li>
        <li>Assign tasks that could be accomplished within the sprint.</li>
    </ol>
</section>
<section class="col">
    <h4>The scrum master's role in a sprint planning session</h4>
    <p>The scrum master's role is to&hellip;<ol><li>call the meeting,</li><li>go through the backlog items with the team,</li><li>document the meeting,</li><li>communicate the work being taken on with the product owner.</li></ol></p>
    <p class="callout primary"><small>Note: Product owners are usually in attendance for sprint planning sessions. I'll have to see how involved I can be when we've got a bunch going on simultaneously.</small></p>
</section>
<section id="retrospectives" class="col">
    <h3>How to run a sprint retrospective session</h3>
    <p>The goal of a retrospective is to improve <em>how the team works together</em>, a.k.a. the "process". This is a time for looking at how you communicate, document, and help each other.</p>
</section>
<section class="col">
    <p>There are <a href="https://blog.logrocket.com/product-management/what-is-a-sprint-retrospective-templates-and-best-practices/" target="_blank" rel="noopener noreferrer">a number of possible formats<span class="show-for-sr"> Opens in a new window</span></a> for prompting the team to think of things are going well, and could be improved. Here is one example, called "start, stop, continue":</p>
</section>
<section class="col">
    <p>In your group&hellip;</p>
    <ol>
        <li>Go around the circle and have each team member list one of each of the following:
            <ul>
                <li>A work practice you'd like to see the team <strong>start</strong> doing,</li>
                <li>a work practice you'd like the team to <strong>stop</strong>,</li>
                <li>a work practice you'd like the team to <strong>continue</strong> doing.</li>
            </ul>
        </li>
        <li>Discuss these practices, and if the team agrees they would be willing to start or stop doing something, discuss <em>how</em> it would happen and <em>who</em> would take responsibility for it.</li>
    </ol>
</section>
<section class="col">
    <h4>The scrum master's role in a sprint retrospective</h4>
    <p>The scrum master's role is to&hellip;<ol><li>choose the format,</li><li>call the meeting,</li><li>remind everyone that the meeting is a safe space to speak without interruption or judgement,</li><li>keep things positive and friendly,</li><li>make sure everyone is heard from,</li><li>if a team member takes responsibility that belongs on a sticky note, put it on the Kanban board,</li><li>document the meeting.</li></ol></p>
    <p class="callout primary"><small>Note: Product owners are usually in attendance for sprint planning sessions. I'll have to see how involved I can be when we've got a bunch going on simultaneously.</small></p>
</section>
<div class="body-spacer"></div>
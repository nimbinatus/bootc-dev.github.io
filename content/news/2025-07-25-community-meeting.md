+++
title = "Bootc Community Meeting Notes - 25 July 2025"
date = 2025-07-25
slug = "2025-july-25-community-meeting"
+++

### Attendees:
- Robert Sturla (Tesco Bank / Universal Blue)
- Hristo Marinov
- Ben Breard
- Laura Santamaria (she/her)
- Joseph Marrero Corchado (Red Hat, Inc.)
- Colin Walters
- Dusty Mabe
- Mohan Shash
- Gursewak Mangat

### Agenda
- [Milestone 5](https://github.com/bootc-dev/bootc/milestone/5)
    - Anyone have anything else to add to the milestone?
    - Added a couple
- Info about contributing: [Blog post on Red Hat Developers](https://developers.redhat.com/blog/2025/07/23/shape-future-linux-contribute-bootc-open-source-project)
- {{speaker(name="Colin")}} Assigning/delegating issues
    - Right now not auto-assigning reviews and issues. Worth starting to do?
    - Bot to round-robin reviews?
    - [GitHub Docs on code review settings](https://docs.github.com/en/organizations/organizing-members-into-teams/managing-code-review-settings-for-your-team)
    - Thoughts, opinions, screaming fights?
        - {{speaker(name="Joseph")}} OpenShift repos have something automatic like this. Agree the custom stuff is heavy-handed for us.
        - {{speaker(name="Colin")}} Merge queue is a huge example of something that GitHub added that used to be custom for other projects
        - {{speaker(name="Colin")}} will take action item to set something up for this
- {{speaker(name="Laura")}} Website PR - build is technically running on my fork
    - [bootc-dev/bootc-dev.github.io#3](https://github.com/bootc-dev/bootc-dev.github.io/pull/3)
    - [Mini preview](https://nimbinatus.com/bootc-dev.github.io/) (except my domain stuff is messing with links)
    - {{speaker(name="Ben")}} Do we want to move the this week in bootc there?
    - {{speaker(name="Ben")}} What about [containers.github.io/bootable/](https://containers.github.io/bootable/) ? Move it? Use it? Wipe it?
        - {{speaker(name="Colin")}} There's two things: Specs/standards vs how it works. People have asked for "what's the bootc spec?" would be good to add it somewhere... Probably don't squash them yet.
        - Containers org has been catchall. Just transfer the repo into bootc-dev? Could explain the spec there.
        - Worth linking or leave it separate?
            - Maybe come back to it? Any strong opinions?
            - {{speaker(name="Mohan")}} Linking would be helpful. Website at bootc.dev that links to it will make it easier to find...
    - {{speaker(name="Colin")}} Let's land website and iterate from there
- rollup of events/blogs/releases, picking back up BCTW?
    - Duplicates news?
    - If there are blog topics we need to write on, talk with Ben?

### TODO
- [ ] Colin - set up review round-robin bot
- [ ] Laura - go fix the css links
- [ ] Laura - cname setup
- [ ] Laura - fix the double-workflow issue on the site
+++
title = "Bootc Community Meeting Notes - 08 August 2025"
date = 2025-08-08
slug = "2025-august-08-community-meeting"
+++

### Attendees
- Robert Sturla (Tesco Bank)
- Hristo Marinov
- Laura Santamaria (she/her; Red Hat)
- Colin Walters
- Joseph Marrero Corchado (Red Hat)
- John Eckersberg (Red Hat, Inc.)
- Chris Kyrouac
- Dusty Mabe (he/him; Red Hat)
- Gursewak Mangat
- Jonathan Lebon
- Sean Thrailkill
- afterstory

### Agenda
- {{speaker(name="Colin")}} More on composefs [bootc-dev/bootc#1498](https://github.com/bootc-dev/bootc/issues/1498)
  -  {{speaker(name="Colin")}} Clientside reworking on how we store files. Then there's the build side to this whole thing. What's the user experience look like for creating an image
  -  {{speaker(name="Colin")}} Recap from previous meeting
  -  {{speaker(name="Colin")}} Fatal flaw of binary copying into host
  -  {{speaker(name="Colin")}} Issue is about build side
  -  {{speaker(name="Colin")}} Logistically simplest - containers build however you want, bootc cleans up, then user provide secure boot key
  -  {{speaker(name="Jonathan")}} Not following super closely, but feels like we're starting with the hard case. Any work around non-sealed composefs builds today? Does it work?
    -  {{speaker(name="Colin")}} Yes, kinda. "It Depends":tm: Gets into whole problem around how we transition installs. Doesn't need to be sealed, but only target UKIs to start. We get into mechanical issue of default Fedora base images aren't set up for UKI. ostree backend does not really support UKIs (at least not with UEFI). Yes, it definitely will support nonsealed systems. Assuming we want to run this tool on your container images anyway.
    -  {{speaker(name="Jonathan")}} Need to make sure that, when designing, want to consider how migrate existing systems, and how will work with unsealed systems. Sealed case may be a specialized thing in beginning. May affect design; overconstrain.
    - {{speaker(name="Colin")}} We will definitely support transitioning existing systems. In end, can always boot without secure boot, too.
    - {{speaker(name="Colin")}} not committing to anything; this is still experimental. Nothing stops us from allowing flow within Dockerfiles, too.
  - {{speaker(name="John")}} Haven't really explored it a whole lot. May change, and likely will hit many walls. Just wanted to start discussion. Please feel free to comment in issue! Help find flaws in plan :)
  - {{speaker(name="Colin")}} Want people to feel free to ask questions in this meeting! Don't be afraid to ask for clarity, ask to help contribute.
- {{speaker(name="Sean")}} Recently gave talk at Flock about state of bootc! Big fan, want to get involved. We've shifted away from how installation process used to work. Used to be build your artifacts, now transitioning to replace the existing install, especially in more cloud-centric areas. What was the impetus for the change in direction?
  - {{speaker(name="Colin")}} Very interested. Wouldn't say it's backing away. We know we have to support a flow where you have a container image, then allow to turn into ISO or raw disk file. Too many use cases for that to give it up (e.g., edge, IOT devices, want to preconfigure before ship). We have to support that. Tension is in some clouds, managing disk images kinda stinks. Esp. AWS, as an example. There's two different worlds, and we do need to do both.
  - {{speaker(name="Dusty")}} bootc image builder supports uploading AMI for AWS, but usually you have to figure that part out on your own. Now also options to boot and then replace. That's more of a "let's remove the extra step from the user's responsibility, allow for existing thing that can be paved over." Might make it easier.
  - {{speaker(name="Sean")}} Makes sense. Sounds like this is to make it simpler for the user; pave over idea makes sense for the user.
  - {{speaker(name="Dusty")}} idea is they already have podman, which can run the container than can then pave your system. Bootc is on engineer's device. Positives and negatives. Positive: You start with whatever image for OS is on your cloud, and then you have to rebase that instance to your container. Negative: Feels like there's a new cloud that pops up everyday. Feels like we're constantly chasing the ball. Better experience is wherever you are is a starting point. So this allows to start from *something* you can start from. Doesn't even have to be EL-based. Can be Ubuntu. Can get to success without having to create your own disk image.
  - {{speaker(name="Colin")}} Not an installer in the partitioning sense. We want to make it easy/happy path for someone making own OS or distro - closer you can get to OS is container, then the installer area can be smaller. Bootc doesn't know how big you want your partition to be, for example, but if you can use whatever installer to install your containerized OS, then you're in a better space. Freya Labs also investigating bootc, called readymade.
  - {{speaker(name="Laura")}} I'll see if I can find them. (chat noted that they're in the universal blue discord)
- {{speaker(name="Jonathan")}} Choice of filesystem in container image and possibility of putting the choice of the filesystem in the image itself
  - {{speaker(name="Colin")}} Would like to support systemd-repart as part of MVP first, possibly able to support something like this later.
- Lots of talk about new friends, inviting new friends, and timezone issues (we know this isn't great for Europeans and others.)
- Discussion of recording meeting, general agreement we should probably record and post
- One option: Split 50%/50% recorded vs not, the advantage of this would be that the second half can be for "stupid questions" that people may not be comfortable having on the Internet Forever
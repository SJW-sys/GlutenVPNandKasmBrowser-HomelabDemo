# TITLE
goal

## Things to note in a deployment of this tool
- this is a DEMO, please see FAQ section of README
- Containers like gluten that have a configuration file, require a reboot of the container to pull in the changes.
- Ensure bind mounts on host are set to 600 permissions (rw-------), and have the correct owner/group to align with uid/gid given to container space.
- Setup for different VPN providers, and using Wireguard v OpenVPN connections are all different.
- Virtualizing anything with Kasm is demanding compared to most traditional containers, I recommend at least 2vCPU and 2RAM accessible to the container for demo purposes
- I DEMO docker swarm secrets, for a simple homelab might be better to just use a .env file

## Prerequisite in a deployment of this exact repo
- Gitlab and a runner are Deployed and configured to talk to target server
- Some Variables have been configured within Gitlab to inject into a pipeline at runtime
- target server at a minimum has docker and openssh server (w/ .pub key) setup
- DNS resolver is already configured
- Updating .env file for your needs
- using [Caddy](https://github.com/SJW-sys/Caddy-HomelabDemo) or a Reverse Proxy to handle SSL for a clean URL and encryption.

## Resources:
- Github: 
- DockerHub: 
- website:
- Documentation:

## FAQ for repo visitors
### Why does the repo have 'Demo' in the title?
this "demo" repo is based on real world local deployments in my Homelab. Some settings may be changed, or different for privacy and safety.

### Why a gitlab pipeline file (.gitlab-ci.yml)?
I selfhost a Gitlab instance at home for experimentation, experience and privacy. So I use gitlab runners to deploy my pipelines, this is the native file for that. In the future I will update these demos to reflect github native pipelines workflows (.github/workflows/PIPELINE.yml), or maybe I'll do a jenkins demo for my own learning.

### Why multiple branches
I have a test and main branch to more demo a enterprise setup, where you might have people pushing changes to a protected test branch that is then has pipelines to stage tooling in a test space. Which once pulled into main, would deploy the same setup to PROD.

### Where can I find more about this project and your thought process?
I make it a habit that my files typically have dozens of in-line comments to better help anyone using them for the first time to understand what is happening, maybe not always why. Also please check out my blog, it typically has more information on my projects (sometimes the post is still being planned).

### Does ths connect to your other Homelab Demo repos?
yes! For the most part this will be treated a siloed deployment, but most of these demos connect to the [reverse proxy](https://github.com/SJW-sys/Caddy-HomelabDemo) for ssl termination.

### Was AI used to generate this?
No, but I have learned and expanded my knowledge of the tools within this project (and prior projects) with AI to design a better solution and skills for other deployments. AI I see as a tool and resource that is loose in the market place regardless of your stance, that you need to follow, know how to use, while educating others on its complexities and putting safeguards around it. I firmly design and deploy with my own brainstorming, knowledge, and troubleshooting as my first approach, but i have used AI to troubleshoot, help expand understanding, research, interpreter (ie. Bash to Go) and experimented with vibe coding. I have deeper thoughts and opinions, but those are better discussed rather than a few sentences in a git repo. 

## Issues to note with this "demo"
I wanted to do a proper code repo that could be poke around so you could see commits and pulls that you might normally see in a team production repo, unfortunately due to the overhead and this [issue](https://github.com/orgs/community/discussions/6292), I will be "cutting corners" and doing everything locally then pushing to main directly from my machine. However, I will still leave the demo "main" and "test" branches with there protections.

## Docker features, CI/CD tooling/skills, and other tools leveraged in this project.
- Docker:
    - image pull
    - compose
    - Networking
    - secrets
    - bind mounts and volumes
    - device passthrough
    - Permissions (capabilities)
    - environment variables
    - managing tooling multiple configurations files
- Yaml
- Git
- Gitlab interface and secret management
- Pipelines (all in Gitlab formatting)
- Git CD/CI best practices (branches, branch protections, etc)
- Linux (general and permissions)
- Bash
- SSH
- Documentation

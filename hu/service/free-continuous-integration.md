# Continuous integration, continuous delivery

Egyes szoftver projekt tárolóknak is része:

* [vcs-code-hosting.md](vcs-code-hosting.md)

## Ajánlott

### AppVeyor

* https://www.appveyor.com/pricing/
* max. 60 perc/fordítás
* korlátlan publikus projekt
* 1 párhuzamos futás
* cég: Vancouver, Kanada
* VCS integráció: GitHub, GitHub Enterprise, Bitbucket, GitLab, Azure Repos, Kiln, Gitea vagy egyéni tároló

### Azure Pipelines

* https://azure.microsoft.com/en-us/services/devops/pipelines/
  * https://github.com/marketplace/azure-pipelines/
* VCS integráció: GitHub
* FOSS: 10 párhuzamos futás, korlátlan futási perc/hó
* privát: 1 párhuzamos futás, 1800 perc/hó

### Bitrise

* https://www.bitrise.io/pricing#Comparison-Section
* 300 kredit/hó (300 Linux perc vagy 150 OS X perc)
* max. 90/futás
* 5 párhuzamos futás
* cég: magyar, irodák: UK, US
* platform: mobil

### Buddy

* https://buddy.works/pricing
* 5 projekt
* 120 futás/hó
* 1 GB RAM, 2 vCPU
* 300 perc*GB(RAM) CI/CD, 1GB gyorsítótár
* 1 párhuzamos futás
* 1GB kiszolgált tárhely, 300 perc*GB
* VCS integráció: GitLab, GitHub, BitBucket

### BuildKite

* https://buildkite.com/pricing
* korlátlan futás/hó
* VCS integráció: GitHub, GitHub Enterprise, GitLab, Bitbucket, Bitbucket Server

### CircleCI

* https://circleci.com/pricing/
  * https://github.com/marketplace/circleci
* 6000 perc/hó
* VCS integráció: GitHub, GitHub Enterprise, Bitbucket

### Cirrus CI

* https://cirrus-ci.org/pricing/
  * https://cirrus-ci.org/faq/#are-there-any-limits
* 8-16 vCPU
* korlátlan perc/hó

### CodeFresh

* https://codefresh.io/pricing/
* korlátlan futás/hó
* 1 párhuzamos futás
* 5 felhasználó
* VCS integráció: GitHub Cloud, GitHub On premises, Bitbucket, GitLab Cloud, GitLab On premises, Azure DevOps Git

### CodeMagic

* https://codemagic.io/pricing/ (nevercode)
* platform: mobil, macOS
* 500 perc/hó futás
* max. 120 perc/futás

### Drone.io

* https://cloud.drone.io/welcome
* cég: San Francisco, Kalifornia
* VCS integráció: GitHub, GitHub Enterprise, Gitea, Gitee, GitLab, Gogs, Bitbucket Cloud, Bitbucket Server

### jFrog

* https://jfrog.com/pricing/
* régi nevén Shippable
* 2GB tárhely
* 10GB/hó forgalom
* 2000 perc/hó

### Semaphore CI

* https://semaphoreci.com/pricing
* platform: Linux, OS X
* 1300 perc/hó futás
* 1 párhuzamos futás
* VCS integráció: GitHub (GitLab, BitBucket?)

## Negatív példák

### AWS CodePipeline

* https://aws.amazon.com/codepipeline/
* CI/CD
* AWS free tier mellé felármentes

### DigitalOcean

* https://www.digitalocean.com/pricing/app-platform
* CI/CD
* forrás: GitHub
* TLS
* CDN

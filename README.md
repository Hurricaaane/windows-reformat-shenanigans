# windows-reformat-shenanigans
reformatted my windows gaming pc and shenanigans happened


### installing git so that it works with keepass' keeagent

- open pageant.exe, create and save a session first https://stackoverflow.com/a/7697167/4506528
  - why? because the installation process of git for windows won't show plink option if this hasn't been done
- install git for windows and in the installation process, set path to plink.exe
- run `./plink.exe mygitlabserver.example.com -P 2222` to add gitlab to putty's known hosts (which are in the registry) https://stackoverflow.com/a/12448986/4506528
  - and don't forget the custom port using `-P`
- install keeagent
- you win

post mortem:

- keeagent doesn't work so seamlessly with openssh, so use putty instead
- if the message `The server's host key is not cached in the registry.` appears during a `git` command, abort immediatly and use `plink.exe` instead. all errors messages stemming from that are meaningless
- ssh ports matter
- i need coffee

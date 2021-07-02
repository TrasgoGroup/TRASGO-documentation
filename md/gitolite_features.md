# Gitolite features

[Gitolite](gitolite.md) is an access control layer on top of git. Here are the features that most people see

- Use a single unix user ("real" user) on the server.
- Provide access to many gitolite users:
    + they are not "real" users,
    + so they do not get shell access.
- Control access to many git repositories:
    + read access controlled at the repo level,
    + write access controlled at the branch/tag/file/directory level, including who can rewind, create, and delete branches/tags.
- Can be installed without root access, assuming git and perl are already installed.
- Authentication is most commonly done using sshd, but you can also use "smart http" mode if you prefer (this may require root access for the initial setup).



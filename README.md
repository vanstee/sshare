SSHare
======

Pairing is fun! But, setting up a tmux screenshare sesh is totally not fun.
Here's a nifty little gem to help with the painfulness.

Science!
--------

1. Run the `sshare` command with some options like your tmux socket

2. Tell your friends to connect via `sshare --friend <github-username>`. We'll
   pull their pubkey off github, but you can restrict which organization they
   belong to as a config option.

3. Behind the scenes, you and your friend will have a quick chat over a heroku
   server to exchange connection information. This step should use STUN/ICE to
   *hopefully* be able get you guys connected even if you're both NATed.

4. Then when your friend finally connects we'll go ahead and shove them into
   the tmux session with you.

Requirements
------------

So far we already can't use the default sshd server on OS X. I have a [gist of
a
formula](https://gist.github.com/vanstee/5018603/raw/0807650328644dab7c09ce90324dee10272b0ac1/openssh.rb)
which installs the latest version of openssh with support for
`AuthorizedKeysCommand`.

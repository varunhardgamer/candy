Welcome to Candy land!
===================

Getting Started
---------------
To get started with the Candy sources, you'll need to get
familiar with [Git and Repo](http://source.android.com/source/version-control.html).


Create the Directories
----------------------

You will need to set up some directories in your build environment.

To create them run:

    mkdir -p ~/bin
    mkdir -p ~/candy


Install the Repository
----------------------

Enter the following to download the "repo" binary and make it executable:

curl http://commondatastorage.googleapis.com/git-repo-downloads/repo > ~/bin/repo && chmod a+x ~/bin/repo

You may need to reboot for these changes to take effect.
Now enter the following to initialize the repository:

    cd ~/oreo


Repositories:
---------------

Before you continue, run this in the terminal
----------------------------------------
    repo init -u https://github.com/CandyRoms/candy.git -b oreo && repo sync -f

*PLEASE NOTE THAT YOU MUST USE THE -f flag when repo syncing/initializing if you want to sync with our default -jX setup as android.googlesource seems to like to reject your requests if you set your -jflag too high.
if you wish to avoid this issue run it repo sync -j1 otherwise -f (force) is recommended so it will resync the repos it gets error codes on. Thank you and have a nice day.*


Building the System
---------------

Please note that if you are building on Mac OS X, you are required to install coreutils from MacPorts before you continue.
Initialize the environment with the envsetup.sh script. Note that replacing "source" with a single dot saves a few characters, and the short form is more commonly used in documentation.

    . build/envsetup.sh
    brunch DEVICE NAME

Submitting Patches
------------------
Patches are always welcome!  Please submit your patches via BBQDroid's Gerrit!
You can do this by using these commands:

    Setting up for repo upload: (run these commands once)
    git config --global review.review.bbqdroid.org.username <Your username registered at Candy's gerrit>
    git config --global review.review.bbqdroid.org.email <Your email registered at Candy's gerrit>

    (From root android directory)
    . build/envsetup.sh
    repo start oreo .
    (Make your changes and commit)
    repo upload .

You can enable a signed GPG push with:

    git config --global push.gpgSign if-asked


and enable signing your commits with:

    git config --global commit.gpgsign true


Note: "." meaning current directory
For more help on using this tool, use this command: repo help upload

Make your changes and commit with a detailed message, starting with what you are working with (i.e. vision: Update Kernel)
Commit your patches in a single commit. Squash multiple commit using this command: git rebase -i HEAD~<# of commits>

To view the status of your and others' patches, visit [Candy's Code Review](http://review.bbqdroid.org/)

If you have any issues/questions please contact us on Google+


Attention designers
-----------------
We've been looking for people to help design a bootanimation, wallpapers, and potentially a theme for Candy
If you'd be interested, just find us on Google+ and leave a message!

Credits to CarbonROM for the layout of this README

# Software releases

* [Intro](#intro)
* [Release run book](#release-run-book)
* [Update Documentation](#update-documentation)
* [Update web-site](#update-web-site)


## Intro

BitDust project development flow is based on two independent GIT repositories:

* [Development repository](https://github.com/bitdust-io/devel)
* [Stable repository](https://github.com/bitdust-io/public)


When changes in the development repo are considered to be "good enough" files are manually copied by one of the developers to the stable repo and new Pull Request is started.
This process can be considered as a new "Release" - we do not have any versioning of the releases.
After Pull Request gets merged - release is done.

Every BitDust node periodically "check & fetch" fresh commits from GIT repository where it was cloned from.
This way BitDust software automatically "updating itself" and stay in sync with "Stable" repository.

Bellow is a step-by-step guide to deliver changes from "Development" repository into "Stable".



## Release run book

Change to "stable" repo folder, you must have it already cloned locally in `./bitdust` folder:

    cd ./bitdust/


Development repository must be already cloned in `./bitdust.devel` folder in same parent folder.
Now import fresh code from "devel" repo on top of existing files:

    ./import ../bitdust.devel/


Turn OFF DEBUG mode in all Python files:

    find . -type f -name "*.py" -exec sed -i 's/_Debug = True/_Debug = False/g' {} +


Mark all modified files in git to be commited in the new release:

    git add -u .


Add all other new files to git manually - this is important here to not miss any files:

    git add ...


If some files or folders was removed from "devel" repo - do not forget to also remove them from "stable" repo and mark those changes to be commited:

    rm ...
    git add -u . 


Check again to be sure you didn't miss to remove / add any other files. Some files and folders should be excluded from "stable" repo so this bellow command will help you to identify differences:

    cd ..
    diff --brief -r bitdust/ bitdust.devel/ | grep -v ".DS_Store" | grep -v "site-packages" | grep -v ".git" | grep -v "__pycache__" | grep -v ".pyc" | grep "Only in"

    Only in bitdust.devel/: HISTORY.txt
    Only in bitdust.devel/: deploy
    Only in bitdust/: import
    ...


Do not commit your changes yet!
Change back to "devel" repo and run such command to list all commits added to "devel" repo after last release of the "stable" repo was published:

    cd ./bitdust.devel/
    ./history ../bitdust/


File `HISTORY.TXT` was created and now it is time to describe which changes we are going to publish in the `CHANGELOG.txt`.

Copy text block from `HISTORY.TXT` file into `CHANGELOG.txt` and make it nice-looking:

    head -30 HISTORY.TXT
    nano CHANGELOG.txt


Commit `CHANGELOG.txt` in the "devel" repo:

    git add CHANGELOG.txt
    git commit -m "updated CHANGELOG, prepare next release"


And also copy `CHANGELOG.txt` to the "stable" repo:

    cp CHANGELOG.txt ../bitdust/


Now you can finally commit changes in the "stable" repo:

    cd ../bitdust/
    git add CHANGELOG.txt
    git commit -m "<glorious name of the new release>"


Push changes to your "stable" repo - you must already have a Fork of "stable" repo:

    git push origin master


Create new [Pull Request](https://github.com/bitdust-io/public/pulls) to the "stable" repository ...

Review ...

Merge ... 

Congratulations, YOU ARE LIVE NOW!!!

Update your fork to stay in sync:

    git pull upstream master
    git push origin master



## Update Documentation

BitDust project Documentation are fully open-sourced and everyone are welcome to contribute and improve it the [Documentation repository](https://github.com/bitdust-io/docs).
Those steps are required to keep documentation in sync with the code.
Update "docs" repo first, you must already have it forked and cloned in `./bitdust.docs/` folder in same parent folder as "devel" and "stable" repos:

    cd ../bitdust.docs/
    ./build_api
    ./build_settings
    # TODO: ./build_changelog


Push changes to your fork of documentation repository and start new [Pull Request](https://github.com/bitdust-io/docs/pulls) to the upstream:

    git push origin master
    # Open & Merge Pull Request


Update your fork to stay in sync after merge:

    git pull upstream master
    git push origin master



## Update web-site

Main BitDust web site at [www.bitdust.io](https://bitdust.io) is also fully open-sourced in [WWW repository](https://github.com/bitdust-io/www).
However only "core" developers have SSH access to the hosting server, anyone are welcome to contribute and improve the web-site via GIT.

You can "auto-generate" all HTML pages based on Markdown sources from documentation repository:

    cd ../bitdust.www/
    ./build


Push changes to your fork of WWW repository and start new [Pull Request](https://github.com/bitdust-io/www/pulls) to the upstream:

    git push origin master
    # Open & Merge Pull Request


Update your fork to stay in sync:

    git pull upstream master
    git push origin master


After merging changes, ask one of the developers to runs "git pull" command on the server via SSH and web site will be immediately updated:

    ./update


ALL DONE!

Git Commit Style Guide

**To Learn About Git Commit/Rebase/Merges:** <https://learngitbranching.js.org/?locale=en_US>

To better keep track of commits and spend less time on their configuration, the following guide details

- How to format a commit (for ORCA and Hi-SNR Lab)
- Rules for a commit message
- Rules for commit frequency

This style guide has influences from ericavob's [Git Commit Style Guide](https://gist.github.com/ericavonb/3c79e5035567c8ef3267#file-git-commit-style-guide-md) and qoomon's

[Conventional Commits Cheatsheet](https://gist.github.com/qoomon/5dfcdf8eec66a051ecd85625518cfd13)

Commit Formatting in ORCA (use this command if you don't use the .gitmessage template)

git commit -m"&lt;type&gt;(&lt;scope&gt;): &lt;subject&gt;" -m"&lt; body&gt;" -m"&lt;optional footer&gt;"

Using the above command, set up your commits in an easy-to-read format.

&lt;type&gt;(&lt;scope&gt;): &lt;subject&gt;

&lt;BLANK LINE&gt;  
&lt;body&gt;

&lt;BLANK LINE&gt;

&lt;optional footer&gt;

Type: the type of change made by commit, list of types will be in commit rules section

Scope: where the change was made e.g. sdr->main.cpp

Subject: summary of changes made

Body: details about commit, includes the motivation for commit and how it is different

Optional Footer: anything one should be aware of, such as how to test the change and anything that now needs to be added because of the change

Commit Rules (in ORCA)

Length

- Subject line must be under 60 characters, this is one line in Github PR description

Types

- feat - a new feature is introduced within the change
- fix - a bug fix has occurred
- chore - maintenance not related to fix or feature
- refactor - code restructure without changing external behavior (no bug or feature)
- docs - update to documentation
- style - formatting that doesn't affect meaning of code e.g. whitespace, semicolons etc.
- test - added missing test or correcting previous one
- ci - continuous integration related, checking code with other developers
- rearrange - files moved, added, deleted etc.

ADD MORE IF NEEDED

Scope

- Where exactly the change was made ex. tests ->data

Subject

- Summary of the changes made a succinct description of change.
- Present tense
- No capitalization on first letter
- Does not end with '.'

Body

- Gives details about the commit
- Why the change was made ex. bug, broken code, new feature
- How it is different from previous behavior

Rules

- Present tense
- Lines must be less that 80 characters long

Footer

\- Notes that someone should be aware of ex. how to test change, additional things needed now after the change (breaking changes)

Commit Frequency Rules in ORCA

Disclaimer: These rules are applicable to a single forked repository shared amongst multiple people making changes and updates.

General rules to follow:

- **Commit Often:** If you have something that works, don't wait to commit it, regular commits help capture slight changes and facilitate easier code reviews.
- **Commit Line Count:** For code changes (not unit tests) keep functions under **20 lines**. If too big, break up into separate functions to keep under this line count.
- **Ensure every commit is a single local change:** Each commit should address one specific task ex. new feature or fixed bug. Avoid bundling multiple, unrelated changes into one single commit.
- **Commit When Code is Functional and Tests Pass:** Whenever you have something that works (does not break anything for others) and a test that passes, commit your work. This will help maintain code stability.
- **Avoid committing half-done work:** Think about using 'git stash' and 'git stash pop' to store unfinished changes you want to commit in the future without committing unfinished work.

Adding New Functionality and Features

_Branch versus Commit_

**Branch**: When you are doing experimental work, and no one else in the work group will need to use your changes, make a separate branch (ex.: adding a separate, transmitting driver to ORCA).

**Commit**: When the edit you are making impacts the overall codebase, you should commit to main (ex: There is a small bug in the code causing a warning due to a new C++ update, and you fix this bug).

_When do you commit_

- Commit at least once a week when working in ORCA
- Confirm all unit tests (including new ones) can run prior to pushing

_Commit size expectations_

- Aim for < 20 lines
- Exceptions for >20 lines if function or change cannot be broken into smaller pieces

_Notes on reviews_

- Feedback
- Submission
  - Need test justification (photo confirmation, unit test confirmation)
- Code check:
  - Reviewers - Have 3 commits reviewed, then you can become a reviewer

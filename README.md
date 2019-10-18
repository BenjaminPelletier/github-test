# github-test
This repository experimentally demonstrates what happens when various GitHub pull request operations are performed in various circumstances.

## Squash and merge branch based off of ancestor
Situation:
```
A - B - C master
 \- D - E feature
```
There is a pull request for feature into master and D and E do not conflict with B or C.  When "Squash and merge" on GitHub's PR UI is used, the result is:
```
A - B - C - DE
```

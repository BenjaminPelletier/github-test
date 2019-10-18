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

## Conflicting PR based off of ancestor
Situation:
```
A - B master
 \- C feature
```
There is a pull request for feature into master, but C conflicts with B.  The GitHub PR UI grays out all merge options and indicates that this branch has conflicts that must be resolved.

## Squash and merge branch merge-sync'd with master
Situation: A contributor created a feature while master simultaneously advanced by a commit.  The contributor merged master into his feature in preparation for merging his feature PR into master.
```
A - B -\ master
 \- C - D feature
```
There is a pull request for feature into master and C and D do not conflict with B.  When "Squash and merge" on GitHub's PR UI is used, the result is:
```
A - B - CD'
```

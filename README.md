# github-test
This repository experimentally demonstrates what happens when various GitHub pull request operations are performed in various circumstances.

## [1] Squash and merge branch based off of ancestor
Situation:
```
A - B - C master
 \- D - E feature
```
There is a pull request for feature into master and D and E do not conflict with B or C.  When "Squash and merge" on GitHub's PR UI is used, the result is:
```
A - B - C - DE
```

## [2] Squash and merge branch merge-sync'd with master
Situation: A contributor created a feature while master simultaneously advanced by a commit.  The contributor merged master into his feature in preparation for merging his feature PR into master.
```
A - B -\ master
 \- C - D feature
```
There is a pull request for feature into master and C and D do not conflict with B.  When "Squash and merge" on GitHub's PR UI is used, the result is:
```
A - B - CD'
```

## [3] Conflicting PR based off of ancestor
Situation:
```
A - B master
 \- C feature
```
There is a pull request for feature into master, but C conflicts with B.  The GitHub PR UI grays out all merge options and indicates that this branch has conflicts that must be resolved.

## [4] Squash and merge mergeable PR based off of ancestor
Situation:
```
A - B master
 \- C feature
```
There is a pull request for feature into master.  B and C both make line additions to the same file, but the additions are in different places.  When "Squash and merge" on GitHub's PR UI is used, the result is:
```
A - B - C' 
```

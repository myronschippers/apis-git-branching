# Git Branching

```
⍟ master
|
|\
| o develop
| |
| |\
| | o feature-[BRANCH NAME]
| | |
| | ⍟ commit "COMMIT MESSAGE" (still on feature-[BRANCH NAME])
| | |
| | ⍟ commit "COMMIT MESSAGE" (still on feature-[BRANCH NAME])
```

- git checkout -b [BRANCH NAME]
- git checkout [BRANCH NAME]
- git branch


## Common Branches

### master

The **master** branch generally contains fully tested code that can be deployed. This is generally used as the starting point for individual projects. The **master** branch is what you have been working with to date, it's created by default.

### feature_NAME

When working on a task, you will want to create a branch for the feature that you are working on. The feature will be created using the branch you're currently on as a starting point. Let's assume we're on the master branch and creating a feature of **feature-login-html**.

**Create the feature-login-html branch**

```
git branch feature-login-html
```


```
⍟ master
|
|\
| o feature-login-html
```

**Switch to the feature-login-html branch**

```
git checkout feature-login-html
```

```
o master
|
|\
| ⍟ feature-login-html
```

**Make some changes and commit them**

Update the code in your files.

```
git add .
git commit -m "COMMIT MESSAGE"
git push origin feature-login-html
```

```
o master
|
|\
| o feature-login-html
| |
| ⍟ commit "COMMIT MESSAGE" (still on feature-login-html)
```

> At this point you can continue making commits.

**Merge your changes back into master (happy path)**

Go back to master

```
git checkout master
```

```
⍟ master
|
|\
| o feature-login-html
| |
| o commit "COMMIT MESSAGE" (still on feature-login-html)
```

Merge from feature-login-html into master

```
git merge --no-ff feature-login-html
```

```
o master
|
|\
| o feature-login-html
| |
| o commit "COMMIT MESSAGE" (still on feature-login-html)
|/
⍟ <- We are now here
```
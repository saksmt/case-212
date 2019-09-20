# How to sign

You can sign this letter by creating a file with a random name (an easy way to create a unique filename is to use *[GUID generator](https://www.guidgenerator.com/online-guid-generator.aspx)*) in the `signed` folder. Put the following lines in the file (each line represents a single person):
```
Name Surname | Position, company
```

## Linux / MacOS / Cygwin (git bash)

```bash
# Here YOUR_FORK - your fork of this repository
git clone ${YOUR_FORK}
cd case-212
# YOUR_GITHUB_USERNAME - username on github, such naming of branch is optional,
# you can name your branch however you want, but don't forget to change git push command as well!
git checkout -b signature/${YOUR_GITHUB_USERNAME}
cd signed
# YOUR_SURNAME - surname, YOUR_NAME - first name, POSITION - position at your company, COMPANY - your company
echo "${YOUR_NAME} ${YOUR_SURNAME} | ${POSITION}, ${COMPANY}" > $(uuidgen)
git commit -a -m 'Signature from ${YOUR_GITHUB_USERNAME}'
git push origin signature/${YOUR_GITHUB_USERNAME}
# time to create pull-request!
```


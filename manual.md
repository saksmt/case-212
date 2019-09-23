# Как подписаться

Вы можете это сделать, создав [в репозитории](https://github.com/developers-against-repressions/case-212) файл со случайным именем (простой способ создать уникальное имя файла — использовать *[генератор GUID](https://www.guidgenerator.com/online-guid-generator.aspx)*) в папку `signed`. В этом файле напишите строки
следующего формата (каждая строка — отдельный человек):
```
Фамилия Имя | Должность, компания
```

## Linux / MacOS / Cygwin / WSL (Windows Subsystem for Linux)

```bash
# Здесь YOUR_FORK - ваш форк этого репозитория
git clone ${YOUR_FORK}
cd case-212
# YOUR_GITHUB_USERNAME - ваше имя пользователя в github, такое именование ветки опционально,
# вы можете выбрать удобный вам способ именования, но не забудьте поменять имя и на git push!
git checkout -b signature/${YOUR_GITHUB_USERNAME}
cd signed
# YOUR_SURNAME - фамилия, YOUR_NAME - имя, POSITION - должность, COMPANY - компания
echo "${YOUR_SURNAME} ${YOUR_NAME} | ${POSITION}, ${COMPANY}" > $(uuidgen)
git commit -a -m 'Signature from ${YOUR_GITHUB_USERNAME}'
git push origin signature/${YOUR_GITHUB_USERNAME}
# идём создавать pull-request
```


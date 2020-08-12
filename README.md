# GitHooks

## Установка:
Скопировать файл "prepare-commit-msg" в папку ./git/hooks Вашего репозитория.
Для GitKraken необходима команда chmod +x prepare-commit-msg в папке с хуками (.git/hooks)
 
 
## Проверено в следующих GUI-клиентах:
    - Sublime merge
    - Fork
    - Tower
    - SourceTree
    - GitKraken 
    
| ----- | Название ветки корректно | Название ветки Некорректно | Название ветки является служебным|
| ---| --- | --- | --- |
| Текст в сообщении содержит issue, совпадающий с issue в имени ветки | Терминал: В этом случае происходит коммит и текст не меняется. GUI-клиент: В этом случае происходит коммит и текст не меняется.   |   -  |  -  |
| Текст в сообщении содержит issue, не совпадающий с issue в имени ветки |  Терминал: В этом случае спрашиваем добавить или нет issue из названия ветки. В зависимости от ответа либо добавляем issue из названия ветки в текст сообщения в формате "issueInMessage_issueInBranch: text" (ответ "Y"), либо оставляем текст сообщения неизменным (ответ "N").<br>
GUI-клиент: В этом случае происходит коммит и текст не меняется.  |  Терминал: В этом случае выводим ERROR с предупреждающим текстом и спрашиваем продолжить или нет. В зависимости от ответа коммит происходит (ответ "Y"), либо отменяется (ответ "N").<br>
GUI-клиент: В этом случае происходит коммит с текстом в формате "[WITHOUT ISSUE]: text".   |  Терминал: В этом случае выводим WARNING с предупреждающим текстом и спрашиваем продолжить или нет. В зависимости от ответа, либо коммит происходит с текстом в формате "[WITHOUT ISSUE]: text" (ответ "Y"), либо коммит не происходит (ответ "N").<br>
GUI-клиент:  В этом случае происходит коммит с текстом в формате "[WITHOUT ISSUE]: text".  |
| Текст в сообщении не содержит issue |  Терминал: В этом случае спрашиваем у пользователя добавить issue в текст сообщения или нет. В зависимости от ответа добавляем issue в текст сообщения в формате "issue: text" (ответ "Y") или коммит не происходит (ответ "N").<br>
GUI-клиент: В этом случае к тексту сообщения добавляется issue из названия ветки в формате "issueInBranch: text"  |  Терминал: В этом случае выводим ERROR с предупреждающим текстом и спрашиваем продолжить или нет. В зависимости от ответа коммит происходит (ответ "Y"), либо отменяется (ответ "N").<br>
GUI-клиент: В этом случае происходит коммит с текстом в формате "[WITHOUT ISSUE]: text".   |  Терминал: В этом случае выводим WARNING с предупреждающим текстом и спрашиваем продолжить или нет. В зависимости от ответа, либо коммит происходит с текстом в формате "[WITHOUT ISSUE]: text" (ответ "Y"), либо коммит не происходит (ответ "N").<br>
GUI-клиент:  В этом случае происходит коммит с текстом в формате "[WITHOUT ISSUE]: text".  |


    
## Как работает:
### Возможны всего 4 сценария:
1) Ветка называться [feature|fix|hotfix]/[abc-123]_... и в сообщении комментария та же issue из Jira (В формате ABCD-1234), что и в названии ветки. 
Терминал: В этом случае происходит коммит и текст не меняется.
GUI-клиент: В этом случае происходит коммит и текст не меняется.
![Hook Image 1](Images/hook_1.png)
2) В сообщении к коммиту нет issue, а в названии ветки issue есть.
Терминал: В этом случае спрашиваем у пользователя добавить issue в текст сообщения или нет. В зависимости от ответа добавляем issue в текст сообщения в формате "issue: text" (ответ "Y") или коммит не происходит (ответ "N"). 
GUI-клиент: В этом случае к тексту сообщения добавляется issue из названия ветки в формате "issueInBranch: text"
![Hook Image 2](Images/hook_2.png)
3) В сообщении к коммиту (issueInMessage) и в названии ветки (issueInBranch) есть issue, но они не совпадают.
Терминал: В этом случае спрашиваем добавить или нет issue из названия ветки. В зависимости от ответа либо добавляем issue из названия ветки в текст сообщения в формате "issueInMessage_issueInBranch: text" (ответ "Y"), либо оставляем текст сообщения неизменным (ответ "N"). 
GUI-клиент: В этом случае происходит коммит и текст не меняется.
![Hook Image 3](Images/hook_3.png)
4) Текущая ветка либо master либо develop:
Терминал: В этом случае выводим WARNING с предупреждающим текстом и спрашиваем продолжить или нет. В зависимости от ответа, либо коммит происходит с текстом в формате "[WITHOUT ISSUE]: text" (ответ "Y"), либо коммит не происходит (ответ "N").
GUI-клиент:  В этом случае происходит коммит с текстом в формате "[WITHOUT ISSUE]: text".
![Hook Image 4](Images/hook_4.png)
5) Название текущей ветки некорректное:
Терминал: В этом случае выводим ERROR с предупреждающим текстом и спрашиваем продолжить или нет. В зависимости от ответа коммит происходит (ответ "Y"), либо отменяется (ответ "N").
GUI-клиент: В этом случае происходит коммит с текстом в формате "[WITHOUT ISSUE]: text".
![Hook Image 5](Images/hook_5.png)


## Дополнительная фича:
- Если в тексте сообщения указана issue строчными буквами, то хук автоматически меняет их на заглавные.

    

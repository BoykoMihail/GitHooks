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
    
## Как работает:
<table>
       <thead>
           <tr>
               <th>----</th>
               <th>Название ветки корректно</th>
               <th>Название ветки некорректно</th>
               <th>Название ветки является служебным|</th>
           </tr>
       </thead>
       <tbody>
           <tr>
               <td rowspan=2>Текст в сообщении содержит issue, совпадающий с issue в имени ветки</td>
               <td>Терминал: В этом случае происходит коммит и текст не меняется. </td>
               <td rowspan=2>-</td>
               <td rowspan=2>-</td>
           </tr>
           <tr>
               <td>GUI-клиент: В этом случае происходит коммит и текст не меняется.</td>
           </tr>
            <tr>
               <td rowspan=2>Текст в сообщении содержит issue, не совпадающий с issue в имени ветки</td>
               <td>Терминал: В этом случае спрашиваем добавить или нет issue из названия ветки. В зависимости от ответа либо добавляем issue из названия ветки в текст сообщения в формате "issueInMessage_issueInBranch: text" (ответ "Y"), либо оставляем текст сообщения неизменным (ответ "N").</td>
               <td>Терминал: В этом случае выводим ERROR с предупреждающим текстом и спрашиваем продолжить или нет. В зависимости от ответа коммит происходит (ответ "Y"), либо отменяется (ответ "N").</td>
               <td>Терминал: В этом случае выводим WARNING с предупреждающим текстом и спрашиваем продолжить или нет. В зависимости от ответа, либо коммит происходит с текстом в формате "[WITHOUT ISSUE]: text" (ответ "Y"), либо коммит не происходит (ответ "N").</td>
           </tr>
           <tr>
               <td>GUI-клиент: В этом случае происходит коммит и текст не меняется.</td>
               <td>GUI-клиент: В этом случае происходит коммит с текстом в формате "[WITHOUT ISSUE]: text".</td>
               <td>GUI-клиент: В этом случае происходит коммит с текстом в формате "[WITHOUT ISSUE]: text".</td>
           </tr>
           <tr>
               <td rowspan=2>Текст в сообщении не содержит issue.</td>
               <td>Терминал: В этом случае спрашиваем у пользователя добавить issue в текст сообщения или нет. В зависимости от ответа добавляем issue в текст сообщения в формате "issue: text" (ответ "Y") или коммит не происходит (ответ "N").</td>
               <td>Терминал: В этом случае выводим ERROR с предупреждающим текстом и спрашиваем продолжить или нет. В зависимости от ответа коммит происходит (ответ "Y"), либо отменяется (ответ "N").</td>
               <td>Терминал: В этом случае выводим WARNING с предупреждающим текстом и спрашиваем продолжить или нет. В зависимости от ответа, либо коммит происходит с текстом в формате "[WITHOUT ISSUE]: text" (ответ "Y"), либо коммит не происходит (ответ "N").</td>
           </tr>
           <tr>
               <td>GUI-клиент: В этом случае к тексту сообщения добавляется issue из названия ветки в формате "issueInBranch: text".</td>
               <td>GUI-клиент: В этом случае происходит коммит с текстом в формате "[WITHOUT ISSUE]: text".</td>
               <td>GUI-клиент: В этом случае происходит коммит с текстом в формате "[WITHOUT ISSUE]: text".</td>
           </tr>
       </tbody>
</table>
    
## Изображения работы:
<img src="Images/hook_1.png" alt="рис. 1" width="250" height="250">
<img src="Images/hook_2.png" alt="рис. 1" width="250" height="250">
<img src="Images/hook_3.png" alt="рис. 1" width="250" height="250">
<img src="Images/hook_4.png" alt="рис. 1" width="250" height="250">
<img src="Images/hook_5.png" alt="рис. 1" width="250" height="250">



## Дополнительная фича:
- Если в тексте сообщения указана issue строчными буквами, то хук автоматически меняет их на заглавные.

    

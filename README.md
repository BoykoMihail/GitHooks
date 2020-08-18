# GitHooks

## Использование:
Скопировать файл "prepare-commit-msg" в папку ./git/hooks Вашего репозитория.
Необходима команда chmod +x prepare-commit-msg в папке с хуками (.git/hooks)
 
## Проверено в следующих GUI-клиентах:
    - Sublime merge
    - Fork
    - Tower
    - SourceTree
    - GitKraken 
    
## Как работает:
<figure style="display:inline-block; border: 1px dotted gray;">
    <p align="center">
        <img width="672" height="378" src="Images/git_hook.png">
    </p>
</figure>
    
## Изображения работы:

| | |
|:-------------------------:|:-------------------------:|
|  <figure style="display:inline-block; border: 1px dotted gray;"> <img src="Images/hook_1.png" width="400" height="300"> <figcaption style="text-align:center">рис. 1</figcaption> </figure> |  <figure style="display:inline-block; border: 1px dotted gray;"><img src="Images/hook_2.png" width="400" height="300"><figcaption style="text-align:center">рис. 2</figcaption> </figure> 
| <figure style="display:inline-block; border: 1px dotted gray;"> <img src="Images/hook_3.png" width="400" height="300"> <figcaption style="text-align:center">рис. 3</figcaption> </figure> | <figure style="display:inline-block; border: 1px dotted gray;"> <img src="Images/hook_4.png" width="400" height="300"> <figcaption style="text-align:center">рис. 4</figcaption> </figure> 
| <figure style="display:inline-block; border: 1px dotted gray;"> <img src="Images/hook_5.png" width="400" height="300"> <figcaption style="text-align:center">рис. 5</figcaption> </figure> |  |
    

## Дополнительная фича:
- Если в тексте сообщения указана issue строчными буквами, то хук автоматически меняет их на заглавные.

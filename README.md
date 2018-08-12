# Legal Open Source
Это публичный репозиторий документов для сайта LegalOpenSource.ru.  
  
## Разметка документов  
В репозитории хранятся шаблоны документов, которые используются на сайте для формирования итоговых документов с использованием данных, предоставленных пользователем в рамках ответов на вопросы в веб-форме.  
  
Для обозначения динамических элементов шаблонов, к примеру, наименований сторон, используется специальная разметка.   
  
Любое использование динамических элементов (переменных или списков) возможно только при отделении от остального текста значками backtick:
```
`{SellerName}` обязуется принять оплату товара.
```
  
### Используемые типы динамических элементов
#### Переменные
`<Вопрос>` - Таким образом обозначаются вопросы, которые автоматически подставляются в веб-форму в отношении каждой новой переменной. Вопрос необходимо указывать при первом использовании переменной. Вопросы могут идти только непосредственно перед переменными в одном блоке бэктиков. 

`{Переменная}` - Таким образом обозначаются наименования переменных. При повторном использовании переменной достаточно повторно написать в тексет шаблона `{Переменная}`. **Совет**: для того, чтобы не плодить сущности, желательно пользоваться уже обозначенными ранее переменные. 
#### Вопросы с опциями
`<Вопрос>^Вариант1|Вариант2|Вариант3^` - При первом установлении значения переменной (к примеру, является ли сторона юридическим лицом, ИП или не зарегистрировано как ИП) необходимо задать вопрос и обозначить варианты ответа. Вопросы могут идти только непосредственно перед переменными в одном блоке бэктиков.
  
`{Options}^Выход1|Выход2|Выход3^` - После вопроса необходимо обозначить переменную, которая запоминает номер варианта ответа (в случае выше - 1, 2 или 3). После переменной необходимо указать, что писать в зависимости от значения переменной. Если вопрос влияет на текст и далее по тексту документа, то достаточно вызвать переменную и прописать в ней варианты выводов, соответствующих вариантам ответов к вопросу, который был задан при первом вызове переменной.
### Пример:  
```
1.1. Настоящая Политика конфиденциальности ("**Политка**") регулирует порядок обработки персональных данных пользователей веб-сайта `<Укажите наименование сайта>{WebSiteName}` ("**Сайт**"), расположенного по адресу `<Укажите URL сайта>{WebSiteURL}`.  
1.2. Используя Сайт, Вы соглашаетесь с условиями настоящей Политики, а также даёте своё согласие на обработку персональных данных, описанную в настоящей Политике.  
1.3. Настоящая Политика относится исключительно к обработке персональных данных, связанной с сайтом `{WebSiteName}`.  
1.4. Обработка осуществляется `<Используется ли автоматизация при обработке?>^Да|Нет^{AutomatProc}^с использованием|без использования^` автоматизации.  
1.5. При обработке соблюдаются все требования, предусмотренные подзаконными актами в отношении `{AutomatProc}^автоматизированной|неавтоматизированной^` обработки персональных данных.
```

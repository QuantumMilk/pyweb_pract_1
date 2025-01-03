
# Введение

**Заголовок презентации "LangChain. Простая разработка приложения на базе LLM"**

Сейчас популярны большие языковые модели, которые часто используются в умных чат-ботах, интеллектуальных помощниках и современных системах обработки данных. Типичный GigaChat, ChatGPT, LLama и т.д. Однако, если вы пытались работать с этими моделями напрямую, интегрировать их в свое приложение или даже  развернуть свою собственную модель - могли столкнуться с рядом проблем.

Чтобы упростить подход к разработке приложений на базе LLM, можно обратиться к LangChain.

LangChain — это мощный инструмент на Python для работы с языковыми моделями, который значительно упрощает процесс создания приложений на базе языковых моделей. Основная задача LangChain — предоставить разработчикам набор удобных абстракций и компонентов для эффективного взаимодействия с языковыми моделями и интеграции их в различные рабочие процессы.


# Почему LangChain?
**Слайд: Проблемы работы с LLM без LangChain**
1. **Сложность управления последовательностями действий**: 
	Трудно создавать сложные цепочки запросов и обработки данных, особенно если задачи зависят друг от друга
2. **Ограниченные возможности подключения данных**:
	Из-за отсутсвия прямого доступа к базам данных, файлам, API или другим источникам, приходится с нуля разрабатывать код для интеграции модели к системе.
3. **Отсутствие памяти и контекста** 
	Не у всех моделей есть функция автоматического сохранение контекста диалога, а если есть то от длительного диалока, контекст размывается, что снижает их эффективность в многократных взаимодействиях.
4. **Трудности в использовании дополнительных инструментов**. 
	 Интеграция LLM с внешними инструментами, что требует как кастомизацию модели, так и разработки дополнительного кода.

**Слайд: Какие дает премуещства LangChain**
LangChain решает ряд проблем своей простотой разработки благодаря модульной структуре фреймворка, поддержкой различных моделей и возможностью создать сложной логики с готовыми шаблонами. 

Какие премущества есть?
* простота разработки
* поддержка различных моделей
* возможность создания сложных логик

# Основные компоненты LongChain

**Слайд: Архитекутра LangChain**

Давайте рассмотрим более подробно архитектуру LangChain. Она использует модульную архитектуру, которая позволяет гибко комбинировать и расширять компоненты для создания приложения.
Основные элементы это:
### 1. **Chains (цепочки):**

- Отвечают за обработку последовательности действий.
- Например, сначала модель отвечает на вопрос, затем обращается к внешнему источнику данных, а после этого обрабатывает полученные данные.

### 2. **Agents (агенты):**

- Используют языковые модели для принятия решений о том, какие инструменты или действия выполнить.
- Например, агент может выбрать, обращаться ли к API, читать документ или задавать уточняющий вопрос.

### 3. **Tools (инструменты):**

- Подключают внешние ресурсы, такие как базы данных, API, файлы или другие модули.
- Позволяют модели взаимодействовать с реальными данными или выполнять действия, выходящие за пределы текстовой обработки.

### 4. **Memory (память):**

- Добавляет сохранение контекста между запросами.
- Например, в диалогах память позволяет модели помнить предыдущие вопросы и ответы, делая взаимодействие более естественным.

### 5. **Document Loaders (загрузчики документов):**

- Инструменты для обработки текстовых данных из различных источников (PDF, Word, веб-страницы и др.).
- Эти данные затем могут использоваться для создания индексов или поиска.

### 6. **Indexes (индексы):**

- Структуры для организации и быстрого поиска по большим массивам данных.
- Используются, чтобы находить информацию в документах или базах данных.

### 7. **Callbacks (обратные вызовы):**

- Позволяют отслеживать выполнение цепочек и агентов в режиме реального времени.
- Это полезно для отладки, мониторинга или улучшения производительности.

### 8. **Connectors (коннекторы):**

- Модули для интеграции с различными платформами (например, облачные сервисы, базы данных).

# Кейсы использования

LangChain используется в рядах крупных компаниях, к примеру в 
* Cohere AI (ко-хир эй-ай) для автоматизации обслуживания клиентов. Они создают интеллектуального чат-бота для автоматического ответа на запросы клиентов. 
Используя LangChain, Cohere построила цепочку, которая комбинирует:
- Извлечение ключевой информации из запросов клиентов.
- Генерацию ответов с использованием модели GPT-4.
- Интеграцию с базой знаний компании через векторные хранилища

 **Компания:** Databricks умные поисковые системы
- **Кейс:** Создание системы поиска в документации компании. LangChain используется для:
    - Индексации документов с векторными хранилищами.
    - Построения контекстных запросов на основе ввода пользователя.
    - Генерации ответов с использованием LLM на основе релевантных документов.
А также в анализе и генерации контента, во всеми известной компании **Notion**. Автоматизация генерации заметок и резюме. LangChain используется для:
- Создания персонализированных шаблонов заметок.
- Автоматического извлечения ключевых идей из текста.
- Генерации структурированных резюме для пользователей.

Дальше давайте рассмотрим практическое применение LangChain 

Дока LangChain: [https://python.langchain.com/docs/introduction/](https://salutejazz.ru/#) 
Дока по GigaChat + LangChain: [https://github.com/ai-forever/gigachain](https://salutejazz.ru/#) 
немного по этой теме от Sber University: [https://courses.sberuniversity.ru/llm-gigachat/0](https://salutejazz.ru/#)
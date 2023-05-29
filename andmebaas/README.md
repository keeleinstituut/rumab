# Andmebaasi tabelite kirjeldus moodulite kaupa

1. [ Sõnade muutetüübid ](#inflections)
2. [ Muttetüüpide mallid ](#inflection_templates)
3. [ Kuznetsovi mallid ](#kuznetsov_templates)
4. [ Zaliznyak sõnastik ](#gramdict)
5. [ Hageni sõnastik ](#hagen_lemmas)
6. [ Ekilex sõnad  ](#ekilex_words)
7. [ Muudatustelogi ](#user_history)

<a name="inflections"></a>
## Sõnade muutetüübid

![rumorf_inflections.png](./img/rumorf_inflections.png)

<a name="inflection_templates"></a>
## Muttetüüpide mallid

![rumorf_inflection_templates.png](./img/rumorf_inflection_templates.png)

<a name="kuznetsov_templates"></a>
## Kuznetsovi mallid

![rumorf_kuznetsov_templates.png](./img/rumorf_kuznetsov_templates.png)

<a name="gramdict"></a>
## Zaliznyak sõnastik

![rumorf_gramdict.png](./img/rumorf_gramdict.png)

<a name="hagen_lemmas"></a>
## Hageni sõnastik

![rumorf_hagen_lemmas.png](./img/rumorf_hagen_lemmas.png)

<a name="ekilex_words"></a>
## Ekilex sõnad 

![rumorf_ekilex_words.png](./img/rumorf_ekilex_words.png)

<a name="user_history"></a>
## Muudatuste logi

![rumorf_user_history.png](./img/rumorf_user_history.png)

**user_history**

| Column         | Data Type    | Nullable | Default           |                                                                                     |
|----------------|--------------|----------|-------------------|-------------------------------------------------------------------------------------|
| **id**         | int(11)      | No       | AUTO_INCREMENT    | rea id                                                                              |
| date_created   | datetime     | No       | CURRENT_TIMESTAMP | muudatuse aeg                                                                       |
| massaction_uid | varchar(36)  | Yes      | NULL              | massmuudatuste id (kui muudeti korraga mitu objekti)                                |
| username       | varchar(36)  | Yes      | NULL              | muutja                                                                              |
| object         | varchar(25)  | Yes      | NULL              | objekti tüüp (nt 'lemma', 'wordgamerow')                                            |
| object_uid     | varchar(100) | Yes      | NULL              | objekti uid                                                                         |
| action         | varchar(20)  | Yes      | NULL              | tegevus ['new', 'add', 'change', 'delete']                                          |
| field          | varchar(20)  | Yes      | NULL              | muudetud väli                                                                       |
| oldvalue       | mediumtext   | Yes      | NULL              | vana väärtus                                                                        |
| newvalue       | mediumtext   | Yes      | NULL              | uus väärtus                                                                         |
| revision       | int(11)      | Yes      | NULL              | pole kasutusel; TODO! eemaldada                                                     |
| reverted       | int(1)       | Yes      | NULL              | pole kasutusel; TODO! eemaldada                                                     |
| reverted_id    | varchar(36)  | Yes      | NULL              | kui muudatus on tagasikeeratud, siis tagasikeeramise muudatuse id                   |
| project        | varchar(10)  | Yes      | NULL              | pole kasutusel; TODO! eemaldada
| diff           | mediumtext   | Yes      | NULL              | muudatuste diff õpikukorpuste tektstide puhul                                       |

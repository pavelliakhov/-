# 
1. 
```
 id |  name  |      pwd       |      email       | gender
----+--------+----------------+------------------+--------
  1 | Vasya  | 21341234qwfsdf | mmm@mmail.com    | m
  2 | Alex   | 21341234       | mmm@gmail.com    | m
  3 | Alexey | qq21341234Q    | alexey@gmail.com | m
  4 | Helen  | MarryMeeee     | hell@gmail.com   | f
  5 | Jenny  | SmakeMyb       | eachup@gmail.com | f
  6 | Lora   | burn23         | tpicks@gmail.com | f
(6 rows)
```
2.
```
SELECT 'This is ' || name ||', '||
CASE gender 
          WHEN 'm' THEN 'he'
          WHEN 'f' THEN 'she'
END
||' has email '|| email AS info 
FROM module_table;

                     info
-----------------------------------------------
 This is Vasya, he has email mmm@mmail.com
 This is Alex, he has email mmm@gmail.com
 This is Alexey, he has email alexey@gmail.com
 This is Helen, she has email hell@gmail.com
 This is Jenny, she has email eachup@gmail.com
 This is Lora, she has email tpicks@gmail.com
(6 rows)
```
3.
```
SELECT
'We have ' || count(*) ||
CASE gender 
            WHEN 'm' THEN ' boys!'
            WHEN 'f' THEN ' girls!'
END
AS "Gender information:" 
FROM module_table 
GROUP BY gender;

 Gender information:
---------------------
 We have 3 boys!
 We have 3 girls!
(2 rows)
```
4.
```
SELECT name, count(*) AS words from vocabulary 
LEFT JOIN word ON (vocabulary.id = word.vocabulary_id) 
GROUP BY name;

  name   | words
---------+-------
 animals |    10
 school  |    10
 SF      |    10
 human   |    10
 nature  |    10
(5 rows)
```

Для решения задачи сгенерируем таблицу в виде строки: `"<table>...</table>"`, а затем присвоим в `innerHTML`.

Алгоритм:

1. Создать объект даты `d = new Date(year, month-1)`. Это первый день месяца `month` (с учетом того, что месяцы в JS начинаются от 0, а не от 1).
2. Ячейки первого ряда пустые от начала и до дня недели `d.getDay()`, с которого начинается месяц. Создадим их.
3. Увеличиваем день в `d` на единицу: `d.setDate(d.getDate()+1)`, и добавляем в календарь очередную ячейку, пока не достигли следующего месяца. При этом последний день недели означает вставку перевода строки <code>"&lt;/tr&gt;&lt;tr&gt;"</code>.
4. При необходимости, если календарь окончился не на воскресенье - добавить пустые `TD` в таблицу, чтобы было все ровно.



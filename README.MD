#База данных

Это моя собственная простейшая имплементация базы данных, реализованная в виде библиотеки.
Также, к проекту прилагаются уже готовые тесты, использующие framework Catch, который также включен в проект.


##Установка

Так как моя база данных поддерживает кроссплатформенность, то это значит,
что вы можете использовать данную библиотеку на любой системе. Просто клонируйте данный репозиторий
на свой локальный компьютер.

##Начало работы

Перед тем как начать использовать базу данных, вы должны инициализировать ее, установив необходимые
настройки и загрузив ранее записанные данные. Сделать все это можно, вызвав всего одну функцию
initialize_db(arg1, arg2), где arg1 - путь, arg2 - размер файла с данными
 Рассмотрим на примере **linux**:
 '''c++
 initialize_db("/home/user_name/CLionProjects/Database/data_files/", 20)
 '''
 В Windows же нужно использовать обратный слэш в имени пути:
  '''c++
  initialize_db("c:\\users\\user_name\\documents\\visual studio 2017\\projects\\database\\data_files\\", 20)
  '''

######**_Значение, выставленное для размера файлов с данными, по умолчанию 8388608 байт (8 МБ)_**

##Использование

Для удобства записи в библиотеке реализованы различные хелперы, делающие процесс хранения и загрузки данных удобным и простым.

---

**Список хелперов для хранения данных**
- store_helper(id, data)
Данная функция поддерживает хранение таких типов данных, как: int, double, string, vector <int>, vector <double>, vector <string>

---

**Список хелперов для загрузки данных**
- load_helper<int>(id)
- load_helper<double>(id)
- load_helper<string>(id)
- load_int_vector_helper(id)
- load_double_vector_helper(id)
- load_string_vector_helper(id)

**Важно!**
Если вы хотите хранить новые данные с id, который уже содержится в базе данных, перед этим требуется удалить все
записи о ранее записанном id с данными. Проделать это можно, вызывав функцию удаления

  '''c++
  delete_id(id)
  '''

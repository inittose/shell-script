# Изучение сценариев командной строки

Подготовил: **Полушвайко Константин Николаевич**

> [!NOTE]
> Все скрипты предствлены в оболочке GNU bash.

## Шебанг *(shebang)*
**Шебанг** *(или Магическая строка)* - это специальный комментарий `#!`, который указывает на то, какой интерпретатор использовать для выполнения скрипта, если при вызове скрипта не был явно указан интерпретатор.

### Пример 1
Файл `script.py` содержит:

###### `script.py`
```python
# Используем шебанг для интерпретатора python
#!/usr/bin/env python

a = 5
b = 7

print(a + b)
```

Запускаем скрипт `script.py` сначала без явного указания интерпретатора, затем с явным указанием python, и еще раз, но с явным указанием интерпретатора bash:

###### `terminal`
```bash
$ ./script.py 
12

$ python script.py 
12

$ bash script.py 
script.py: line 3: a: command not found
script.py: line 4: b: command not found
script.py: line 6: syntax error near unexpected token `a'
script.py: line 6: `print(a + b)'
```

Из примера видно, что шебанг используется для удобства запуска скриптов, а также указывает на нужный интерпретатор для скрипта.

# Разделы в разработке

## Констукция if-elif-else
```bash
if [ условие ]
then
  команды
elif [ другое условие ]
then
  другие команды
else
  команды по умолчанию
fi
```
> А можно и так:
>```bash
>if [ условие ]; then команды; elif [ другое условие ]; then другие команды; else команды по умолчанию fi 
>```

## Констукция case
```bash
case выражение in
  шаблон1)
    команды1
    ;;
  шаблон2)
    команды2
    ;;
  *)
    команды по умолчанию
    ;;
esac
```

## Операторы условного выражения

### Сравнение чисел:
- `-eq`: равно
- `-ne`: не равно
- `-lt`: меньше
- `-le`: меньше или равно
- `-gt`: больше
- `-ge`: больше или равно

### Сравнение строк:
- `=:` равно
- `!=`: не равно
- `-z`: строка пустая
- `-n`: строка не пустая

### Проверка файлов:
- `-e`: файл существует
- `-f`: файл существует и это регулярный файл
- `-d`: файл существует и это директория
- `-r`: файл существует и доступен для чтения
- `-w`: файл существует и доступен для записи
- `-x`: файл существует и доступен для выполнения
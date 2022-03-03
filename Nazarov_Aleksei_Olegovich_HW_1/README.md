# Postman HW_1

## Создать запросы в Postman

|       1       |       2       |
| ------------- |:-------------:|
| Protocol      | http          |
| IP            | 162.55.220.72 |
| Port          | 5005          |

===================================================

`EP_1`

```python
Method: GET
EndPoint: /get_method
request url params:
 name: str
 age: int
```

response:

```js
[
    “Str”,
    “Str”
]
```

+ В Postman нажимаем `Collection` --> `new` --> создаем коллекцию с именем --> `EP_1`
+ далее нажимаем на коллекцию `EP_1` --> `collection is empty` --> `add`
+ выбираем метод `GET` --> в строке URL добавляем `http://162.55.220.72:5005/get_method`
+ в области `Query Params` вводим:
     `1. KEY = name, VALUE = Aleksei`
     `2. KEY = age, VALUE = 28`
+ в строке URL наблюдаем следующее: `http://162.55.220.72:5005/get_method?name=aleksei&age=28`
+ нажимаем `Save` --> `Send` --> `Body` -->

```json
[
    "Aleksei",
    "28"
]
```

===================================================

`EP_2`

```python
Method: POST
EndPoint: /user_info_3
request form data:
 name: str
 age: int
 salary: int
```

response:

```python
{'name': name,
          'age': age,
          'salary': salary,
          'family': {'children': [['Alex', 24], ['Kate', 12]],
                     'u_salary_1_5_year': salary * 4}}
```

+ создаем коллекцию с именем `EP_2` --> `collection is empty` --> `add request`
+ выбираем метод `POST` --> `Body` --> `form-data` --> в строке URL добавляем `http://162.55.220.72:5005/user_info_3`
+ вводим:
   `1. KEY = name, VALUE = Aleksei`
   `2. KEY = age, VALUE = 28`
   `3. KEY = salary, VALUE = 1000`
+ нажимаем `Save` --> нажимаем `Send` --> `Body` -->

```json
{
    "age": "28",
    "family": {
        "children": [
            [
                "Alex",
                24
            ],
            [
                "Kate",
                12
            ]
        ],
        "u_salary_1_5_year": 4000
    },
    "name": "Aleksei",
    "salary": 1000
}
```

====================================================

`EP_3`

```python
Method: GET
EndPoint: /object_info_1
request url params:
 name: str
 age: int
 weight: int
```

response:

```python
{'name': name,
          'age': age,
          'daily_food': weight * 0.012,
          'daily_sleep': weight * 2.5}
```

+ создаем коллекцию с именем `EP_3` --> `collection is empty` --> `add request`
+ выбираем метод `GET` --> в строке URL добавляем `http://162.55.220.72:5005/object_info_1`
+ в области `Query Params` вводим:
     `1. KEY = name, VALUE = Aleksei`
     `2. KEY = age, VALUE = 28`
     `3. KEY = weight, VALUE = 70`
+ в строке URL наблюдаем следующее: `http://162.55.220.72:5005/object_info_1?name=Aleskei&age=28&weight=70`
+ нажимаем `Save` --> `Send` --> `Body` -->

```json
{
    "age": 28,
    "daily_food": 0.84,
    "daily_sleep": 175.0,
    "name": "Aleskei"
}
```

====================================================

`EP_4`

```python
Method: GET
EndPoint: /object_info_2
request url params:
 name: str
 age: int
 salary: int
```

response:

```python
{'start_qa_salary': salary,
          'qa_salary_after_6_months': salary * 2,
          'qa_salary_after_12_months': salary * 2.7,
          'qa_salary_after_1.5_year': salary * 3.3,
          'qa_salary_after_3.5_years': salary * 3.8,
          'person': {'u_name': [user_name, salary, age],
                     'u_age': age,
                     'u_salary_5_years': salary * 4.2}
          }
```

+ создаем коллекцию с именем `EP_4` --> `collection is empty` --> `add request`
+ выбираем метод `GET` --> в строке URL добавляем `http://162.55.220.72:5005/object_info_2`
+ в области `Query Params` вводим:
     `1. KEY = name, VALUE = Aleksei`
     `2. KEY = age, VALUE = 28`
     `3. KEY = salary, VALUE = 1000`
+ в строке URL наблюдаем следующее: `http://162.55.220.72:5005/object_info_2?name=Aleksei&age=28&salary=1000`
+ нажимаем `Save` --> `Send` --> `Body` -->

```json
{
    "person": {
        "u_age": 28,
        "u_name": [
            "Aleksei",
            1000,
            28
        ],
        "u_salary_5_years": 4200.0
    },
    "qa_salary_after_1.5_year": 3300.0,
    "qa_salary_after_12_months": 2700.0,
    "qa_salary_after_3.5_years": 3800.0,
    "qa_salary_after_6_months": 2000,
    "start_qa_salary": 1000
}
```

====================================================

`EP_5`

```python
Method: GET
EndPoint: /object_info_3
request url params:
 name: str
 age: int
 salary: int
```

response:

```python
{'name': name,
          'age': age,
          'salary': salary,
          'family': {'children': [['Alex', 24], ['Kate', 12]],
                     'pets': {'cat':{'name':'Sunny',
                                     'age': 3},
                              'dog':{'name':'Luky',
                                     'age': 4}},
                     'u_salary_1_5_year': salary * 4}
          }
```

+ создаем коллекцию с именем `EP_5` --> `collection is empty` --> `add request`
+ выбираем метод `GET` --> в строке URL добавляем `http://162.55.220.72:5005/object_info_3`
+ в области `Query Params` вводим:
     `1. KEY = name, VALUE = Aleksei`
     `2. KEY = age, VALUE = 28`
     `3. KEY = salary, VALUE = 1000`
+ в строке URL наблюдаем следующее: `http://162.55.220.72:5005/object_info_3?name=Aleksei&age=28&salary=1000`
+ нажимаем `Save` --> `Send` --> `Body` -->

```json
{
    "age": "28",
    "family": {
        "children": [
            [
                "Alex",
                24
            ],
            [
                "Kate",
                12
            ]
        ],
        "pets": {
            "cat": {
                "age": 3,
                "name": "Sunny"
            },
            "dog": {
                "age": 4,
                "name": "Luky"
            }
        },
        "u_salary_1_5_year": 4000
    },
    "name": "Aleksei",
    "salary": 1000
}
```

====================================================

`EP_6`

```python
Method: GET
EndPoint: /object_info_4
request url params:
 name: str
 age: int
 salary: int
```

response:

```python
{'name': name,
          'age': int(age),
          'salary': [salary, str(salary * 2), str(salary * 3)]}
```

+ создаем коллекцию с именем `EP_6` --> `collection is empty` --> `add request`
+ выбираем метод `GET` --> в строке URL добавляем `http://162.55.220.72:5005/object_info_4`
+ в области `Query Params` вводим:
     `1. KEY = name, VALUE = Aleksei`
     `2. KEY = age, VALUE = 28`
     `3. KEY = salary, VALUE = 1000`
+ в строке URL наблюдаем следующее: `http://162.55.220.72:5005/object_info_4?name=Aleksei&age=28&salary=1000`
+ нажимаем `Save` --> `Send` --> `Body` -->

```json
{
    "age": 28,
    "name": "Aleksei",
    "salary": [
        1000,
        "2000",
        "3000"
    ]
}
```

====================================================

`EP_7`

```python
Method: POST
EndPoint: /user_info_2
request form data:
 name: str
 age: int
 salary: int
```

response:

```python
{'start_qa_salary': salary,
          'qa_salary_after_6_months': salary * 2,
          'qa_salary_after_12_months': salary * 2.7,
          'qa_salary_after_1.5_year': salary * 3.3,
          'qa_salary_after_3.5_years': salary * 3.8,
          'person': {'u_name': [user_name, salary, age],
                     'u_age': age,
                     'u_salary_5_years': salary * 4.2}
          }
```

+ создаем коллекцию с именем `EP_7` --> `collection is empty` --> `add request`
+ выбираем метод `POST` --> `Body` --> `form-data` --> в строке URL добавляем `http://162.55.220.72:5005/user_info_2`
+ вводим:
   `1. KEY = name, VALUE = Aleksei`
   `2. KEY = age, VALUE = 28`
   `3. KEY = salary, VALUE = 1000`
+ нажимаем `Save` --> нажимаем `Send` --> `Body` -->

```json
{
    "person": {
        "u_age": 28,
        "u_name": [
            "Aleksei",
            1000,
            28
        ],
        "u_salary_5_years": 4200.0
    },
    "qa_salary_after_1.5_year": 3300.0,
    "qa_salary_after_12_months": 2700.0,
    "qa_salary_after_3.5_years": 3800.0,
    "qa_salary_after_6_months": 2000,
    "start_qa_salary": 1000
}
```

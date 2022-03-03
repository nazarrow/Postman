# Postman HW_2

`http://162.55.220.72:5005/first`

1. Отправить запрос.

2. Статус код 200

```js
pm.test("Статус код 200", function () {
    pm.response.to.have.status(200);
});
```

3. Проверить, что в body приходит правильный string.

```js
pm.test("Body matches string", function () {
    pm.expect(pm.response.text()).to.include("This is the first responce from server!");
});
```

<hr>

`http://162.55.220.72:5005/user_info_3`

1. Отправить запрос.

2. Статус код 200

```js
pm.test("Статус код 200", function () {
    pm.response.to.have.status(200);
});
```

3. Спарсить response body в json.

```js
let jsonData = pm.response.json();
```

4. Проверить, что name в ответе равно name s request (name вбить руками.)

```js
pm.test("name = Aleksei", function () {
    pm.expect(jsonData.name).to.eql("Aleksei");
});
```

5. Проверить, что age в ответе равно age s request (age вбить руками.)

```js
pm.test("age = 28", function () {
    pm.expect(jsonData.age).to.eql("28");
});
```

6. Проверить, что salary в ответе равно salary s request (salary вбить руками.)

```js
pm.test("salary = 1000", function () {
    pm.expect(jsonData.salary).to.eql(1000);
});
```

7. Спарсить request.

```js
let reqData = request.data;
```

8. Проверить, что name в ответе равно name s request (name забрать из request.)

```js
pm.test("Response = Request", function () {
    pm.expect(jsonData.name).to.eql(reqData.name);
});
```

9. Проверить, что age в ответе равно age s request (age забрать из request.)

```js
pm.test("Response age = Request age", function () {
    pm.expect(jsonData.age).to.eql(reqData.age);
});
```

10. Проверить, что salary в ответе равно salary s request (salary забрать из request.)

```js
pm.test("Response salary = Request salary", function () {
    pm.expect(jsonData.salary).to.eql(+reqData.salary);
});
```

11. Вывести в консоль параметр family из response.

```js
console.log(jsonData.family);
```

12. Проверить что u_salary_1_5_year в ответе равно salary*4 (salary забрать из request)

```js
pm.test("Response u_salary_1_5_year = salary*4", function () {
    pm.expect(jsonData.family.u_salary_1_5_year).to.eql(+reqData.salary*4);
});
```

<hr>

`http://162.55.220.72:5005/object_info_3`

1. Отправить запрос.

2. Статус код 200

```js
pm.test("Статус код 200", function () {
    pm.response.to.have.status(200);
});
```

3. Спарсить response body в json.

```js
let jsonData = pm.response.json();
```

4. Спарсить request.

```js
let reqData = pm.request.url.query.toObject();
```

5. Проверить, что name в ответе равно name s request (name забрать из request.)

```js
pm.test("Response name = Request name", function () {
    pm.expect(jsonData.name).to.eql(reqData.name);
});
```

6. Проверить, что age в ответе равно age s request (age забрать из request.)

```js
pm.test("Response age = Request age", function () {
    pm.expect(jsonData.age).to.eql(reqData.age);
});
```

7. Проверить, что salary в ответе равно salary s request (salary забрать из request.)

```js
pm.test("Response salary = Request salary", function () {
    pm.expect(jsonData.salary).to.eql(+reqData.salary);
});
```

8. Вывести в консоль параметр family из response.

```js
console.log(jsonData.family);
```

9. Проверить, что у параметра dog есть параметры name.

```js
pm.test("dog has name", function() {
    pm.expect(jsonData.family.pets.dog).to.have.property("name");
});
```

10. Проверить, что у параметра dog есть параметры age.

```js
pm.test("dog has age", function() {
    pm.expect(jsonData.family.pets.dog).to.have.property("age");
});
```

11. Проверить, что параметр name имеет значение Luky.

```js
pm.test("name has Luky", function() {
    pm.expect(jsonData.family.pets.dog.name).to.eql("Luky");
});
```

12. Проверить, что параметр age имеет значение 4.

```js
pm.test("age has 4", function() {
    pm.expect(jsonData.family.pets.dog.age).to.eql(+"4");
});
```

<hr>

`http://162.55.220.72:5005/object_info_4`

1. Отправить запрос.

2. Статус код 200

```js
pm.test("Статус код 200", function () {
    pm.response.to.have.status(200);
});
```

3. Спарсить response body в json.

```js
let jsonData = pm.response.json();
```

4. Спарсить request.

```js
let reqData = pm.request.url.query.toObject();
```

5. Проверить, что name в ответе равно name s request (name забрать из request.)

```js
pm.test("Response name = Request name", function () {
    pm.expect(jsonData.name).to.eql(reqData.name);
});
```

6. Проверить, что age в ответе равно age из request (age забрать из request.)

```js
pm.test("Response age = Request age", function () {
    pm.expect(jsonData.age).to.eql(+reqData.age);
});
```

7. Вывести в консоль параметр salary из request.

```js
console.log("Request salary", reqData.salary);
```

8. Вывести в консоль параметр salary из response.

```js
console.log("Reponse salary", jsonData.salary);
```

9. Вывести в консоль 0-й элемент параметра salary из response.

```js
console.log(jsonData.salary[0]);
```

10. Вывести в консоль 1-й элемент параметра salary параметр salary из response.

```js
console.log(jsonData.salary[1]);
```

11. Вывести в консоль 2-й элемент параметра salary параметр salary из response.

```js
console.log(jsonData.salary[2]);
```

12. Проверить, что 0-й элемент параметра salary равен salary из request (salary забрать из request.)

```js
pm.test("Response salary [0] = Request salary", function () {
    pm.expect(jsonData.salary[0]).to.eql(+reqData.salary);
});
```

13. Проверить, что 1-й элемент параметра salary равен salary*2 из request (salary забрать из request.)

```js
pm.test("Response salary [1] = Request salary*2", function () {
    pm.expect(jsonData.salary[1]).to.eql+(reqData.salary*2);
});
```

14. Проверить, что 2-й элемент параметра salary равен salary*3 из request (salary забрать из request.)

```js
pm.test("Response salary [2] = Request salary*2", function () {
    pm.expect(jsonData.salary[2]).to.eql+(reqData.salary*3);
});
```

15. Создать в окружении переменную name

16. Создать в окружении переменную age

17. Создать в окружении переменную salary

18. Передать в окружение переменную name

```js
pm.environment.set("name", jsonData.name);
```

19. Передать в окружение переменную age

```js
pm.environment.set("age", jsonData.age);
```

20. Передать в окружение переменную salary

```js
pm.environment.set("salary", jsonData.salary[0]);
```

21. Написать цикл который выведет в консоль по порядку элементы списка из параметра salary.

```js
for (let i of jsonData.salary) {
     console.log(i);
};
```

<hr>

`http://162.55.220.72:5005/user_info_2`

1. Вставить параметр salary из окружения в request

2. Вставить параметр age из окружения в age

3. Вставить параметр name из окружения в name

4. Отправить запрос.

5. Статус код 200

```js
pm.test("Статус код 200", function () {
    pm.response.to.have.status(200);
});
```

6. Спарсить response body в json.

```js
let jsonData = pm.response.json();
```

7. Спарсить request.

```js
let reqData = request.data;
```

8. Проверить, что json response имеет параметр start_qa_salary

```js
pm.test("json response has start_qa_salary", function () {
    pm.expect(jsonData).to.have.property("start_qa_salary");
});
```

9. Проверить, что json response имеет параметр qa_salary_after_6_months

```js
pm.test("json response has qa_salary_after_6_months", function () {
    pm.expect(jsonData).to.have.property("qa_salary_after_6_months");
});
```

10. Проверить, что json response имеет параметр qa_salary_after_12_months

```js
pm.test("json response has qa_salary_after_12_months", function () {
    pm.expect(jsonData).to.have.property("qa_salary_after_12_months");
});
```

11. Проверить, что json response имеет параметр qa_salary_after_1.5_year

```js
pm.test("json response has qa_salary_after_1.5_year", function () {
    pm.expect(jsonData).to.have.property("qa_salary_after_1.5_year");
});
```

12. Проверить, что json response имеет параметр qa_salary_after_3.5_years

```js
pm.test("json response has qa_salary_after_3.5_years", function () {
    pm.expect(jsonData).to.have.property("qa_salary_after_3.5_years");
});
```

13. Проверить, что json response имеет параметр person

```js
pm.test("json response has person", function () {
    pm.expect(jsonData).to.have.property("person");
});
```

14. Проверить, что параметр start_qa_salary равен salary из request (salary забрать из request.)

```js
pm.test("Response start_qa_salary = Request start_qa_salary", function () {
    pm.expect(jsonData.start_qa_salary).to.eql(+reqData.salary);
});
```

15. Проверить, что параметр qa_salary_after_6_months равен salary*2 из request (salary забрать из request.)

```js
pm.test("Response qa_salary_after_6_months = Request salary*2", function () {
    pm.expect(jsonData.qa_salary_after_6_months).to.eql(+reqData.salary*2);
});
```

16. Проверить, что параметр qa_salary_after_12_months равен salary*2.7 из request (salary забрать из request.)

```js
pm.test("Response qa_salary_after_12_months = Request salary*2.7", function () {
    pm.expect(jsonData.qa_salary_after_12_months).to.eql(+reqData.salary*2.7);
});
```

17. Проверить, что параметр qa_salary_after_1.5_year равен salary*3.3 из request (salary забрать из request.)

```js
pm.test("Response qa_salary_after_1.5_year = Request salary*3.3", function () {
    pm.expect(jsonData["qa_salary_after_1.5_year"]).to.eql(+reqData.salary*3.3);
});
```

18. Проверить, что параметр qa_salary_after_3.5_years равен salary*3.8 из request (salary забрать из request.)

```js
pm.test("Response qa_salary_after_3.5_years = Request salary*3.8", function () {
    pm.expect(jsonData["qa_salary_after_3.5_years"]).to.eql(+reqData.salary*3.8);
});
```

19. Проверить, что в параметре person, 1-й элемент из u_name равен salary из request (salary забрать из request.)

```js
pm.test("Response person [1] u_name = Request salary", function () {
    pm.expect(jsonData.person.u_name[1]).to.eql(+reqData.salary);
});
```

20. Проверить, что что параметр u_age равен age из request (age забрать из request.)

```js
pm.test("Response u_age = Request age", function () {
    pm.expect(jsonData.person.u_age).to.eql(+reqData.age);
});
```

21. Проверить, что параметр u_salary_5_years равен salary*4.2 из request (salary забрать из request.)

```js
pm.test("Response u_salary_5_years  = Request salary*4.2", function () {
    pm.expect(jsonData.person.u_salary_5_years).to.eql(+reqData.salary*4.2);
});
```

22. ***Написать цикл который выведет в консоль по порядку элементы списка из параметра person.

```js
for (let i = 0; i < jsonData.person.u_name.length; i++) {
  console.log("Вывод из списка, элемента с индексом " + i + ": " + jsonData.person.u_name[i]);
}
// либо 
/*
for (let i of jsonData.person.u_name){
    console.log(i)
}
*/
// либо 
/*
for(let KEY in jsonData.person) {
   if(typeof(jsonData.person[KEY]) == "object"){
       for(let i = 0; i < Object.keys(jsonData.person[KEY]).length; i++){
           console.log(jsonData.person[KEY][i]);
       }
   }
   else if(typeof(jsonData.person[KEY]) != "object") {
        console.log(jsonData.person[KEY]);
   }
}
*/
```

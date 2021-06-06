# python-flask-docker
Итоговый проект курса "Машинное обучение в бизнесе"

Стек:

ML: sklearn, pandas, numpy
API: flask
Данные: 

Задача: п параметрам определить потенциальное наличие сердечно-сосудистого заболевания у человека

Используемые признаки:

- 'age', 'height', 'weight', 'ap_hi', 'ap_lo'
- 'gender', 'cholesterol'
- 'gluc', 'smoke', 'alco', 'active'

Преобразования признаков: tfidf

model: logreg

### Клонируем репозиторий и создаем образ
```
$ git clone https://github.com/ishubenko/ML_business.git
$ cd project
$ docker build -t ishubenko/ml_business .
```

### Запускаем контейнер

Здесь Вам нужно создать каталог локально и сохранить туда предобученную модель (<your_local_path_to_pretrained_models> нужно заменить на полный путь к этому каталогу)
```
$ docker run -d -p 8180:8180 -p 8181:8181 -v <your_local_path_to_pretrained_models>:/app/app/models ishubenko/ml_business
```

### Переходим на localhost:8181

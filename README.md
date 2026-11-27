# Uzbekistan Demos

Python va JavaScript’da yozilgan, O‘zbekiston uchun moslashtirilgan ikkita demo. Interfeys o‘zbek va rus tillarida ishlaydi.

## Demolar / Возможности

- **Valyuta kurslari / Курсы валют.** Загрузка данных из JSON API Центрального банка Узбекистана. Курс приводится к одной единице валюты и отображается в сумах с датой вступления в силу.
- **Bilimlar bazasi / База знаний.** Поиск по встроенному справочнику условного кассового приложения на узбекском и русском. Ответы сопровождаются идентификаторами записей.

## Ishga tushirish / Запуск

```bash
python -m pip install -r requirements.txt
python -m uvicorn server:app --host 127.0.0.1 --port 8000
```

Откройте http://127.0.0.1:8000. Документация API доступна по адресу http://127.0.0.1:8000/docs.

| Метод | Назначение |
| --- | --- |
| `GET /api/rates` | Курсы USD, EUR, RUB и KZT к UZS. Требуется доступ к cbu.uz. |
| `GET /api/knowledge?q=hisobot&lang=uz` | Лексический поиск по справочнику. Параметр `lang` принимает `uz` или `ru`. |

- `server.py` — приложение FastAPI, клиент ЦБ и поиск по справочнику.
- `index.html` — двуязычный интерфейс на JavaScript.
- `requirements.txt` — зависимости Python.

[Документация JSON API Центрального банка Республики Узбекистан](https://cbu.uz/en/arkhiv-kursov-valyut/veb-masteram/)

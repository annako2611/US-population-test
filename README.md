# Розробка інтерактивного дашборду на Python з використанням Streamlit


[![Open in Streamlit](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)](https://us-population-test.streamlit.app/)


- Crafting a Dashboard App in Python using Streamlit, https://www.youtube.com/watch?v=asFqpMDSPdM
- Building a dashboard in Python using Streamlit, https://blog.streamlit.io/crafting-a-dashboard-app-in-python-using-streamlit
- GitHub repo, https://github.com/dataprofessor/population-dashboard?ref=blog.streamlit.io
- Dasbboard app, https://population-dashboard.streamlit.app/?ref=blog.streamlit.io



## Частина 1: Вступ та основні концепції

### Вступ
В контексті науки про дані візуалізація є надзвичайно важливим інструментом. Як кажуть, "одна картинка варта тисячі слів". Хоча статичні графіки корисні, інтерактивні дашборди дозволяють користувачам взаємодіяти з даними, роблячи їх аналіз більш глибоким та інформативним.

### Технічний стек
1. Streamlit - фреймворк для створення веб-інтерфейсу
2. Pandas - інструмент для аналізу та обробки даних
3. Altair/Plotly - бібліотеки для візуалізації
4. NumPy, Scikit-Learn - для обробки та аналізу даних

## Частина 2: Структура дашборду

### Ключові метрики
1. Визначення основної мети дашборду
2. Вибір показників для вимірювання
3. Приклади для різних галузей:
   - Продажі: ефективність продажів, територіальний розподіл
   - Маркетинг: конверсія, CLV, CAC
   - Фінанси: прибутковість, маржинальність

### Розвідувальний аналіз даних (EDA)
1. Збір та підготовка даних
2. Аналіз наявних даних
3. Вибір методів візуалізації:
   - Хороплети для географічних даних
   - Теплові карти для часових рядів
   - Кільцеві діаграми для процентних співвідношень

## Частина 3: Практична реалізація

### Налаштування середовища
```python
import streamlit as st
import pandas as pd
import altair as alt
import plotly.express as px

st.set_page_config(
    page_title="Dashboard",
    layout="wide",
    initial_sidebar_state="expanded"
)
```

### Створення компонентів дашборду

#### 1. Бічна панель
```python
with st.sidebar:
    st.title('Dashboard')
    selected_year = st.selectbox('Виберіть рік', year_list)
    selected_color_theme = st.selectbox('Виберіть тему', color_theme_list)
```

#### 2. Візуалізації
- Теплова карта
- Хороплет
- Кільцева діаграма
- Метрики та показники

### Функції для обробки даних
```python
def format_number(num):
    if num > 1000000:
        return f'{round(num / 1000000, 1)} M'
    return f'{num // 1000} K'
```

## Частина 4: Розгортання та оптимізація

### Розгортання дашборду
1. Підготовка файлів
2. Налаштування серверу
3. Розгортання в хмарі

### Оптимізація продуктивності
1. Кешування даних
2. Оптимізація запитів
3. Ефективне оновлення компонентів

## Частина 5: Найкращі практики

### Рекомендації з розробки
1. Проводити ретельний EDA
2. Визначати ключові метрики
3. Вибирати оптимальні візуалізації
4. Групувати пов'язані метрики
5. Використовувати чіткі позначення

### Поширені помилки
1. Перевантаження інформацією
2. Неправильний вибір візуалізацій
3. Відсутність інтерактивності
4. Погана оптимізація

## Висновки
Streamlit є потужним інструментом для створення інтерактивних дашбордів, що дозволяє швидко та ефективно візуалізувати дані. Особливо цінною є можливість автоматичного оновлення при зміні даних, що робить його ідеальним для візуалізації даних у реальному часі.

### How to run it on your own machine

1. Install the requirements

   ```
   $ pip install -r requirements.txt
   ```

2. Run the app

   ```
   $ streamlit run streamlit_app.py
   ```

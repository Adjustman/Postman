# Postman

При запросе методом POST на EP_7 сервер не отрабатывает математику. 

  Expected result:
  {
    "person": {
        "u_age": 37,
        "u_name": [
            "Diman",
            500,
            37
        ],
        "u_salary_5_years": salary * 4.2
    },
    "qa_salary_after_1.5_year": salary * 3.3,
    "qa_salary_after_12_months": salary * 2.7,
    "qa_salary_after_3.5_years": salary * 3.8,
    "qa_salary_after_6_months": salary * 2,
    "start_qa_salary": 500
}

  Actual result:

  {
    "person": {
        "u_age": 37,
        "u_name": [
            "Diman",
            500,
            37
        ],
        "u_salary_5_years": 2100.0
    },
    "qa_salary_after_1.5_year": 1650.0,
    "qa_salary_after_12_months": 1350.0,
    "qa_salary_after_3.5_years": 1900.0,
    "qa_salary_after_6_months": 1000,
    "start_qa_salary": 500
}

    Comment: Первую часть ответа от сервера, там где он возвращает введённые нами значения ключей(name, age, salary), мы получили корректно. А во второй части ответа мы получаем прописанные константы, или т.н. "Затычки". Это значит на стороне сервера не отрабатывается формула "salary * X", где X - коэффициент "за уровень подготовки и профессионализм".
        

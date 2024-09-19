# I. Введение
## 1. Описание задачи
Прогнозирование склонности клиента к покупке продукта является важной задачей для многих компаний, помогая:

- оценить потребности клиента, сформировать профиль его продукта;
- улучшать качество рекомендаций, формировать пакетные предложения, формировать индивидуальные условия;
- правильно сформировать стратегию коммуникации с клиентом оценить доход, который клиент может принести компании в будущем, исходя из прибыльности продукции, в которой он заинтересован (Customer Life Value — CLTV).

Для решения подобных задач обычно используются различные данные о клиенте:

    - профиль клиента;
    - история предыдущих покупок и коммуникаций;
    - транзакционная деятельность;
    - геоинформация о местах постоянного или временного проживания;
    - и т. д.;
    
Особое значение имеют данные, характеризующие закономерности поведения клиента (цепочки событий), так как они помогают понять закономерности в действиях клиента, оценить динамику изменения его поведения. Совместное использование поведенческих данных из различных источников помогает более полно описать клиента с точки зрения прогнозирования его потребностей, что, в свою очередь, ставит задачу наиболее эффективного сочетания различных модальностей для повышения производительности и качества разрабатываемой модели.

## 2. Описание датасета
[Датасетом MBD](https://huggingface.co/datasets/ai-lab/MBD-mini) c историями транзакций клиентов.
Набор данных состоит из обезличенных исторических данных, которые содержат следующую информацию: транзакционная активность (транзакции), встраивания диалогов (диалоги), геоактивность (геострим) для некоторых клиентов Банка за 12 месяцев.
Нас будут интересовать следующие признаки:

```
|-- trx Desc: Transactional activity
    |-- client_id: str Desc: Client id
    |-- event_time: timestamp Desc: Transaction's date
    |-- amount: float Desc: Transaction's amount
    |-- fold: int
    |-- event_type: int Desc: Transaction's type
    |-- event_subtype: int Desc: Clarifying the transaction type
    |-- currency: int Desc: Currency
    |-- src_type11: int Desc: Feature 1 for sender
    |-- src_type12: int Desc: Clarifying feature 1 for sender
    |-- dst_type11: int Desc: Feature 1 for contractor
    |-- dst_type12: int Desc: Clarifying feature 1 for contractor 
    |-- src_type21: int Desc: Feature 2 for sender
    |-- src_type22: int Desc: Clarifying feature 2 for sender
    |-- src_type31: int Desc: Feature 3 for sender
    |-- src_type32: int Desc: Clarifying feature 3 for sender
```

```
|-- targets
    |-- mon: str  Desc: Reporting month
    |-- target_1: int Desc: Mark of product issuance in the first reporting month
    |-- target_2: int Desc: Mark of product issuance in the second reporting month
    |-- target_3: int Desc: Mark of product issuance in the third reporting month
    |-- target_4: int Desc: Mark of product issuance in the fourth reporting month
    |-- trans_count: int Desc: Number of transactions
    |-- diff_trans_date: int Desc: Time difference between transactions
    |-- client_id: str Desc: Client id
```

Это только те признаки, которые мы будем использовать. С полным списком параметров(гео-данные, эмбеднги диалогов) и их описанием Вы можете ознакомиться на странице [датасета](https://huggingface.co/datasets/ai-lab/MBD-mini).

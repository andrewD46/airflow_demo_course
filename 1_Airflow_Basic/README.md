<h1 align="center">Основные понятия</h1>


### Основные компоненты Airflow


<p align="center">
<img src="https://airflow.apache.org/docs/apache-airflow/stable/_images/arch-diag-basic.png" width="80%"><br>
<small>Схема основных компонентов Airflow</small></p>


- **Webserver** – отвечает за веб-интерфейс, который является основным инструментом работы с Airflow и позволяет пользователю визуализировать свои DAG-и (Directed Acyclic Graph) и контролировать их выполнение. Кроме того, Webserver предоставляет экспериментальный REST API, которые позволяют управлять Airflow не через веб-интерфейс, а программно.


<p align="center">
<img src="https://docs.qubole.com/en/latest/_images/AirflowWebServer.png" width="80%"><br>
<small>Веб-интерфейс Airflow</small></p>

<p align="center">
<img src="img.png" width="80%"><br></p>

- **Scheduler** — главный компонент в Airflow, контролирующий расписание выполнения, обновлением DAGs и запуском Tasks. оркестрирует выполнение DAG-ов, обеспечивая их запуск в нужное время и в нужном порядке.

> И **Webserver**, и **Scheduler** – это долгоживущие сервисы, то есть они поднимаются при запуске Airflow и работают постоянно.


- **Workers** – представляют собой эфемерные pod-ы. Их создает Kubernetes Executor, и они служат только для выполнения одной-единственной DAG-задачи. После того, как задача выполнена, ее Worker-pod уничтожается.

<p align="center">
<img src="https://datavalley.technology/wp-content/uploads/2021/03/image-8-1024x512.png" width="80%"><br>
<small>Flow взаимодействия компонентов Airflow</small></p>

# Database Agent for Natural Language to SQL Queries

This project is a database agent that converts natural language questions into SQL queries using an LLM (Large Language Model) and executes those queries on a MySQL database. It is designed to interact with a customer churn database, allowing users to query the data using simple, human-readable questions.

## Features
- Converts natural language questions into SQL queries.
- Executes SQL queries against a MySQL database.
- Supports custom queries about customer data such as credit scores, transaction history, and account information.
- Includes a pre-defined schema for the `churn` table to answer complex queries.
- Uses `Groq` for the natural language processing component.

## Prerequisites
- Python 3.8+
- Jupyter Notebook (for interactive use)
- MySQL server running locally with a database named `hgs_bank_churn`
- A `.env` file with the following environment variables:
  - `GROQ_API_KEY`: Your API key for the Groq service.
  - `MYSQL_HOST`: The MySQL host (e.g., `localhost`).
  - `MYSQL_USER`: Your MySQL username.
  - `MYSQL_PASSWORD`: Your MySQL password.
  - `MYSQL_DATABASE`: The name of your MySQL database (e.g., `bank_churn`).

Install the required Python packages:
Copy code:

pip install -r requirements.txt


Create a .env file in the root directory with the following content:

GROQ_API_KEY=your_actual_groq_api_key
MYSQL_HOST=localhost
MYSQL_USER=root
MYSQL_PASSWORD=your_mysql_password
MYSQL_DATABASE=hgs_bank_churn


Ensure that your MySQL server is running and create the bank_churn database if it does not exist.

Usage
Run the Jupyter Notebook:

bash
Copy code
jupyter notebook
Open the notebook and run the cells to create the churn table, load data from churn_data.csv, and execute queries using natural language.

Use the get_answer_from_llm function to ask questions in natural language, such as:

python
Copy code
print(get_answer_from_llm("How many customers have a credit score above 700?"))
The notebook will generate the corresponding SQL query, execute it, and return the result.

Data
The data used in this project is stored in churn_data.csv, which contains customer information such as:
customer_id, gender, customer_age, marital_status, occupation, location, and other financial details.
The data is loaded into a MySQL table named churn and is used for answering queries.

Contributing
Feel free to open issues or submit pull requests for any improvements.

License
This project is licensed under the MIT License - see the LICENSE file for details.


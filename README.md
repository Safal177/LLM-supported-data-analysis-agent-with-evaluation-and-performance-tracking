AI agent reliability evaluation with analyzing LLM analytical capabilities and tool operations

# Main goals and objectives:
•	agent that takes user questions related to sales dataset using SQL.                                                                                                                                        
•	Connect DuckDB with OpenAI tool calling for data questing and answering.
•	Test SQL queries and compare true results with expected results.
•	 Find the accuracy of the agent’s results associated in natural language answers. 
•	Consider multiple test cases to find the evaluation pass rate. 
•	Use Phoenix tracing to track agent response.  
•	Create a base for more complicated agent response, reliability test, and error analysis.

# Tools:
Jupyter notebook (python) , Pandas , Json, OpenAI api , DuckDB and  Phoenix are used.

# Sales dataset: 
Columns are Store_Number, SKU_Coded, Product_Class_Code, Sold_Date, Qty_Sold, Total_Sale_Value, and On_Promo.

# Sales dataset summary:
Total rows (697,894), total quantity sold (1,036,049 units), Total sales value (about $13.27 million), and date (from November 1, 2021 to March 31, 2024)
For SQL supported data analysis, the dataset was registered in DuckDB.

# LLM agent processing pipeline:
Agent considers the following steps:
•	Receive a question in natural language.
•	Send both question and tool parameters to the OpenAI model.
•	Use the “search_sales_data” to get a SQL query
•	Run the query into store_sales_df with the help of DuckDB.
•	Give the SQL result to the model
•	Use query result to get a natural language answer.
•	Test the SQL result and final answer with expected values.
•	Use Phoenix to review agent monitoring data

# LLM agent implementation and evaluation pipeline followed by agent:
•	Initialize the Python environment and Jupyter Notebook with implementing OpenAI API Interaction and model Integration
•	Import the Parquet sales dataset using Pandas, review its structure, column names, record counts, data quality, and then register it into DuckDB.
•	Create search_sales_data(query) that runs through and confirms SQL queries for reading as well as grouping sales dataset from DuckDB, with applying initial security checks against unacceptable queries.
•	Connect the “gpt-4o-mini” model with the “search_sales_data” tool which creates SQL queries with the help of natural-language questions, applies them through the notebook and sends the responses back to the model for final answer preparation.
•	Analyze the LLM agent using 3 test queries with predetermined expected results, examining SQL tool picking, query syntax, SQL outputs, LLM response accuracy, and comprehensive evaluation rating for each test.
•	Use the local Phoenix interface to connect Phoenix tracking used to measure agent activity and examine model results, tool interactions, SQL query workflow, tool responses, and final answers. 

# Results:
•	697,894 (row count)
•	1,036,049 (units sold)
•	 2970 (store) that sold the top units:
•	 The real results received from 3 observations are equal to the expected results.

To run this project, all necessary Python libraries and frameworks were installed in the Conda (agent_eval) environment and applied for the jupyter notebook implementation / testing pipeline and the Phoenix interface, enabling agent interaction and information retrieval.

# Project file;
ai_agent_operations_evaluation.jpynb

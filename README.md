# Online Appendix: A Step Towards Cognitive Automation: Integrating LLM Agents with Process Rules

## Appendix A: Code
### 0. Installation
#### 0.1 Create conda environment
Execute:
```
conda env create -f agentic_bpa.yml
```

#### 0.2 Get and store an OpenAI API key
1. Create an OpenAI account and setup your billing.

2. Deposit $25 to the account.

3. Generate an API key [here](https://platform.openai.com/api-keys).

4. Setup the OpenAI API key as described [here](https://help.openai.com/en/articles/5112595-best-practices-for-api-key-safety).

### 1. Simulation of Error Handling and User Requests
Run the Jupyter notebooks in the following order:

1. _00_rule_generation.ipynb_
2. _01_description_generation.ipynb_
3. _02_vector_db_generation.ipynb_
4. _03_simulation_rules.ipynb_
5. _04_simulation_descriptions.ipynb_
6. _03_simulation_rules_user_requests.ipynb_
7. _04_simulation_descriptions_user_requests.ipynb_
8. _07_results.ipynb_

This will produce the results.

You can also just run _07_results.ipynb_ to gather the results only. 


### 2. Minimal Working Example
You can run _08_minimal_working_example.ipynb_ when you only want to try out a minimal example.

The minimal example will use the existing rules and descriptions and run only one process example for the error-handling simulation.

### 3. Prompt Engineering Examples
In the folder _prompt_engineering_examples_ some examples show how precise information is important for our approach.


## Appendix B: Files
### Prompt Engineering Examples
#### Error-Handling
![](prompt_engineering_examples/bpmn/example_0002.png)

The additional information in the red box was initially not included in the process diagram. This led the LLM agent to search the BELNR in "E1EDK02" instead of the "E1EDP01", which is not incorrect but without providing the correct segment the LLM agent could also hallucinate an incorrect segment, because there is no additional information given in the BPMN model leading to an incomplete rule.

![](prompt_engineering_examples/bpmn/example_0003.png)

We can see the same problem as in the previous example within the image above. In case of the image above the LLM agent chose the 'E1EDL24' segment instead of the intended but not explicitly modeled 'E1EDP01' because there is no additional information given in the BPMN model leading to an incomplete rule.

#### User Requests
![](prompt_engineering_examples/bpmn/example_0005.png)

When the above example is transformed in a user request to the LLM agent and the rpa_parameter 'ORDER_NUMBER' is not explicitly named, it falsely refers to 'order id'.

![](prompt_engineering_examples/bpmn/example_0007.png)

Similar to the example above, the LLM agent fails to set the right parameters when not explicitly named in the user request. 

### BPMN Models for the Processes in the Error Handling Simulation
Process 1
![](bpmn/process1.png)

Process 2
![](bpmn/process2.png)

Process 2
![](bpmn/process1.png)

Process 3
![](bpmn/process3.png)

Process 4
![](bpmn/process4.png)

Process 5
![](bpmn/process5.png)

Process 6
![](bpmn/process6.png)


Process 7
![](bpmn/process7.png)

### BPMN Models for the User Requests
Process: 0000
![](bpmn_user_requests/0000_tasks_8_gateways_2.png)


Process: 0001
![](bpmn_user_requests/0001_tasks_5_gateways_2.png)


Process: 0002
![](bpmn_user_requests/0002_tasks_5_gateways_2.png)


Process: 0003
![](bpmn_user_requests/0003_tasks_6_gateways_1.png)


Process: 0004
![](bpmn_user_requests/0004_tasks_6_gateways_1.png)


Process: 0005
![](bpmn_user_requests/0005_tasks_5_gateways_1.png)


Process: 0006
![](bpmn_user_requests/0006_tasks_6_gateways_2.png)


Process: 0007
![](bpmn_user_requests/0007_tasks_5_gateways_2.png)


Process: 0008
![](bpmn_user_requests/0008_tasks_5_gateways_1.png)


Process: 0009
![](bpmn_user_requests/0009_tasks_6_gateways_1.png)


Process: 0010
![](bpmn_user_requests/0010_tasks_10_gateways_2.png)


Process: 0011
![](bpmn_user_requests/0011_tasks_12_gateways_2.png)


Process: 0012
![](bpmn_user_requests/0012_tasks_15_gateways_2.png)


Process: 0013
![](bpmn_user_requests/0013_tasks_14_gateways_2.png)


Process: 0014
![](bpmn_user_requests/0014_tasks_12_gateways_2.png)


Process: 0015
![](bpmn_user_requests/0015_tasks_9_gateways_2.png)


Process: 0016
![](bpmn_user_requests/0016_tasks_7_gateways_2.png)


Process: 0017
![](bpmn_user_requests/0017_tasks_11_gateways_2.png)


Process: 0018
![](bpmn_user_requests/0018_tasks_4_gateways_1.png)


Process: 0019
![](bpmn_user_requests/0019_tasks_4_gateways_1.png)


Process: 0020
![](bpmn_user_requests/0020_tasks_3_gateways_1.png)


Process: 0021
![](bpmn_user_requests/0021_tasks_11_gateways_2.png)


Process: 0022
![](bpmn_user_requests/0022_tasks_11_gateways_1.png)


Process: 0023
![](bpmn_user_requests/0023_tasks_15_gateways_2.png)


### Other Files
1. Data for the error-handling simulation can be found under _error_cases_translated.csv_
2. Data for the user request simulation can be found under _user_requests.json_
3. The five different rules generated are stored in the folder _rules_.
4. The five different rules databases generated are stored in the folder _vector_db_.
5. The five different descriptions generated are stored in the folder _descriptions_
6. The five different descriptions generated are stored in the folder _vector_db_descriptions_



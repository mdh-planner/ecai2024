# ijcai2024

To successfully use a test instance, you need to use three matching files (tasks,agents,weights). For example tasks_2_8.txt, agents_2_8.txt, and weights_2_8.txt are one instance.

Agents file explanation
1st column - Agent's index
2nd column - Agent's equipment

Tasks file explanation
1st column - Task's index

2nd column - The number of agents required for the task

3rd column - Task's required equipment

4st column - 1 if the task is virtual (no location), 0 if it is physical

5th column - Precedence relations, the index of the task from the 1st column precedes the task that is here

6th column - Task duration

7th column - List of tasks that can run in parallel

Keep in mind that it works both ways, although it is not explicitly stated here. For example, if task 3 can run in parallel with task 7, that means that task 7 can run in parallel with task 3 even though in 7th column of task 7 there might not be task 3. 

-1 is just int that fills in the empty space.

Weights file explanation

It is an adjacency matrix. Rows go as following:
First m rows are agents. (every file has "name_m_n_.txt". The first number (m) is the number of agents in that instance, the second number (n) is the number of tasks in that instance)
After m rows for agents, the next n rows are tasks. Lastly, the remaining rows represent the destination depots.

Note that virtual tasks have value 0 when traveling to or from, it means you don't need to travel to execute them.

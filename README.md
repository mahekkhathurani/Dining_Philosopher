# Dining_Philosopher
Solving the Dining Philosopher Problem

# 1. Introduction
The Dining Philosophers problem is one of the classic problems used to describe synchronization issues in a multi-threaded environment and illustrate techniques for solving them. Dijkstra first formulated this problem and presented it regarding computers accessing tape drive peripherals. The present formulation was given by Tony Hoare, who is also known for inventing the quicksort sorting algorithm.

# 2. The Problem

![image](https://user-images.githubusercontent.com/72668413/114557946-d00d9080-9c87-11eb-84c7-022aea193722.png)

There are five silent philosophers (P1 – P5) sitting around a circular table, spending their lives eating and thinking. There are five forks for them to share (1 – 5) and to be able to eat, a philosopher needs to have forks in both his hands. After eating, he puts both of them down and then they can be picked by another philosopher who repeats the same cycle.
The goal is to come up with a scheme/protocol that helps the philosophers achieve their goal of eating and thinking without getting starved to death.

# 3. A Solution
Each philosopher is initially thinking. After a certain amount of time, the philosopher gets hungry and wishes to eat.
At this point, he reaches for the forks on his either side and once he's got both of them, proceeds to eat. Once the eating is done, the philosopher then puts the forks down, so that they're available for his neighbour. 
i.e. a Philosopher thinks for a while and then decides to eat. After this, he acquires the forks to his left and right and starts eating. When done, he places the forks down. 

# 4. Problem of Deadlock
Though it seems that the above solution is correct, there's an issue of a deadlock arising. A deadlock is a situation where the progress of a system is halted as each process is waiting to acquire a resource held by some other process.
We can confirm the same by running the above code a few times and checking that some times, the code just hangs. 
In this situation, each of the Philosophers has acquired his left fork, but can't acquire his right fork, because his neighbour has already acquired it. This situation is commonly known as the circular wait and is one of the conditions that results in a deadlock and prevents the progress of the system.

# 5. Resolving the Deadlock
As we saw above, the primary reason for a deadlock is the circular wait condition where each process waits upon a resource that's being held by some other process. Hence, to avoid a deadlock situation we need to make sure that the circular wait condition is broken. There are several ways to achieve this, the simplest one being the follows:

All Philosophers reach for their left fork first, except one who first reaches for his right fork.

# Implementation:
# Technology Used: Java, AWT, Swing

In this code, we have 3 options:
1. Face Problem of Deadlock.
2. Avoid Deadlock
3. Quit GUI

# Output:
1. Initial View:

![image](https://user-images.githubusercontent.com/72668413/114559877-cd139f80-9c89-11eb-931b-5c0d622b3e02.png)

![image](https://user-images.githubusercontent.com/72668413/114559644-95a4f300-9c89-11eb-9d4d-69a400e31a35.png)

2. Face Problem of Deadlock:

![image](https://user-images.githubusercontent.com/72668413/114559970-e0266f80-9c89-11eb-8859-957f82aae708.png)


3. Avoid Deadlock:

![image](https://user-images.githubusercontent.com/72668413/114560302-2f6ca000-9c8a-11eb-8d97-a4647bedcaad.png)

# THINK_COLOR = blue;
# WAIT_COLOR = red;
# EAT_COLOR = green;

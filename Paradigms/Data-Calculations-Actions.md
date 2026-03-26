# Data, Calculations, and Actions
  
## Functional thinking
- **Recall:** In this class we will focus on the functional programming skills, thought processes, and techinques in practical use in the industry  
- On of the first such FP techniques is to distringuish data, calculations, and actions in one's code  
<img width="689" height="498" alt="DataCalculationsAndActions png" src="https://github.com/user-attachments/assets/7760dab2-72e2-41b8-8002-91a7592f3b27" />

## Actions
- **Definition:** an action is aninstruction for which the time and order in which it is called matters  
            - Actions hace side effects - calling them causes some change in a system  
            - Actions are also called impure functions  
                           
- Examples:  
            - print to screen, send email, update databses,  
            - reassign global variable, reassign instance variable, change list element  
- You MUST be careful with actions!

### Techniques for actions
- Functional programmers use specific techniques to handle actions  
            - Ways to safely change state over time  
            - Ways to guarantee ordering  
            - Ways to ensure actions happen only once  
  
<img width="1089" height="613" alt="Actions png" src="https://github.com/user-attachments/assets/4d4d8b91-b009-4c70-ab51-472834deca07" />

### Non-actions
- Everything for which time and order to not matter is not an action  
- Everything that is not an action is either a calculation or data  
  
- Non-actions are easier to work with because it doesn't matter when or in what order you use them!  

## Data
- **Definition:** Data is facts about events  
          - Data does no work  
          - E.g., variables, arrays, lists, objects  
  
- **Definition:** Immutable data is data that cannot be changed  
- **Definition:** Mutable data is data that can be changed  
- Functional programmers prefer immutable data over mutable data

### Techniques for data
- Organize data for efficient access  
- Disciplines for storing data  
- Principles for capturing what is important using data

## Calculations
- **Definition:** A calculation is a computation from input to output   
              - Calculations have no side effects  
              - Calculations are also called pure functions  
              - The same calculation performed on the same input ALWAYS produces the same output  
              - The input and output of a calculation is usually data   
              - E.g., find the maximum value of a collection; check if an email address is valid  
  
- Functional programmers prefer calculations over actions   

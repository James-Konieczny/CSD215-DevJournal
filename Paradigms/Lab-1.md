# Lab Notes
Category walk-through notes (braindump)
- CategoryController
    - Sqeuence,
    - no logic - data comes from here and goes to here
    - when to do things
 
- CategoryRepository
    - Take list of catgeories from database
    - NOT returning a list of jdbc rows: Returns the columns in the data types that we pick
 
- logging is built into the jdbc

- MainLayout.java has the UI for the menu items and stuff
- AppController.java
- DataService.java pulls on the repositories we need, knows about database connection. Make sure the reposiorty is only called once

- CategoryValidor - take some unvaild category information and make sure its vaild (the puprpose of validating data is to vaildate user data - the rules of the data)


## Start Of Lab - Supplier Implementation  
- What I'll need to do:
- Files that will be created/changed:  
  - Supplier
  - SupplierView
  - SupplierEditView
  - SupplierNewView
  - SupplierRepository
  - SupplierValidator
  - SupplierController  
<br>
      - MainLayout  
      - AppController  
      - DataService  
   
- In CategoryRepository.java, what does allCategoryNames() and countProductsInCategory() do?

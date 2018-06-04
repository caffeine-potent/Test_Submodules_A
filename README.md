# Structure  

Two Repositories:  

- A - https://github.com/caffeine-potent/Test_Submodules_A  
- B - https://github.com/caffeine-potent/Test_Submodules_B  


A is a parent to B. The means that A is a project with submodule B. 
`A<b1,h1>` denotes reponsitory `A` on branch `b1` with hash `h1`.  
  
# Things to test:

- **TEST 1**: Given that `A<b1,h1>` is parent to `B<b2, h2>`, a change made in `B` that brings the state of `B<b2, h2>` to `B<b2, h3>` (`A<b1, h1>` is unaltered) 
will maitain that `A<b1, h1>`'s submodule init still only pulls `B<b2,h2>`.  



# Creating a submodule:  

```git submodule add https://github.com/caffeine-potent/Test_Submodules_B```
    
run `git status`. You should see `.gitmodules` and `Test_Submodules_B`

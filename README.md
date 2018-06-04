# Structure  

Two Repositories:  

- A - https://github.com/caffeine-potent/Test_Submodules_A  
- B - https://github.com/caffeine-potent/Test_Submodules_B  


A is a parent to B. The means that A is a project with submodule B. 
`A<b1,h1>` denotes reponsitory `A` on branch `b1` with hash `h1`.  
  
# Things to test:

- **TEST 1**: Given that `A<b1,h1>` is parent to `B<b2, h2>`, a change is made in `B` that brings the state of `B<b2, h2>` to `B<b2, h3>`. Assuming `A<b1, h1>` is unaltered, `A<b1, h1>`'s submodule init still only pulls `B<b2,h2>`, not the newer version `B<b2,h3>`.  
- **TEST 2**: Initial configuration. `A<b1,h1>` is parent to `B<b2, h2>`.
Changes: state of `B<b2, h2>` is brought to `B<b2,h3>`. This change is pushed. Changes tracked in `A` for submodule `B` is pushed changing `A<b1, h1>` to `A<b1, h4>`. This tests assumptions about how submodules are updated in a parent.  

# Test Results:  
- ☑ **Test 1** : State is frozen despite changes in Submodule B.
- ☑ **Test 2** : State of submodule B is updated. Validating the idea that it is the parent's responsibility to update the current state of the submodule, rather than the submodule changes being tracked.
# Creating a submodule:  

```git submodule add https://github.com/caffeine-potent/Test_Submodules_B```
    
run `git status`. You should see `.gitmodules` and `Test_Submodules_B`

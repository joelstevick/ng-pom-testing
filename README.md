# Introduction
This module compliments *Angular Testbed*.  We suggest that you use one of the available helper-libraries that wrap Angular Testbed: [Spectator](https://netbasal.com/spectator-v4-a-powerful-tool-to-simplify-your-angular-tests-bd65a0bf317e) or [Testing-Library](https://testing-library.com/docs/angular-testing-library/intro/)

1. **mergeConfig()** - accepts a list of configuration objects.  Precedence follows the es6 implementation of Object.assign().  The merge operation is "deep."  Arrays are not replaced -- the entries are concatenated. 


        console.log(
            mergeConfig(
                { imports: [ReactiveFormsModule]}, 
                { imports: [MaterialModule]}
            )
        )

        // {imports: [ReactiveFormsModule, MaterialModule]}

2. **POM** - implements the [page-object-model pattern](https://martinfowler.com/bliki/PageObject.html).  The POM is generated using a *finite state machine* driven from a configuration object that you set up.  The configuration object specifies the various states that your component can enter and how to validate those states.  The configuration object also defines the actions that can be taken: the steps to be performed and the new state for the component after the action is completed.
    
    const pom = new POM({ container, detectChanges}, pomConfig);
    

[This example]() illustrates how to use *mergeConfig* and *POM*. 
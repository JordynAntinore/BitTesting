# BitTesting
this is a repository to see what working with Bit is like. this is solely a testing repository for Bit.

- I followed a tutorial for this repository, heres the link: https://bit.dev/docs/quick-start/

- To Run:
  - run 'bit install'
  - cd to the workspace (my-workspace-name) <-- this is the actual name of the workspace
  - run 'bit start'
  - your application will be on localhost:3000
  
 ## Steps to create your own workspace:
  - run 'bit new react tasks-workspace --default-scope my-org.tasks-scope'
  - you should see 'Let's get started!
                      cd tasks-workspace
                      bit start'
  - to inspect/preview the status of your workspace run: 'cd tasks-workspace' then 'bit start'
  - to see the status of your workspace at anytime in detail, run: 'bit status'
  - to see a list of your components within your workspace run: 'bit list'
                        
 ## Steps to create your own component:
  - to create the component run 'bit create react apps/to-do(component name) --scope my-org.tasks-scope(workspace)'
  - components all have an ID that consists of the scope name and component name combined.
  - to see metadata of a component run 'bit show apps/to-do(component name)'
  - import dependencies at the top of components file like so: 'import { InputText } from '@teambit/design.inputs.input-text';'
  - then do bit install *package*.
  
 ## Steps to export a finished component:
  - Run 'bit status' to see the components state
  - If everything just says '...ok' youre good to go!
  - run bit snap apps/to-do(component name) --message "initial snap" to create a message and get ready to export
    - you can also to the same call but with "tag" instead of "snap" for releases
  - run 'bit export' 
  - this export will save the component within the name of the account youve made within bit.cloud.
  
## Installing components
Components once exported to a remote scope can be consumed in any other project/app with the package manager of your choice.
 - example: npm install @my-org/scope.my-component
            yarn add @my-org/scope.my-component
 - then import the component into the code (another example): import { myComponent } from '@my-org/scope.my-component';
 
## Authentication:
  If you need to be able to login to bit in order to export or you are having issues because of authenication fails, heres what you do:
   -  run 'bit login'
   - Bit generated a .npmrc in your user-home directory (~ in macOS/Linux, %USERPROFILE% in Windows) with a basic config containing your authentication token.
   - Open the .npmrc file and add the following line (complete the account name according to where components are hosted)
    - @ACCOUNT:registry=https://node.bit.cloud
  

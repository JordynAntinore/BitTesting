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
  
 ## Bit commands
  Here are commands you can use with bit and what they do:
    Start a working area
      init           create or reinitialize an empty workspace
      new            create a new workspace from a template

    Workspace commands
      config         global config management
      scope-config   scope config management
      login          log in to Bit cloud
      logout         log the CLI out of Bit
      doctor         diagnose a bit workspace
      completion     enable bash/zsh-completion shortcuts for commands and options
      cli            EXPERIMENTAL. enters bit cli program and generates commands list
      help           shows help
      clear-cache    clears Bit's cache from current working machine

    Collaborate on components
      remote         manage set of tracked bit scope(s)
      use            set aspects in the workspace/scope config to make them loadable by the workspace/scope
      remove         remove component(s) from the workspace, or a remote scope
      export         export components from the workspace to remote scopes
      import         import components from their remote scopes to the local workspace
      pack           create tar for npm publish
      deprecate      deprecate a component
      undeprecate    undeprecate a deprecated component (local/remote)
      rename         EXPERIMENTAL. rename component. if tagged/exported, create a new component and deprecate the original component
      fork           EXPERIMENTAL. create a new component out of an existing one (copies source files and config)

    View components
      dependents     EXPERIMENTAL. show dependents of the given component
      show           display the component's essential information
      deps           manage dependencies
      log            show components(s) version history

    Develop components
      add            Add any subset of files to be tracked as a component(s).
      move           move a component to a different filesystem path
      diff           show the diff between the components' source files and config
      envs           list all components maintained by the workspace and their corresponding envs
      start          run the ui/development server
      ui-build       build production assets for deployment.
      scope          EXPERIMENTAL. manage the scope-name for components
      eject-conf     eject components configuration (create a `component.json` file)
      watch          automatically recompile modified components (on save)
      pattern        list the component ids matching the given pattern
      checkout       switch between component versions or remove local changes
      component-issueslist available component-issues
      create         create a new component (source files and config) using a template.
      templates      list templates for "bit create" and "bit new"
      build          run set of tasks for build
      artifacts      EXPERIMENTAL. list and download components artifacts
      compile        compile components in the workspace
      install        installs workspace dependencies
      uninstall      uninstall dependencies
      update         update dependencies
      link           create links in the node_modules directory, to core aspects and to components in the workspace
      tag            create an immutable and exportable component snapshot, tagged with a release version.
      reset          revert tagged or snapped versions for component(s)
      merge          merge changes of different component versions
      refactor       EXPERIMENTAL. source code refactoring / codemod
      status         present the current status of components in the workspace, and notifies when issues are detected
      test           test components in the workspace
      schema         shows the API schema of a certain component.
      check-types    check typescript types
      write-tsconfig EXPERIMENTAL. write tsconfig.json files in the component directories
      aspect         EXPERIMENTAL. manage aspects
      eject          replace components maintained in the workspace with their corresponding packages
      format         format components in the development workspace
      lint           lint components in the development workspace

    Workspace
      globals        list all globals

    Explore components
      graph          EXPERIMENTAL. generate an image file with the dependencies graph
      list           list components on a workspace, local scope or a remote scope.

    Capsules
      capsule        manage capsules

    Applications
      run            run an app (independent of bit's dev server)
      app            Manages apps
    


|                |                                   |
| -------------- | --------------------------------- |
| `ng --version` | To get the version of the angular |
| `ng -new`      |                                   |
![[Pasted image 20240718121633.png]]


==To create project==
1.To create project
`ng -new [--skip-tests=true] [--standalone=false] <app-name>`
`<app-name>` -> do not start with a digit, do not use spaces, limit digits usage,naming convention lowercase+kebab case

`ng [--package-manager]-new [--skip-tests=true] [--standalone=false] <app-name>` -> to change the package manager

`ng -new [--skip-tests=true] [--skip-install=true] [--standalone=false] <app-name>` -> to skip the npm installation in the early stage

2.How to start Server

`ng serve`
This is need to be used in any case `npm start` not gonna used

to change the dev server start port
`ng server [--port = <portNumber>]`

==To create Module==

3.To create module 
`ng gnerarte(g) moudle(m) [--flat=[true]] [path/]<modulename>`

`--flat=true` -> to create the module with in the direct app. Not in a new folder inside the app

==To create components==

`ng generate(g) component(c) [--skip-test=false][--standalone=false] [--inline-styles=true][--inline-template=true][--module=<modulename>] [path/]<component>`

`--skip-test=false` -> to mange the skip of test. The default value is the similar value that was given to the project

`--standalone=false` -> to manage the standalone. The default values in the similar value that was given during the create project

`inline-styles=true` -> to set the inline style. This combine the ts file and style together

`inline-template=true` -> to set he inline template. This combine all ts, html , css together

`--moudule<module name>` -> to set the module. If the module is not mentioned in the command then select the module base on the path

`[path/]` -> to specify a special directory to create the  component

cli commands ->  https://angular.dev/cli
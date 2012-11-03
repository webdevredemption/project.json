# My proposal for the "Front-end tools and existing projects" issue / problem.

By [Tom Lane](http://tomlane.me)

--- 

## Project.json

### A common hook for front end tools to access project structure and information.

#### What is it?

A simple JSON file that states essential information for front-end tools to be able to just drop in to an existing project and begin working straight away.

#### Why is it needed?

Most front-end tools (such as Yeoman) are only compatible if the project is created using the tool itself and has no support for existing projects.

#### How will it be implemented?

Implementation will need to happen in 2 stages:

- Tools need to check for the existence of this file and work accordingly.
- Existing projects need to create a project.json file in order for it to be used and processed by the tools.

#### What would a typical project.json file include?

- Directory information.
	- CSS
		- Pre-processor input directory.
		- CSS output directory.
		- Linting?
		- Minifying?
	- Javascript
		- Pre-processor input directory (e.g. coffeescript).
		- JS output directory.
		- Linting?
		- Minifying?
	- HTML
		- Pre-processor input directory.
		- HTML output directory.
		- Linting?
		- Minifying?
	- Project server directory
		- Where to serve files from for local server testing.
- Existing tools used.

#### Would it be extensible?

Yes, being JSON the contents and uses can be very flexible. For example, existing JSON such as Bower's component.json can easily be integrated.
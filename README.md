# Server Planning

Write a library that calculates the number of servers (which have the same configuration) needed to host a specified
amount of virtual machines.

Your library should return the number of servers that is required, to host a non-empty collection of virtual machines.
This means you should implement the following method (UML definition):
```
+calculate(serverType: Server, virtualMachines: VirtualMachine[1..*]): int
```
All servers have the same type. This type defines the hardware resources each server provides: CPU, RAM, Storage.
Each virtual machine is defined by the virtual hardware resources it needs (on a server): CPU, RAM, Storage.

The algorithm for the virtual machine distribution should implement a 'first fit' strategy. 
This means there is no resource optimization or 'look back'.
Virtual machines are always allocated on the current or the next server (in case of limited resources).

If a virtual machine is too 'big' for a server, it should be skipped.
If the collection of virtual machines is empty, an exception should be thrown.

## Example
* Server type = `{CPU: 2, RAM: 32, Storage: 100}`
* Virtual Machines = `[{CPU: 1, RAM: 16, Storage: 10}, {CPU: 1, RAM: 16, Storage: 10}, {CPU: 2, RAM: 32, Storage: 100}]`
* Result = 2

## General Requirements
* Don't fork this repository
* Create a composer project with the latest PHP version
* Free choice of dependencies, but keep it simple
* Your code should be tested. Code coverage of 100% is not required, but all
  important code paths should be tested
* If you are using Docker, please also hand in your Docker configuration
* Leave your git project in a state you would be happy with for turning it in for code review
* Don't leave your solution in a publicly accessible git project, instead hand in a git archive
  (https://git-scm.com/docs/git-archive) as a ZIP file.

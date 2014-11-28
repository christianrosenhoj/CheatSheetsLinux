## Vagrant Commandos

| Task 					| Command
| :---                  | :---
| `vagrant up` 			| Start alle VM's na elkaar op (die gedefinieerd staan in de vagrantfile)
| `vagrant up <naam server>`| Start 1 bepaalde VM op
| `vagrant halt` 		| Stopy alle VM's 
| `vagrant halt <naam machine>`  		| Stopt 1 bepaalde VM 
| `vagrant reload` 		| Herstart de VM's
| `vagrant destroy` 	| destroys the machine
| `vagrant provision` 	| Draait het Vagrant script en voert alle nieuwe code uit
| `vagrant status` 		| Geeft alle VM's weer die aanstaan
| `vagrant ssh <naam amchine>`			| Maakt een ssh verbinding met een bepaalde VM

## Algemene Vagrant instellingen
| Task 					| Command
| :---                  | :---
| `Vagrant box add <naam die je aan de box wilt geven> --name <path waar je box staat>` | Die voegt een box toe zodat je dze kan gebruiken
| `vagrant init <naam van de box>`| Dit initialliseert de vagrant box

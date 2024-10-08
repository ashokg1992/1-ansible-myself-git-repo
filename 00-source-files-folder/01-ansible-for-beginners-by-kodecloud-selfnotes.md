---
ansible

- ansible cfg file has different sections, in that we have  many parameters 
-

======= ansible tasks ========
- we can create users by using ansible plaaybooks
- setting firewall configurations to manged hosts /servers
- adding dns names to config file
#
- deploy servers on pub ,pri cloud
- provision storage to all vms
setup n/w configuration on  private vms
-set up cluster configuration
-configure web server on 20 pub vms
-configure db server on 20 private vms
-set up load balnceing b/n private and pub vms
-set up monitoring components
- install and configure backup clients on vms
- 

- - crating users by using single task by loops .
- creating custom roles and collections  to share across project for roles collections
- 





- what are order of different configuration files, 
# what type of playbooks you have written
- n/w playbooks, webserver playbooks, db-playbooks, storage-playbooks

# how you trouble shoot ansible configuration issues?

# in inverntory file, we have diff groups, in that groups we can  create different child groups like : db servers is parent group; db servers-us , db- servers-ap-south are child groups
- by using children  keyword we create child group in the parent group
- 

# varailbe:
- we can include variables dynamically into the playbooks by using "lineinfile" under the tasks filed

# variable types:
-host varialbes : are assositeated to each host
- global variables: 
- magic variables- hostvara: by using it we can get other host var details
	- msg'{{ hostvars[web2].ansible_host_name}}'
	- by this , we can get details of any into required place
- magic varailbes -groups:
	- 

# module: a different task are done by tasks , then it is called as module
- shell module; 
- set up module: to get facts. ansible by defaults executes this setup module to get facts
-yum module: oinstall package
- service module : to start restart aservice
-scritp module:
-command module: 
- 

# we can see o/p of play book in many ways
- by using verbose method -v
- by using register varailbe and assign o/p to result key and result.stdout is shown the o/p details, so that we can debug playbook
- 

# ansible facts:
- collects system archetecutue like os type, version, process type, memery details, cpu , ip address, mac address, all 
-- set up module: to get facts. ansible by defaults executes this setup module to get facts
- all facts are stored in ansible_facts variable  in ansible
- we can disable gather_facts : no , by this command we can disable gattheirng facts
- in ansible ansible.cfg file we can set gathering = implicit , by this we can enable gather_facts automatically
- 

# ansible playbooks


# verifying  playbooks:
	-check mode
	- diff mode
- to check syntax 
	- ansible-playbook --syntax-check option  # it checks syntax errors
- 


# ansible -lint
- ansible-lint playbook.yaml   # it checks any syantax check 

#

# ansible conditions:
- by using "when" block, conditions we can do implement it.
- 
-  to implement conditionals in loops in ansible, we use" when : item.required == true " 
- by using conditions and using variables, we can do specific actions specific environments specific instances specific tasks

# loops
- crating users by using single task by loops .
- "with_items", " item  over loop " do same functionality.
- with_* - is a look up plugin in ansible to do looping functionality
- 

# modules
#system moudles
-user
group
hostname
iptables
lvg
lvol
make
mouont
ping
timezone
susstemd
service
# commands module
command
except
raw
script
shell
# files modules
acl
archive
copy
file
find
lineinfile
replace
stat
templat
unarchive
# database mdule
mongodb
mssql
MySQL
postgressql
proxysql
vertica
# cloud module
aws 
azure
# windows module



# idempotence
- "lineinfile" is example of idempotence
- lineinfile is  used to add a  line in a file
- 

# ansible plugins
-to get real time data like current vpc ,sg ,tags directly from coud providers api to ensure  inventory upto date, and reflects the current  state of  infrastructure, .

- ansible plugin : 
	- it s is for what purpose?
	-

# roles
- in roles, we group common tasks , so that just all other users or across anislbe  we use that role rather we write again and again, just by refering it's name under role section.
- 

# ansible galaxy
- to hsare roles across globally we use galaxy. it is web based platform to share roles 
-by defalult /etc/nsible/roles,  in this path by deault ansible look for roles. 
- we can    set a path for a role  also  as our wish under roles_path in ansible.cfg file
- 

# ansible collections
- for versioning, to interactwith cloud providrs, ensure depenecies.
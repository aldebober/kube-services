### Role Description

- Create service accounts default namespace and namespaces.
- Create roles read-role-{{namespace}} write-role-{{namespace}} in each namespaces.
- Binding roles and service accounts.
- Binding cluster role to list and get namespaces
- Jenkins bot service account and cluster role.

### Default params

Resources of read role are listed in {{ read_resources }} and write role in {{ write_resources }}
Read role has ["create", "update", "patch", "delete"] verbs
And write role has only ["get", "watch", "list"]

{{teams}} is a list of all teams and there are several list of teams users {{team_name}}_users 

To add new team create list of users of it.

{{namespaces}} is a list of base prefix which is will be addded to namespace like {{namespaces}}-{{team_name}}

### Usage

`ansible-playbook -i inventory/subaru-fi-prod/hosts.ini playbooks/subaru-fi-prod/rbac-users.yml -b -v -u automation --vault-password-file ~/vault`

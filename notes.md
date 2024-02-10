Introduction to Roles

Roles are a way to organize playbooks and related files (variables, templates, tasks, etc.) into a reusable structure.
Using roles, you can break down complex playbooks into manageable, reusable components. Roles are typically used to
encapsulate the logic required to configure a particular service or piece of software. Roles directory could look like this:
```yaml
roles/
   nginx/
      tasks/
         main.yml.j2
      handlers/
         main.yml.j2
      templates/
      files/
      vars/
         main.yml.j2
      defaults/
         main.yml.j2
      meta/
         main.yml.j2
```
- Tasks: The main set of tasks that the role executes.
- Handlers: Tasks that are only run in response to other tasks.
- Templates: Jinja2 templates that can be deployed via this role.
- Files: Static files that can be deployed via this role.
- Vars: Variables related to this role.
- Defaults: Default variables for the role.
- Meta: Metadata about the role, such as dependencies.

### Best Practices for Roles
- Role Names: Use clear and descriptive names for roles to reflect their purpose.
- Task Granularity: Break down tasks into the smallest logical components for ease of use and reusability.
- Variable Use: Utilize default variables for broad configuration and vars for more specific use cases.
- Role Documentation: Document each role and its variables to make it easier to understand and use.
- Reusability: Design roles to be reusable in different environments to maximize efficiency.

## Modularization

Modularization refers to the process of designing Ansible playbooks and roles in a way that they can be easily reused and maintained. This is achieved by:

- Encapsulating functionality: Each role should manage one aspect of the system.
- Parameterization: Using role variables to customize the role's behavior without changing the role's tasks.
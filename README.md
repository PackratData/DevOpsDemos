# DevOpsDemos
DevOps Examples

## Setting up Environment

- Create initial pipenv with:

  ```
  pipenv install --dev ansible boto3
  ```

## Ansible Demos
- Activate shell
  ```
  pipenv shell
  ```

- Set up Environmental Variables:
  - on [macOS](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-envvars.html)

  - Common Environmental Variables
    - `AWS_ACCESS_KEY_ID`
    - `AWS_SECRET_ACCESS_KEY`
  
  
  - Playbook Specific

    | Playbook | Environment Variables |
    |:---|:---|
    | create_route53_records.yml | `HOSTED_ZONE_ID`<br/>`ROUTE_53_DOMAIN_NAME` |
    

### 
- Run an ansible playbook from the project root in `--check` mode

  ```
  ansible-playbook playbooks/create_route53_records.yml -i group_vars/aws/aws_route53_records.yml --extra-vars @inventories/aws_route53_records.yml --check
  ```

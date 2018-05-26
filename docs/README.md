# TFLint Issue Documentation
## Issue Type
Issues are classified into the following three types.

- **ERROR**
    - There is a issue that an execution error occurs. We strongly recommend that you fix it if this is reported.
- **WARNING**
    - It is reported if something that is explicitly unrecommended is used. We recommend that you fix it.
- **NOTICE**
    - It is a issue that is considered desirable to fix.

## General Issue

- **AWS Instance**
    - [aws_instance_invalid_type](aws_instance_invalid_type.md)
    - [aws_instance_previous_type](aws_instance_previous_type.md)
    - [aws_instance_default_standard_volume](aws_instance_default_standard_volume.md)
- **AWS DB Instance**
    - [aws_db_instance_invalid_type](aws_db_instance_invalid_type.md)
    - [aws_db_instance_previous_type](aws_db_instance_previous_type.md)
    - [aws_db_instance_default_parameter_group](aws_db_instance_default_parameter_group.md)
    - [aws_db_instance_readable_password](aws_db_instance_readable_password.md)
- **AWS ElastiCache Cluster**
    - [aws_elasticache_cluster_invalid_type](aws_elasticache_cluster_invalid_type.md)
    - [aws_elasticache_cluster_previous_type](aws_elasticache_cluster_previous_type.md)
    - [aws_elasticache_cluster_default_parameter_group](aws_elasticache_cluster_default_parameter_group.md)
- **AWS Route**
    - [aws_route_not_specified_target](aws_route_not_specified_target.md)
    - [aws_route_specified_multiple_targets](aws_route_specified_multiple_targets.md)
- **AWS CloudWatch Metric Alarm**
    - [aws_cloudwatch_metric_alarm_invalid_unit](aws_cloudwatch_metric_alarm_invalid_unit.md)
- **Terraform**
    - [terraform_module_pinned_source](terraform_module_pinned_source.md)

### Default Disabled Issue
These rules are not always useful, so they are disabled by default. If you want to check the following, enabled the rule in configuration file.

- **Terraform**
    - [terraform_resource_explicit_provider](terraform_resource_explicit_provider.md)

### Invalid Reference Issue
Report these issues if you have specified invalid resource ID, name, etc. All issues are reported as ERROR. These issues are reported when enabled deep check. In many cases, an incorrect value is specified, so please fix it.

- **AWS Instance**
    - aws_instance_invalid_iam_profile
    - aws_instance_invalid_ami
    - aws_instance_invalid_key_name
    - aws_instance_invalid_subnet
    - aws_instance_invalid_vpc_security_group
- **AWS ALB**
    - aws_alb_invalid_security_group
    - aws_alb_invalid_subnet
- **AWS ELB**
    - aws_elb_invalid_security_group
    - aws_elb_invalid_subnet
    - aws_elb_invalid_instance
- **AWS DB Instance**
    - aws_db_instance_invalid_vpc_security_group
    - aws_db_instance_invalid_db_subnet_group
    - aws_db_instance_invalid_parameter_group
    - aws_db_instance_invalid_option_group
- **AWS ElastiCache Cluster**
    - aws_elasticache_cluster_invalid_parameter_group
    - aws_elasticache_cluster_invalid_subnet_group
    - aws_elasticache_cluster_invalid_security_group
- **AWS Route**
    - aws_route_invalid_route_table
    - aws_route_invalid_gateway
    - aws_route_invalid_egress_only_gateway
    - aws_route_invalid_nat_gateway
    - aws_route_invalid_vpc_peering_connection
    - aws_route_invalid_instance
    - aws_route_invalid_network_interface

### Duplicate Resource Issue
Report these issues if you have specified resource ID, name, etc that already existed and must be unique. All issues are reported as ERROR. These issues are reported when enabled deep check. For example, it happens when resources with the same name is already created. Please check the actual resources again.

- **AWS Security Group**
    - aws_security_group_duplicate_name
- **AWS ALB**
    - aws_alb_duplicate_name
- **AWS ELB**
    - aws_elb_duplicate_name
- **AWS DB Instance**
    - aws_db_instance_duplicate_identifier
- **AWS ElastiCache Cluster**
    - aws_elasticache_cluster_duplicate_id
- **AWS ECS Cluster**
    - aws_ecs_cluster_duplicate_name

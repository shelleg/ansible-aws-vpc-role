## VARS
command variable state whether to create or remove/clean the VPC from amazon
options are create or remove
```yaml
command: create
```

# instances
```yaml
    ---
    instances:
      - name: all
        roles: admin_portal,event_server,application_server,metadata_service
        subnet_type: private
        type: c4.2xlarge
        count: 1
        volumes:
            - device_name: /dev/sda1
                volume_size: 55
        groups: [allow_vpc, allow_ssh]
        loadbalancer: True
```
roles must only be using underscores as seperators and not hyphens

# RDS/ElasticCache
if you want to use RDS and ElasticCache ie. 
```yaml
    use_data_cloud_services: true
```
you must supply two or more AZ for deployment which means you will have a highly
available deployment (num of AZs * service machines for each service)
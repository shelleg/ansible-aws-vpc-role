## VARS

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
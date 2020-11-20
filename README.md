# Usage

See [action.yml](action.yml)

Basic:
```yaml
steps:
- name: Configure sysctl limits
  run: |
    sudo swapoff -a
    sudo sysctl -w vm.swappiness=1
    sudo sysctl -w fs.file-max=262144
    sudo sysctl -w vm.max_map_count=262144

- uses: Stark-Tech-Group/stg-elastic-action@v1
  with:
    elasticsearch version: '7.6.1'
    host_port: 9200
    container_port: 9200
    host_node_port: 9300
    node_port: 9300
    discovery_type: 'single-node'
```

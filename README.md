# nexentastor-csi-driver

NexentaStor CSI driver for Kubernetes.

## Build

```bash
make
```

## Run
```bash
make && ./bin/nexentastor-csi-plugin --rest-ip="https://10.3.199.253:8443,https://10.3.199.252:8443" --username="admin" --password="Nexenta@1"
```

## Tests

```bash
# run all tests
make test
# or
make test | grep --color 'FAIL\|$'

# with options
go test ./tests/**             # run all
go test ./tests/** -v          # more output
go test ./tests/** -v -count 1 # disable cache

# NexentaStor provider test options
go test ./tests/ns_provider -v -count 1 \
    --address="https://10.3.199.254:8443" \
    --username="admin" \
    --password="pass" \
    --pool="myPool" \
    --dataset="myDataset" \
    --filesystem="myFs" \
    --log="true"
```

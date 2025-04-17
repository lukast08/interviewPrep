`Secret` kind
- ruzne typy, nejcastejsi typ `Opaque` (key-value pairs)
- values need to be encoded - not for security reason but as a formatting requirement
- by default encoded values stored unencrypted in etcd

- Values need to be encrypted to protect the values
- Two approaches:
	- At rest (when stored in etcd)
	- when accessed via the K8s API
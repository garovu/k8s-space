# Kubeadm Cheatsheet Commands

Here are some useful commands for working with Kubeadm:

1. Initialize a Kubernetes control-plane node:

   ```shell
   kubeadm init
   ```

2. Join a worker node to the Kubernetes cluster:

   ```shell
   kubeadm join <control-plane-host>:<control-plane-port> --token <token> --discovery-token-ca-cert-hash <hash>
   ```

3. Reset a node and remove all Kubernetes related configuration:

   ```shell
   kubeadm reset
   ```

4. Upgrade the Kubernetes control-plane components:

   ```shell
   kubeadm upgrade plan
   kubeadm upgrade apply <version>
   ```

5. Upgrade the kubelet and kubectl on a node:

   ```shell
   apt-get update && apt-get install -y kubelet=<version> kubectl=<version>
   ```

6. Generate a kubeconfig file for a user:

   ```shell
   kubeadm alpha kubeconfig user --client-name <username> --apiserver-advertise-address <address> --apiserver-bind-port <port> --kubeconfig <path>
   ```

7. Generate a kubeconfig file for a kubelet:

   ```shell
   kubeadm alpha kubeconfig kubelet --apiserver-advertise-address <address> --apiserver-bind-port <port> --kubeconfig <path>
   ```

8. Generate a kubeconfig file for the kube-proxy:

   ```shell
   kubeadm alpha kubeconfig kube-proxy --apiserver-advertise-address <address> --apiserver-bind-port <port> --kubeconfig <path>
   ```

9. Check the status of the Kubernetes control-plane components:

   ```shell
   kubeadm version
   kubeadm config images list
   ```

10. View the join command for a worker node:

    ```shell
    kubeadm token create --print-join-command
    ```

11. Upgrade the kubelet and kubectl on all worker nodes:

    ```shell
    apt-get update && apt-get install -y kubelet=<version> kubectl=<version>
    systemctl restart kubelet
    ```

12. Generate a kubeconfig file for an external etcd cluster:

    ```shell
    kubeadm alpha kubeconfig user --client-name <username> --apiserver-advertise-address <address> --apiserver-bind-port <port> --kubeconfig <path> --etcd-servers <etcd-servers>
    ```

13. Generate a kubeconfig file for a kube-scheduler:

    ```shell
    kubeadm alpha kubeconfig kube-scheduler --apiserver-advertise-address <address> --apiserver-bind-port <port> --kubeconfig <path>
    ```

14. Generate a kubeconfig file for a kube-controller-manager:

    ```shell
    kubeadm alpha kubeconfig kube-controller-manager --apiserver-advertise-address <address> --apiserver-bind-port <port> --kubeconfig <path>
    ```

15. Generate a kubeconfig file for the kubelet-bootstrap user:

    ```shell
    kubeadm alpha kubeconfig user --client-name kubelet-bootstrap --kubeconfig <path>
    ```

16. Generate a kubeconfig file for the kubelet node user:

    ```shell
    kubeadm alpha kubeconfig user --client-name system:node:<node-name> --kubeconfig <path>
    ```

Remember to replace `<version>`, `<username>`, `<address>`, `<port>`, `<path>`, and `<etcd-servers>` with the appropriate values.

For more information, refer to the official [Kubeadm documentation](https://kubernetes.io/docs/reference/setup-tools/kubeadm/).

```bash
                        _              __            _                       
  ___ ___  _ __ ___  __| |_ __  ___   / _| ___  __ _| |_ _   _ _ __ ___  ___ 
 / __/ _ \| '__/ _ \/ _` | '_ \/ __| | |_ / _ \/ _` | __| | | | '__/ _ \/ __|
| (_| (_) | | |  __/ (_| | | | \__ \ |  _|  __/ (_| | |_| |_| | | |  __/\__ \
 \___\___/|_|  \___|\__,_|_| |_|___/ |_|  \___|\__,_|\__|\__,_|_|  \___||___/
```

CoreDNS is a flexible, extensible DNS server written in Go that serves as the
default DNS server in Kubernetes clusters. It follows a plugin-based
architecture where functionality is added through modular plugins, making it
highly customizable for different use cases. CoreDNS can handle traditional DNS
serving, service discovery, load balancing, and advanced features like
DNS-over-HTTPS/TLS. Its configuration uses a simple Corefile format that
defines which plugins to use for different zones. Originally created by the
Cloud Native Computing Foundation, CoreDNS replaced kube-dns in Kubernetes and
is widely used in cloud-native environments for its performance and
flexibility.

Project: https://github.com/coredns/coredns

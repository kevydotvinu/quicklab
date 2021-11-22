## oc-quicklab-plugin
The oc-quicklab-plugin is a CLI plugin that works with oc/kubectl and gives the quicklab shared cluster information in the CLI.

### Prerequisites
- [OpenShift CLI](https://access.redhat.com/downloads/content/290)
- [Chromium](https://www.chromium.org/) or [Google Chrome Web Browser](https://www.google.com/chrome/)
- Configure `Integrated Authentication` and `Kerberos Credentials Delegation` in Chrome browser - Add the below in `/etc/opt/chrome/policies/managed/redhat-corp.json` file.
```bash
{
    "AuthServerWhitelist": "*.redhat.com",
    "AuthNegotiateDelegateWhitelist": "*.redhat.com"
}
```

### Installation
Either use prebuilt binary:
```bash
$ wget -O oc-quicklab https://github.com/kevydotvinu/oc-quicklab-plugin/releases/download/v1/oc-quicklab-plugin_v1_linux_amd64
$ sudo mv oc-quicklab /usr/local/bin/
$ sudo chmod +x /usr/bin/local/oc-quicklab
$ oc quicklab help
```
Or build it from source:
```bash
git clone https://github.com/kevydotvinu/oc-quicklab-plugin.git
cd oc-quicklab-plugin
go build -o oc-quicklab main.go
sudo mv oc-quicklab /usr/local/bin
oc quicklab
```

### Usage
- Help
```bash
oc quicklab help
```
- List quicklab shared clusters
```bash
oc quicklab list
```
- Login into quicklab shared cluster
```bash
oc quicklab login --cluster <cluster-name-from-above>
```
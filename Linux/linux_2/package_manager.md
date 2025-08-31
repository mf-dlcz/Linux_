# Linux Package Manager

The four most popular Linux package managers are **RPM, YUM, DNF,** and **Zypper.**

- **RPM** is a low-level package manager for handling .rpm package files, used in RPM-based distributions.
- **YUM** is a high-level package manger that builds on RPM, providing easier package management

<br>

Installing a package with RPM
```
$ sudo rpm -i package_name.rpm
```

Installing a package with YUM
```
$ sudo yum install package_name
```

Updating a package with RPM
```
$ sudo rpm -u package_name.rpm
```

Updating a package with YUM
```
$ sudo yum update package_name
```

Removing a package with RPM
```
$ sudo rpm -e package_name.rpm
```

Removing a package with YUM
```
$ sudo yum remove package_name
```
#linux_ntp_client

This role will install and configure ntp on a RedHat- or Debian-based system.

* Chrony will be disabled.
* If firewall (UFW, firewalld) is enabled, NTP allow rule will be added to the default zone.
* NTP sources and options will be configured.

## Requirements

* This role utilizes root to install system packages and template system files. <code>ansible_user</code> must be able to sudo without a password.
* This role utilizes Ansible magic variables to discover the distribution. Facts must be available.

## Role Variables

|parameter|required|default|choices|comments|
|---|---|---|---|---|
|linux_ntp_client|no| | | A list of lines to add to <code>/etc/ntp.conf</code> to add. Check out https://www.digitalocean.com/community/tutorials/how-to-configure-ntp-for-use-in-the-ntp-pool-project-on-centos-7 for valid ntp.conf syntax.|
## Example Playbook

```yaml
    - hosts: servers
      roles:
        - ar_linux_ntp_client
```

## Author Information

|Author              |E-mail                   |
|:-------------------|:------------------------|
|Derek 'dRock' Halsey|derek.halsey@dinohead.com|

## License

MIT License

Copyright (c) 2019 Dinohead LLC

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

## Role Development Information

### Testing

### Git SCM
Please refer to the .gitignore file and update accordingly depending on your
development environment, etc.  The particular file was generated at 
[gitignore.io](https://www.gitignore.io/) and contains settings for the following:
  - Ansible
  - Python
  - Vim
  - Eclipse
  - IntelliJ IDEA
  - Linux
  - Windows
  
### Versioning
Please update [VERSION.md](./VERSION.md) as you release new versions of your role and try to
abide by [Semantic Versioning](http://semver.org/spec/v2.0.0.html).

### Self-contained
Please try to keep this role as self-contained as possible such that it may be
simply installed (e.g. `ansible-galaxy install`) and applied as part of a 
playbook.

-  Build issues solved

https://access.redhat.com/discussions/4168901

Additionally, 389-ds is an interesting case because it is packaged as a "module", and is one of the very few modules which are entirely disabled in the default RHEL 8 configuration. Run "yum module list" to see the complete list of modules available (389-ds should be right at the top) and their current status. To get access to the packages in the "389-ds" module ("stream" version 1.4), run:

```
yum module enable 389-ds
```
For the other packages (except python3-argparse-manpage, I didn't find that at all on my system), run:

```
subscription-manager repos --enable codeready-builder-for-rhel-8-x86_64-rpms
```
```
  294  sudo yum module info idm:DL1
  295  sudo yum -y install @idm:DL1
  296  yum search 389-ds
  297  yum install 389-ds-base-devel.x86_64 -y
```
- kdb/db2.so
```
/usr/lib64/krb5/plugins/kdb/db2.so  provided by krb5-server on rhel 8

```

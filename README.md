### Objective

- setup cvxopt
  - build python 3.5.1 from source


### Usage

Here is a list of commands:

```
## tool version checks (vagrant, ansible)
$ vagrant version
Installed Version: 1.7.4
...
$ ansible --version
ansible 2.1.0 (devel 50dfd4b057) last updated 2016/02/07 13:39:55 (GMT +900)
  lib/ansible/modules/core: (detached HEAD e1ec52e365) last updated 2016/02/07 13:41:53 (GMT +900)
  lib/ansible/modules/extras: (detached HEAD 14a62fb5d6) last updated 2016/02/07 13:42:45 (GMT +900)
  config file =
  configured module search path = Default w/o overrides

## launch VM
$ vagrant up

## check ansible ssh connection
$ ansible -i hosts -u ubuntu -m ping all

## download tar sources
$ wget https://github.com/cvxopt/cvxopt/archive/1.1.8.tar.gz -O files/cvxopt-1.1.8.tar.gz
$ wget https://www.python.org/ftp/python/3.5.1/Python-3.5.1.tgz -O files/Python-3.5.1.tgz

## run ansible playbook
$ ansible-playbook -v -i hosts playbook.yml

## check if cvxopt installation works
$ ssh ubuntu@192.168.33.10 python3 cvxopt-1.1.8/examples/doc/chap8/lp.py
     pcost       dcost       gap    pres   dres   k/t
 0: -8.1000e+00 -1.8300e+01  4e+00  0e+00  8e-01  1e+00
 1: -8.8055e+00 -9.4357e+00  2e-01  1e-16  4e-02  3e-02
 2: -8.9981e+00 -9.0049e+00  2e-03  3e-16  5e-04  4e-04
 3: -9.0000e+00 -9.0000e+00  2e-05  3e-16  5e-06  4e-06
 4: -9.0000e+00 -9.0000e+00  2e-07  9e-17  5e-08  4e-08
Optimal solution found.

x =

[ 1.00e+00]
[ 1.00e+00]
```

### References

- https://github.com/cvxopt/cvxopt/blob/1.1.8/INSTALL
- https://docs.python.org/2/using/unix.html
- http://askubuntu.com/questions/417726/installing-a-comprehensive-lapack-implementation-under-ubuntu
- http://askubuntu.com/questions/472146/building-atlas-and-later-octave-w-atlas


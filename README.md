# include-test

```
---
- hosts: localhost
  roles:
    - role: test_role
    
```

Expected results:
```
PLAY [localhost] ***************************************************************

TASK [setup] *******************************************************************
Tuesday 02 August 2016  13:15:18 -0400 (0:00:00.085)       0:00:00.085 ********
ok: [localhost]

TASK [test_role : pre task] ****************************************************
Tuesday 02 August 2016  13:15:24 -0400 (0:00:05.763)       0:00:05.849 ********
changed: [localhost]

TASK [test_role : included task] ***********************************************
Tuesday 02 August 2016  13:15:24 -0400 (0:00:00.292)       0:00:06.141 ********
changed: [localhost]

TASK [test_role : post task] ***************************************************
Tuesday 02 August 2016  13:15:25 -0400 (0:00:00.226)       0:00:06.367 ********
changed: [localhost]

PLAY RECAP *********************************************************************
localhost                  : ok=4    changed=3    unreachable=0    failed=0

```

Observed results:
```
PLAY [localhost] ***************************************************************

TASK [setup] *******************************************************************
Tuesday 02 August 2016  13:11:59 -0400 (0:00:00.044)       0:00:00.044 ********
ok: [localhost]

TASK [test_role : pre task] ****************************************************
Tuesday 02 August 2016  13:12:04 -0400 (0:00:05.763)       0:00:05.808 ********
changed: [localhost]

PLAY RECAP *********************************************************************
localhost                  : ok=2    changed=1    unreachable=0    failed=0
```

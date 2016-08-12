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
Friday 12 August 2016  18:13:05 -0400 (0:00:00.084)       0:00:00.084 *********
ok: [localhost]

TASK [test_role : pre task] ****************************************************
Friday 12 August 2016  18:13:11 -0400 (0:00:05.828)       0:00:05.912 *********
changed: [localhost]

TASK [test_role : include task] ************************************************
Friday 12 August 2016  18:13:11 -0400 (0:00:00.237)       0:00:06.149 *********
included: /home/abutcher/include_test/roles/test_role/tasks/included.yml for localhost

TASK [test_role : included task] ***********************************************
Friday 12 August 2016  18:13:11 -0400 (0:00:00.026)       0:00:06.176 *********
changed: [localhost]

TASK [test_role : nested included task] ****************************************
Friday 12 August 2016  18:13:11 -0400 (0:00:00.192)       0:00:06.368 *********
included: /home/abutcher/include_test/roles/test_role/tasks/nested/main.yml for localhost

TASK [test_role : nested pre] **************************************************
Friday 12 August 2016  18:13:11 -0400 (0:00:00.039)       0:00:06.408 *********
changed: [localhost]

TASK [test_role : include] *****************************************************
Friday 12 August 2016  18:13:11 -0400 (0:00:00.211)       0:00:06.620 *********
included: /home/abutcher/include_test/roles/test_role/tasks/nested/extra_nested/extra_nested.yml for localhost

TASK [test_role : include] *****************************************************
Friday 12 August 2016  18:13:11 -0400 (0:00:00.056)       0:00:06.677 *********
included: /home/abutcher/include_test/roles/test_role/tasks/nested/extra_nested/extra_nested1.yml for localhost

TASK [test_role : extra nested 1] **********************************************
Friday 12 August 2016  18:13:11 -0400 (0:00:00.093)       0:00:06.770 *********
changed: [localhost]

TASK [test_role : include] *****************************************************
Friday 12 August 2016  18:13:12 -0400 (0:00:00.238)       0:00:07.009 *********
included: /home/abutcher/include_test/roles/test_role/tasks/nested/extra_nested/extra_nested2.yml for localhost

TASK [test_role : extra nested 2] **********************************************
Friday 12 August 2016  18:13:12 -0400 (0:00:00.102)       0:00:07.112 *********
changed: [localhost]

TASK [test_role : nested post] *************************************************
Friday 12 August 2016  18:13:12 -0400 (0:00:00.247)       0:00:07.359 *********
changed: [localhost]

TASK [test_role : post task] ***************************************************
Friday 12 August 2016  18:13:12 -0400 (0:00:00.182)       0:00:07.542 *********
changed: [localhost]

PLAY RECAP *********************************************************************
localhost                  : ok=13   changed=7    unreachable=0    failed=0
```

Results:

```
PLAY [localhost] ***************************************************************

TASK [setup] *******************************************************************
Friday 12 August 2016  18:12:20 -0400 (0:00:00.055)       0:00:00.055 *********
ok: [localhost]

TASK [test_role : pre task] ****************************************************
Friday 12 August 2016  18:12:26 -0400 (0:00:05.662)       0:00:05.717 *********
changed: [localhost]

TASK [test_role : included task] ***********************************************
Friday 12 August 2016  18:12:26 -0400 (0:00:00.302)       0:00:06.019 *********
changed: [localhost]

TASK [test_role : nested pre] **************************************************
Friday 12 August 2016  18:12:26 -0400 (0:00:00.213)       0:00:06.233 *********
changed: [localhost]

TASK [test_role : include] *****************************************************
Friday 12 August 2016  18:12:26 -0400 (0:00:00.219)       0:00:06.453 *********
included: /home/abutcher/include_test/roles/test_role/tasks/nested/extra_nested/extra_nested.yml for localhost

TASK [test_role : include] *****************************************************
Friday 12 August 2016  18:12:26 -0400 (0:00:00.154)       0:00:06.608 *********
included: /home/abutcher/include_test/roles/test_role/tasks/nested/extra_nested/extra_nested1.yml for localhost

TASK [test_role : extra nested 1] **********************************************
Friday 12 August 2016  18:12:27 -0400 (0:00:00.269)       0:00:06.878 *********
changed: [localhost]

PLAY RECAP *********************************************************************
localhost                  : ok=7    changed=4    unreachable=0    failed=0
```

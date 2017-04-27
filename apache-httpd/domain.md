# Apache Httpd prefork vs worker


## prefork
- Apache Multi-Processing Modules(MPM, 다중처리모듈)의 Prefork 와 Worker 방식의 비교
- 하나의 자식 프로세스가 하나의 쓰레드를 갖는 구조로, 자식 프로세스는 1024까지 늘일 수 있다.
- 한개의 자식 프로세스는 한 개의 연결을 담당한다.
- 프로세스가 생성되는 구조이므로 당연히 worker보다는 많은 메모리를 사용함.
- 프로세스간 메모리를 직접 공유하지 않으므로, 메모리 공간이 독립적이어서 안정적임
- httpd.conf에서 httpd-mpm.conf 파일을 include 시켜야 한다.
- httpd-mpm.conf 파일에서

```
  <IfModule mpm_prefork_module>
      StartServers 5
      MinSpareServers 5
      MaxSpareServers 10
      MaxClients 150
      MaxRequestsPerChild 0
  </IfModule>
```

## worker
- 자식 프로세스들이 여러개의 쓰레드를 갖을 수 있으며, 각 쓰레드는 한번에 한 연결을 담당함.
- Prefork보다 메모리 사용량이 적음. 통신량이 많은 서버에 적절함.
- 쓰레드 간에 메모리 공간을 공유함. 리소스 경합이 발생하지 않도록 주의 필요.

```
<IfModule mpm_worker_module>
    StartServers 2
    MaxClients 150
    MinSpareThreads 25
    MaxSpareThreads 75
    ThreadsPerChild 25
    MaxRequestsPerChild 0
</IfModule>
```

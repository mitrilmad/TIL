
## Race Condition
- Race conditions arise in software when an application depends on the sequence or timing of processes or threads for it to operate properly.
- Critical race conditions often happen when the processes or threads depend on some shared state. Operations upon shared states are critical sections that must be mutually exclusive.
- 두개 이상의 프로세스가 공통 자원을 병행적으로 읽거나 쓸 때, 공용 데이터에 대한 접근이 어떤 순서에 따라 이루어졌는지에 따라 그 실행 결과가 달라지는 상황.
- race condition 이 발생하게 되면 모든 프로세스에 원하는 결과가 발생하는 것을 보장 할 수 없다.

### mutual exclusion
- 두개 이상의 프로세스가 공용 데이터에 동시에 접근하는 것을 막는 것. 한 프로세스가 공용 데이터를 사용하고 있으면 다른 프로세스가 그 자원을 사용하지 못하도록 막는 것,
   다른 프로세스가 이미 공용 자원을 사용하고 있으면 이 프로세스가 그 자원을 사용하지 못하도록 막는것.

### critical section
- 프로세스 입장에서 공용 데이터에 접근하는 부분을 critical region or critical section 이라고 부름. 두 프로세스가 동시에 critical section에 들어가지 않도록 할 수 있으면 race condition 피할 수 있음.

### deadlock
- 상호배제(Mutual exclusion) : 프로세스들이 필요로 하는 자원에 대해 배타적인 통제권을 요구한다.
- 점유대기(Hold and wait) : 프로세스가 할당된 자원을 가진 상태에서 다른 자원을 기다린다.
- 비선점(No preemption) : 프로세스가 어떤 자원의 사용을 끝낼 때까지 그 자원을 뺏을 수 없다.
- 순환대기(Circular wait) : 각 프로세스는 순환적으로 다음 프로세스가 요구하는 자원을 가지고 있다.

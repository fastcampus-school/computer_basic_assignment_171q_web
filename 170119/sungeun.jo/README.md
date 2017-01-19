### 기술 부채(Technical debt)

1. AKA design debt/code debt

2. a concept in programming that reflects the extra development work that arises when code that is easy to implement in the short run is used instead of applying the best overall solution

1. 일반적인 '부채'가 이자를 내고 돈을 쓰는 시점을 당기는 것처럼 기술 부채는 기술적으로 해결되어야 할 문제들을 뒤로 미루고, 비즈니스 문제를 해결하는 시점을 당기는 것이다.

2. 특징
 - 돈을 빌리는 것과 달리 기술 부채는 빚을 지는 사람과 갚아야 할 사람이 다를 수도 있다. 어떤 사람이 코드를 리팩터링 하지 않은 채로 두면 그 부채는 다른 팀원이 갚을 수도 있고, 나의 후임이 갚아야 할 수도 있다. 
 - 돈을 빌리면 내가 어느 시점에 얼마를 갚아야 할지 정확히 알 수 있지만 기술 부채는 끝까지 해결하지 않아도 별다른 문제가 되지 않을 수도 있고, 폭탄이 되어 프로젝트를 망칠 수도 있다.

3. 원인
 - Business pressures
 - Lack of process or understanding
 - Lack of a test suite
 - Lack of collaboration 등 

 > 예
 > 설계된 것을 문서로 남기지 않는다.
 > 더 이상 사용되지 않는 DB의 항목을 지우지 않는다.
 > 반복되는 일(배포 등)을 자동화하지 않는다.
 > 긴급하게 스펙을 변경한다.

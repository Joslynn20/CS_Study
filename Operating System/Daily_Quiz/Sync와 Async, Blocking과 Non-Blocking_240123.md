> Blocking과 Non-Blocking의 차이는 **호출되는 함수가 제어권을 바로 넘겨주는지의 여부**입니다.

Blocking은 호출되는 함수가 자신의 작업을 마칠 때까지 제어권을 넘기지 않습니다. 이와 달리 Non-Blocking은 호출되는 함수가  자신의 작업을 마치는 것과 상관없이 바로 리턴하여 자신을 호출한 함수로 제어권을 넘깁니다. 따라서 Non-Blocking에서는 호출한 함수가 다른 작업을 할 수 있는 기회가 주어집니다.  

- 동기식 입출력: I/O 요청 후 입출력 작업이 완료된 후에 제어가 사용자 프로그램으로 넘어간다.
- 비동기식 입출력 : I/O 요청 후 입출력 작업이 끝나기를 기다리지 않고 제어가 사용자 프로그램으로 즉시 넘어가는 것을 뜻합니다.

> Synchronous와 Asynchronous의 차이는 **호출되는 함수의 작업 완료 여부를 신경쓰는지**의 여부입니다.

Synchronous는 호출하는 함수가 호출되는 함수의 작업 완료를 지속적으로 확인 및 결과값을 받자마자 처리하는 것을 의미합니다. Asynchronous의 경우, 호출하는 함수가 호출되는 함수의 작업완료를 신경쓰지 않습니다. 또한, 결과값을 반환받더라도 바로 실행하지 않을수 있습니다. 자바스크립트의 경우, 비동기 함수 호출로 인해 뒤죽박죽으로 실행될 수 있는 코드의 순서를 해결하기 위해 함수의 작업이 완료되면, 호출되는 함수가 전달 받은 callback 함수를 실행합니다.

**참고 설명**
자바스크립트에서 Asynchronous한 작업들을 많이 진행하는데, 메인 스레드가 싱글 스레드인 자바스크립트의 작업 환경에서 모든 함수들이 동기식으로 작업할 경우,  사용자는 그만큼의 대기 시간이 길어져 부정적인 사용자 경험을 제공할 수 있습니다.


Sync-Non-Blocking과 Async-Blocking 모두 발생 가능합니다. 

Sync-Non-Blocking의 경우 호출부에서 호출된 함수는 거의 바로 리턴합니다. 호출부에서는 다른 작업을 하면서도, polling 방식으로 피호출부의 작업 완료 여부를 계속해서 확인합니다.

Async-Blocking의 경우 보통 개발자가 의도적으로 구현했다기보단 Async-Non-Blocking 방식을 추구했으나 작업 과정 중 하나라도 Blocking으로 일어날 경우, Async-Blocking으로 동작하게 됩니다. 호출부에서 호출된 함수가 작업이 끝날 때까지 제어권은 호출된 함수가 가지고 있으며, 결과값을 리턴 시에도 바로 처리하지 않거나 callback 함수를 통해서 처리합니다. 

Async-Blocking의 경우 Node.js와 MySQL의 사용을 대표적인 예로 들 수 있습니다. 싱글스레드 기반 Node.js는 Async로 작업을진행하더라도 DB 호출 시 MySQL은 Blocking 방식으로 동작하므로, Async-Blocking으로 동작합니다. 
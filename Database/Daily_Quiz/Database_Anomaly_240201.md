# DB Anomaly
<hr>

한 릴레이션에 여러 엔티티의 속성들을 혼합할 경우 정보가 중복 저장될 수 있고, 중복된 정보로 인해 이상 현상이 발생할 수 있습니다. 잘 설계된 데이터베이스는 곧 정보의 이상현상이 발생하지 않도록 설계된 데이터베이스를 의미합니다.

이상현상은  Insertion Anomaly(삽입 이상), Modification Anomaly(갱신 이상), Deletion Anomaly(삭제 이상)으로 구분됩니다.

- Insertion Anomaly : 불필요한 정보를 함께 저장하지 않고서는 어떤 정보를 저장하는 것이 불가능한 상태를 의미합니다.  
- Modification Anomaly : 반복된 데이터 중에 일부를 갱신할 경우 데이터의 불일치가 발생하는 상태를 의미합니다.
- Deletion Anomaly : 필요한 정보를 함께 삭제하지 않고서는 어떠한 정보를 삭제하는 것이 불가한 상태를 의미합니다.

앞선 이상 현상은 정규화(Normalization)을 통해 방지할 수 있습니다. 

[참고 자료]
https://github.com/JaeYeopHan/Interview_Question_for_Beginner/tree/main/Database#%EC%A0%95%EA%B7%9C%ED%99%94%EC%97%90-%EB%8C%80%ED%95%B4%EC%84%9C
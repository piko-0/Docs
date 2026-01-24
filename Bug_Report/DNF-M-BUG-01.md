# [Bug-01] 특정 네트워크 지연 환경에서 '불사' 스킬 미발동

### 1. 결함 정보 (Information)
- **Issue ID:** DNF-M-BUG-01
- **Severity:** Critical (치명적)
- **Priority:** High (긴급)
- **Category:** 전투 로직 (TC No.2)
- **Environment:** Android 14 (Galaxy S24), Wi-Fi (Network Emulator 150ms 지연)

### 2. 결함 요약 (Summary)
남마법사 캐릭터가 사망에 이르는 피해를 입었을 때, 특정 네트워크 지연 상황에서 '불사' 패시브가 트리거되지 않고 즉시 사망 처리되는 현상.

### 3. 재현 단계 (Steps to Reproduce)
1. 던전(빌마르크 제국 실험장)에 남마법사 캐릭터로 진입.
2. 네트워크 에뮬레이터를 통해 지연 시간(Ping)을 150ms 이상으로 설정.
3. 캐릭터의 HP를 5% 이하로 조절한 후 몬스터에게 피격 유도.
4. '불사' 버프 활성화 여부 확인.

### 4. 실제 결과 (Actual Result)
- '불사' 로직이 가동되지 않고 캐릭터가 즉시 유령 상태(사망)로 전환됨.

### 5. 기대 결과 (Expected Result)
- 어떤 네트워크 환경에서도 HP가 0이 되는 순간 '불사' 무적 로직이 최우선으로 가동되어야 함.

### 6. 첨부 자료 (Evidence)
- [링크] `../Evidence/Bug_Videos/BUG_01_Immortal_Fail.mp4`

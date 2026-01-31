# 📸 Evidence: 결함 증거 자료 및 비교 분석

이 디렉토리는 **[BUG-001] 빙결사 가죽 방어구 마스터리 미적용** 결함을 증명하기 위한 조건별 스크린샷과 데이터를 관리합니다. 

---

## 🔍 검증 개요
* **목적:** 방어구 레벨 상승에 따른 마스터리 보너스(HP/MP) 반영 여부 확인
* **핵심 결함:** 고레벨(25Lv) 방어구 착용 시 저레벨(15Lv) 대비 HP 수치가 역전되거나 마스터리 보너스가 누락되는 로직 오류 발견

---

## 🖼 스크린샷 리스트 (클릭 시 이미지 열람)

| 순번 | 파일명 (Click to View) | 테스트 조건 | 주요 확인 사항 |
| :--- | :--- | :--- | :--- |
| **01** | [01_Equip_None_HP.png](./Screenshots/01_Equip_None_HP.png) | 장비 미착용 (Base) | 기본 HP 및 스탯 수치 (대조군) |
| **02** | [02_Equip_Armor_Lv15_HP.png](./Screenshots/02_Equip_Armor_Lv15_HP.png) | 15레벨 가죽 방어구 착용 | 마스터리에 의한 HP 상승분 확인 |
| **03** | [03_Equip_Armor_Lv15_StatDetail.png](./Screenshots/03_Equip_Armor_Lv15_StatDetail.png) | 15레벨 방어구 스탯 상세 | 가죽 마스터리 활성화 여부 및 세부 스탯 |
| **04** | [04_Equip_Armor_Lv25_HP.png](./Screenshots/04_Equip_Armor_Lv25_HP.png) | 25레벨 가죽 방어구 착용 | **[이슈]** 15레벨 대비 HP 상승폭 미달 혹은 역전 현상 |
| **05** | [05_Equip_Armor_Lv25_StatDetail.png](./Screenshots/05_Equip_Armor_Lv25_StatDetail.png) | 25레벨 방어구 스탯 상세 | **[결함]** 마스터리 계수 미적용 및 데이터 누락 증거 |

---

## 📊 결함 분석 결과 (Summary)

1. **HP 수치 역전 현상:** * 15레벨 방어구 착용 시보다 25레벨 방어구 착용 시 최종 HP가 낮게 측정되는 기현상 발견.
   * 이는 방어구 기본 스탯은 상승했으나, **레벨에 따른 마스터리 추가 계수**가 25레벨 데이터 테이블에서 누락되었음을 시사함.

2. **마스터리 로직 미작동:** * 상세 스탯창 확인 결과, 빙결사 전용 가죽 마스터리의 '물리 방어력' 및 '최대 HP %' 증가 옵션이 연산에서 완전히 제외됨을 확인.

---
[👈 Bug Report로 돌아가기](../Bug_Report/BUG-001_Armor_Mastery_Issue.md)

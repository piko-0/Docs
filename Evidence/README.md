# 📸 Evidence: 결함 증거 자료 및 비교 분석

이 디렉토리는 **[BUG-001] 빙결사 가죽 방어구 마스터리 미적용** 결함을 증명하기 위한 조건별 스크린샷과 데이터를 관리합니다. 

---

## 🔍 검증 개요
* **목적:** 방어구 레벨 상승에 따른 마스터리 보너스(HP/MP) 반영 여부 확인
* **핵심 결함:** 고레벨(25Lv) 방어구 착용 시 저레벨(15Lv) 대비 HP 수치가 역전되는 로직 오류 발견

---

## 🖼 스크린샷 리스트 (클릭 시 이미지 열람)

| 순번 | 파일명 (Click to View) | 테스트 조건 | 주요 확인 사항 |
| :--- | :--- | :--- | :--- |
| **01** | [01_Equip_None_HP.png](./Screenshots/01_Equip_None_HP.png) | 장비 미착용 (Base) | 기본 HP 수치 (대조군) |
| **02** | [02_Equip_Armor_Lv15_HP.png](./Screenshots/02_Equip_Armor_Lv15_HP.png) | 15레벨 가죽 상의 착용 | 마스터리에 의한 HP 상승분 확인 |
| **03** | [03_Equip_Armor_Lv15_StatDetail.png](./Screenshots/03_Equip_Armor_Lv15_StatDetail.png) | 15레벨 상의 상세 정보 | 가죽 마스터리 활성화 및 세부 스탯 |
| **04** | [04_Equip_Armor_Lv25_HP.png](./Screenshots/04_Equip_Armor_Lv25_HP.png) | 25레벨 가죽 상의 착용 | **[이슈]** 15레벨 대비 HP 수치 역전 확인 |
| **05** | [05_Equip_Armor_Lv25_StatDetail.png](./Screenshots/05_Equip_Armor_Lv25_StatDetail.png) | 25레벨 상의 상세 정보 | **[결함]** 마스터리 계수 미적용 증거 |

---

## 📑 Reference (자료 출처)
본 결함 분석에 사용된 에비던스(스크린샷 및 데이터)는 업데이트 당시 유저 제보를 통해 확인된 실제 사례를 바탕으로 QA 관점에서 재구성되었습니다.
* **Source:** [던전앤파이터 모바일 공식 커뮤니티 제보 게시글](https://dnfm.nexon.com/Community/Free/View/3356986)

---

## 📊 결함 분석 결과 (Summary)
1. **HP 수치 역전 현상:** 15레벨 상의 착용 시(14,018)보다 25레벨 상의 착용 시(13,914) 최종 HP가 낮게 측정됨.
2. **로직 오류 증명:** 상세 스탯 분석 결과, 25레벨 구간에서 가죽 마스터리의 '최대 HP %' 증가 계수가 연산에서 누락된 데이터 테이블 결함으로 판단됨.

---
[👈 Bug Report로 돌아가기](../Bug_Report/BUG-001_Armor_Mastery_Issue.md)
---
[👈 Bug Report로 돌아가기](../Bug_Report/BUG-001_Armor_Mastery_Issue.md)

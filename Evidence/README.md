# 📸 Evidence: 결함 증거 자료 및 비교 분석

이 디렉토리는 **[BUG-001] 빙결사 가죽 방어구 마스터리 미적용** 결함을 증명하기 위한 조건별 스크린샷과 데이터를 관리합니다. 

---

## 🔍 검증 개요
* **목적:** 방어구 레벨 상승에 따른 마스터리 보너스(HP/MP) 반영 여부 확인
* **핵심 결함:** 고레벨(25Lv) 방어구 착용 시 저레벨(15Lv) 대비 HP 수치가 역전되는 로직 오류 발견

---

## 🖼 증거 자료 상세 (Screenshots)

### 1. 기본 상태 (Base Line)
| 01. 장비 미착용 기본 HP (13,459) |
| :---: |
| ![01_Base](./Screenshots/01_Equip_None_HP.png) |

---

### 2. 정상 적용군 (15Lv Leather Top)
| 02. 15Lv 착용 HP (14,018) | 03. 15Lv 상세 정보 |
| :---: | :---: |
| ![02_Lv15_HP](./Screenshots/02_Equip_Armor_Lv15_HP.png) | ![03_Lv15_Detail](./Screenshots/03_Equip_Armor_Lv15_StatDetail.png) |
| **정상 상승 확인** | **마스터리 정상 활성화** |

---

### 3. 결함 발생군 (25Lv Leather Top)
| 04. 25Lv 착용 HP (13,914) | 05. 25Lv 상세 정보 |
| :---: | :---: |
| ![04_Lv25_HP](./Screenshots/04_Equip_Armor_Lv25_HP.png) | ![05_Lv25_Detail](./Screenshots/05_Equip_Armor_Lv25_StatDetail.png) |
| **[결함] 15Lv 대비 수치 역전** | **[결함] 마스터리 계수 누락** |

---

## 📑 Reference (자료 출처)
본 결함 분석에 사용된 데이터는 공식 커뮤니티의 제보 사례를 바탕으로 QA 관점에서 재구성되었습니다.
* **Source:** [던전앤파이터 모바일 공식 커뮤니티 제보 게시글](https://dnfm.nexon.com/Community/Free/View/3356986)

---

## 📊 결함 분석 결과 (Summary)
1. **HP 수치 역전 현상:** 15레벨 상의 착용 시(14,018)보다 25레벨 상의 착용 시(13,914) 최종 HP가 낮게 측정됨.
2. **로직 오류 증명:** 상세 스탯 분석 결과, 25레벨 구간에서 가죽 마스터리의 '최대 HP %' 증가 계수가 연산에서 누락된 데이터 테이블 결함으로 판단됨.

---
[👈 Bug Report로 돌아가기](../Bug_Report/BUG-001_Armor_Mastery_Issue.md)

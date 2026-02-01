# 📸 Evidence: 결함 증거 자료 및 비교 분석

이 디렉토리는 빙결사 핵심 결함(**방어구 마스터리 미적용** 및 **헤일스톰 타격 판정 누락**)을 증명하기 위한 조건별 스크린샷과 데이터를 관리합니다.

---

## 🔍 [BUG-001] 가죽 방어구 마스터리 결함
* **핵심 이슈:** 고레벨(25Lv) 방어구 착용 시 저레벨(15Lv) 대비 HP 수치가 역전되는 로직 오류.

### 1. 기본 상태 및 정상 적용 비교 (Base vs 15Lv)
| 01. 장비 미착용 기본 HP (13,459) | 02. 15Lv 착용 HP (14,018) | 03. 15Lv 상세 정보 |
| :---: | :---: | :---: |
| ![01_Base](./Screenshots/01_Equip_None_HP.png) | ![02_Lv15_HP](./Screenshots/02_Equip_Armor_Lv15_HP.png) | ![03_Lv15_Detail](./Screenshots/03_Equip_Armor_Lv15_StatDetail.png) |
| **기준점 확인** | **비정상 상승 (+559)** | **마스터리 비활성화** |

### 2. 결함 발생 확인 (25Lv 스탯 역전)
| 04. 25Lv 착용 HP (13,914) | 05. 25Lv 상세 정보 |
| :---: | :---: |
| ![04_Lv25_HP](./Screenshots/04_Equip_Armor_Lv25_HP.png) | ![05_Lv25_Detail](./Screenshots/05_Equip_Armor_Lv25_StatDetail.png) |
| **[결함] 15Lv 대비 낮은 수치** | **[결함] 최대 HP % 계수 누락** |

---

## 🔍 [BUG-002] 헤일스톰 타격 판정 결함
* **핵심 이슈:** 추가 타격 판정 누락으로 인한 데미지 저하 현상 및 패치 후 정상화 검증.

### 1. 패치 전/후 데미지 리포트 비교
| 패치 전 (Damage Issue) | 패치 후 (Resolved) |
| :---: | :---: |
| ![Before](./Screenshots/Hailstorm_Damage_Before_Patch.png) | ![After](./Screenshots/Hailstorm_Damage_After_Patch.jpg) |
| **평균 데미지: 185,148** | **평균 데미지: 473,641,771** |

---

## 📊 결함 분석 요약 (Data Summary)

| 결함 ID | 분석 대상 | 주요 현상 | 원인 추정 |
| :--- | :--- | :--- | :--- |
| **BUG-001** | 방어구 마스터리 | 방어구 마스터리 미적용 현상 | 데이터 테이블 내 계수 값 누락 |
| **BUG-002** | 헤일스톰 스킬 | 평균 데미지 비정상 저하 (약 2,500% 차이) | 특정 상황 타격 판정 로직 오류 |

---

## 📑 Reference (자료 출처)
본 결함 분석에 사용된 데이터는 공식 커뮤니티의 실제 제보 사례를 바탕으로 QA 관점에서 재구성되었습니다.
* **Source:** [던전앤파이터 모바일 공식 커뮤니티 제보 게시글](https://dnfm.nexon.com/Community/Free/View/3356986)

---
[👈 Bug Report 리스트로 돌아가기](../Bug_Report/README.md)

# 📂 Another Portfolio

본 저장소는 게임 분석 역량과 프로토타입 구현 능력을 증명하기 위한 자료를 담고 있습니다.

## 1. 블루아카이브 시스템 분석서
* **분석 주제**: "블루아카이브가 장기적으로 운영될 수밖에 없는 특별한 시스템은 무엇인가?"
* **주요 내용**: 장기 흥행 중인 라이브 게임의 구조와 운영 시스템에 대한 심층 분석 및 설명 자료
* **문서 확인**: [BlueArchive_System_Analysis.pdf](./BlueArchive_System_Analysis.pdf)

## 2. 서사형 2D 플랫포머 프로토타입
* **작업 내용**: 팀 프로젝트 기획안을 바탕으로 직접 1인 구현 및 기능 검증 완료
* **활용 에셋**: 
    * [심플 2D 플랫포머 에셋 팩](https://assetstore.unity.com/packages/2d/characters/simple-2d-platformer-assets-pack-188518) 기반 캐릭터 및 맵 구성
    * [탑다운 2D RPG 에셋 팩](https://assetstore.unity.com/packages/2d/characters/top-down-2d-rpg-assets-pack-188718) 기반 NPC 상호작용 시스템 구축
    
* **영상 재생**: [Prototype_play.mp4](./Prototype_play.mp4)

## 🛠 주요 구현 기술 (Core Logic)

프로토타입 제작 시 핵심적으로 설계하고 검증한 로직입니다.

### 1. 지능형 몬스터 AI 및 지형 인식 (`EnemyMove.cs`)
* **지형 인식**: `Raycast2D`를 활용하여 전방의 낭떠러지를 감지하고 자동으로 방향을 전환하는 정찰 로직 구현.
* **상태 제어**: `Invoke`와 `Random.Range`를 결합하여 불규칙한 이동 및 대기 패턴 생성.

### 2. 플랫폼 물리 기반 조작 (`PlayerMove.cs`)
* **점프 메커니즘**: `Raycast`를 통해 바닥 접지 상태를 정밀하게 체크하여 무한 점프 방지 및 조작감 최적화.
* **상호작용**: 적의 상단을 밟았을 때 반동 점프(`AddForce`)와 공격 판정을 동시에 처리하는 밟기 로직 구현.

### 3. 상태 기반 서사 시스템 (`PlayerTalk.cs`)
* **NPC 상호작용**: 트리거(Trigger) 범위를 활용한 NPC 접근 감지 및 대화 시스템 구축.
* **이동 제한**: 대화 중 플레이어의 입력을 일시적으로 제한(Component 활성/비활성)하여 게임의 흐름(Flow) 제어.

### 4. 중앙 집중식 게임 관리 (`GameManager.cs`)
* **스테이지 라이프사이클**: 스테이지 전환, 플레이어 리스폰, 점수 합산 및 UI 업데이트를 싱글톤 패턴과 유사하게 중앙 관리.
* **예외 처리**: 체력 0 도달 시 사망 연출 및 게임 오버 팝업을 통한 재시작 프로세스 구현.

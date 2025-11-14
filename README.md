# 🐞 Issue Management System (IMS)

> **소프트웨어 개발 과정에서 발생하는 다양한 이슈(버그, 기능 개선 요청 등)를 체계적으로 관리하는 시스템이다.**
> JIRA, Bugzilla, TRAC 등의 상용 도구를 벤치마킹했으며, **OOA & OOD(객체지향 분석 및 설계)** 원칙을 준수하여 개발했다.

<br>

## ❓ Project Overview
이 프로젝트는 개발 프로젝트 내에서 발생하는 이슈를 효율적으로 추적하고 관리하기 위한 도구이다. 관리자, PL, 개발자, 테스터 등 역할에 따른 권한 분리와 이슈의 생명주기 관리를 핵심 목표로 한다.

<br>

## 🙌 Key Functions

### 1️⃣ 계정 및 프로젝트 관리 (Account Management)
- **Admin**은 프로젝트를 생성하고 관리한다.
- 프로젝트에 참여할 사용자들을 배정하고, 각 사용자에게 역할을 부여한다.
- **Roles**
  - `Admin`: 시스템 및 프로젝트 관리
  - `PL (Project Leader)`: 이슈 배정 및 상태 관리
  - `Developer`: 할당된 이슈 처리 및 코멘트 작성
  - `Tester`: 이슈 발견 및 등록

### 2️⃣ 이슈 등록 (Issue Registration)
- **Tester**는 새로운 이슈를 시스템에 등록할 수 있다.
- **입력 정보:** 이슈 타입, 제목, 상세 설명, 우선순위 등
- **초기 상태:** 이슈 등록 시 자동으로 상태는 `New`가 되며, 보고자는 해당 테스터로 기록된다.

### 3️⃣ 이슈 검색 및 조회 (Browse & Search)
- 다양한 필터를 통해 원하는 이슈를 빠르게 찾을 수 있다.
- **검색 조건:** 타입, 담당자, 보고자, 우선순위, 현재 상태
- 검색 결과는 가독성 높은 테이블 형태로 표시된다.

### 4️⃣ 상태 관리 및 배정 (State & Assignment)
- **PL**은 이슈의 상태를 변경하고 개발자에게 업무를 할당할 권한을 가진다.
- **State Workflow**
  - `New` → `Assigned` (개발자 배정)
  - `Assigned` → `Resolved` (해결 완료)
  - `Resolved` → `Closed` (검증 완료 및 종료)
  - `Reopened` (재발생 시)

### 5️⃣ 커뮤니케이션 (Comments)
- 이슈 해결 과정에서 사용자 간 코멘트를 주고받을 수 있다.
- 각 코멘트에는 작성자의 ID, 역할, 작성 시간이 타임스탬프로 기록된다.

<br>

## 🛠 System Design (OOA & OOD)

본 프로젝트는 철저한 객체지향 분석 및 설계를 기반으로 구현되었다.

### 1. Use Case Diagram
> 사용자 역할(Actor)에 따른 시스템의 기능을 정의했다.
![Use Case Diagram](./images/usecase_diagram.png)

### 2. Domain Model
> 시스템 내의 개념적 클래스와 관계를 도출했다.
![Domain Model](./images/domain_model.png)

### 3. Sequence Diagram
> 주요 기능의 실행 흐름과 객체 간 상호작용을 정의했다.

**3.1 로그인 및 회원가입**
![Login Sequence](./images/sequence_login.png)
![Signup Sequence](./images/sequence_signup.png)

**3.2 이슈 생성 및 조회**
![Issue Sequence](./images/sequence_issue.png)

### 4. Class Diagram
> 시스템의 정적 구조와 클래스 간의 관계를 설계했다.
![Class Diagram1](./images/class_diagram1.png)
![Class Diagram2](./images/class_diagram2.png)

<br>

## 📸 Screenshots & Scenarios

### 🔐 Authentication
| 로그인 화면 | 회원가입 화면 | 비밀번호 찾기 |
|:---:|:---:|:---:|
| ![Login](./images/login.png) | ![Signup](./images/signup.png) | ![FindPW](./images/findpw.png) |

### 👤 Role-Based Scenarios

#### 1. Admin Scenario
> 프로젝트 생성 및 Team Member 배정 과정이다.
> 
|  |  |  |
|:---:|:---:|:---:|
| ![Admin_screen1](./images/admin_screen1.png) | ![Admin_screen2](./images/admin_screen2.png) | ![Admin_screen3](./images/admin_screen3.png) |
| ![Admin_screen4](./images/admin_screen4.png) | ![Admin_screen5](./images/admin_screen5.png) | ![Admin_screen6](./images/admin_screen6.png) |
| ![Admin_screen7](./images/admin_screen7.png) | ![Admin_screen8](./images/admin_screen8.png) |  |

#### 2. Tester Scenario
> 버그 발견 후 이슈 등록(New) 및 내가 등록한 이슈를 조회하는 화면이다.

**이슈 등록**
|  |  |  |
|:---:|:---:|:---:|
| ![Tester_screen1](./images/tester_screen1.png) | ![Tester_screen2](./images/tester_screen2.png) |
|  ![Tester_screen3](./images/tester_screen3.png) | ![Tester_screen4](./images/tester_screen4.png) |

**이슈 조회**
|  |  |  |
|:---:|:---:|:---:|
| ![Browse1](./images/browse1.png) | ![Browse2](./images/browse2.png) |
| ![Browse_tester1](./images/browse_tester1.png) | ![Browse_tester2](./images/browse_tester2.png) |

#### 3. PL (Project Leader) Scenario
> 등록된 이슈를 확인한 뒤 개발자를 배정(Assigned)하고 상태를 변경한다.

|  |  |  |
|:---:|:---:|:---:|
| ![Pl_screen1](./images/pl_screen1.png) | ![Pl_screen2](./images/pl_screen2.png) | ![Pl_screen3](./images/pl_screen3.png) |
| ![Pl_screen4](./images/pl_screen4.png) | ![Pl_screen5](./images/pl_screen5.png) | ![Pl_screen6](./images/pl_screen6.png) |
| ![Pl_screen7](./images/pl_screen7.png) | ![Pl_screen8](./images/pl_screen8.png) | ![Pl_screen9](./images/pl_screen9.png) |

#### 4. Developer Scenario
> 자신에게 배정된 이슈를 확인하고 코멘트를 작성하여 해결 과정을 공유한다.

|  |  |  |
|:---:|:---:|:---:|
| ![Dev_screen1](./images/dev_screen1.png) | ![Dev_screen2](./images/dev_screen2.png) | 

#### 5. Issue Details

|  |  |  |
|:---:|:---:|:---:|
| ![Issue1](./images/issue1.png) | ![Issue2](./images/issue2.png) | ![Issue3](./images/issue3.png) |

#### 6. Comments

|  |  |  |
|:---:|:---:|:---:|
| ![Comment1](./images/comment1.png) | ![Comment2](./images/comment2.png) |

<br>

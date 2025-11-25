# 1. VPC 네트워크 설계 (Public/Private Subnet)

## 📌 개요
AWS 클라우드에서 격리된 사설 네트워크 공간인 **VPC**를 설계하고, 외부 접속이 가능한 **Public Subnet**과 외부 접속이 차단된 **Private Subnet**을 구성하는 실습입니다.

## 🧱 아키텍처 구성
### 1. 구성 요소
* **VPC:** CIDR 블록 10.0.0.0/16을 사용하여 사설 네트워크 정의.
* **Subnet:** 2개의 Public Subnet (각 AZ에 1개), 2개의 Private Subnet (각 AZ에 1개) 구성.
* **Internet Gateway (IGW):** Public Subnet의 EC2가 인터넷과 통신할 수 있도록 VPC에 연결.
* **NAT Gateway:** Private Subnet의 EC2가 외부(인터넷)로는 통신하되, 외부에서 직접 접근할 수 없도록 구성. Public Subnet에 배치.
* **Route Table:**
    * **Public Route Table:** 0.0.0.0/0 트래픽을 IGW로 라우팅.
    * **Private Route Table:** 0.0.0.0/0 트래픽을 NAT Gateway로 라우팅.
* **Security Group:** 각 리소스에 대한 인바운드/아웃바운드 트래픽 제어.

### 2. 아키텍처 다이어그램
*(실제 실습 시 직접 그린 다이어그램 이미지 파일을 이 폴더에 업로드하고 링크를 대체하세요.)*

## ✅ 주요 학습 내용 및 검증
* **VPC의 기본 개념** 및 CIDR 블록의 서브넷팅 이해.
* **IGW와 NAT Gateway**의 명확한 역할 분리 및 설정 방법.
* Route Table을 통한 **트래픽 라우팅** 제어.
* Private Subnet에 배치된 EC2가 **NAT Gateway를 통해 패치 업데이트** 등을 성공적으로 수행할 수 있는지 검증.

---

### 3. 커밋하여 저장

1.  스크롤을 내려서 **'Commit changes'** 섹션을 확인합니다.
2.  **Commit message**는 기본값(예: `Create VPC_Design/README.md`) 그대로 두어도 됩니다.
3.  **'Commit new file'** 버튼을 클릭하여 파일을 저장하고 폴더를 생성합니다.

### 4. 나머지 두 폴더/파일 생성

위의 1~3단계를 반복하여 나머지 두 실습 폴더와 `README.md` 파일도 만들어 주세요.

| 폴더/파일명 | 파일 내용 (제목만 임시로) |
| :--- | :--- |
| `EC2_ALB_ASG/README.md` | `# 2. EC2 기반 고가용성 웹 서비스 구축 (ALB + AutoScaling)` |
| `S3_CloudFront_Static_Website/README.md` | `# 3. S3를 활용한 정적 웹사이트 배포 (CloudFront 적용)` |

---

세 개의 폴더가 모두 생성되면, 이제 **실습 2**의 상세 내용인 **EC2 + ALB + AutoScaling** 문서를 작성해 보겠습니다. 모두 만드시면 알려주세요!

# 3. S3를 활용한 정적 웹사이트 배포 (CloudFront 적용)

## 📌 개요
비용 효율적인 **Amazon S3**를 스토리지로 사용하고, **Amazon CloudFront (CDN)**를 통해 콘텐츠 전송 속도를 높이고 보안을 강화하여 정적 웹사이트를 전 세계 사용자에게 배포하는 실습입니다.

## 🧱 아키텍처 구성
### 1. 구성 요소
* **Amazon S3 Bucket:** 정적 파일(HTML, CSS, JS, 이미지)을 저장하는 원본(Origin) 서버 역할.
* **CloudFront Distribution (CDN):**
    * 전 세계 엣지 로케이션에 S3 콘텐츠를 캐싱하여 사용자에게 **최저 지연 시간**으로 콘텐츠를 전달.
    * **Origin Access Control (OAC)** 또는 **Origin Access Identity (OAI)**를 설정하여 CloudFront를 통해서만 S3 버킷에 접근 가능하도록 보안 강화. (S3 버킷의 퍼블릭 접근 차단)
* **Route 53 (선택 사항):** 도메인을 연결하여 CloudFront URL 대신 사용자 지정 도메인으로 서비스 제공.

### 2. 아키텍처 다이어그램
[Image of AWS Architecture Diagram for Static Website Hosting using S3 and CloudFront]
*(직접 그린 S3와 CloudFront 연결 다이어그램 이미지 파일을 이 폴더에 업로드하고 링크를 대체하세요.)*

## ✅ 주요 학습 내용 및 검증
* **S3 정적 웹사이트 호스팅**의 설정 및 S3 버킷 정책 이해.
* **CDN (Content Delivery Network)**의 역할 및 성능 최적화 원리 이해.
* **OAC/OAI 설정**을 통한 S3 버킷에 대한 직접 접근을 차단하고 **보안을 강화**하는 방법.
* **캐싱 동작 검증:** CloudFront URL을 통해 접속했을 때 S3가 아닌 엣지 로케이션에서 콘텐츠가 제공되는지 확인.
* 최종 **CloudFront Domain Name**을 통한 웹사이트 접속 성공 확인.

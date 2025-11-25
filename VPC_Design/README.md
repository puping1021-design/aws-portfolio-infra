# AWS マルチAZ Webアーキテクチャ  
VPC + Public/Private Subnet + NAT Gateway + ALB + EC2

本プロジェクトは、AWS における代表的な **高可用性（HA）Webアーキテクチャ** を  
実際に構築することで、ネットワーク・セキュリティ・負荷分散の基礎を理解することを目的としています。

---

## 🏗 アーキテクチャ図
![AWS Architecture](./aws_architecture.png)

---

## 🎯 学習目的
- AWS ネットワーク基礎の理解  
- Public / Private Subnet の分離  
- Application Load Balancer による負荷分散  
- NAT Gateway 経由のアウトバウンド通信  
- マルチAZ構成による高可用性  
- ルートテーブル / セキュリティグループ設定の理解  

---

## 🔧 使用サービス
### ネットワーク
- VPC（10.0.0.0/16）  
- Public Subnet (1a, 1c)  
- Private Subnet (1a, 1c)  
- Internet Gateway  
- NAT Gateway  
- Route Table (Public / Private)

### コンピューティング
- EC2（Private Subnet - App Server）  
- Bastion Host（任意）

### ロードバランサ
- ALB（Application Load Balancer）

---

## 🌐 トラフィックフロー
1. 利用者 → ALB  
2. ALB → Private Subnet 内の EC2  
3. EC2 はインターネットへ直接出られない  
4. アップデート時は NAT Gateway 経由  
5. Public Subnet は IGW を介してインターネットへ直接接続  

---

## 📘 ルーティング設定
### Public Route Table

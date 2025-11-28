# AWS 基礎演習ポートフォリオ

本リポジトリでは、AWS の主要サービス（VPC、EC2、S3、CloudFront など）を用いて構築した  
3つの基礎アーキテクチャ演習の成果物をまとめています。

各演習ごとにアーキテクチャ設計図、実装手順、学習ポイントを整理し、  
クラウドインフラの基礎理解を深めることを目的としています。

---

## 演習一覧

| No | 演習テーマ | 主な AWS サービス | リンク |
| :---: | :--- | :--- | :--- |
| 1 | VPC ネットワーク設計 | VPC, Subnet, IGW, NAT Gateway, Route Table | [VPC 設計演習の詳細](./VPC_Design/README.md) |
| 2 | 高可用性 Web サービス構築 | EC2, ALB, Auto Scaling, Multi-AZ | [EC2/ALB/ASG 演習の詳細](./EC2_ALB_ASG/README.md) |
| 3 | 静的 Web サイト配信 | S3, CloudFront（CDN）, OAC | [S3/CloudFront 演習の詳細](./S3_CloudFront_Static_Website/README.md) |

---

## リポジトリ構成

aws-portfolio-infra
├── README.md（本ドキュメント）
├── VPC_Design
├── EC2_ALB_ASG
└── S3_CloudFront_Static_Website

# 2. EC2 ベースの自動スケーリング Web サービス構築（ALB + Auto Scaling Group）

本プロジェクトでは、事前に構築した Multi-AZ VPC 環境上に  
Application Load Balancer（ALB）と Auto Scaling Group（ASG）を組み合わせ、  
トラフィック量に応じてサーバー数を自動的に調整し、障害発生時には自動で復旧する  
「弾力性（Elasticity）」と「高可用性（High Availability）」を備えた Web サービスを構築しました。

---

## アーキテクチャ図
![ALB と ASG を利用した Web アーキテクチャ図](./alb_asg_architecture.png)

---

## 学習目標

- 自動スケーリング（Elasticity）の実現：トラフィックに応じて EC2 台数を自動調整  
- 自己修復（Self-Healing）：インスタンス障害を ASG が検知し自動置換  
- 負荷分散の理解：ALB を用いて複数 AZ に跨る EC2 へトラフィックを分散  
- Launch Template を利用したサーバー構成の標準化と自動化  

---

## 使用した AWS サービス

### ロードバランシング & 自動スケーリング
- Application Load Balancer（ALB）：L7 レベルの負荷分散およびヘルスチェック  
- Target Group：ALB がトラフィックを転送する EC2 インスタンス群  
- Launch Template：ASG によって起動される EC2 インスタンスの設定（User Data を含む）  
- Auto Scaling Group（ASG）：最小／最大／希望容量の管理およびスケーリングポリシーの実行  

### コンピューティング & ネットワーク
- EC2（Web Server）：ASG により管理される Web サーバー  
- VPC、Public Subnet、Security Group（前演習で構築済み）  

---

## トラフィックおよびスケーリングの流れ

1. 利用者が ALB の DNS にアクセス  
2. ALB が Target Group 内の正常な EC2（Public Subnet）へトラフィックを分散  
3. CPU 使用率などのメトリクスを基に ASG が自動的にスケールアウト／スケールイン  
4. ヘルスチェックが失敗したインスタンスは ASG によって即座に置き換えられ、サービス継続性を確保  

---

## 主要な学習ポイント

- クラウドの弾力性（Elasticity）を実際に構築し理解  
- ASG と Multi-AZ 構成によるフォールトトレランス（Fault Tolerance）の実現  
- ALB のヘルスチェックと負荷分散メカニズムの理解  
- Launch Template を用いたサーバー自動デプロイの設定経験  


# ☁️ Projeto Final do Programa de Bolsas da Compass UOL | AWS e DevSecOps - Infraestrutura AWS para um eCommerce da Fast Engineering

## 📋 Integrantes do Projeto
- Bruno Silveira: https://github.com/brunohsilv
- Edilson Maria: https://github.com/EdilsonMaria
- Felipe Santos: https://github.com/Felipe53650
- Laura Capssa: https://github.com/laura-capssa
- Juan paulo: https://github.com/juanfricke

---

## 🔎 **CASE:**
A Fast Engineering S/A é uma empresa de e-commerce que está crescendo rapidamente. Desde o início do ano, os acessos e compras estão aumentando em 20% a cada mês. A arquitetura on-premise atual, composta por servidores dedicados para aplicação, web server e banco de dados, não suporta mais a alta demanda de acessos e compras. Diante disso, a solução encontrada foi migrar o ambiente para a nuvem AWS, garantindo escalabilidade, segurança e alta disponibilidade para o e-commerce.

### **Arquitetura Atual**
Atualmente, o ambiente on-premise consiste em:
- **1 servidor para Banco de Dados MySQL**
- **1 servidor para aplicação (React)**
- **1 servidor de Web Server**, que também armazena arquivos estáticos como fotos e links.

<img src="/imgs/arquitetura_atual.png">

---

## 🆕 **Nova Arquitetura em Cloud (AWS)**

A solução de migração envolve a implementação de uma arquitetura na AWS, projetada para garantir alta disponibilidade, escalabilidade e segurança.

![Diagrama da Arquitetura](link_para_diagrama_arquitetura.png) <!-- Substitua pelo link do diagrama final -->

### **Descrição da Nova Arquitetura:**

1. **Usuário acessa o site do e-commerce da Fast Engineering** através do serviço **AWS Route 53**, que faz o roteamento do tráfego DNS.
   
2. **AWS WAF** é utilizado para garantir a segurança, protegendo contra ataques e acessos maliciosos.
   
3. O conteúdo estático (como fotos e links) será distribuído globalmente utilizando **Amazon CloudFront** para reduzir a latência e melhorar a experiência do usuário.
   
4. O tráfego chega a um **Load Balancer (Elastic Load Balancer - ELB)**, que distribui as solicitações para os containers e microsserviços.

5. **Aplicação em Containers gerenciados pelo EKS (Elastic Kubernetes Service)** utilizando **AWS Fargate**. 
    - **Pods rodando o front-end (React)**.
    - **Pods rodando um Web Server (Nginx)** para os arquivos estáticos que estarão armazenados em **Amazon S3** e compartilhados com **Amazon EFS** (Elastic File System).

6. O banco de dados será migrado para **Amazon RDS (MySQL)** com configuração de Multi-AZ, garantindo alta disponibilidade e backups automáticos.

7. **AWS CodePipeline** e **AWS CodeDeploy** serão usados para a entrega contínua (CI/CD) da aplicação, garantindo automatização e eficiência nas atualizações.

8. **AWS CloudWatch** será configurado para monitorar a saúde dos serviços e enviar alertas sobre qualquer anomalia.

9. O gerenciamento de permissões será feito com **AWS IAM** para garantir segurança e controle de acessos.

<img src="/imgs/arquitetura_aws.png">

<img src="/imgs/arquitetura_kubernetes.png">

---

## 🧰 **Serviços e Recursos Usados na Arquitetura**

1. **AWS Route 53**: Gerencia o tráfego DNS e direciona os usuários para a aplicação.
   
2. **AWS WAF (Web Application Firewall)**: Proporciona segurança contra ameaças da web, como ataques DDoS e injeções de SQL.
   
3. **Amazon CloudFront**: Distribui globalmente os conteúdos estáticos da aplicação, diminuindo a latência.

4. **Elastic Load Balancer (ELB)**: Balanceia a carga entre as instâncias de aplicação, garantindo alta disponibilidade.

5. **Amazon EKS (Elastic Kubernetes Service)**: Serviço gerenciado de Kubernetes, utilizado para orquestração dos containers da aplicação e do web server.

6. **AWS Fargate**: Serviço de containers serverless, que executa os pods de aplicação sem a necessidade de gerenciar servidores.

7. **Amazon S3**: Armazena os arquivos estáticos como imagens, vídeos e documentos de forma escalável e segura.

8. **Amazon EFS (Elastic File System)**: Sistema de arquivos elástico, compartilhado entre os pods de web server.

9. **Amazon RDS (MySQL)**: Banco de dados gerenciado, com configuração Multi-AZ para alta disponibilidade e escalabilidade.

10. **AWS CodePipeline e AWS CodeDeploy**: Ferramentas de CI/CD para automação de deploys e integração contínua.

11. **AWS CloudWatch**: Monitora métricas dos recursos e serviços da AWS, enviando alertas em caso de falhas ou picos de uso.

12. **AWS IAM (Identity and Access Management)**: Gerenciamento de identidades e permissões para acesso seguro aos recursos AWS.

---

## 💰 **Orçamento**
<!-- Previsão de custos será detalhada após a migração -->
A ser anexado.

---

## 📬 **Cronograma**
<!-- Dividir o cronograma da migração por etapas -->
A ser anexado.

---

## 📑 **Referências**
- [AWS Route 53](https://aws.amazon.com/route53/)
- [AWS WAF](https://aws.amazon.com/waf/)
- [Amazon CloudFront](https://aws.amazon.com/cloudfront/)
- [Elastic Load Balancer](https://aws.amazon.com/elasticloadbalancing/)
- [Amazon EKS](https://aws.amazon.com/eks/)
- [AWS Fargate](https://aws.amazon.com/fargate/)
- [Amazon S3](https://aws.amazon.com/s3/)
- [Amazon RDS](https://aws.amazon.com/rds/)
- [AWS CodePipeline](https://aws.amazon.com/codepipeline/)
- [AWS CloudWatch](https://aws.amazon.com/cloudwatch/)
- [AWS IAM](https://aws.amazon.com/iam/)

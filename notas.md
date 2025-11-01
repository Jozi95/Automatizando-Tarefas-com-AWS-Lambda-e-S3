# 🧾 Notas do Desafio - AWS Lambda e S3

## 📍 Etapas Realizadas
1. Criação do bucket S3 para upload de arquivos.
2. Criação da função Lambda no console AWS.
3. Adição de gatilho do S3 para a função Lambda.
4. Testes de upload e verificação dos logs no CloudWatch.

---

## ⚙️ Permissões IAM
A função Lambda precisa de uma **IAM Role** com as seguintes permissões:
- `AWSLambdaBasicExecutionRole` (para gravar logs no CloudWatch)
- `AmazonS3ReadOnlyAccess` (para ler informações do bucket)

---

## 🧰 Comandos Úteis (via AWS CLI)
```bash
# Listar buckets S3
aws s3 ls

# Enviar um arquivo de teste
aws s3 cp teste.txt s3://nome-do-seu-bucket/

# Ver logs no CloudWatch
aws logs describe-log-groups


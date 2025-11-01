
- **README.md** → Documentação completa do projeto.  
- **/src/lambda_function.py** → Código da função Lambda.  
- **notas.md** → Anotações pessoais e comandos úteis utilizados no desenvolvimento.  

---

## 🚀 Passo a Passo da Implementação

1. **Criação do bucket S3**  
   - Criar um bucket para armazenar os arquivos de teste.  
   - Ativar a opção de eventos do S3 para acionar a função Lambda em uploads.  

2. **Criação da Função Lambda**  
   - Criar a função no **AWS Lambda** com runtime **Python 3.x**.  
   - Adicionar o código responsável por registrar logs no **CloudWatch**.  

   Exemplo de código:
   ```python
   import json
   import logging

   logger = logging.getLogger()
   logger.setLevel(logging.INFO)

   def lambda_handler(event, context):
       logger.info("Evento recebido do S3:")
       logger.info(json.dumps(event))
       return {
           'statusCode': 200,
           'body': json.dumps('Logs gerados com sucesso!')
       }


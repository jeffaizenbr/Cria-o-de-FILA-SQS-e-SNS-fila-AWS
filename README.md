# Cria-o-de-FILA-SQS-e-SNS-fila-AWS

## exemplo de solicitação : 

Solicito a criação de duas filas:
 
data-prod-curator-raw-to-mutable

data-beta-curator-raw-to-mutable
 
E adicionar assinatura nos tópicos de SNS (para essas filas) respectivamente:
 
data-prod-profile-people-consolidation

data-beta-profile-people-consolidation

## pesquisar SQS  (simple query service)


```bash
create queue
```
## search sns
create and edit aceess policy
```bash
{
  "Version": "2008-10-17",
  "Id": "__default_policy_ID",
  "Statement": [
    {
      "Sid": "__default_statement_ID",
      "Effect": "Allow",
      "Principal": {
        "AWS": "*"
      },
      "Action": [
        "SNS:GetTopicAttributes",
        "SNS:SetTopicAttributes",
        "SNS:AddPermission",
        "SNS:RemovePermission",
        "SNS:DeleteTopic",
        "SNS:Subscribe",
        "SNS:ListSubscriptionsByTopic",
        "SNS:Publish",
        "SNS:Receive"
      ],
      "Resource": "arn:aws:sns:us-east-1:723891204374:AWS-Notify",
      "Condition": {
        "StringEquals": {
          "AWS:SourceOwner": "723891204374"
        }
      }
    }
  ]
}
```


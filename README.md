# challenge_four
Análise do código abaixo:

![image](https://user-images.githubusercontent.com/69819910/90843643-7a6f2700-e338-11ea-8114-47c207039238.png)

1) O método faz um update na Agency, nos atributos "Opportunity__c" e "Type__c", a partir das informações obtidas de "this.salesforceContext".
Os asserts Assert.assert agency != null e assert agencyType != null tem o objetivo de verificar se a agency e agencyType são diferentes de null, para só depois prosseguir com os métodos put.
Após agency receber os atributos via put, realiza o post de agency, levando em conta que é necessário o token para realização da requisição com sucesso.
O último assert tem o objetivo de verificar o código de status da resposta da requisição post feita na linha anterior, comparando o valor recebido na resposta com "201".

2) As validações feitas no código estão marcadas em verde (3).
3) Ações: PUT nas linhas:
```
agency.put("Opportunity__c", this.salesforceContext.getOpportunityId());

e

agency.put("Type__c", agencyType.fields()
                .next()
                .getValue()
                .get(random.nextInt(agencyType.fields().next().getValue().size()))
                .toString()
                .replaceAll("^\"|\"$", ""));
```
e POST na linha:
```
ResponseEntity<String> responseAgencyRelationship = restUtils.post(
                String.format(SalesforceContext.SALESFORCE_OPPORTUNITY_AGENCY_PATH, StringUtils.EMPTY),
                agency,
                this.salesforceContext.getAuthorizationHeaderWithToken());
```

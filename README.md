# challenge_four
Análise do código abaixo:

![image](https://user-images.githubusercontent.com/69819910/90843643-7a6f2700-e338-11ea-8114-47c207039238.png)

1) As validações feitas no código estão marcadas em verde (3).
2) Ações: PUT nas linhas:
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

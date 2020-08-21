# challenge_four
Análise do código abaixo:

![image](https://user-images.githubusercontent.com/69819910/90843643-7a6f2700-e338-11ea-8114-47c207039238.png)

1) As validações feitas no código estão marcadas em verde (3).
2) Há uma ação feita pelo método PUT, nas linhas:
```
 agency.put("Type__c", agencyType.fields()
                .next()
                .getValue()
                .get(random.nextInt(agencyType.fields().next().getValue().size()))
                .toString()
                .replaceAll("^\"|\"$", ""));
                
e
                
 agency.put("Opportunity__c", this.salesforceContext.getOpportunityId());
```


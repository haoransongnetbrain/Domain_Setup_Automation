License Node Information REST API Design
========================================

GET /V1/System/nodeinfo
-----------------------

Call this API to get the overall system license node information.

User must have System Admin privilege to issue this API call.

Detail Information
------------------

\| Title: License Node Information API

\| Version: 10/09/2019

\| API Server URL: http(s)://IP Address of NetBrain Web API
Server/ServicesAPI/API/V1/System/nodeinfo

\| Authentication:

| **Type**              | **In**  | **Name**             |
|-----------------------|---------|----------------------|
| Bearer Authentication | Headers | Authentication token |

Request body (\*required)
-------------------------

\| No parameters required.

Query Parameters (\*required)
-----------------------------

\| No parameters required.

Headers
-------

\| Data Format Headers

| **Name**     | **Type** | **Description**            |
|--------------|----------|----------------------------|
| Content-Type | String   | Support “application/json” |
| Accept       | String   | Support “application/json” |

\| Authorization Headers

| **Name** | **Type** | **Description**                           |
|----------|----------|-------------------------------------------|
| Token    | String   | Authentication token, get from login API. |

Response
--------

| **Name**                           | **Type** | **Description**                               |
|------------------------------------|----------|-----------------------------------------------|
| totalMaximumNodes                  | Integer  | Total license nodes                           |
| totalFreeNodes                     | Integer  | Total free license nodes                      |
| totalUsedNodes                     | Integer  | Total used license nodes                      |
| tenants                            | List     | A list of existing tenants                    |
| tenants.tenantId                   | String   | Tenant ID                                     |
| tenants.tenantName                 | String   | Tenant name                                   |
| tenants.description                | String   | Tenant description                            |
| tenants.tenantMaximumNodes         | Integer  | Tenant assigned nodes                         |
| tenants.tenantFreeNodes            | Integer  | Tenant free nodes                             |
| tenants.tenantUsedNodes            | Integer  | Tenant used nodes                             |
| tenants.domains                    | List     | A list of existing domains of a tenant        |
| tenants.domains.domainId           | String   | Domain ID                                     |
| tenants.domains.domainName         | String   | Domain name                                   |
| tenants.domains.description        | String   | Domain description                            |
| tenants.domains.domainMaximumNodes | Integer  | Domain assigned nodes                         |
| tenants.domains.domainFreeNodes    | Integer  | Domain free nodes                             |
| tenants.domains.domainUsedNodes    | Integer  | Domain used nodes                             |
| statusCode                         | Integer  | The returned status code of executing the API |
| statusDescription                  | String   | The explanation of the status code            |

\| *Example*

1.  {  

2.      "totalMaximumNodes":1000,  

3.      "totalFreeNodes":500,  

4.      "totalUsedNodes":500,  

5.      "tenants":[  

6.          {  

7.              "tenantId":"4e75247a-309c-4231-96a5-823b6cb1e78d",  

8.              "tenantName":"Tenant1",  

9.              "description":"tenant1",  

10.             "tenantMaximumNodes":300,  

11.             "tenantFreeNodes":100,  

12.             "tenantUsedNodes":200,  

13.             "domains":[  

14.                 {  

15.                     "domainId":"4e75247a-309c-4231-96a5-823b6cb1e95e",  

16.                     "domainName":"Domain11",  

17.                     "description":"domain11",  

18.                     "domainMaximumNodes":200,  

19.                     "domainFreeNodes":50,  

20.                     "domainUsedNodes":150  

21.                 },  

22.                 {  

23.                     "domainId":"4e75247a-309c-4231-96a5-823b6cb1e95d",  

24.                     "domainName":"Domain12",  

25.                     "description":"domain12",  

26.                     "domainMaximumNodes":100,  

27.                     "domainFreeNodes":30,  

28.                     "domainUsedNodes":70  

29.                 }  

30.             ]  

31.         },  

32.         {  

33.             "tenantId":"4e75247a-309c-4231-96a5-823b6cb1e78f",  

34.             "tenantName":"Tenant2",  

35.             "description":"tenant2",  

36.             "tenantMaximumNodes":200,  

37.             "tenantFreeNodes":100,  

38.             "tenantUsedNodes":100,  

39.             "domains":[  

40.                 {  

41.                     "domainId":"4e75247a-309c-4231-96a5-823b6cb1e96d",  

42.                     "domainName":"Domain21",  

43.                     "description":"domain21",  

44.                     "domainMaximumNodes":100,  

45.                     "domainFreeNodes":20,  

46.                     "domainUsedNodes":80  

47.                 }  

48.             ]  

49.         }  

50.     ],  

51.     "statusCode":790200,  

52.     "statusDescription":"Succeed."  

53. }  

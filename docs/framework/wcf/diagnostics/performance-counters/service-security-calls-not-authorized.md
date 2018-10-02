---
title: 服务：Security Calls Not Authorized（未授权的安全调用次数）
ms.date: 03/30/2017
ms.assetid: 3024b20a-5250-4bd1-a38c-c6d79f89610b
author: BrucePerlerMS
ms.openlocfilehash: f90ed5746c8b798e55b7e300ba7ff63bbafdcac4
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2018
ms.locfileid: "48035878"
---
# <a name="service-security-calls-not-authorized"></a>服务：Security Calls Not Authorized（未授权的安全调用次数）
计数器名称：Security Calls Not Authorized（未授权的安全调用次数）。  
  
## <a name="description"></a>描述  
 当 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> 方法返回 `false` 时，此计数器将递增。 它指示传入的消息来自有效的用户并得到了良好保护，但该用户没有获得执行特定任务的授权。

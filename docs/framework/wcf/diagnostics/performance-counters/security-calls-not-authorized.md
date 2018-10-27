---
title: Security Calls Not Authorized（未授权的安全调用次数）
ms.date: 03/30/2017
ms.assetid: cb6acdcd-7336-42e1-9ae8-ac891336cd58
ms.openlocfilehash: 492886a8e0083e8993b68ad710229113faf79e8d
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/25/2018
ms.locfileid: "50033319"
---
# <a name="security-calls-not-authorized"></a>Security Calls Not Authorized（未授权的安全调用次数）
计数器名称：Security Calls Not Authorized（未授权的安全调用次数）。  
  
## <a name="description"></a>描述  
 当 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> 方法返回 `false` 时，此计数器将递增。 它指示传入的消息来自有效的用户并得到了良好保护，但该用户没有获得执行特定任务的授权。

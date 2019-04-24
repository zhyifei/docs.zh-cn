---
title: Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure
ms.date: 03/30/2017
ms.assetid: 1b9f5139-e122-4716-9ef7-2f38e1813993
ms.openlocfilehash: 93c96d94aaeddeb7e7b04ea80645b8de95b0343e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59143320"
---
# <a name="microsofttransactionstransactionbridgeenlisttransactionfailure"></a>Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure
WS-AT 协议服务无法使用提供的协调上下文在事务上登记。  
  
## <a name="description"></a>描述  
 对于给定的 2pc 协议，当 MSDTC 无法在事务上登记时跟踪。  当事务不再存在、不再允许登记或者已存在过多的登记项时可能出现这种情况。  
  
## <a name="troubleshooting"></a>疑难解答  
 检查跟踪消息中的状态字符串以确定是否存在任何可操作的项。  
  
## <a name="see-also"></a>请参阅

- [跟踪](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [使用跟踪来排除应用程序故障](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [管理和诊断](../../../../../docs/framework/wcf/diagnostics/index.md)

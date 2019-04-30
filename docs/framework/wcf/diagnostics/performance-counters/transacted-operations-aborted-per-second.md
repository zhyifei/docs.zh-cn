---
title: Transacted Operations Aborted Per Second（每秒中止的事务处理操作次数）
ms.date: 03/30/2017
ms.assetid: 19fc993f-2b3d-4898-852e-3b98ec2153a5
ms.openlocfilehash: 6369fea6def5ebb6b62274caed31d5fb63b3b0e1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61998187"
---
# <a name="transacted-operations-aborted-per-second"></a>Transacted Operations Aborted Per Second（每秒中止的事务处理操作次数）
计数器名称：每秒中止的事务处理的操作。  
  
## <a name="description"></a>描述  
 在此服务中一秒内已中止的事务性操作的数量。  
  
 此计数器为性能计数器类型[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)

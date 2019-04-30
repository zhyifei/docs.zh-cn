---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: 936e870c1ec991e2e33acf8a08ccc93975989679
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61964289"
---
# <a name="activitytransfer"></a>ActivityTransfer
活动传输事件  
  
## <a name="syntax"></a>语法  
  
```csharp
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a>方法  
 ActivityTransfer 类不定义任何方法。  
  
## <a name="properties"></a>属性  
 ActivityTransfer 类具有以下属性：  
  
### <a name="activityid"></a>ActivityID  
  
- 数据类型：object  
    访问类型：只读  
  
- 活动 ID  
  
### <a name="relatedactivityid"></a>RelatedActivityID  
  
- 数据类型：object  
    访问类型：只读  
  
- 相关活动 ID  
  
## <a name="requirements"></a>要求  
  
|MOF|已在 Servicemodel.mof 中声明。|  
|---------|-----------------------------------|  
|命名空间|已在 root\ServiceModel 中定义。|

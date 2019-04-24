---
title: AspNetCompatibilityRequirementsAttribute
ms.date: 03/30/2017
ms.assetid: 00908a39-a21b-4029-bbb9-33e5a6ed25a7
ms.openlocfilehash: 8e4b2e0e32ccd3b671e81531833ccb3aa3788389
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59768275"
---
# <a name="aspnetcompatibilityrequirementsattribute"></a>AspNetCompatibilityRequirementsAttribute
AspNetCompatibilityRequirementsAttribute  
  
## <a name="syntax"></a>语法  
  
```csharp
class AspNetCompatibilityRequirementsAttribute : Behavior  
{  
  string RequirementsMode;  
};  
```  
  
## <a name="methods"></a>方法  
 AspNetCompatibilityRequirementsAttribute 类不定义任何方法。  
  
## <a name="properties"></a>属性  
 AspNetCompatibilityRequirementsAttribute 类具有以下属性。  
  
### <a name="requirementsmode"></a>RequirementsMode  
 数据类型：String  
  
 访问类型：只读  
  
 指示 Asp.Net 兼容模式是否处于活动状态。  
  
## <a name="requirements"></a>要求  
  
|MOF|已在 Servicemodel.mof 中声明。|  
|---------|-----------------------------------|  
|命名空间|已在 root\ServiceModel 中定义|  
  
## <a name="see-also"></a>请参阅

- <xref:System.ServiceModel.ServiceHostingEnvironment.AspNetCompatibilityEnabled%2A>

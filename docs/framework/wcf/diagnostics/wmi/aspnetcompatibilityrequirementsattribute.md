---
title: AspNetCompatibilityRequirementsAttribute
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 00908a39-a21b-4029-bbb9-33e5a6ed25a7
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 29ab9cf69ca7ccef82ed21f505d309d6a641ce8a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="aspnetcompatibilityrequirementsattribute"></a>AspNetCompatibilityRequirementsAttribute
AspNetCompatibilityRequirementsAttribute  
  
## <a name="syntax"></a>语法  
  
```  
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
  
## <a name="see-also"></a>另请参阅  
 <xref:System.ServiceModel.ServiceHostingEnvironment.AspNetCompatibilityEnabled%2A>

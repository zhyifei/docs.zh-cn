---
title: AsymmetricSecurityBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 82e5365a440d103727f354e682d0ebecb5f46a46
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="asymmetricsecuritybindingelement"></a><span data-ttu-id="8c7f9-102">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="8c7f9-102">AsymmetricSecurityBindingElement</span></span>
<span data-ttu-id="8c7f9-103">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="8c7f9-103">AsymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c7f9-104">语法</span><span class="sxs-lookup"><span data-stu-id="8c7f9-104">Syntax</span></span>  
  
```  
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="8c7f9-105">方法</span><span class="sxs-lookup"><span data-stu-id="8c7f9-105">Methods</span></span>  
 <span data-ttu-id="8c7f9-106">AsymmetricSecurityBindingElement 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="8c7f9-106">The AsymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="8c7f9-107">属性</span><span class="sxs-lookup"><span data-stu-id="8c7f9-107">Properties</span></span>  
 <span data-ttu-id="8c7f9-108">AsymmetricSecurityBindingElement 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="8c7f9-108">The AsymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="8c7f9-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="8c7f9-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="8c7f9-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="8c7f9-110">Data type: string</span></span>  
  
 <span data-ttu-id="8c7f9-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="8c7f9-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8c7f9-112">此绑定的消息加密和签名的顺序。</span><span class="sxs-lookup"><span data-stu-id="8c7f9-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="8c7f9-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="8c7f9-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="8c7f9-114">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="8c7f9-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="8c7f9-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="8c7f9-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8c7f9-116">此绑定是否需要签名确认。</span><span class="sxs-lookup"><span data-stu-id="8c7f9-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c7f9-117">惠?</span><span class="sxs-lookup"><span data-stu-id="8c7f9-117">Requirements</span></span>  
  
|<span data-ttu-id="8c7f9-118">MOF</span><span class="sxs-lookup"><span data-stu-id="8c7f9-118">MOF</span></span>|<span data-ttu-id="8c7f9-119">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="8c7f9-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="8c7f9-120">命名空间</span><span class="sxs-lookup"><span data-stu-id="8c7f9-120">Namespace</span></span>|<span data-ttu-id="8c7f9-121">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="8c7f9-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8c7f9-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="8c7f9-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>

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
ms.openlocfilehash: 104810fc24cfe7c4c6ddf7ee5ece9f16a345c80c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="asymmetricsecuritybindingelement"></a><span data-ttu-id="5ed25-102">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="5ed25-102">AsymmetricSecurityBindingElement</span></span>
<span data-ttu-id="5ed25-103">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="5ed25-103">AsymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ed25-104">语法</span><span class="sxs-lookup"><span data-stu-id="5ed25-104">Syntax</span></span>  
  
```  
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="5ed25-105">方法</span><span class="sxs-lookup"><span data-stu-id="5ed25-105">Methods</span></span>  
 <span data-ttu-id="5ed25-106">AsymmetricSecurityBindingElement 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="5ed25-106">The AsymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="5ed25-107">属性</span><span class="sxs-lookup"><span data-stu-id="5ed25-107">Properties</span></span>  
 <span data-ttu-id="5ed25-108">AsymmetricSecurityBindingElement 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="5ed25-108">The AsymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="5ed25-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="5ed25-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="5ed25-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="5ed25-110">Data type: string</span></span>  
  
 <span data-ttu-id="5ed25-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="5ed25-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5ed25-112">此绑定的消息加密和签名的顺序。</span><span class="sxs-lookup"><span data-stu-id="5ed25-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="5ed25-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="5ed25-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="5ed25-114">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="5ed25-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="5ed25-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="5ed25-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5ed25-116">此绑定是否需要签名确认。</span><span class="sxs-lookup"><span data-stu-id="5ed25-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ed25-117">要求</span><span class="sxs-lookup"><span data-stu-id="5ed25-117">Requirements</span></span>  
  
|<span data-ttu-id="5ed25-118">MOF</span><span class="sxs-lookup"><span data-stu-id="5ed25-118">MOF</span></span>|<span data-ttu-id="5ed25-119">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="5ed25-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="5ed25-120">命名空间</span><span class="sxs-lookup"><span data-stu-id="5ed25-120">Namespace</span></span>|<span data-ttu-id="5ed25-121">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="5ed25-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5ed25-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5ed25-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>

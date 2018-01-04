---
title: SymmetricSecurityBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b2e182b6-c041-4d80-a926-6058068d9f79
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 7960ae9972490f2363b0f6f9942e947677c7d299
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="symmetricsecuritybindingelement"></a><span data-ttu-id="69581-102">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="69581-102">SymmetricSecurityBindingElement</span></span>
<span data-ttu-id="69581-103">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="69581-103">SymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69581-104">语法</span><span class="sxs-lookup"><span data-stu-id="69581-104">Syntax</span></span>  
  
```  
class SymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="69581-105">方法</span><span class="sxs-lookup"><span data-stu-id="69581-105">Methods</span></span>  
 <span data-ttu-id="69581-106">SymmetricSecurityBindingElement 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="69581-106">The SymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="69581-107">属性</span><span class="sxs-lookup"><span data-stu-id="69581-107">Properties</span></span>  
 <span data-ttu-id="69581-108">SymmetricSecurityBindingElement 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="69581-108">The SymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="69581-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="69581-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="69581-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="69581-110">Data type: string</span></span>  
  
 <span data-ttu-id="69581-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="69581-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="69581-112">此绑定的消息加密和签名的顺序。</span><span class="sxs-lookup"><span data-stu-id="69581-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="69581-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="69581-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="69581-114">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="69581-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="69581-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="69581-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="69581-116">此绑定是否需要签名确认。</span><span class="sxs-lookup"><span data-stu-id="69581-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69581-117">惠?</span><span class="sxs-lookup"><span data-stu-id="69581-117">Requirements</span></span>  
  
|<span data-ttu-id="69581-118">MOF</span><span class="sxs-lookup"><span data-stu-id="69581-118">MOF</span></span>|<span data-ttu-id="69581-119">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="69581-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="69581-120">命名空间</span><span class="sxs-lookup"><span data-stu-id="69581-120">Namespace</span></span>|<span data-ttu-id="69581-121">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="69581-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="69581-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="69581-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>

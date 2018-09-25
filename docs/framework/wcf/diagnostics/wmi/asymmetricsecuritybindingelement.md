---
title: AsymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
author: BrucePerlerMS
ms.openlocfilehash: 63af1c9a607cb9f81e2c0abf795ee2b3432cbf9c
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47075045"
---
# <a name="asymmetricsecuritybindingelement"></a><span data-ttu-id="cbeba-102">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="cbeba-102">AsymmetricSecurityBindingElement</span></span>
<span data-ttu-id="cbeba-103">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="cbeba-103">AsymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbeba-104">语法</span><span class="sxs-lookup"><span data-stu-id="cbeba-104">Syntax</span></span>  
  
```  
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="cbeba-105">方法</span><span class="sxs-lookup"><span data-stu-id="cbeba-105">Methods</span></span>  
 <span data-ttu-id="cbeba-106">AsymmetricSecurityBindingElement 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="cbeba-106">The AsymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="cbeba-107">属性</span><span class="sxs-lookup"><span data-stu-id="cbeba-107">Properties</span></span>  
 <span data-ttu-id="cbeba-108">AsymmetricSecurityBindingElement 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="cbeba-108">The AsymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="cbeba-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="cbeba-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="cbeba-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="cbeba-110">Data type: string</span></span>  
  
 <span data-ttu-id="cbeba-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="cbeba-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cbeba-112">此绑定的消息加密和签名的顺序。</span><span class="sxs-lookup"><span data-stu-id="cbeba-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="cbeba-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="cbeba-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="cbeba-114">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="cbeba-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="cbeba-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="cbeba-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cbeba-116">此绑定是否需要签名确认。</span><span class="sxs-lookup"><span data-stu-id="cbeba-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbeba-117">要求</span><span class="sxs-lookup"><span data-stu-id="cbeba-117">Requirements</span></span>  
  
|<span data-ttu-id="cbeba-118">MOF</span><span class="sxs-lookup"><span data-stu-id="cbeba-118">MOF</span></span>|<span data-ttu-id="cbeba-119">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="cbeba-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="cbeba-120">命名空间</span><span class="sxs-lookup"><span data-stu-id="cbeba-120">Namespace</span></span>|<span data-ttu-id="cbeba-121">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="cbeba-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cbeba-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="cbeba-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>

---
title: AsymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
ms.openlocfilehash: e968f5f2d7ffdb193b30762d32a47be3778b98dc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54621352"
---
# <a name="asymmetricsecuritybindingelement"></a><span data-ttu-id="8a77a-102">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="8a77a-102">AsymmetricSecurityBindingElement</span></span>
<span data-ttu-id="8a77a-103">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="8a77a-103">AsymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a77a-104">语法</span><span class="sxs-lookup"><span data-stu-id="8a77a-104">Syntax</span></span>  
  
```csharp
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="8a77a-105">方法</span><span class="sxs-lookup"><span data-stu-id="8a77a-105">Methods</span></span>  
 <span data-ttu-id="8a77a-106">AsymmetricSecurityBindingElement 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="8a77a-106">The AsymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="8a77a-107">Properties</span><span class="sxs-lookup"><span data-stu-id="8a77a-107">Properties</span></span>  
 <span data-ttu-id="8a77a-108">AsymmetricSecurityBindingElement 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="8a77a-108">The AsymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="8a77a-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="8a77a-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="8a77a-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="8a77a-110">Data type: string</span></span>  
  
 <span data-ttu-id="8a77a-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="8a77a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8a77a-112">此绑定的消息加密和签名的顺序。</span><span class="sxs-lookup"><span data-stu-id="8a77a-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="8a77a-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="8a77a-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="8a77a-114">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="8a77a-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="8a77a-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="8a77a-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8a77a-116">此绑定是否需要签名确认。</span><span class="sxs-lookup"><span data-stu-id="8a77a-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a77a-117">要求</span><span class="sxs-lookup"><span data-stu-id="8a77a-117">Requirements</span></span>  
  
|<span data-ttu-id="8a77a-118">MOF</span><span class="sxs-lookup"><span data-stu-id="8a77a-118">MOF</span></span>|<span data-ttu-id="8a77a-119">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="8a77a-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="8a77a-120">命名空间</span><span class="sxs-lookup"><span data-stu-id="8a77a-120">Namespace</span></span>|<span data-ttu-id="8a77a-121">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="8a77a-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8a77a-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="8a77a-122">See also</span></span>
- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>

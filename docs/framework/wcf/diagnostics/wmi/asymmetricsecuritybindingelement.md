---
title: AsymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
ms.openlocfilehash: 0f86fc1b410753b5ec100f0a7d43de9badd1401b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59196042"
---
# <a name="asymmetricsecuritybindingelement"></a><span data-ttu-id="d960f-102">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="d960f-102">AsymmetricSecurityBindingElement</span></span>
<span data-ttu-id="d960f-103">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="d960f-103">AsymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d960f-104">语法</span><span class="sxs-lookup"><span data-stu-id="d960f-104">Syntax</span></span>  
  
```csharp
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d960f-105">方法</span><span class="sxs-lookup"><span data-stu-id="d960f-105">Methods</span></span>  
 <span data-ttu-id="d960f-106">AsymmetricSecurityBindingElement 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="d960f-106">The AsymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d960f-107">属性</span><span class="sxs-lookup"><span data-stu-id="d960f-107">Properties</span></span>  
 <span data-ttu-id="d960f-108">AsymmetricSecurityBindingElement 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="d960f-108">The AsymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="d960f-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="d960f-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="d960f-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="d960f-110">Data type: string</span></span>  
  
 <span data-ttu-id="d960f-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d960f-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d960f-112">此绑定的消息加密和签名的顺序。</span><span class="sxs-lookup"><span data-stu-id="d960f-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="d960f-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="d960f-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="d960f-114">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="d960f-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="d960f-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d960f-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d960f-116">此绑定是否需要签名确认。</span><span class="sxs-lookup"><span data-stu-id="d960f-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d960f-117">要求</span><span class="sxs-lookup"><span data-stu-id="d960f-117">Requirements</span></span>  
  
|<span data-ttu-id="d960f-118">MOF</span><span class="sxs-lookup"><span data-stu-id="d960f-118">MOF</span></span>|<span data-ttu-id="d960f-119">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="d960f-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d960f-120">命名空间</span><span class="sxs-lookup"><span data-stu-id="d960f-120">Namespace</span></span>|<span data-ttu-id="d960f-121">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="d960f-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d960f-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="d960f-122">See also</span></span>

- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>

---
title: AsymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 09bfaa3ab4f2aceb3e80644953a87686fca9830c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33484357"
---
# <a name="asymmetricsecuritybindingelement"></a><span data-ttu-id="4b04a-102">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="4b04a-102">AsymmetricSecurityBindingElement</span></span>
<span data-ttu-id="4b04a-103">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="4b04a-103">AsymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b04a-104">语法</span><span class="sxs-lookup"><span data-stu-id="4b04a-104">Syntax</span></span>  
  
```  
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4b04a-105">方法</span><span class="sxs-lookup"><span data-stu-id="4b04a-105">Methods</span></span>  
 <span data-ttu-id="4b04a-106">AsymmetricSecurityBindingElement 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="4b04a-106">The AsymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4b04a-107">属性</span><span class="sxs-lookup"><span data-stu-id="4b04a-107">Properties</span></span>  
 <span data-ttu-id="4b04a-108">AsymmetricSecurityBindingElement 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="4b04a-108">The AsymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="4b04a-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="4b04a-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="4b04a-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="4b04a-110">Data type: string</span></span>  
  
 <span data-ttu-id="4b04a-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="4b04a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b04a-112">此绑定的消息加密和签名的顺序。</span><span class="sxs-lookup"><span data-stu-id="4b04a-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="4b04a-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="4b04a-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="4b04a-114">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="4b04a-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="4b04a-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="4b04a-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b04a-116">此绑定是否需要签名确认。</span><span class="sxs-lookup"><span data-stu-id="4b04a-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b04a-117">要求</span><span class="sxs-lookup"><span data-stu-id="4b04a-117">Requirements</span></span>  
  
|<span data-ttu-id="4b04a-118">MOF</span><span class="sxs-lookup"><span data-stu-id="4b04a-118">MOF</span></span>|<span data-ttu-id="4b04a-119">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="4b04a-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4b04a-120">命名空间</span><span class="sxs-lookup"><span data-stu-id="4b04a-120">Namespace</span></span>|<span data-ttu-id="4b04a-121">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="4b04a-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4b04a-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="4b04a-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>

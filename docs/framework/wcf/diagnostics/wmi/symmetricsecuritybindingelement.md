---
title: SymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: b2e182b6-c041-4d80-a926-6058068d9f79
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 7fc720f4f0be25a0cec25d979942af8472efa4ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485051"
---
# <a name="symmetricsecuritybindingelement"></a><span data-ttu-id="ff058-102">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="ff058-102">SymmetricSecurityBindingElement</span></span>
<span data-ttu-id="ff058-103">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="ff058-103">SymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff058-104">语法</span><span class="sxs-lookup"><span data-stu-id="ff058-104">Syntax</span></span>  
  
```  
class SymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ff058-105">方法</span><span class="sxs-lookup"><span data-stu-id="ff058-105">Methods</span></span>  
 <span data-ttu-id="ff058-106">SymmetricSecurityBindingElement 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="ff058-106">The SymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ff058-107">属性</span><span class="sxs-lookup"><span data-stu-id="ff058-107">Properties</span></span>  
 <span data-ttu-id="ff058-108">SymmetricSecurityBindingElement 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="ff058-108">The SymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="ff058-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="ff058-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="ff058-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="ff058-110">Data type: string</span></span>  
  
 <span data-ttu-id="ff058-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ff058-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ff058-112">此绑定的消息加密和签名的顺序。</span><span class="sxs-lookup"><span data-stu-id="ff058-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="ff058-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="ff058-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="ff058-114">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="ff058-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="ff058-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ff058-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ff058-116">此绑定是否需要签名确认。</span><span class="sxs-lookup"><span data-stu-id="ff058-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff058-117">要求</span><span class="sxs-lookup"><span data-stu-id="ff058-117">Requirements</span></span>  
  
|<span data-ttu-id="ff058-118">MOF</span><span class="sxs-lookup"><span data-stu-id="ff058-118">MOF</span></span>|<span data-ttu-id="ff058-119">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="ff058-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ff058-120">命名空间</span><span class="sxs-lookup"><span data-stu-id="ff058-120">Namespace</span></span>|<span data-ttu-id="ff058-121">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="ff058-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ff058-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="ff058-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>

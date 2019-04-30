---
title: SymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: b2e182b6-c041-4d80-a926-6058068d9f79
ms.openlocfilehash: f6effd533a205d0e8fd1421119e325f06b340dd1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61956710"
---
# <a name="symmetricsecuritybindingelement"></a><span data-ttu-id="9ffdd-102">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="9ffdd-102">SymmetricSecurityBindingElement</span></span>
<span data-ttu-id="9ffdd-103">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="9ffdd-103">SymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ffdd-104">语法</span><span class="sxs-lookup"><span data-stu-id="9ffdd-104">Syntax</span></span>  
  
```csharp
class SymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="9ffdd-105">方法</span><span class="sxs-lookup"><span data-stu-id="9ffdd-105">Methods</span></span>  
 <span data-ttu-id="9ffdd-106">SymmetricSecurityBindingElement 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="9ffdd-106">The SymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9ffdd-107">属性</span><span class="sxs-lookup"><span data-stu-id="9ffdd-107">Properties</span></span>  
 <span data-ttu-id="9ffdd-108">SymmetricSecurityBindingElement 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="9ffdd-108">The SymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="9ffdd-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="9ffdd-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="9ffdd-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="9ffdd-110">Data type: string</span></span>  
  
 <span data-ttu-id="9ffdd-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="9ffdd-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9ffdd-112">此绑定的消息加密和签名的顺序。</span><span class="sxs-lookup"><span data-stu-id="9ffdd-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="9ffdd-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="9ffdd-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="9ffdd-114">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="9ffdd-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="9ffdd-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="9ffdd-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9ffdd-116">此绑定是否需要签名确认。</span><span class="sxs-lookup"><span data-stu-id="9ffdd-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ffdd-117">要求</span><span class="sxs-lookup"><span data-stu-id="9ffdd-117">Requirements</span></span>  
  
|<span data-ttu-id="9ffdd-118">MOF</span><span class="sxs-lookup"><span data-stu-id="9ffdd-118">MOF</span></span>|<span data-ttu-id="9ffdd-119">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="9ffdd-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9ffdd-120">命名空间</span><span class="sxs-lookup"><span data-stu-id="9ffdd-120">Namespace</span></span>|<span data-ttu-id="9ffdd-121">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="9ffdd-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9ffdd-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="9ffdd-122">See also</span></span>

- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>

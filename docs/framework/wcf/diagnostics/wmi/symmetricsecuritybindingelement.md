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
ms.openlocfilehash: ab341f55947bfcfbc776143e3bbc33e125da89c8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="symmetricsecuritybindingelement"></a><span data-ttu-id="39516-102">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="39516-102">SymmetricSecurityBindingElement</span></span>
<span data-ttu-id="39516-103">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="39516-103">SymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39516-104">语法</span><span class="sxs-lookup"><span data-stu-id="39516-104">Syntax</span></span>  
  
```  
class SymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="39516-105">方法</span><span class="sxs-lookup"><span data-stu-id="39516-105">Methods</span></span>  
 <span data-ttu-id="39516-106">SymmetricSecurityBindingElement 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="39516-106">The SymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="39516-107">属性</span><span class="sxs-lookup"><span data-stu-id="39516-107">Properties</span></span>  
 <span data-ttu-id="39516-108">SymmetricSecurityBindingElement 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="39516-108">The SymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="39516-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="39516-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="39516-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="39516-110">Data type: string</span></span>  
  
 <span data-ttu-id="39516-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="39516-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="39516-112">此绑定的消息加密和签名的顺序。</span><span class="sxs-lookup"><span data-stu-id="39516-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="39516-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="39516-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="39516-114">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="39516-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="39516-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="39516-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="39516-116">此绑定是否需要签名确认。</span><span class="sxs-lookup"><span data-stu-id="39516-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39516-117">要求</span><span class="sxs-lookup"><span data-stu-id="39516-117">Requirements</span></span>  
  
|<span data-ttu-id="39516-118">MOF</span><span class="sxs-lookup"><span data-stu-id="39516-118">MOF</span></span>|<span data-ttu-id="39516-119">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="39516-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="39516-120">命名空间</span><span class="sxs-lookup"><span data-stu-id="39516-120">Namespace</span></span>|<span data-ttu-id="39516-121">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="39516-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="39516-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39516-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>

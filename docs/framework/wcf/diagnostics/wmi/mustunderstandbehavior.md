---
title: MustUnderstandBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 40075acb2a098c98b4cd0ab35f213981c09f8486
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="mustunderstandbehavior"></a><span data-ttu-id="51c73-102">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="51c73-102">MustUnderstandBehavior</span></span>
<span data-ttu-id="51c73-103">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="51c73-103">MustUnderstandBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51c73-104">语法</span><span class="sxs-lookup"><span data-stu-id="51c73-104">Syntax</span></span>  
  
```  
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="51c73-105">方法</span><span class="sxs-lookup"><span data-stu-id="51c73-105">Methods</span></span>  
 <span data-ttu-id="51c73-106">MustUnderstandBehavior 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="51c73-106">The MustUnderstandBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="51c73-107">属性</span><span class="sxs-lookup"><span data-stu-id="51c73-107">Properties</span></span>  
 <span data-ttu-id="51c73-108">MustUnderstandBehavior 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="51c73-108">The MustUnderstandBehavior class has the following property:</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="51c73-109">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="51c73-109">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="51c73-110">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="51c73-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="51c73-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="51c73-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="51c73-112">如果为 `true`，则所有具有 `MustUnderstand` 属性的未处理 SOAP 标头将导致引发异常的行为。</span><span class="sxs-lookup"><span data-stu-id="51c73-112">When `true`, all SOAP headers with the `MustUnderstand` attribute that are not handled cause the behavior to throw an exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51c73-113">要求</span><span class="sxs-lookup"><span data-stu-id="51c73-113">Requirements</span></span>  
  
|<span data-ttu-id="51c73-114">MOF</span><span class="sxs-lookup"><span data-stu-id="51c73-114">MOF</span></span>|<span data-ttu-id="51c73-115">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="51c73-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="51c73-116">命名空间</span><span class="sxs-lookup"><span data-stu-id="51c73-116">Namespace</span></span>|<span data-ttu-id="51c73-117">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="51c73-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="51c73-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="51c73-118">See Also</span></span>  
 <xref:System.ServiceModel.Description.MustUnderstandBehavior>

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
ms.workload: dotnet
ms.openlocfilehash: 9b6838c6ce98e0d373a45c136b12bdedbd8c9eb6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="mustunderstandbehavior"></a><span data-ttu-id="49950-102">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="49950-102">MustUnderstandBehavior</span></span>
<span data-ttu-id="49950-103">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="49950-103">MustUnderstandBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49950-104">语法</span><span class="sxs-lookup"><span data-stu-id="49950-104">Syntax</span></span>  
  
```  
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="49950-105">方法</span><span class="sxs-lookup"><span data-stu-id="49950-105">Methods</span></span>  
 <span data-ttu-id="49950-106">MustUnderstandBehavior 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="49950-106">The MustUnderstandBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="49950-107">属性</span><span class="sxs-lookup"><span data-stu-id="49950-107">Properties</span></span>  
 <span data-ttu-id="49950-108">MustUnderstandBehavior 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="49950-108">The MustUnderstandBehavior class has the following property:</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="49950-109">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="49950-109">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="49950-110">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="49950-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="49950-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="49950-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="49950-112">如果为 `true`，则所有具有 `MustUnderstand` 属性的未处理 SOAP 标头将导致引发异常的行为。</span><span class="sxs-lookup"><span data-stu-id="49950-112">When `true`, all SOAP headers with the `MustUnderstand` attribute that are not handled cause the behavior to throw an exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49950-113">惠?</span><span class="sxs-lookup"><span data-stu-id="49950-113">Requirements</span></span>  
  
|<span data-ttu-id="49950-114">MOF</span><span class="sxs-lookup"><span data-stu-id="49950-114">MOF</span></span>|<span data-ttu-id="49950-115">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="49950-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="49950-116">命名空间</span><span class="sxs-lookup"><span data-stu-id="49950-116">Namespace</span></span>|<span data-ttu-id="49950-117">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="49950-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="49950-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="49950-118">See Also</span></span>  
 <xref:System.ServiceModel.Description.MustUnderstandBehavior>
